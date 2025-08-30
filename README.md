# 🔍 DIGITAL FORENSICS LAB RECORD  

This repository contains practical experiments performed using popular Digital Forensics tools.  
The experiments include:  
1. FTK Imager  
2. TestDisk  
3. Wireshark  
4. Mail Header Analysis  
5. Autopsy  

---

## 📘 Experiment 1 – FTK Imager  

### 🎯 Aim  
To acquire RAM data and create a forensic disk image using **FTK Imager**.  

### ⚙️ Installation  
- Download: [FTK Imager Download](https://accessdata.com/product-download/ftk-imager-version-4-2-1)  
- Install by running `FTK Imager.exe`.  
- Launch as Administrator.  

### 📝 Procedure  
**Capturing RAM**  
1. Open **FTK Imager**.  
2. Go to **File → Capture Memory**.  
3. Select a **destination folder** and provide a **filename**.  
4. (Optional) Check **Include Pagefile** to capture paging file data.  
5. Click **Capture Memory** and wait until the process completes.  

**Creating Disk Image**  
1. Open **FTK Imager**.  
2. Go to **File → Create Disk Image**.  
3. Choose the source:  
   - **Physical Drive** → captures entire hard disk.  
   - **Logical Drive** → captures selected partitions.  
4. Select Image Type:  
   - **Raw (dd)** → uncompressed format.  
   - **E01 (Expert Witness Format)** → compressed with metadata.  
   - **SMART/Split Raw** → other supported formats.  
5. Enter **Case Information** (Case number, Evidence number, Examiner).  
6. Provide **destination path** and filename.  
7. Review summary and click **Finish**.  
8. Verify the hash values (MD5/SHA1) generated.  

### ✅ Result  
Successfully captured RAM and created a forensic disk image.  

🔗 [View Full Experiment](Experiment-1-FTK-imager.pdf)  

---

## 📘 Experiment 2 – TestDisk  

### 🎯 Aim  
To recover lost partitions and deleted files using **TestDisk**.  

### ⚙️ Installation  
- Download: [TestDisk Download](https://www.cgsecurity.org/wiki/TestDisk_Download)  
- Extract and run `testdisk_win.exe` (Windows) or `testdisk` (Linux).  

### 📝 Procedure  
1. Launch **TestDisk**.  
2. Choose `Create` to generate a new log file.  
3. Select the **disk** to analyze from the list.  
4. Choose **partition table type** (TestDisk usually detects it automatically).  
5. Select **Analyse** → TestDisk scans for partitions.  
6. Use **Quick Search** to find recently deleted partitions.  
7. If needed, use **Deeper Search** for a full scan.  
8. To view files, highlight the partition and press **P**.  
9. Navigate through files, select required ones, and press **C** to copy.  
10. Save recovered files to another safe directory.  

### ✅ Result  
Recovered lost partitions and deleted files using **TestDisk**.  

🔗 [View Full Experiment](Experiment-2-TestDisk.pdf)  

---

## 📘 Experiment 3 – Wireshark  

### 🎯 Aim  
To capture and analyze live network packets using **Wireshark**.  

### ⚙️ Installation  
- Download: [Wireshark Download](https://www.wireshark.org/download.html)  
- Install via setup wizard.  
- Launch Wireshark and choose active network interface.  

### 📝 Procedure  
1. Open **Wireshark**.  
2. Select a **network interface** (e.g., Wi-Fi, Ethernet).  
3. Click the **Start Capturing Packets** (blue fin icon).  
4. Perform internet activities (e.g., browse websites).  
5. Stop capture by clicking the **red square button**.  
6. Use filters for analysis:  
   - `http` → shows HTTP packets.  
   - `tcp.port == 80` → TCP packets on port 80.  
   - `ip.addr == 192.168.x.x` → packets from/to a specific IP.  
7. Right-click a packet → **Follow → TCP Stream** to reconstruct communication.  
8. Save captured data as `.pcap` for later use.  

### ✅ Result  
Successfully captured and analyzed packets using **Wireshark**.  

🔗 [View Full Experiment](Experiment-3-Wireshark.pdf)  

---

## 📘 Experiment 4 – Mail Header Analysis  

### 🎯 Aim  
To analyze an email header and detect spoofing/phishing attempts.  

### ⚙️ Access  
- Gmail: `More (⋮) → Show Original`  
- Outlook: `File → Properties → Internet Headers`  
- Online Tool: [Mail Header Analyzer](https://mha.azurewebsites.net/)  

### 📝 Procedure  
1. Open the target email.  
2. Copy the **full email header**.  
   - Gmail → `More (⋮) → Show Original → Copy to Clipboard`.  
   - Outlook → `File → Properties → Internet Headers`.  
3. Open [Mail Header Analyzer](https://mha.azurewebsites.net/).  
4. Paste the header into the text box.  
5. Click **Analyze Header**.  
6. Check:  
   - **Received From chain** → routing path of the email.  
   - **SPF/DKIM/DMARC** → authentication checks.  
   - **Originating IP Address** → real sender’s location.  
7. Compare sender domain with originating IP to identify spoofing.  

### ✅ Result  
Analyzed email headers and detected spoofing indicators.  

🔗 [View Full Experiment](Experiment-4-Mail-Header-Analyzer.pdf)  

---

## 📘 Experiment 5 – Autopsy  

### 🎯 Aim  
To analyze disk images and recover forensic artifacts using **Autopsy**.  

### ⚙️ Installation  
- Download: [Autopsy Download](https://www.autopsy.com/download/)  
- Install via setup wizard.  
- Launch Autopsy.  

### 📝 Procedure  
1. Open **Autopsy**.  
2. Create a **New Case** → provide case name, examiner name, and case directory.  
3. Add **data source** (e.g., `.E01`, `.dd`, `.raw`).  
4. Select **ingest modules** (file analysis, hash lookup, web history, keyword search, etc.).  
5. Start the analysis process.  
6. Browse results under different categories:  
   - Deleted files.  
   - Web browser activity.  
   - User documents.  
   - Registry data.  
7. Generate **Timeline View** to see activity patterns.  
8. Export case results as **HTML, PDF, or Excel report**.  

### ✅ Result  
Analyzed disk image and generated forensic report with **Autopsy**.  

🔗 [View Full Experiment](Experiment-5-Autopsy.pdf)  

---


