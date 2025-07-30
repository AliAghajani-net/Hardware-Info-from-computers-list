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
  - powershell
  - Enable-PSRemoting -Force

- ✅ User running the script must have administrative rights on the remote systems.

- ✅ TCP port 5985 must be open on remote machines (default for WinRM).

- ✅ The shared folder (for reports) must:

  - Be accessible from all target computer
  - Be writable by the executing user

---


## 🚀 How to Use
- ✅Edit the script and set the following variables:
  - $computersFile = "C:\Path\To\computers.txt"
  - $reportShare = "\\your-server\shared-folder\Hardware Info"
  - Prepare your computers.txt file with one computer name per line.

## Run the script in PowerShell:
  - .\HardwareInfoComputersList.ps1


## Result:
- ✅For each computer, a text report will be generated at the path you configured:
  - \\your-server\shared-folder\Hardware Info\PC01-hardware-info.txt




---




# 🔧 دریافت اطلاعات سخت‌افزاری از لیست کامپیوترها

این اسکریپت PowerShell به شما اجازه می‌دهد که از راه دور، اطلاعات سخت‌افزاری کامپیوترهایی را که در یک لیست مشخص شده‌اند جمع‌آوری کرده و گزارش‌ها را در یک پوشه اشتراکی در شبکه ذخیره کنید.

---

## ✅ امکانات

این اسکریپت اطلاعات سخت‌افزاری زیر را جمع‌آوری می‌کند:

- ✅ نام کامپیوتر
- ✅ پردازنده (نام، تعداد هسته، تعداد رشته، سرعت کلاک)
- ✅ کارت گرافیک (نام، نسخه درایور، حافظه)
- ✅ حافظه RAM (ظرفیت، سرعت، سازنده، نوع DDR)
- ✅ باتری (در لپ‌تاپ‌ها)
- ✅ هارد دیسک (مدل، ظرفیت، نوع رابط، شماره سریال)
- ✅ آداپتورهای شبکه (MAC، سرعت، نوع)
- ✅ مادربورد (مدل، شماره سریال)
- ✅ کیبورد و ماوس

✅ از دستور `Invoke-Command` برای اجرای از راه دور استفاده می‌کند.  
✅ برای هر کامپیوتر، یک فایل متنی جداگانه با نام همان سیستم ایجاد می‌شود.  
✅ برای استفاده در محیط‌های دامینی طراحی شده است.

---

## 📁 ساختار فایل‌ها

- `HardwareInfoComputersList.ps1`  
  اسکریپت اصلی PowerShell که اطلاعات سخت‌افزاری را جمع‌آوری و ذخیره می‌کند.

- `computers.txt`  
  یک فایل متنی ساده که لیستی از نام کامپیوترها را (NetBIOS یا FQDN) شامل می‌شود. هر خط یک نام کامپیوتر:

PC01
PC02
LAPTOP-ALICE



---

## ⚙️ پیش‌نیازها

- ✅ فعال بودن PowerShell Remoting روی تمام کامپیوترهای هدف:

   - Enable-PSRemoting -Force
- ✅ یوزری که اسکریپت را اجرا می‌کند باید دسترسی مدیریتی (administrator) روی سیستم‌های مقصد داشته باشد.

- ✅ پورت 5985 (WinRM) روی سیستم‌های مقصد باز باشد.

- ✅ پوشه اشتراکی که گزارش‌ها در آن ذخیره می‌شوند باید:

از تمام کامپیوترها قابل دسترسی باشد

قابل نوشتن (Write) توسط یوزر اجراکننده باشد

🚀 نحوه استفاده
- ✅ اسکریپت را ویرایش کرده و مسیر فایل لیست کامپیوترها و مسیر پوشه گزارش‌ها را مشخص کنید:


  - $computersFile = "C:\Path\To\computers.txt"
  - $reportShare = "\\your-server\shared-folder\Hardware Info"
فایل computers.txt را با نام هر کامپیوتر در هر خط آماده کنید.

اسکریپت را در PowerShell اجرا کنید:


.\HardwareInfoComputersList.ps1
نتیجه:
برای هر کامپیوتر یک فایل گزارش به‌صورت زیر در مسیر مشخص‌شده ایجاد خواهد شد:


\\your-server\shared-folder\Hardware Info\PC01-hardware-info.txt
