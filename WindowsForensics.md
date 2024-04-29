# Windows Forensics
- 鑑識物件(Forensics objects)是具有鑑識價值的物體，它包含已發生事件的資料或證據的任何對象，例如日誌(log)、登錄表(registry)及設定單元等
- 龐大的Windows作業系統有許多資料可當作數位鑑識的分析物件，這些通稱為Windows Artifacts
- 針對Windows Artifacts進行數位鑑識的分析就是Windows數位鑑識的任務
- Windows數位鑑識已發展多年，有許多工具是數位鑑識資安人員須熟悉的知識與技能

## 參考書籍
- Practical Windows Forensics, Ayman Shaaban , Konstantin Sapronov (PacktPub)
- Windows Forensic Analysis Toolkit: Advanced Analysis Techniques for Windows 7
- 13Cubed在YOUTUE有22部Introduction to Windows Forensics系列教學影片可提供學員進階學習
- https://www.youtube.com/@13Cubed

# 常用的Windows 數位跡證(Artifacts)
- NTFS檔案系統的數位跡證(Artifacts)
  - NTFS Forensics
    - [Windows OS Forensics](https://www.coursera.org/learn/windows-os-forensics?action=enroll) 
- 記憶體的數位跡證(Artifacts)
- 👍登錄檔(Registry) ==> Windows registry Forensics
- Windows ShellBag
- 資源回收桶(Recycle Bin)
- 👍事件日誌(Event Log)
- 捷徑(LNK Files)
- Jump Lists
- Prefetch Files
- Windows 錯誤回報 (WER, Windows Error Reporting)
- 遠端桌面協定快取(Remote Desktop Protocol (RDP) Cache)
- ShimCache / AppCompatCache
- Amcache
- UserAssist
- Shellbag
- 更多Windows artifacts 請參閱 [Windows forensic artifacts guide](https://github.com/Psmths/windows-forensic-artifacts)


# Windows Artifacts and tools
- OpenText/Guidance Software EnCase(商業版軟體)
- AccessData FTK(商業版軟體)
- Magnet Forensics AXIOM(商業版軟體)
- OSForensics(商業版軟體)
- Autopsy/Sleuth Kit(免費軟體)

# [SANS Windows Forensic Analysis](https://www.sans.org/posters/windows-forensic-analysis/)

# FOR_LABS:
- LABS_1:Imanging: FTK imager
  - Hard Disc
  - USB Disc
  - Memory
- LABS_2:被駭系統的數位鑑識
  - CFReDS: Hacking Case
  - 資料下載點與問題說明請參閱底下網址
  - https://cfreds-archive.nist.gov/Hacking_Case.html
