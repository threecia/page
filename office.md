# Office tips
---
## 小技巧
 - 在cmd中使用預設應用程式開啟檔案: `start "" <file>`, `start`後面的空字串是必須的 [參考來源](https://superuser.com/questions/144347/is-there-windows-equivalent-to-the-bashrc-file-in-linux)  
 - TBD

## install & run sshd on Windows 10
內網電腦需要彼此溝通; 但資安因素禁止安裝openssh  
 1. 對外只允許3389 (RDP), 對內不受限  
 2. 但由於禁止禁止範圍包括安裝openssh server, 連帶使內網電腦無法透過SSH連線溝通  
 3. 要透過offline installation的方式安裝並開啟內網的ssh service  

方法如下:
 1. 直接[下載](https://github.com/PowerShell/Win32-OpenSSH/releases)編好的openssh client/server package(或是透過設定->應用程式->新增功能->選用功能?)  
 2. 解壓縮到`C:\Program Files (x86)\OpenSSH`資料夾  
 3. 執行powershell script安裝  
    `powershell.exe -ExecutionPolicy Bypass -File install-sshd.ps1`
 4. 防火牆允許port 22 SSH連線  
    `netsh advfirewall firewall add rule name=sshd dir=in action=allow protocol=TCP localport=22`
 5. 啟動sshd  `net start sshd`

[reference](https://github.com/PowerShell/Win32-OpenSSH/wiki/Install-Win32-OpenSSH)

## codebase
 - 需求:  
  1. 能夠支援Home/Office工作需要, 速度要能接受  

 - 方法: 
  1. 寫個script跑daily patch (create on PC2-> apply on PC1)
  2. SVN folder 放在PC2上()