# The VT-May-2020-WinEXE-Malware-Image dataset

* To enable malware researchers to compare different classification approaches, we disclose how to create our dataset.

* This dataset contains 1,556 malware images from 18 different malware families. The original malware of the dataset are included in the VirusTotal malwere sample folder. 

* When your papers or articles use the dataset, please cite the following paper.

* COMPSAC

### 1. Apply for the VirusTotal premium service as academic user

* Apply at the VirusTotal site. If you are approved for an academic account, there is no charge.
* https://www.virustotal.com/gui/home/upload
* Contact Us -> I have a commercial inquiry -> I am interested in premium services

### 2. Access to VirusTotal malware sample folder 

* Move to 2020-05-06 folder.
* Download Win32_EXE.7z.

### 3. Unzip malware files
* See the "README - VirusTotal Academic Malware Samples.docx."
* Note that these are real malware.

### 4. Make malware images
* The following steps are confirmed in Ubuntu 20.04 LTS.
* Put unzipped malware files to "virustotal" directory.
```
sudo apt-get install pnmtopng
```
```
./00_binary_copy.sh
```
```
./01_malwareimage.sh
```
```
./02_image_copy.sh
```


### 5. Check the malware image samples
* dataset/001/0aa73b88b3f3272b04599d7d834b27ae42ff1dafa2403b5dccecc6ad817da863.png
![](./sample01.png)
* dataset/017/0fdb1ba9b20b248e25e65c34a6c7bc587c71a71b82c87758380533454dc4c59b.png
![](./sample02.png)