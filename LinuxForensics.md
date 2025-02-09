# Linux Forensics

## Linux鑑識分析最常見的情境
- 當資安單位捕獲到某駭客攻擊時所用的Linux(如最著名的Kali Linux)
- 當機關使用Linux建置各種伺服器時，遭受到攻擊，需要對受駭的Linux進行鑑識分析如：
  - 被植入各種rootkit的Linux
  - 各種Linux伺服器(SSH server、web server 、Database server)被入侵的情境
  - 各種攻擊Linux的技術可參閱MITRE ATT&CK® Linux Matrix https://attack.mitre.org/matrices/enterprise/linux/

## Linux鑑識分析常見的數位跡證(Artifacts)
- 系統相關數位跡證(Artifacts)
  - OS Information and System configuration
    - 系統資訊
    - 系統資訊可讓鑑識人員深入了解系統上發生的活動，並有助於識別任何潛在的罪魁禍首
    - 檢視作業系統版本：cat /etc/os-release
    - 檢視環境變數 ==> printenv
    - 檢視網路設定
      - cat /etc/network/interfaces
      - ip address show ==> ifconfig
    - 檢視主機名稱(Hostname)：cat /etc/hostname
    - 檢視主機的Timezone(時區)：cat /etc/timezone
    - 檢視DNS 設定：
      - cat /etc/hosts
      - cat /etc/resolv.conf
  - Network Interfaces
- 定期執行的工作(Scheduled Tasks)
  - Startup Items
  - cron
    - [Linux 設定 crontab 例行性工作排程教學與範例](https://blog.gtwang.org/linux/linux-crontab-cron-job-tutorial-and-examples/) 
  - WINDOWS : at (要淘汰)  ==>   schtasks [中文版說明](https://learn.microsoft.com/zh-tw/windows-server/administration/windows-commands/schtasks)  [英文版說明](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/schtasks)
    - [Schtasks命令詳解](https://www.twblogs.net/a/5b8907ab2b71775d1cdf5c77)
      - `schtasks /create /sc minute /mo 20 /tn "Security Script" /tr \\central\data\scripts\sec.vbs` 
- 檔案與檔案系統相關數位跡證(Artifacts)
  - 檔案系統 ==> ext/ext2/ext3/ext4/......
  - [Linux 的檔案權限](https://linux.vbird.org/linux_basic/centos7/0210filepermission.php)
  - [Linux chmod命令](https://www.runoob.com/linux/linux-comm-chmod.html)
    - chmod +x xxx.sh
    - chmod 754 XXX.sh
- 使用者相關數位跡證(Artifacts) | User Accounts and User activities
  - 使用者帳戶Home目錄底下的數位跡證 資料來源：[Linux Forensics Artifacts in a Users home Directory](https://library.mosse-institute.com/articles/2022/07/linux-forensics-artifacts-in-a-users-home-directory/linux-forensics-artifacts-in-a-users-home-directory.html#linux-forensics-artifacts-in-a-users-home-directory)
    - 建立使用者帳戶時，也會為該使用者建立一個home/目錄
    - 在home/中有兩個隱藏目錄 .local/與.cache/。這兩個目錄中有許多子資料夾與有用資訊
    - 最近使用的文件(recently used files)
    - 已刪除的檔案/資料夾(deleted files/folders)
    - 縮圖(thumbnails)
  - GUI 應用程式的使用：使用頻率、上次使用時間戳(last used timestamp)
    - 檔案/資料夾資訊：絕對路徑(absolute path)、上次使用的時間戳
- 登入活動的紀錄[PAM身分驗證]：包含從GUI桌面登入、console登入、網路登入
  - PAM 身分驗證 == >  Pluggable Authentication Modules 可插入身份驗證模組(PAM)
  - Linux PAM是一套庫，允許 Linux 系統管理員配置對使用者進行身份驗證的方法。
  - 它提供了一種靈活且集中的方法，通過使用配置檔而不是更改應用程式代碼來切換受保護應用程式的身份驗證方法
  - Linux PAM 庫允許使用本地密碼、LDAP 或指紋讀取器等方法進行身份驗證。
  - Linux PAM 是從 Unix 可插拔身份驗證模組架構演變而來的。
  - Linux-PAM將認證任務分為四個獨立的管理組：
    - `帳戶模組`檢查指定的帳戶是否是當前條件下的有效身份驗證目標。這可能包括帳戶到期、一天中的時間以及使用者有權訪問所請求的服務等條件。
    - `身份驗證模組`驗證使用者的身份，例如通過請求和檢查密碼或其他機密。它們還可能將身份驗證資訊傳遞到其他系統，例如密鑰環。
    - `密碼模組`負責更新密碼，通常與身份驗證步驟中使用的模組耦合。它們還可用於強制執行強密碼。
    - `會話模組`定義在會話開始和結束時執行的操作。使用者成功通過身份驗證后，會話將啟動。
  - 比較 WINDOWS: Active Directory (AD) authentication
    - WINDOWS WORKGROUPS(工作權組) ==> SAM(Security Account Manager)
    - WINDOWS AD(中央控管) ==> NTDS.DIT
      - [Understanding NTDS.DIT: The Core of Active Directory](https://medium.com/@harikrishnanp006/understanding-ntds-dit-the-core-of-active-directory-faac54cc628a) 
      - LAN Manager (LM)
      - NT LAN Manager (NTLM)
      - Kerberos protocol
- bash/zsh History | 執行過的指令
- 最近開啟的檔案(Recent Files) | Trash(資源回收桶)
- 日誌相關數位跡證(Artifacts)(System Logs and Logfile analysis)
- Linux稽核子系統與稽核日誌

# Linux鑑識分析工具：
- 擷取與成像(Imaging)工具
  - 一般擷取與成像(Imaging)工具：dd |DC3DD| Guymager
  - 記憶體擷取與成像(Imaging)工具:
    - AVML(Acquire Volatile Memory Linux)
      - https://github.com/microsoft/avml
    - LiME(Linux Memory Extractor)
      - https://github.com/504ensicsLabs/LiME
    - Linpmem -- a physical memory acquisition tool for Linux
      - https://github.com/Velocidex/Linpmem
- 分析工具：有許多(底下介紹以鑑識用途的Linux為主)
  - SANS SIFT Workstation
  - CAINE Linux
  - Tsurugi Linux
  - Kali linux (有部分工具,詳見2023 年版本 11-Forensics 工具)

# Labs
- 鑑識情境：某機關制定資安政策來規範員工，本案例是針對可疑的使用者活動違背機關資安政策的鑑識情境
- 測試樣本：Hocrux.E01
- 資料來源：Def Con 2019(Linux Forensics)
- 鑑識工具：FTK Imager
- 參考解答 https://www.jaiminton.com/Defcon/DFIR-2019/#category-linux-forensics

# 參考書籍
- 更多Linux鑑識分析常見的數位跡證(artifacts)與分析技術請參閱
- 實戰 Linux 系統數位鑑識 (Practical Linux Forensics: A Guide for Digital Investigators)
- Bruce Nikkel 著 江湖海 譯碁峰資訊

## 補充說明
- Linux Authentication: PAM(Pluggable Authentication Modules) 
```
PAM(Pluggable Authentication Modules)身分驗證學習資源
PAM 是一套程式庫，允許 Linux系統管理員設定對使用者進行身份驗證的方法
PAM提供了一種靈活且集中的方式，透過使用設定檔而不是更改應用程式程式碼來切換安全應用程式的身份驗證方法
https://en.wikipedia.org/wiki/Linux_PAM
```
- 檔案系統(File System Analysis)分析
- 檔案系統可以提供有關特定檔案位置的資訊，這有助於確定事件發生的順序
- 此外，還可以幫助鑑識人員確定哪些文件最近被存取或修改，以及哪些使用者有權存取這些文件
- 最後，檔案系統還可以包含可用於識別檔案中包含的數據類型的元數據(metadata)，這有助於確定其與鑑識的相關性
- 常用工具：The Sleuth Kit (TSK)  、Debugfs
- 檔案分析(File Analysis)
- 包含許多檔案類型確認：file指令，各種類型檔案的metadata分析，執行檔分析：readelf、objdump、ldd等等
- 有關linux執行檔分析可參閱：No Starch Press出版的Practical Binary Analysis(Dennis Andriesse著)

