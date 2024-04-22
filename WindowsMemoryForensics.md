# Windows Memory Forensics
- Memory Forensics
- 休眠檔案(hibernation files)
  - hiberfil.sys 是電腦休眠時，為了能回到休眠前的工作狀態，所存在的一種記憶體暫存檔，所以停用休眠，正常情況下這個檔案就不會存在
  - 休眠檔案分析可以使用volatility來分析.raw檔案
  - 如同一般記憶體分析模式
- pagefiles 與 swapfiles
  - pagefile.sys是系統的分頁檔，作為虛擬記憶體使用，當開啟的程式超過實體記憶體的負荷，便將多的資料暫存在硬碟中，維持正常運作的狀態
- 行程傾印與系統崩潰
  - 產生行程傾印(process dump)的方法:
    - 使用Windows內建的工作管理員(Task Manager)
    - 使用Procdump
      - https://kb.acronis.com/content/27931?ckattempt=1
      - https://support.sitecore.com/kb?id=kb_article_view&sysparm_article=KB0253710
  - 產生系統崩潰(system crash)的方法: NotMyFault

# Labs
- Lab1
- 使用FTK Imager擷取休眠檔案
- 使用FTK Imager擷取pagefiles 
- Lab 2:MemLabs
  - MemLabs 是P. Abhiram Kumar開發以教育性與介紹性的 CTF 風格題目，來鼓勵學生、安全研究人員及 CTF 玩家進入記憶體鑑識領域
  - 共有七大題詳見表
  - 下載網址https://github.com/stuxnet999/MemLabs
  - 學員可以參考網路的參考解答完成練習
    - https://n1ght-w0lf.github.io/categories/#ctf-writeups
    - https://ellisstannard.medium.com/memlabs-ctf-using-volatility-labs-1-3-25f7b46faf88
    - https://www.youtube.com/@TheCyberExpert/videos

