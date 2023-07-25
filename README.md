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

=========================================
📢 Reminder: Always ensure that the correct version of Java and Maven are being used during your builds and tests. Happy coding! 🚀

