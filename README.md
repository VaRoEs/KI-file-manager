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
