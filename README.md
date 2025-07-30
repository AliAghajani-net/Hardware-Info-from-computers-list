## 🔧 Hardware-Info-from-computers-list
This PowerShell script allows you to remotely collect detailed hardware information from a predefined list of computers and save the reports to a shared network folder.
## ✅ Features
- Collects detailed hardware information including:
  - ✅ Computer Name
  - ✅ CPU (Name, Cores, Threads, Clock Speed)
  - ✅ GPU (Name, Driver Version, Memory)
  - ✅ RAM (Capacity, Speed, Manufacturer, DDR Type)
  - ✅ Battery status (for laptops)
  - ✅ Hard Disk (Model, Size, Interface, Serial)
  - ✅ Network Adapters (MAC, Speed, Type)
  - ✅ Motherboard (Model, Serial)
  - ✅ Keyboard & Mouse

- Uses `Invoke-Command` to run the collection remotely
- Saves each report as a `.txt` file named after the computer
- Designed for use in domain environments

---

## 📁 File Structure

- `HardwareInfoComputersList.ps1`  
  The main PowerShell script that collects and saves hardware information.

- `computers.txt`  
  A plain text file that contains the list of target computers (NetBIOS names or FQDNs), one per line:

PC01
PC02
LAPTOP-ALICE

---

## ⚙️ Requirements

- ✅ PowerShell Remoting must be enabled on all target computers:
 -powershell
 -Enable-PSRemoting -Force

- ✅ User running the script must have administrative rights on the remote systems.

- ✅ TCP port 5985 must be open on remote machines (default for WinRM).

- ✅ The shared folder (for reports) must:

Be accessible from all target computers

Be writable by the executing user

---


## 🚀 How to Use
Edit the script and set the following variables:
$computersFile = "C:\Path\To\computers.txt"
$reportShare = "\\your-server\shared-folder\Hardware Info"
Prepare your computers.txt file with one computer name per line.

## Run the script in PowerShell:
.\HardwareInfoComputersList.ps1


## Result:
For each computer, a text report will be generated at the path you configured:
\\your-server\shared-folder\Hardware Info\PC01-hardware-info.txt
