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
  - Network Interfaces
- 定期執行的工作(Scheduled Tasks)
  - Startup Items
- 檔案與檔案系統相關數位跡證(Artifacts)
- 使用者相關數位跡證(Artifacts) | User Accounts and User activities
- 登入活動的紀錄[PAM身分驗證]：包含從GUI桌面登入、console登入、網路登入
- bash/zsh History | 執行過的指令
- 最近開啟的檔案(Recent Files) | Trash(資源回收桶)
- 日誌相關數位跡證(Artifacts)(System Logs and Logfile analysis)

# 參考書籍
- 更多Linux鑑識分析常見的數位跡證(artifacts)與分析技術請參閱
- 實戰 Linux 系統數位鑑識 (Practical Linux Forensics: A Guide for Digital Investigators)
- Bruce Nikkel 著 江湖海 譯碁峰資訊
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

