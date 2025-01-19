# Hardware
in this section i collected some one-liners and scripts to monitor hardware both in linux and windows environments.

## Hardware checks
if you want check,control your hardware in linux  with bash scripts.just check here:

<ul>

<li>1.if you want check weather your usb ports can support usb3.0 or more just check:

    lsub -t 

</li>
<p>if xhci is written in output it mean an enhanced version of hci (usb3.0) can be supported.</p>

<li>2. ...</li>

</ul>

## Bios

to get information about bios just run this command in powershell:

    Get-ItemProperty -Path HKLM:\HARDWARE\DESCRIPTION\System\BIOS


To view the full list of BIOS parameters that are available in the Win32_BIOS WMI class, use the command:

    Get-WmiObject -Class Win32_BIOS | Format-List *

## Hard disk health check
for more information you can visit <a href="/Storage/SSD_Heal_Check.bat">Here</a>.