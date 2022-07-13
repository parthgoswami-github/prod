# Managing Windows Server from Red Hat Server using Ansible on AWS EC2


Recently, while working on an internal project I was required to ping a Windows server from a RHEL server. Sounds easy, right? It would have been indeed, however, the task was to ping the Windows server from RHEL via ansible, and that's where the scenario got tricky. I went through a few articles and videos on and thought of documenting my learnings in this blog. 

Let's start by getting to know the host requirements. 

# Host requirements:

For Ansible to communicate to a Windows host and use Windows modules, the Windows host must meet these requirements:
- Ansible can generally manage Windows versions under current and extended support from Microsoft. 
- Ansible can manage desktop OSs including Windows 7, 8.1, and 10, and server OSs including Windows Server 2008, 2008 R2, 2012, 2012 R2, 2016, and 2019.
- Ansible requires PowerShell 3.0 or newer and at least .NET 4.0 to be installed on the Windows host.
- A WinRM listener should be created and activated. 


# Use below steps to configure:

## 1. Configure Windows server 2016: 
<br/> a. **Open Windows PowerShell and check the version:**

<br/>

`PS C:\Users\Adminstrator> Get-Host | Select-Object version`

![version](/images/ansible_sd/1a.png "powershell version")

<br/>The powershell version should at least be 3.0 or more. If not then upgrade it using this document. 
     Since we have version 5.1 no need to upgrade the version.


<br/>
<br/>

 b. **Once PowerShell has been upgraded, the final step is for the WinRM service to be configured so that Ansible can connect to it:**
```
PS C:\Users\Administrator> [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12
PS C:\Users\Administrator> $url = "https://raw.githubusercontent.com/ansible/ansible/devel/examples/scripts/ConfigureRemotingForAnsible.ps1"$file = "$env:temp\ConfigureRemotingForAnsible.ps1"
PS C:\Users\Administrator> (New-Object -TypeName System.Net.WebClient).DownloadFile($url, $file)
PS C:\Users\Administrator> powershell.exe -ExecutionPolicy ByPass -File $file
```

<br/>

 c. **Run this below script on Windows PowerShell ISE and check the version after successful script completion:**
    

```
Param([string]$computerName)

Function enableWinRM {
	$result = winrm id -r:$global:compName 2>$null

	Write-Host	
	if ($LastExitCode -eq 0) {
		Write-Host "WinRM already enabled on" $global:compName "..." -ForegroundColor green
	} else {
		Write-Host "Enabling WinRM on" $global:compName "..." -ForegroundColor red
		.\pstools\psexec.exe \\$global:compName -s C:\Windows\system32\winrm.cmd qc -quiet
		if ($LastExitCode -eq 0) {
			.\pstools\psservice.exe \\$global:compName restart WinRM
			$result = winrm id -r:$global:compName 2>$null
			
			if ($LastExitCode -eq 0) {Write-Host 'WinRM successfully enabled!' -ForegroundColor green}
			else {exit 1}
		} 
		else {exit 1}
	}
}

$global:compName = $computerName
enableWinRM
exit 0
```    
![Version after script completion](/images/ansible_sd/1c.png "version after script completion")

<br/>

 d. **Check if ports are listening:**
<br/>
 `PS C:\Users\Administrator> winrm enumerate winrm/config/Listener`
![istener](/images/ansible_sd/1d.png "port listener")

<br/>


## 2. Configure Red Hat 8 Server:
<br/> a. **If you have subscription manager account then subscribe your system using subscription-manager command:**

`[root@ip-172-31-23-177 ~]# subscription-manager register`

<br/>

 b. **Install ansible if package is not available:**
<br/>
`[root@ip-172-31-23-177 ~]# yum install ansible`

<br/>

 c. **Install python-pip package:**
<br/>
```
[root@ip-172-31-23-177 ~]# pip2 --version
[root@ip-172-31-23-177 ~]# pip3 --version
[root@ip-172-31-23-177 ~]# dnf install python2-pip
[root@ip-172-31-23-177 ~]# dnf install python3-pip
[root@ip-172-31-23-177 ~]# pip2 --version
pip 9.0.3 from /usr/lib/python2.7/site-packages (python 2.7)
[root@ip-172-31-23-177 ~]# pip3 --version
pip 9.0.3 from /usr/lib/python3.6/site-packages (python 3.6)
[root@ip-172-31-23-177 ~]# pip3 install "pywinrm>=0.2.2"
```
<br/>

 d. **Now write a ansible playbook to ping windows server:**
<br/>
```
[root@ip-172-31-23-177 ~]# tail /etc/ansible/hosts 
## db-[99:101]-node.example.com

[windows]
107.20.75.188

[windows:vars]
ansible_user="windows_username"				//for example: ansible_user="Administrator"
ansible_password="windows_user_password"
ansible_connection=winrm
ansible_winrm_server_cert_validation=ignore
```
<br/>

 e. **Use the below command to ping windows server:**
<br/>
`[root@ip-172-31-23-177 ansible]# ansible all -i hosts -m win_ping`
![ping](/images/ansible_sd/2e.png "pinging windows server")
## Resources:

1. [Setting up a Windows Host](https://docs.ansible.com/ansible/latest/user_guide/windows_setup.html)
2. [WinRM Setup](https://docs.ansible.com/ansible/latest/user_guide/windows_setup.html#winrm-setup) 
3. [WinRM setup script](https://community.spiceworks.com/scripts/show/2703-remotely-enable-winrm-powershell)
4. [Linux and Windows host setup](https://www.ansible.com/blog/connecting-to-a-windows-host)
5. [How to install pip in RHEL 8 / CentOS 8 step by step instructions](https://linuxconfig.org/how-to-install-pip-in-redhat-8#:~:text=The%20pip%20command%20may%20be,pip2%20and%20pip3%20commands%20respectively)
6. [Windows PowerShell Upgrade](https://docs.ansible.com/ansible/latest/user_guide/windows_setup.html)
7. [Ansible-windows-lab-setup (where ansible server is in linux and target node is in windows)
](https://www.youtube.com/watch?v=LaTFB2-y8uU)

> Tip: <br/>
> RDP Port No: 3389

-------
<br/>


*Shreya Dhange is a Technical Training Developer at [Red Hat](https://www.redhat.com/en), who likes to explore and learn new technologies and share her knowledge by writing articles. She has completed her Masters in Computer Science and has gained award for her exemplary academic performance. She has been engaged in creating and delivering content in the cloud and linux space. She can be reached out [LinkedIn](https://www.linkedin.com/in/shreyadhange/) or via [email](https://mail.google.com/mail/u/0/?fs=1&tf=cm&source=mailto&to=shreyadhange@gmail.com)*.

