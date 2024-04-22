# Network Forensics
- Network Artifacts
  - pcap
  - log
  - flow
    - Netflow
    - sflow  
- Network Forensics主題
- Network Forensics:工具
  - wireshark
  - tshark
  - NetworkMiner
  - Online Tools
- Topics:
## Windows作業系統上常用網路鑑識工具
- Wireshark/Tshark
- NetworkMiner
- WinDump(Windows版Tcpdump，已不在支援開發)
- Npcap (https://npcap.com/)
- 線上PCAP分析工具
  - packettotal.com
  - apackets.com
- 更多工具請參閱 https://github.com/caesar0301/awesome-pcaptools


# Topics
- Deep Packet Inspection (DPI)
- 統計流量分析(Statistical Flow Analysis)
  - Yet Another Flowmeter (YAF)
  - SiLK - the System for Internet-Level Knowledge
- 惡意流量分析：特別是擷取流量中的惡意程式
  - 根據檔案特徵(file signature: header與footer)從網路流量擷取檔案的工具，例如tcpxtract工具
- 加密流量分析
  - 包含辨識駭客使用的各種tunneling的封包及VPN、HTTPs 、SSH等
- 無線網路流量分析(請參閱底下推薦書籍) ==> 

# 推薦書籍
- Hands-On Network Forensics,Nipun Jaswal, packt publishing
  - https://www.packtpub.com/product/hands-on-network-forensics/9781789344523
- 加密流量分析學習資源
  - https://paireds.com/dns-tunneling-the-risks-and-real-examples/
  - https://arxiv.org/pdf/2103.17028.pdf

# LABS:
- Lab_1:使用tshark命令列指令擷取流量中的資料
- 範例檔案下載 https://github.com/nipunjaswal/networkforensics/tree/master/Ch3/ICMP%20Camp
- Lab_2:Network Miner
  - 下載底下測試PCAP並解壓縮 https://wiki.wireshark.org/uploads/__moin_import__/attachments/SampleCaptures/http_with_jpegs.cap.gz
- Lab_3:Dridex 惡意流量分析
  - 測試樣本https://blueteamlabs.online/home/challenge/network-analysis-malware-compromise-e882f32908
  - 實作內容A：使用Wireshark分析
  - 實作內容B：使用NetworkMiner分析
  - 實作內容C：使用線上Pcap 分析平台分析
- Lab_4:Lokibot惡意流量分析
  - https://www.ithome.com.tw/news/157357
  - 名稱：loki-bot_network_traffic.pcap
  - 來源：https://github.com/R3MRUM/loki-parse
  - 參考文獻: [Loki-Bot: Information Stealer, Keylogger,and More](https://sansorg.egnyte.com/dl/WlXtH2QXTm)
  - 可參考Hands-On Network Forensics, Nipun Jaswal, packt.第六章分析
- Lab_5:金融木馬IcedID惡意流量分析
  - PCAP檔案：[Cold as Ice: Unit 42 Wireshark Quiz for IcedID](https://unit42.paloaltonetworks.com/wireshark-quiz-icedid/)
  - 參考解答
    - https://unit42.paloaltonetworks.com/wireshark-quiz-icedid-answers/
  - MITRE ATT&CK: https://attack.mitre.org/software/S0483/

# SANS訓練課程
- GIAC Network Forensic Analyst (GNFA)
- [FOR572: Advanced Network Forensics: Threat Hunting, Analysis, and Incident Response](https://www.sans.org/cyber-security-courses/advanced-network-forensics-threat-hunting-incident-response/)

# 參考資料
- [Network Forensics: A Comprehensive Review of Tools and Techniques](https://www.researchgate.net/publication/351998718_Network_Forensics_A_Comprehensive_Review_of_Tools_and_Techniques)
