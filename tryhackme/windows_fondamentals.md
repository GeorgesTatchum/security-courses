## The file system

The file system used in modern versions of Windows is the New Technology File System or simply |[NTFS](https://docs.microsoft.com/en-us/windows-server/storage/file-server/ntfs-overview) .

Before NTFS, there was FAT16/FAT32 (File Allocation Table) and HPFS (High Performance File System).

You still see FAT partitions in use today. For example, you typically see FAT partitions in USB devices, MicroSD cards, etc. but traditionally not on personal Windows computers/laptops or Windows servers.

NTFS is known as a journaling file system. In case of a failure, the file system can automatically repair the folders/files on disk using information stored in a log file. This function is not possible with FAT.

NTFS addresses many of the limitations of the previous file systems; such as:

    - Supports files larger than 4GB
    - Set specific permissions on folders and files
    - Folder and file compression
    - Encryption ( Encryption File System or EFS )

If you're running Windows, what is the file system your Windows installation is using? You can check the Properties (right-click) of the drive your operating system is installed on, typically the C drive (C:\).

You can read Microsoft's official documentation on FAT, HPFS, and NTFS [here](https://docs.microsoft.com/en-us/troubleshoot/windows-client/backup-and-storage/fat-hpfs-and-ntfs-file-systems) .

Let's speak briefly on some features that are specific to NTFS.

On NTFS volumes, you can set permissions that grant or deny access to files and folders.

The permissions are:

    - Full control
    - Modify
    - Read & Execute
    - List folder contents
    - Read
    - Write

How can you view the permissions for a file or folder?

    - Right-click the file or folder you want to check for permissions.
    - From the context menu, select `Properties` .
    - Within Properties, click on the `Security` tab.
    - In the ``Group or user names`` list, select the user, computer, or group whose permissions you want to view.

Refer to the Microsoft documentation to get a better understanding of the NTFS permissions for Special Permissions .

Another feature of NTFS is **Alternate Data Streams** ( **ADS** ).

Alternate Data Streams (ADS) is a file attribute specific to Windows NTFS (New Technology File System).

Every file has at least one data stream ( `$DATA` ), and ADS allows files to contain more than one stream of data. Natively [Window Explorer](https://support.microsoft.com/en-us/windows/what-s-changed-in-file-explorer-ef370130-1cca-9dc5-e0df-2f7416fe1cb1) doesn't display ADS to the user. There are 3rd party executables that can be used to view this data, [PowerShell](https://docs.microsoft.com/en-us/powershell/scripting/overview?view=powershell-7.1) also gives you the ability to view ADS for files. We will cover how you can use PowerShell to view any ADS for any files in the [Windows PowerShell](https://tryhackme.com/room/windowspowershell) room.

From a security perspective, malware writers have used ADS to hide data.

Not all its uses are malicious. For example, when you download a file from the Internet, there are identifiers written to ADS to identify that the file was downloaded from the Internet.

To learn more about ADS, refer to the following link from MalwareBytes [here](https://tryhackme.com/room/windowspowershell) .
