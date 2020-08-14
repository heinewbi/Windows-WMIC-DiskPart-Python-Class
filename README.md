# Windows-WMIC-DiskPart-Python-Class

This is a simple single-module (MGsysutils.py) Python wrapper class.
It creates detailed Windows Storage information in python dict() via instances of Windows WMIC and DiskPart.

A Python Class to allow simple calls to retrieve Windows system storage details- Disks, Volumes, Partitions, Boot Drive. 

Additional utility methods for 
  - Diskpart disk Format operation 
  - Diskpart disk Get/Set UniqueID value
  
And a standalone function for Windows temp file operations
  - Create/Write an application\temp  file (generic function, but created for creating scripts for utility processes)
  
There is a __main__ program for standalone script testing & learning the details of the Dicts() that are built by the methods.

The most recent testing 2020-08 base on Windows10 release -2004

----- test program output ----
** MGSysUtils.py TEST PROGRAM **
Temp file with some data at:  C:\Users\PGDEV~1\AppData\Local\Temp\tmpu5f43dbd
Temp file with some data at:  C:\Users\PGDEV~1\AppData\Local\Temp\tmpk00wo5kx


DiskPart information dump...

----- Disk ----->   {'Disk ###': '0', 'Status': 'Online', 'Size': '476 GB', 'Free': '10 MB', 'Dyn': '', 'Gpt': '*'}
------Disk Details {'Disk ###': 0, 'On computer': 'NUC-001', 'Disk ID': '{AE83AAA8-F2AE-446E-91CD-58887432F4B0}', 'Type   ': 'SATA', 'Status ': 'Online', 'Path   ': '0', 'Target ': '0', 'LUN ID ': '0', 'Location Path ': 'PCIROOT(0)#PCI(1700)#ATA(C00T00L00)', 'Current Read-only State ': 'No', 'Read-only  ': 'No', 'Boot Disk  ': 'No', 'Pagefile Disk  ': 'No', 'Hibernation File Disk  ': 'No', 'Crashdump Disk  ': 'No', 'Clustered Disk  ': 'No'}
-----Volumes {'Disk ###': 0, 'Volume ###': '0', 'Ltr': 'D', 'Label': 'MGWork-Adat', 'Fs': 'NTFS', 'Type': 'Partition', 'Size': '249 GB', 'Status': 'Healthy', 'Info': ''}
-----Volumes {'Disk ###': 0, 'Volume ###': '1', 'Ltr': 'F', 'Label': 'MGWork-ADat', 'Fs': 'NTFS', 'Type': 'Partition', 'Size': '214 GB', 'Status': 'Healthy', 'Info': ''}
-----Volumes {'Disk ###': 0, 'Volume ###': '2', 'Ltr': 'G', 'Label': 'MGwork-ADat', 'Fs': 'NTFS', 'Type': 'Partition', 'Size': '13 GB', 'Status': 'Healthy', 'Info': ''}
-----Partitions {'Disk ###': 0, '###': '1  ', 'Type': 'Reserved   ', 'Size': '15 MB', 'Offset': '17 KB'}
-----Partitions {'Disk ###': 0, '###': '2  ', 'Type': 'Primary    ', 'Size': '249 GB', 'Offset': '16 MB'}
-----Partitions {'Disk ###': 0, '###': '3  ', 'Type': 'Primary    ', 'Size': '214 GB', 'Offset': '249 GB'}
-----Partitions {'Disk ###': 0, '###': '4  ', 'Type': 'Primary    ', 'Size': '13 GB', 'Offset': '463 GB'}
-----Disk GUID AE83AAA8-F2AE-446E-91CD-58887432F4B0
----- Disk ----->   {'Disk ###': '1', 'Status': 'Online', 'Size': '238 GB', 'Free': '2048 KB', 'Dyn': '', 'Gpt': '*'}
------Disk Details {'Disk ###': 1, 'On computer': 'NUC-001', 'Disk ID': '{12F1EA0E-2CB7-4A7E-862C-BB1E7770212E}', 'Type   ': 'NVMe', 'Status ': 'Online', 'Path   ': '0', 'Target ': '0', 'LUN ID ': '0', 'Location Path ': 'PCIROOT(0)#PCI(1D00)#PCI(0000)#NVME(P00T00L00)', 'Current Read-only State ': 'No', 'Read-only  ': 'No', 'Boot Disk  ': 'Yes', 'Pagefile Disk  ': 'Yes', 'Hibernation File Disk  ': 'No', 'Crashdump Disk  ': 'Yes', 'Clustered Disk  ': 'No'}
-----Volumes {'Disk ###': 1, 'Volume ###': '3', 'Ltr': 'C', 'Label': 'Windows', 'Fs': 'NTFS', 'Type': 'Partition', 'Size': '193 GB', 'Status': 'Healthy', 'Info': 'Boot'}
-----Volumes {'Disk ###': 1, 'Volume ###': '4', 'Ltr': 'E', 'Label': 'NUC-E', 'Fs': 'NTFS', 'Type': 'Partition', 'Size': '41 GB', 'Status': 'Healthy', 'Info': ''}
-----Volumes {'Disk ###': 1, 'Volume ###': '5', 'Ltr': 'Q', 'Label': 'NUC-Q', 'Fs': 'FAT32', 'Type': 'Partition', 'Size': '3000 MB', 'Status': 'Healthy', 'Info': ''}
-----Volumes {'Disk ###': 1, 'Volume ###': '6', 'Ltr': '', 'Label': 'SYSTEM', 'Fs': 'FAT32', 'Type': 'Partition', 'Size': '100 MB', 'Status': 'Healthy', 'Info': 'System'}
-----Partitions {'Disk ###': 1, '###': '1  ', 'Type': 'System     ', 'Size': '100 MB', 'Offset': '1024 KB'}
-----Partitions {'Disk ###': 1, '###': '2  ', 'Type': 'Reserved   ', 'Size': '16 MB', 'Offset': '101 MB'}
-----Partitions {'Disk ###': 1, '###': '3  ', 'Type': 'Primary    ', 'Size': '193 GB', 'Offset': '117 MB'}
-----Partitions {'Disk ###': 1, '###': '4  ', 'Type': 'Recovery   ', 'Size': '625 MB', 'Offset': '193 GB'}
-----Partitions {'Disk ###': 1, '###': '5  ', 'Type': 'Primary    ', 'Size': '41 GB', 'Offset': '194 GB'}
-----Partitions {'Disk ###': 1, '###': '6  ', 'Type': 'Primary    ', 'Size': '3000 MB', 'Offset': '235 GB'}
-----Partitions {'Disk ###': 1, '###': '7  ', 'Type': 'Recovery   ', 'Size': '450 MB', 'Offset': '238 GB'}
-----Disk GUID 12F1EA0E-2CB7-4A7E-862C-BB1E7770212E
--Format output--  []


WMIC information dump...

Boot {'BootDrive': 'C', 'BootFolder': '\\WINDOWS', 'Boot Disk ###': 1, 'Boot Partition ###': 1, 'Config name': 'BootConfiguration'}
disk {'Caption': 'ADATA SU800', 'DeviceID': 0, 'Partitions': 3, 'Size': 512105932800}
disk {'Caption': 'WDC WDS256G1X0C-00ENX0', 'DeviceID': 1, 'Partitions': 6, 'Size': 256052966400}
volume {'Capacity': 267386875904, 'DriveType': 3, 'FileSystem': 'NTFS', 'FreeSpace': 267230162944, 'Label': 'MGWork-Adata0', 'Name': 'D:\\'}
volume {'Capacity': 230686715904, 'DriveType': 3, 'FileSystem': 'NTFS', 'FreeSpace': 230581649408, 'Label': 'MGWork-AData1', 'Name': 'F:\\'}
volume {'Capacity': 14008971264, 'DriveType': 3, 'FileSystem': 'NTFS', 'FreeSpace': 13966581760, 'Label': 'MGwork-AData2-Scratch', 'Name': 'G:\\'}
volume {'Capacity': 207622328320, 'DriveType': 3, 'FileSystem': 'NTFS', 'FreeSpace': 27087663104, 'Label': 'Windows', 'Name': 'C:\\'}
volume {'Capacity': 655355904, 'DriveType': 3, 'FileSystem': 'NTFS', 'FreeSpace': 88449024, 'Label': '', 'Name': '\\\\?\\Volume{2d5bbb08-1e3b-4c15-b4a2-b7b88d950ed8}\\'}
volume {'Capacity': 44039077888, 'DriveType': 3, 'FileSystem': 'NTFS', 'FreeSpace': 4337303552, 'Label': 'NUC-E', 'Name': 'E:\\'}
volume {'Capacity': 3141533696, 'DriveType': 3, 'FileSystem': 'FAT32', 'FreeSpace': 2829582336, 'Label': 'NUC-Q', 'Name': 'Q:\\'}
volume {'Capacity': 471855104, 'DriveType': 3, 'FileSystem': 'NTFS', 'FreeSpace': 457293824, 'Label': 'Windows RE tools', 'Name': '\\\\?\\Volume{0e104f2e-abb5-4a53-b1d5-4b41263430b8}\\'}
volume {'Capacity': 100663296, 'DriveType': 3, 'FileSystem': 'FAT32', 'FreeSpace': 73121792, 'Label': 'SYSTEM', 'Name': '\\\\?\\Volume{e0eef54c-6b27-4d70-b551-08a9987aba0a}\\'}
partition {'BootPartition': 'FALSE', 'Index': 0, 'Disk ###': 0, 'Partition ###': 0, 'NumberOfBlocks': 522240000, 'PrimaryPartition': 'TRUE', 'Size': 267386880000}
partition {'BootPartition': 'FALSE', 'Index': 1, 'Disk ###': 0, 'Partition ###': 1, 'NumberOfBlocks': 450560000, 'PrimaryPartition': 'TRUE', 'Size': 230686720000}
partition {'BootPartition': 'FALSE', 'Index': 2, 'Disk ###': 0, 'Partition ###': 2, 'NumberOfBlocks': 27361280, 'PrimaryPartition': 'TRUE', 'Size': 14008975360}
partition {'BootPartition': 'TRUE', 'Index': 0, 'Disk ###': 1, 'Partition ###': 0, 'NumberOfBlocks': 204800, 'PrimaryPartition': 'TRUE', 'Size': 104857600}
partition {'BootPartition': 'FALSE', 'Index': 1, 'Disk ###': 1, 'Partition ###': 1, 'NumberOfBlocks': 405512367, 'PrimaryPartition': 'TRUE', 'Size': 207622331904}
partition {'BootPartition': 'FALSE', 'Index': 2, 'Disk ###': 1, 'Partition ###': 2, 'NumberOfBlocks': 1280000, 'PrimaryPartition': 'FALSE', 'Size': 655360000}
partition {'BootPartition': 'FALSE', 'Index': 3, 'Disk ###': 1, 'Partition ###': 3, 'NumberOfBlocks': 86013952, 'PrimaryPartition': 'TRUE', 'Size': 44039143424}
partition {'BootPartition': 'FALSE', 'Index': 4, 'Disk ###': 1, 'Partition ###': 4, 'NumberOfBlocks': 6144000, 'PrimaryPartition': 'TRUE', 'Size': 3145728000}
partition {'BootPartition': 'FALSE', 'Index': 5, 'Disk ###': 1, 'Partition ###': 5, 'NumberOfBlocks': 921600, 'PrimaryPartition': 'FALSE', 'Size': 471859200}
PRODUCT INFORMATION [{'Node': 'NUC-001', 'Description': 'Computer System Product', 'Identifier': 'G6BN73200PFG', 'Product Name': 'NUC7i5BNH', 'Vendor': 'Intel Corporation', 'Version': 'J31169-306'}]
** MGSysUtils.py TEST PROGRAM COMPLETE**
