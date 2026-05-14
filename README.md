<img width="1313" height="745" alt="Screenshot_13" src="https://github.com/user-attachments/assets/772b54ee-009d-4186-8b9c-ffe585955e79" />
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

## ⚙️ Configuration & Personalization

KI File Manager is designed to be highly portable and customizable. All preferences are stored in simple plain-text files. By default, the application looks for these files in your **User Profile directory** (e.g., `C:\Users\YourName\`).

### 📂 Configuration Files Location
The manager and the Configurator (`set0.7.c`) primarily use the following paths:
* **Main Settings:** `%USERPROFILE%\ki_settings.txt`
* **Favorites:** `%USERPROFILE%\ki_favorites.txt`
* **File Associations:** `%USERPROFILE%\ki_assoc.txt`
* **Search Index:** `C:\ki_index.txt` (and `ki_index.bin` for fast loading)

---

### 🛠 Settings Detail (`ki_settings.txt`)
This file controls the visual behavior and custom icon mappings.
* **`DarkMode=1`**: Enables the "Neon Dark" mode (Classic Mac aesthetic with a high-contrast green glow).
* **`TrashSkin=0/1/2`**: Sets the Trash bin design (0: Classic, 1: Mesh, 2: Boxy).
* **`Icon:.ext=ID`**: Maps a specific file extension to one of the built-in icons (0-5).
    * *Example:* `Icon:.c=5` maps C files to the "Code" icon.

### 🌟 Favorites (`ki_favorites.txt`)
Allows you to define quick-access folders in the Star (★) menu.
* **Format:** `DisplayName -- FullPath`
* **Example:** `My Projects -- C:\Users\Dev\Projects`

### 🔗 File Associations (`ki_assoc.txt`)
Define which application should open specific file types within the manager.
* **Format:** `AppName -- ExecutablePath -- Extensions`
* **Example:** `VSCode -- C:\Path\To\Code.exe -- .c .h .cpp .json`

### 🔍 Search Index (`ki_index.txt`)
This file is generated automatically when you run the indexing command (`-ref` in the search bar). It contains a recursive map of your drives for near-instant searching.

<img width="1313" height="745" alt="Screenshot_13" src="https://github.com/user-attachments/assets/a8dd0feb-db98-4781-92e1-42da9b6611e0" />
Main theme

<img width="280" height="176" alt="Screenshot_14" src="https://github.com/user-attachments/assets/7f78bf86-05d2-4062-b5d4-18d2267e20e5" /><img width="344" height="266" alt="Screenshot_15" src="https://github.com/user-attachments/assets/f320d846-5bdf-4b3c-a5d7-5364bec18a85" />
Elevator works, you can tap on black poit if you want back

<img width="622" height="681" alt="Screenshot_4" src="https://github.com/user-attachments/assets/f26c76a2-471c-446d-9f58-5fc14018dd9f" />
Dont forget tap on chooser one more if you want remove check mark mode

<img width="425" height="451" alt="Screenshot_6" src="https://github.com/user-attachments/assets/d844872f-2c68-4226-920a-1844387b7208" />
context menu

<img width="487" height="383" alt="Screenshot_7" src="https://github.com/user-attachments/assets/6b778eb5-fefc-4408-9139-f2a03d32615c" />
Computer teleport you in disk view space

<img width="700" height="518" alt="Screenshot_18" src="https://github.com/user-attachments/assets/527e5f5c-5b2c-484b-90ec-2769ee7fa24f" />
Settings
3 type bin as gift)
Program will be translated, on eng in future
