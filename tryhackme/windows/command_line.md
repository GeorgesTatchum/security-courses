# Basics command line

| **Command**     | **Description**                                          |
| --------------- | -------------------------------------------------------- |
| `ipconfig`      | show our IP address, subnet mask, and default gateway.   |
| `ipconfig /all` | show more information about your network configuration   |
| `tracert`       | traces the network route traversed to reach the target   |
| `nslookup`      | look up a host or domain and returns its IP address      |
| `netstat`       | displays current network connections and listening ports |
| `dir`           | show child directories                                   |
| `tree`          | to visually represent the child directories              |
| `type`          | view text files content                                  |
| `copy`          | copy files from one location to another                  |
| `del/erase`     | delete a file                                            |
| tasklist        | to list the running processes                            |

# PowerShell

**PowerShell** is a powerful tool from Microsoft designed for task automation and configuration management. It combines a command-line interface and a scripting language built on the .NET framework. Unlike older text-based command-line tools, PowerShell is _object-oriented_, which means it can handle complex data types and interact with system components more effectively.

PowerShell syntax: `Cmdlet -Property "pattern*"`

**Piping** is a technique used in command-line environments that allows the output of one command to be used as the input for another. This creates a sequence of operations where the data flows from one command to the next. Represented by the `|` symbol, piping is widely used in the Windows CLI, as introduced earlier in this module, as well as in Unix-based shells.

```
Get-ChildItem | Sort-Object Length
```

Here, `Get-ChildItem` retrieves the files (as objects), and the pipe (`|`) sends those file objects to `Sort-Object`, which then sorts them by their `Length` (size) property. This object-based approach allows for more detailed and flexible command sequences.

In the example above, we have leveraged the `Sort-Object` cmdlet to sort objects based on specified properties. Beyond sorting, PowerShell provides a set of cmdlets that, when combined with piping, allow for advanced data manipulation and analysis.

```
Get-ChildItem | Where-Object -Property "Extension" -eq ".txt"
```

Here, `Where-Object` filters the files by their `Extension` property, ensuring that only files with extension equal (`-eq`) to `.txt` are listed.

The operator `-eq` (i.e. "**equal to**") is part of a set of **comparison operators** that are shared with other scripting languages (e.g. Bash, Python). To show the potentiality of the PowerShell's filtering, we have selected some of the most useful operators from that list:

- `-ne`: "**not equal**". This operator can be used to exclude objects from the results based on specified criteria.
- `-gt`: "**greater than**". This operator will filter only objects which exceed a specified value. It is important to note that this is a strict comparison, meaning that objects that are equal to the specified value will be excluded from the results.
- `-ge`: "**greater than or equal to**". This is the non-strict version of the previous operator. A combination of `-gt` and `-eq`.
- `-lt`: "**less than**". Like its counterpart, "greater than", this is a strict operator. It will include only objects which are strictly below a certain value.
- `-le`: "**less than or equal to**". Just like its counterpart `-ge`, this is the non-strict version of the previous operator. A combination of `-lt` and `-eq`.

| **Command**                           | **Description**                                                                                                                           |
| ------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| `Get-Help`                            | Get documentation about a command                                                                                                         |
| `Get-Content`                         | Retrieves (gets) the content of a file and displays it in the console                                                                     |
| `Set-Location`                        | Changes (sets) the current working directory                                                                                              |
| `Get-Command`                         | Lists all available cmdlets, functions, aliases, and scripts that can be executed in the current PowerShell session                       |
| `Get-Command -CommandType "Function"` | display only the available commands of type “function”                                                                                    |
| `Get-Alias`                           | Lists all aliases available                                                                                                               |
| `Find-Module`                         | To search for modules (collections of cmdlets) in online repositories like the PowerShell Gallery                                         |
| `Get-ChildItem`                       | lists the files and directories in a location specified with the `-Path` parameter                                                        |
| `New-Item`                            | To create an item                                                                                                                         |
| `Remove-Item`                         | Removes both directories and files                                                                                                        |
| `Copy-Item`                           |                                                                                                                                           |
| `Move-Item`                           |                                                                                                                                           |
| `Select-Object`                       | used to select specific properties from objects or limit the number of objects returned.                                                  |
| `Get-ComputerInfo`                    | Retrieves comprehensive system information, including operating system information, hardware specifications, BIOS details, and more       |
| `Get-LocalUser`                       | Lists all the local user accounts on the system                                                                                           |
| `Get-NetIPConfiguration`              | provides detailed information about the network interfaces on the system, including IP addresses, DNS servers, and gateway configurations |
| `Get-NetIPAddress`                    | show details for all IP addresses configured on the system, including those that are not currently active                                 |
| `Get-Process`                         | provides a detailed view of all currently running processes, including CPU and memory usage                                               |
| `Get-Service`                         | allows the retrieval of information about the status of services on the machine                                                           |
| `Get-FileHash`                        | for generating file hashes                                                                                                                |
| `Invoke-Command`                      | executing commands on remote systems                                                                                                      |
