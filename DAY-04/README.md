# Day 4: Kali, DNS, and Reconnaissance

## 1️⃣ Steps to Add a User in Kali

1. **Open Terminal** in Kali Linux.

2. Use the following command to add a user:

   ```bash
   sudo adduser <username>
   ```

   Example:

   ```bash
   sudo adduser shreya
   ```

3. You will be prompted to enter and confirm a password for the user.

4. You will also be prompted to enter additional information (Full Name, Room Number, etc.). You can leave them blank by pressing `Enter`.

5. To add the user to the `sudo` group (to give administrative privileges):

   ```bash
   sudo usermod -aG sudo <username>
   ```

   Example:

   ```bash
   sudo usermod -aG sudo shreya
   ```

6. To switch to the new user:

   ```bash
   su - <username>
   ```

---

## 2️⃣ Reasons and Benefits of Adding a User in Kali

* **Security**: Running as `root` always can lead to accidental system damage or security breaches. A normal user reduces this risk.
* **User Management**: Allows multiple users to work on the same system without interfering with each other.
* **Practice Realistic Scenarios**: In real-world penetration testing, you rarely operate with root access initially.
* **Controlled Privileges**: You can grant `sudo` access only when needed.
* **Better System Hygiene**: Keeps your workflow organized by separating administrative tasks from daily tasks.
* **Safer Learning**: Ideal for beginners to prevent accidental execution of harmful commands as `root`.

---

## 3️⃣ DNS Server Explained

### What does it contain?

* A **DNS (Domain Name System) server** contains:

  * A **database of domain names** and their corresponding **IP addresses**.
  * Records like:

    * **A record** (IPv4 address)
    * **AAAA record** (IPv6 address)
    * **MX record** (Mail Exchange servers)
    * **CNAME record** (Canonical names)
    * **NS record** (Name servers)

### What is its purpose?

* To **translate human-readable domain names** (like `www.google.com`) into **machine-readable IP addresses** (like `142.250.183.36`).
* To simplify browsing the internet without remembering IP addresses.
* To **route traffic efficiently** to the correct servers.

### How does it work?

1. You type a website URL into your browser.
2. Your system checks the **local DNS cache** for the IP address.
3. If not found, it queries the **configured DNS server**.
4. The DNS server checks:

   * If it has the domain's IP in its cache.
   * If not, it queries the **root DNS servers** → **TLD servers (like .com, .org)** → **Authoritative DNS servers**.
5. Once found, the IP address is returned to your system.
6. Your browser then uses this IP address to connect to the web server and load the website.

---

## 4️⃣ What is Reconnaissance in Cyber Security?

* **Reconnaissance** (also called **Recon**) in cybersecurity is the **initial phase of ethical hacking or penetration testing**, where you gather information about a target before actively engaging with it.

### Types of Reconnaissance:

* **Passive Reconnaissance:** Gathering information without directly interacting with the target (e.g., using public sources, social media, WHOIS, Google hacking).
* **Active Reconnaissance:** Interacting with the target directly to gather information (e.g., ping sweeps, port scanning).

### Purpose:

* To understand the **target's structure, systems, and potential vulnerabilities**.
* To **identify potential attack vectors**.
* To gather details like:

  * Domain names
  * IP addresses
  * Open ports and services
  * Employee details
  * Technology stack used by the target

Reconnaissance is crucial for **planning efficient attacks during penetration testing or red teaming** while helping defenders understand what attackers can gather about their systems.
