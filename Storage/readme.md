# disks and storage
as a sys admin dealing with storage is so much stressing because you need backups you need to manage users on vast scales,storage is critical.


<ul>
<li>Disk scan in windows</li>
<li>Undetected Hard Drives While booting</li>
<li>How to organize Files in a Directory</li>
<li>Getting information aboyt disks in CMD </li>
<li>SSD health check</li>
</ul>

## Disk scan in windows
<ul>
<li>The chkdsk command scans the file system on the disk and checks the integrity of the files and metadata:

    chkdsk

</li>
</ul>


## Undetected Hard Drives While booting
i am trying to install windows 10 or 11 but my hard drives aren't detected in list disk and also i can't see in my disks what should i do?
<p>just disable secure boot and VDM in bios setting! and then try to boot on usb that contain windows .iso</p>

## How to organize Files in a Directory
open a notepad  and then copy this code in it and save it .bat format 

    @echo off
    for %%a in (".\*") do (
    if "%%~xa" NEQ "" if "%%~dpxa" NEQ "%~dpx0" (
    if not exist "%%~xa" mkdir "%%~xa"
    move "%%a" "%%~dpa%%~xa\"
    ))

just open it in anywhere you like,usb flash drive or external hard drives ...


## Getting information about disks in CMD
to get information of how many disk you have on this pc

    fsutil fsinfo drives

also in powershell

    Get-PSDrive


## SSD health check

### WIndows Environments
in windows environments just type in cmd in order to check health of your ssd.

    winsat disk -ran -write -drive [drive_letter]  

### Linux
To run a write test, type this command: 

    dd if=/dev/zero of=/tmp/tempfile bs=1M count=1024 conv=fdatasync

To test your disk's read speed next. The temporary file we created in the previous command is cached, giving you a bad result. So, you need to clear the cache beforehand by entering this:

    sudo /sbin/sysctl -w vm.drop_caches=3

Now you're ready to test your disk's read speed with this command: 

    dd if=tempfile of=/dev/null bs=1M count=1024