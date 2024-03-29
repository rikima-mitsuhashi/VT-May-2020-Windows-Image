# The VT-May-2020-Windows-Image dataset

* To enable malware researchers to compare different classification approaches, we disclose how to create our dataset.

* This dataset contains 1,556 malware images from 18 different malware families. The original malware binary programs are included in the VirusTotal malwere sample folder.

* If your papers use the dataset or the script-tools for the dataset, please cite the following paper.

* Rikima Mitsuhashi and Takahiro Shinagawa, <br>
"Exploring Optimal Deep Learning Models for Image-based Malware Variant Classification,"<br>
*2022 IEEE 46th Annual Computers, Software, and Applications Conference (COMPSAC), 2022.*<br>
https://doi.org/10.1109/COMPSAC54236.2022.00128

# How to create the dataset
### 1. Apply for access to the VirusTotal Malware Sample Folder

* https://www.virustotal.com/gui/home/upload
* Contact Us -> I have a commercial inquiry -> I am interested in premium services
* There is no charge for an academic account.

### 2. Access to the VirusTotal Malware Sample Folder 

* Download Win32_EXE.7z from 2020-05-06 folder.

### 3. Unzip the downloaded file
* A password is written in the README of the VirusTotal Malware Sample folder.
* Note that the unzipped files are real malware.

### 4. Make directory and copy malware files
* The following steps are confirmed in Ubuntu 20.04 LTS.
```
./00_make_directory.sh
```
* Copy your unzipped malware files to "virustotal" directory.
* "/media/user/usb/Win32_EXE" should be changed to suit your environment.
```
find /media/user/usb/Win32_EXE -type f | xargs -i cp {} ./virustotal
```
* Check the file type. 
```
file ./virustotal/0e4d9bc8ddea1aa097399cc55a19f16760c12122080192933ee5d2541dd02862
```
-> PE32 executable (GUI) Intel 80386, for MS Windows, UPX compressed

### 5. Create the dataset
```
sudo apt-get install pnmtopng
```
```
./01_binary_copy.sh
```
```
./02_malwareimage.sh
```
```
./03_image_copy.sh
```


### 6. Check the results
```
zip -r -X VirusTotal-May-2020-Windows-Image.zip ./dataset
```
```
sha256sum ./VirusTotal-May-2020-Windows-Image.zip
```
-> 4d1cdc4397d9ab75a4409b118138d49babbd6065d9cd6dfe0997d60519b9caa3
```
eog ./dataset/01/0aa73b88b3f3272b04599d7d834b27ae42ff1dafa2403b5dccecc6ad817da863.png &
```
<img src="./sample01.jpg" width=10%>

```
eog ./dataset/02/1d6bddc4d5568ff753cfc4b9157222dbb0f2ded7378d3422c15f492810baa446.png &
```
<img src="./sample02.jpg" width=10%>

# References
* The VT-May-2020-Android-Image dataset
* https://github.com/rikima-mitsuhashi/VT-May-2020-Android-Image
* The DR-20-DEX-Image datase
* https://github.com/rikima-mitsuhashi/DR-20-DEX-Image
