## Lab - Harden a Linux System

In this lab, we will use a security auditing tool to discover system vulnerabilities and implement recommended solutions to harden the system.

### What is system Harden?

System hardening" in Linux refers to the process of implementing security measures to protect a Linux system from potential attacks by configuring settings, managing user accounts, restricting access, and securing network components, essentially minimizing the system's attack surface and enhancing its overall security posture; this often involves hardening the kernel, managing firewall rules, and disabling unnecessary services.

- Part 1: Open a terminal on Ubuntu VM.

- Part 2: Examine the current version of Lynis.

- Part 3: Run the Lynis tool.

- Part 4: Review the results of your scan and address any warnings.

### Objectives:

Use a security auditing tool to discover system vulnerabilities.
Implement recommended solutions to harden the system.

### Background / Scenario:

Auditing a system for potential misconfigurations or unprotected services is an important aspect of system hardening. Lynis is an open source security auditing tool with an automated set of scripts developed to test a Linux system. Lynis performs an extensive health scan of your system. It includes a detailed report of vulnerabilities and recommended actions. In this lab, we will use Lynis to scan the Ubuntu VM and then implement solutions to harden the system.

### Required Resources

PC with the Ubuntu installed in VirtualBox

### Instructions

**Part 1: Install and Update Lynis.**

**Step 1: Determine the installed Lynis version.**

- a. Launch the Ubuntu VM.

- b. Double-click the Terminal icon to open a terminal.

- c. To determine the latest version provided by CISOfy, enter the following command at the terminal.

sudo apt-cache policy lynis

If Lynis is not installed or the latest version is not installed, go to the next step to install Lynis.

**Step 2: Install Lynis**

Lynis is security tool for systems running Unix-based OS, such as Linux and macOS. lynis will be used later in another activity to harden a Linux system. The application Lynis is maintained by CISOfy. In this step, we will add the software repository and install Lynis.

- a. Copy and paste the following command into a terminal to import the key from the CISOfy keyserver. This key is required to verify the integrity of your download when you download lynis:

sudo curl -fsSL https://packages.cisofy.com/keys/cisofy-software-public.key | sudo gpg - dearmor -o /etc/apt/trusted.gpg.d/cisofy-software-public.gpg

sudo echo "deb [arch=amd64,arm64 signed-by=/etc/apt/trusted.gpg.d/cisofy-software-public.gpg] https://packages.cisofy.com/community/lynis/deb/ stable main" | sudo tee /etc/apt/sources.list.d/cisofy-lynis.list

The software repository uses preferably HTTPS for secure transport. Install the 'https' method for APT, if it was not available yet.

sudo apt install apt-transport-https

Using your software in English? Then configure APT to skip downloading translations. This saves bandwidth and prevents additional load on the repository servers.

sudo echo 'Acquire::Languages "none";' | sudo tee /etc/apt/apt.conf.d/99disable-translations

- b. Copy and paste the following command into a terminal to add the lynis repository maintained by CISOfy.
sudo echo "deb https://packages.cisofy.com/community/lynis/deb/ stable main" | sudo tee /etc/apt/sources.list.d/cisofy-lynis.list

- c. Perform an update after adding a new repository. At the prompt.
sudo apt-get update.

- d. Use the command apt install to install Lynis if it is not already installed.
sudo apt install lynis

- e. Perform an upgrade after the installation to ensure that the installed Lynis is latest version. At the prompt, enter 

sudo apt-get upgrade.

**Part 2: Examine the current version of Lynis.**

Change to the Lynis directory, and then enter the sudo lynis update info command to check the update information for Lynis. Enter password for the sudo password. This command verifies that this is the latest version and updates for the tool at the time of writing of this lab. If the installed Lynis version is not up to date, enter sudo apt-get upgrade at the prompt.

Is your version not the latest? Run sudo apt-cache policy lynis to see where your package came from.
 Consider pinning

If you keep receiving an old version from your distribution, 'pin' the Lynis package. Create the file /etc/apt/preferences.d/lynis with the following contents:

Package: lynis

 Pin: origin packages.cisofy.com
 
 Pin-Priority: 600

Note: In this example, a priority of 600 was used, which is typically higher than the other sources. If not, increase the number.

**Part 3: Run the Lynis tool.**

- a. Enter the sudo lynis - auditor cisco command. You may or may not need to enter the password again. The scan will take about a minute to run.

sudo lynis - auditor cisco

- b. You should receive output for a variety of system features starting with Initializing program and ending with Hardening, Custom tests, and Plugins (phase 2).
The next section is the Lynis 3.1.3 Results. Your results most likely include the Warning(s) shown below. You may also receive other warnings. In addition, there will be a section with a listing of Suggestions, which lists 51 in the example output below. Only the first suggestion is shown.

**Part 4: Review the results of your scan and address any warnings.**

- a. Scroll to the Results section in the output for your scan.

How many Warnings did you receive?

1

How many Suggestions did you receive?

51

- b. You should address the warnings. Pick at least one warning and research how to fix that problem. You can use the link provided in the warning output as a starting point for addressing a warning. But you may also need to use your internet research skills to track down additional information.

Which warning are you addressing?


What is your solution?

The iptables were populated with the following firewall rules:

sudo iptables -L

sudo iptables -A INPUT -i lo -j ACCEPT

sudo iptables -A INPUT -m state - state ESTABLISHED,RELATED -j ACCEPT

sudo iptables -A INPUT -p icmp -j ACCEPT

sudo iptables -A INPUT -p tcp - dport 22 -j ACCEPT

sudo iptables -A INPUT -p tcp - dport 80 -j ACCEPT

sudo iptables -A INPUT -p tcp - dport 443 -j ACCEPT

sudo iptables -A INPUT -p udp - dport 1194 -j ACCEPT

sudo iptables -A INPUT -s 192.168.0.10 -j ACCEPT

sudo iptables -A INPUT -s 192.168.0.20 -j DROP

sudo iptables -P INPUT DROP

sudo iptables -P FORWARD DROP

sudo iptables -P OUTPUT ACCEPT

Enter the below command to save the iptables

sudo iptables-save

sudo ufw status

sudo ufw enabled

Enter the sudo lynis - auditor cisco command to run lynis again

Next: You can also address the suggestions. Pick at least one suggestion and research how to fix that problem. You can use the link provided in the suggestion output as a starting point for addressing a suggestion. But you may also need to use your internet research skills to track down additional information.

**Skills Gained from the Project:**

System Hardening Techniques

Security Auditing

Implementing secure configurations

Writing and applying firewall rules 

Problem-Solving and Research

Incident Detection and Response Preparation 

Proactive Cybersecurity Practices

**Conclusion**

Successfully hardening a Linux system is a critical step in strengthening its security posture and reducing vulnerabilities. By using tools like Lynis, you can identify potential weaknesses, implement effective solutions, and ensure a proactive defense against cyber threats. The knowledge gained from this lab empowers you to audit and secure systems systematically, enabling you to maintain robust, secure environments in real-world scenarios. Continual practice with system hardening techniques builds a strong foundation for advancing your cybersecurity expertise.

To view this project with screenshots, please visit [my medium page](https://medium.com/@eberechukwunemeremjohnsunday/lab-harden-a-linux-system-cf6b320ceda0)
