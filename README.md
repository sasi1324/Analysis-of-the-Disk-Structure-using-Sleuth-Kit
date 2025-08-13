# Analysis-of-the-Disk-Structure-using-Sleuth-Kit
## AIM:
To analyze the disk structure of a given disk image using Sleuth Kit tools in Kali Linux.

## DESIGN STEPS:
### Step 1:
Obtain or create a disk image file (e.g., disk.dd) to analyze. Open the terminal in Kali Linux.

### Step 2:
Use Sleuth Kit tools like mmls, fsstat, and fls to examine the partition layout, file system details, and file listing.

### Step 3:
Interpret the output of the tools to understand the disk structure, including partitions, sectors, and files.

## PROGRAM:
Sleuth Kit Disk Analysis Commands

✅ Option 1: Create a Sample Disk Image (for Testing)

Let’s create a 10MB blank disk image and simulate file system activity:


Go to  directory cd ~/Downloads

# Step 1: Create an empty disk image
```
dd if=/dev/zero of=disk.dd bs=1M count=10
```
# Step 2: Format it with a file system (like FAT32)
```
mkfs.vfat disk.dd
```

## OUTPUT:

![image](https://github.com/user-attachments/assets/6bfafae7-e804-4f4a-a2fa-fbcc6432943c)

### Create Disk
![image](https://github.com/user-attachments/assets/d2832ea2-b793-4cde-b51c-7c63d84f15fb)

### mmls 
```bash
mmls disk.dd
```
### fls
```bash
fls -f fat -o 0 disk.dd
```
![image](https://github.com/user-attachments/assets/4afa1fc3-52c3-4c25-bb69-5788b0e8bdf1)
```
sudo mkdir -p /dmt/mount
sudo mount -o loop disk.dd /dmt/mount

```
![image](https://github.com/user-attachments/assets/a80da0b5-a83e-44fd-bc54-146df3eb0257)

```
sudo cp /home/kali/Desktop/kali.png /dmt/mount
sudo touch /dmt/mount/hello.txt
sudo mkdir /dmt/mount/test_folder
```

![image](https://github.com/user-attachments/assets/91520c9e-8c99-4347-82d2-2fa42f09d486)
```
fls -f ext4 -o 2048 disk.dd
```
![image](https://github.com/user-attachments/assets/1972eea0-f2aa-471e-8cc7-83e1279f38eb)
```
fls -f fat -o 0 disk.dd
```

![image](https://github.com/user-attachments/assets/29319725-7fe4-4803-a949-ba7aae598fd1)

## RESULT:
The analysis was performed successfully using Sleuth Kit, and the disk structure was understood in detail.


