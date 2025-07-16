# Day 05: Custom Command Creation in Kali Linux (Ethical Hacking)

## 🖥️ Practical: Creating a Custom Command to Fetch IP Address

In today's session, we created a **custom command `myip`** that fetches the **IP address of Kali Linux** and copies it to the clipboard.

---

### Step-by-Step Process

#### 1️⃣ Understanding Commands:
- **`ifconfig`**: Displays network interface information including IP addresses.
- To filter only the IP address:
    - `ifconfig eth0`: Shows details of `eth0` interface.
    - `ifconfig eth0 | grep inet`: Filters lines containing "inet".
    - `ifconfig eth0 | grep inet | grep -v ":"`: Removes IPv6, keeping only IPv4.
    - `ifconfig eth0 | grep inet | grep -v ":" | awk '{print $2}'`: Extracts the IP address (e.g., `10.0.2.15`).

#### 2️⃣ Creating the Bash Script:
- Create a directory:
  ```bash
  mkdir mycode
  cd mycode
  ```
- Create a bash script:
  ```bash
  nano myip.sh
  ```
- Paste the command:
  ```bash
  ifconfig eth0 | grep inet | grep -v ":" | awk '{print $2}'
  ```
- Save and exit the file.

#### 3️⃣ Making the Script Executable:
- Check permissions:
  ```bash
  ls -lh
  ```
- Add execute permission:
  ```bash
  chmod +x myip.sh
  ```
- Execute the script:
  ```bash
  ./myip.sh
  ```

#### 4️⃣ Converting Script into a Custom Command:
- Rename the script:
  ```bash
  mv myip.sh myip
  ```
- Move to `/bin` for global access:
  ```bash
  sudo cp -r myip /bin
  ```
- Now, typing `myip` anywhere will display the IP address.

#### 5️⃣ Copying IP Address Directly to Clipboard:
- Install clipboard utility:
  ```bash
  sudo apt install -y xclip
  ```
- Edit the `myip` file in `/bin`:
  ```bash
  sudo nano /bin/myip
  ```
- Replace contents with:
  ```bash
  ipv4_add=$(ifconfig eth0 | grep inet | grep -v ":" | awk '{print $2}')
  echo -n "$ipv4_add" | xclip -selection clipboard
  echo "$HOSTNAME IP Address: $ipv4_add (Copied to Clipboard)"
  sleep 5
  clear
  ```
- Save and exit.

Now, executing `myip` will display your IP address and automatically copy it to your clipboard for easy pasting.

---

## 📘 Theory Portion

### What is Ethical Hacking?
Ethical hacking is the **authorized practice of bypassing system security to identify potential data breaches and threats in a network**. It helps strengthen system security by proactively finding vulnerabilities.

### Types of Ethical Hackers
- **White Hat Hackers:** Ethical professionals focusing on securing systems with permission.
- **Grey Hat Hackers:** Hack without explicit permission but typically report vulnerabilities found.
- **Black Hat Hackers:** Hack for malicious purposes without permission.
- **Red Hat Hackers:** Focus on attacking black hats to disrupt their activities.
- **Hacktivists:** Hack to promote political or social causes.
- **Script Kiddies:** Inexperienced individuals using existing tools/scripts to hack systems without deep knowledge.
