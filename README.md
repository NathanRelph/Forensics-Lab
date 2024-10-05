# Forensics-Lab
<img src="https://github.com/NathanRelph/Forensics-Lab/blob/main/images/0.jpeg" width="420" height="300" />

- This is the USB stick I will be using throughout this project.
- The tools I will be using are listed below.

<h2><ins>Tools:</ins></h2>

- [FTK Imager](https://github.com/NathanRelph/Forensics-Lab/tree/main?tab=readme-ov-file#ftk-imager)
- [Autopsy](https://github.com/NathanRelph/Forensics-Lab/blob/main/README.md#autopsy)
- [Diskpart Link](https://github.com/NathanRelph/Forensics-Lab/blob/main/README.md#diskpart)
- [DBAN Link](https://github.com/NathanRelph/Forensics-Lab/blob/main/README.md#dban)


<h2><ins>Goal:</ins></h2>

- Recover deleted files using FTK Imager and Autopsy.
- Showcase Fdisk & DBAN secure wipe.

## FTK Imager
<img src="https://github.com/NathanRelph/Forensics-Lab/blob/main/images/1.png" width="550" height="300" /> <img src="https://github.com/NathanRelph/Forensics-Lab/blob/main/images/2_Crop.png" width="220" height="300" />
- In this lab I will be trying to recover deleted files from this USB stick, so the first step is to delete all the files.
- Open FTK Imager, and add an Evidence Item.

<img src="https://github.com/NathanRelph/Forensics-Lab/blob/main/images/3_Crop.png" width="350" height="300" /><img src="https://github.com/NathanRelph/Forensics-Lab/blob/main/images/4_Crop.png" width="350" height="300" />
- Picking a physical drive here would be better than the logical drive in this scenario because it creates a bit-by-bit copy inlcuding deleted or hidden date.
- Logical acquisition is faster, but using the file system table can miss these deleted files.
- Then I'm going to select my USB stick here.

<img src="https://github.com/NathanRelph/Forensics-Lab/blob/main/images/5_Crop.png" width="250" height="300" />

- The select export disk image to start the data aquisition process.
  
<img src="https://github.com/NathanRelph/Forensics-Lab/blob/main/images/6_Crop.png" width="700" height="300" />

- Select raw(dd) or SMART. In this scenario I'm going to choose raw(dd) for the bit-by-bit copy.

  
<img src="https://github.com/NathanRelph/Forensics-Lab/blob/main/images/7.png" width="350" height="250" /><img src="https://github.com/NathanRelph/Forensics-Lab/blob/main/images/8.png" width="350" height="250" />

- Adding image information is done here for documentation purposes, and then a destination for the image is chosen.

<img src="https://github.com/NathanRelph/Forensics-Lab/blob/main/images/9.png" width="350" height="300" /><img src="https://github.com/NathanRelph/Forensics-Lab/blob/main/images/10_Crop.png" width="350" height="250" />

- After that, the creation of the image can begin, and a hash is created for verification purposes.

<img src="https://github.com/NathanRelph/Forensics-Lab/blob/main/images/11.png" width="350" height="250" />

- Once done, FTK Imager can be closed, and the next step of analyzing the image in Autopsy can begin.

## Autopsy

<img src="https://github.com/NathanRelph/Forensics-Lab/blob/main/images/12.png" width="350" height="250" />

- On start up, click new case.
  
<img src="https://github.com/NathanRelph/Forensics-Lab/blob/main/images/13.png" width="550" height="350" />

- Enter a case name, and directory to store files.

<img src="https://github.com/NathanRelph/Forensics-Lab/blob/main/images/14.png" width="550" height="350" />

- The information for the case can also be input here for documentation purposes.
  
<img src="https://github.com/NathanRelph/Forensics-Lab/blob/main/images/15.png" width="550" height="350" />

- After that, create a new host.
  
<img src="https://github.com/NathanRelph/Forensics-Lab/blob/main/images/16.png" width="550" height="350" />

- Select the disk image since that's what we created with FTK Imager. It is also possible to pick local disk and skip the FTK Imager process if the USB device or storage device is directly connected.

<img src="https://github.com/NathanRelph/Forensics-Lab/blob/main/images/17.png" width="550" height="350" />

- Select a path for saving the output files of the Autopsy case.
  
<img src="https://github.com/NathanRelph/Forensics-Lab/blob/main/images/18.png" width="550" height="350" />

- Select the modules for the desired information you wish to search for in the image.
  
<img src="https://github.com/NathanRelph/Forensics-Lab/blob/main/images/19.png" width="600" height="150" />

- And hit start to add the data source and begin analyzing the image.
  
<img src="https://github.com/NathanRelph/Forensics-Lab/blob/main/images/20.png" width="1250" height="300" />

- On my usb image, these were the images that had previosly been deleted, but were recoverable. Although data is deleted and put into the recycle bin, it still exists.

## Diskpart
<img src="https://github.com/NathanRelph/Forensics-Lab/blob/main/images/21.png" width="350" height="250" />

<img src="https://github.com/NathanRelph/Forensics-Lab/blob/main/images/22.png" width="600" height="100" />

- Diskpart is a tool used to manage storage devices on a Windows computer. In this example, Disk 3 is chosen since it matches the size of the USB's storage. This can be cross-referenced with Window's File Explorer under "This PC".
  
  
<img src="https://github.com/NathanRelph/Forensics-Lab/blob/main/images/23.png" width="350" height="75" />

- Diskpart clean all is the command show here. It basically rewrites every sector on the USB with zeroes so the data is harder to recover.
  
<img src="https://github.com/NathanRelph/Forensics-Lab/blob/main/images/24.png" width="600" height="400" />

- bullet
  
<img src="https://github.com/NathanRelph/Forensics-Lab/blob/main/images/25.png" width="350" height="150" />

- bullet
  
<img src="https://github.com/NathanRelph/Forensics-Lab/blob/main/images/26.png" width="350" height="100" />

- bullet
  
<img src="https://github.com/NathanRelph/Forensics-Lab/blob/main/images/27.png" width="200" height="250" />

- bullet

## DBAN
<img src="https://github.com/NathanRelph/Forensics-Lab/blob/main/images/28.png" width="650" height="250" />

- bullet
  
<img src="https://github.com/NathanRelph/Forensics-Lab/blob/main/images/29.png" width="650" height="250" />

- bullet


