# D: Drive 99% Full: Hidden File History Backup (730 GB)

**Device:** Lenovo Legion Y7000P (Windows 11)
**Category:** Storage / Disk space
**Result:** Resolved. D: free space went from 12.8 GB to 742 GB.

## Problem

The 931 GB data drive (D:) showed about 12.8 GB free. Browsing the drive in File Explorer showed only a few games (a Steam library and Fortnite, roughly 175 GB combined), so roughly 700+ GB of usage couldn't be accounted for. Uninstalling apps that might have stored data (VirtualBox, Prism Launcher) and emptying the Recycle Bin didn't free any space.

## Diagnosis

1. Ran **WizTree** as administrator and scanned D:. It reads the drive's file table directly, so it shows folders File Explorer doesn't surface.
2. The scan showed a single `FileHistory` folder using about 730 GB (roughly 80% of the drive), holding around 900,000 files.
3. The treemap showed the bulk of it was a backed-up Downloads folder, including a large game-files folder.
4. **Root cause:** Windows File History was backing up the user's Downloads folder to D: and keeping every version of every file, including files deleted from the original location.

## Attempted fixes

- **File History > Advanced settings > Clean up versions:** failed with an "element not found" error. File History no longer recognized D: as an active backup target, so the cleanup screen had nothing to point at.

## Fix

Ran the following in an elevated (administrator) Command Prompt:

1. `takeown /f D:\FileHistory /r /d y` (take ownership of the folder tree)
2. `icacls D:\FileHistory /grant administrators:F /t` (grant the Administrators group full control)
3. `rmdir /s /q D:\FileHistory` (delete the folder and everything in it)

Notes:
- `takeown` was mistyped on the first attempt and Windows reported it wasn't a recognized command. `icacls` still processed every file with **0 failures**, so the delete went through without needing a second pass.
- With around 900,000 files on a hard drive (HDD), each step took a long time. The Command Prompt looked frozen and Task Manager showed low MB/s with spiky active time. That's normal for many small files on an HDD, since the limit is seek time, not transfer speed.
- Deleting this folder removes backup copies only, not the original files. Checked first that nothing in the backup was still needed.

## Prevention

- Disable the **File History Service** (`services.msc` > File History Service > Startup type: Disabled > Stop) so it can't start refilling the drive.
- If File History is ever turned back on, exclude large folders (Downloads, game files) and cap how many versions are kept.

## Lessons learned

- **File Explorer doesn't show everything.** When free space doesn't match what's visible, use a tool that reads the file table directly (WizTree).
- **Uninstalling an app doesn't delete its data**, and deleted files can still count as used space until the Recycle Bin is emptied.
- **Built-in cleanup tools can fail** when the backup target is no longer recognized. The command-line route (ownership, permissions, delete) works as a fallback.
- **HDD operations on huge numbers of small files are slow.** Watch active time in Task Manager, not MB/s, to tell if a job is working or stuck.
