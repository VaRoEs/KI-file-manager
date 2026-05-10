# KI-file-manager
a lightweight file manager somewhat similar to the system1 manager
# Lightweight Windows File Manager

This project aims to develop a fast, extremely lightweight file shell/manager specifically optimized for low-end Windows computers. Built purely on C and WinAPI, it provides essential file management capabilities with a unique, minimalist graphical interface and zero unnecessary overhead.

Key Features

* **Unique "Elevator" Navigation:** A vertical dotted bar that visually represents folder depth, allowing you to dive deep into your file system (like descending into a mine shaft).
* **Fluid Animations:** Smooth visual feedback for moving, copying, and deleting files, as well as an animated Trash bin interface.
* **Advanced File Analytics:** Calculates exact file sizes, space occupied on the disk, and the percentage of total disk space used by a specific file.
* **Search Console:** Built-in search functionality featuring a simple and intuitive syntax.
* **Favorites System:** A dedicated menu to save and quickly access your most used directories and files.
* **Concurrent Operations:** Safely handles up to 4 parallel file operations (copying, pasting, moving, deleting) using custom memory buffers to prevent system freezes.
* **"Apple" Menu:** Quick access to essential Windows utilities directly from the UI (Run..., Windows Settings, and Control Panel).
* **Smart Deletion:** Supports both sending files to the Trash and instant permanent deletion.
* **Rich Context Menu:** Includes Create Folder/File/Group, Cut, Copy, Paste, Create Shortcut, Sort by Date/Name/Size, Properties, Refresh, Delete, Rename, and jump to "Computer".
* **Hover Popups:** Instant tooltips and details shown when hovering over files or folders.
* **Multi-selection Mode:** Easily select and manage multiple files at once.

## 🛠 Status & Known Issues
All major and critical bugs (including memory leaks during mass copying) have been successfully resolved. The core functionality is highly stable. However, as this is a custom-built UI, some minor graphical or edge-case bugs may still occur. 

## 📄 License
This project is open-source and available under the **MIT License**.

## ⚙️ Advanced Configuration (Power User Bonuses)
KI File Manager can be heavily customized using simple text files located in your `C:\` drive (or your User Profile directory). 

* **Custom File Associations (`ki_assoc.txt`)**
  You can manually map file extensions to specific executable programs for instant launching.
  *Format:* `ID) AppName --C:\Path\to\app.exe-- .ext1 .ext2`
  *Example:*
  `1) Notepad --C:\Windows\notepad.exe-- .txt .ini .log .cfg`
  `2) Explorer --C:\Windows\explorer.exe-- .exe .bat .cmd`

* **Custom Favorites (`ki_favorites.txt`)**
  Manage your starred/favorite directories for quick access from the UI.
  *Format:* `DisplayName --C:\Path\to\folder--`
  *Example:*
  `KI --C:\Users\Sigrika\Desktop\ki--`
  `PF --C:\Program Files (x86)--`

## 🔍 Advanced Search Syntax
The built-in search console supports powerful console-like commands and modifiers to find exactly what you need across your system:

* **Global Search:** Type `findall` to search everywhere across all available drives.
* **Wildcards & Boundaries:** Use parentheses `()` to set strict filename boundaries and `@` as a wildcard for unknown characters. 
  *Example:* `(@.txt)` finds all `.txt` files.
* **Size Filters:** Find files by size using `+` (greater than) or `-` (less than). Supported units: `b`, `kb`, `mb`, `gb`.
  *Example:* `-500mb` (files smaller than 500 MB), `+2gb` (files larger than 2 GB).
* **Top Size Sorting (`top`):** Find and filter the largest or smallest files in a directory.
  *Example:* `top 5 h` (returns the 5 *highest/largest* files).
  *Example:* `top 5 s` (returns the 5 *smallest* files).
* **Examples syntax**
top 5 s (small five files and folders)
findall (@.png) (all png files)
findall (@.exe) +100kb (all files exe more than 100kb size)
