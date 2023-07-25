# DevopsProject2JavaMavenSetup
A step-by-step guide to setting up Java 7 and Maven for Java-based projects. Perfect for newcomers to Java development and for those setting up a new environment. From web applications to standard Java apps, follow this guide to get up and running smoothly!
# 🛠 Maven Installation Guide
Set up Maven and Java for your Java-based projects. This guide is perfect for Java web applications, Java libraries, and standard Java applications.

# 📌 Table of Contents
Installing Java 7
Install Maven
Set JAVA_HOME Environment Variable
# 🟢 1. Installing Java 7
# 📥 a. Add the Repository

=========================================

sudo add-apt-repository ppa:openjdk-r/ppa

=========================================
# 🔄 b. Update the System

 =========================================
 
sudo apt update

=========================================
# 🔧 c. Install Java 7

=========================================

sudo apt install openjdk-7-jdk

=========================================
# ✅ d. Verify the Java Installation

=========================================

java -version

=========================================
# 🟡 2. Install Maven
# 📥 a. Install Maven

=========================================

sudo apt install maven -y

=========================================
# ✅ b. Verify Maven Installation

=========================================

mvn -v

=========================================
# 🔵 3. Set JAVA_HOME Environment Variable
# 🔍 a. Check if JAVA_HOME is Already Set

=========================================

echo $JAVA_HOME

=========================================
# 📝 b. Set JAVA_HOME if not Set

=========================================

echo "export JAVA_HOME=$(readlink -f /usr/bin/java | sed "s:bin/java::")" >> ~/.bashrc

source ~/.bashrc

📢 Reminder: Always ensure that the correct version of Java and Maven are being used during your builds and tests. Happy coding! 🚀
Step 1: Set Up Ansible on the Maven Machine:
# Install Ansible:

Since you're on an Ubuntu machine, you can use the following commands to install Ansible:


========================================

sudo apt update
sudo apt install software-properties-common
sudo apt-add-repository --yes --update ppa:ansible/ansible
sudo apt install ansible

========================================
# Check Ansible Installation:

Run the following command to make sure Ansible is installed:

========================================
 
ansible --version

========================================
# Step 2: Set Up SSH Keys for Ansible:
Generate an SSH key (if not already generated) on your Maven machine:

========================================
 
ssh-keygen

========================================
Press Enter through all prompts to accept defaults.

Copy the public SSH key to the Jenkins machine:

This allows the Maven machine (with Ansible) to securely communicate with the Jenkins machine without a password. Use the command below:

========================================

ssh-copy-id <username>@<jenkins_machine_IP>
Replace <username> with the user on the Jenkins machine you want to connect as.
Replace <jenkins_machine_IP> with the IP address of the Jenkins machine.

========================================
# Step 3: Test Ansible Communication:
Create a simple Ansible inventory file:

Create a file named hosts:

========================================

nano hosts

========================================
And add the following content:

========================================

[jenkins]
<jenkins_machine_IP> ansible_ssh_user=<username>
Replace <jenkins_machine_IP> with the IP address of your Jenkins machine.
Replace <username> with the username you'd use to SSH into the Jenkins machine.

========================================
# Test the connection using Ansible:

========================================

ansible -i hosts jenkins -m ping

========================================
This command will ping the Jenkins machine. If everything is set up correctly, you should receive a "SUCCESS" response.
