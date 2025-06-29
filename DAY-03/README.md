# Day 3: Basic Linux Concepts and Commands

## 1) What is the `sudo` command?

* `sudo` stands for **Super User Do**.
* It allows a permitted user to execute a command as the **superuser (root)** or another user.
* It is used for performing **administrative tasks** without logging in as the root user.
* It helps in maintaining **system security** by avoiding logging in as root unnecessarily.
* Commands requiring system-level changes (like installing or updating packages) often need `sudo`.
* Example: `sudo apt update` will update the package lists with superuser permissions.

---

## 2) What is the difference between `kali/user` and `root`?

* **`kali/user` (Normal User):**

  * Has **limited permissions**.
  * Cannot perform administrative tasks without using `sudo`.
  * Provides **security** by preventing accidental system-wide changes.
  * Used for **regular daily activities**.

* **`root` (Superuser):**

  * Has **full system access and control**.
  * Can modify **all files and configurations**.
  * Used for **administrative and critical system tasks**.
  * Mistakes while using root can **break the system**.
  * Should be used **only when necessary** for security and stability.

---

## 3) What is `apt` in Linux?

* `apt` stands for **Advanced Package Tool**.
* It is used for **installing, updating, upgrading, and removing software packages** in Debian-based systems like Kali Linux and Ubuntu.
* It automatically handles **dependencies** required by software packages.
* Common `apt` commands include `apt update`, `apt upgrade`, `apt install`, and `apt remove`.
* Helps keep the system **up to date** and **manage packages efficiently**.

---

## Basic Linux Commands for Beginners

### 1) `sudo apt upgrade` - What is this command used for?

* Upgrades **all installed packages** on the system to the latest available versions.
* It **does not remove any packages** but may install new dependencies if required.
* Used to keep the system **updated with security patches and improvements**.
* Should be run after `sudo apt update` to apply the fetched updates.

### 2) `sudo apt update` - What is this command used for?

* Updates the **package index** on the system by retrieving the latest package lists from repositories.
* It **does not upgrade any packages** but informs the system of available updates.
* Must be run before `sudo apt upgrade` to ensure packages are upgraded to the latest versions.

### 3) `ls` - What is this command used for?

* Used to **list the contents of a directory**.
* Shows files and folders in the current or specified directory.
* Variants like `ls -l` display detailed information, and `ls -a` shows hidden files.

### 4) `mkdir` - What is this command used for?

* Used to **create a new directory (folder)**.
* Syntax: `mkdir <directory_name>`.
* Example: `mkdir Projects` will create a folder named "Projects".

### 5) `pwd` - What is this command used for?

* Stands for **Print Working Directory**.
* Displays the **full path of the current directory** you are working in.
* Useful for identifying your current location in the file system.

### 6) `cd` - What is this command used for?

* Stands for **Change Directory**.
* Used to **navigate between directories** in the file system.
* Example: `cd Documents` moves you into the Documents folder.
* `cd ..` moves you one level up, while `cd` alone returns you to the home directory.



