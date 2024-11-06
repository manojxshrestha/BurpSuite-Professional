![IMG_8694](https://github.com/user-attachments/assets/65fbe3a1-72e8-4bb8-9ef4-79c079dbafe4)


# <h1 align="center"> Burpsuite Professional </h1>

<p align="center"> Burp Suite is a all-in-one tool for web app security testing. It’s packed with tools like a Proxy to intercept traffic, a Scanner to catch common bugs, and Intruder for automated attacks. Basically, if you're looking to find security holes in a website, Burp’s got you covered. You can go manual or let it do the heavy lifting—either way, it’s the go-to toolkit for anyone into ethical hacking or security checks. There’s a free version, but the Pro one has all the good stuff. </p>

<h1 align="center">

[Overview](https://portswigger.net/burp/pro)
 </h1>

<br></br>

<h1 align="center"> Step by Step Installation </h1>

<br></br>

[Download the file](https://drive.google.com/uc?export=download&id=1R19bRsw72NeGTlwJ9U96rOp8mk8fHQ9m)



- ### Step 1: Download Burp Suite

> 1. Download the Burp Suite ZIP file.

> 2. Extract the ZIP file to a folder on your OS.


- ### Step 2: Download and Install OpenJDK

To run Burp Suite, you’ll need to install OpenJDK (Java Development Kit), as it provides the necessary Java environment.

> 1. Go to OpenLogic’s OpenJDK download page. [Click here](https://www.openlogic.com/openjdk-downloads?field_java_parent_version_target_id=416&field_operating_system_target_id=426&field_architecture_target_id=391&field_java_package_target_id=396)

>2. Select and download the following:

![Screenshot at 2024-11-05 17-24-48](https://github.com/user-attachments/assets/21aceef7-d88f-4f03-afb2-b730a5426242)


<br>
 • Version: 8u392-b08 (or similar version if updated)
<br>
 • OS: Linux
 <br>
• Architecture: x86 64-bit
 <br>
• Package: .deb file
</br>


> 4. Once downloaded, open a terminal in the location where you saved the .deb file.

> 6. Run the following commands to install OpenJDK:

```bash
chmod +x openlogic-openjdk-8u392-b08-linux-x64-deb.deb
```

```bash
sudo dpkg -i openlogic-openjdk-8u392-b08-linux-x64-deb.deb`
```

> Enter your password when prompted to complete the installation.


- ### Step 3: Set OpenJDK as the Default Java Version

- ### After installing OpenJDK, configure it as the default Java version:

> 1. Run the following command to list all installed Java versions:

```bash
sudo update-alternatives --config java
```

> 2. You’ll see a list of available Java versions. Each option is numbered. Find the path for OpenLogic OpenJDK 8 (in this case, `/usr/lib/jvm/openlogic-openjdk-8-hotspot-amd64/bin/java`).

![Screenshot at 2024-11-05 17-33-32](https://github.com/user-attachments/assets/83c03b36-e72a-4a8e-9a92-a0b7789b8f7e)


> 3. Type the selection number for OpenLogic OpenJDK 8 (e.g., 3) and press Enter to set it as the default.


- ### Step 4: Launch Burp Suite

> 1. After extracting the Burp Suite ZIP file, open a terminal and navigate to the extracted directory:

```bash
cd ~/Desktop/Burpsuite
```


> 2. List the files to ensure the ESEdition.jar (or similar JAR file) is present.
> 3. Run the Burp Suite JAR file with the following command:

```bash
java -jar ESEdition.jar
```
![Screenshot at 2024-11-05 17-39-50](https://github.com/user-attachments/assets/21cc9ad0-d40a-4032-861b-27900761dc79)


> This command will start Burp Suite using the Java Runtime Environment.


# <h1 align="center"> Setting Up Burp Suite Pro with Custom Shortcut on Linux </h1>


- ### Step 1: Create and Configure the Burp Suite Script

> 1. Open Pluma:

 <br>
• Open your terminal and launch Pluma by typing:
</br>

```bash
pluma
```

> 2. Create the burp.sh Script:

<br>
• If the burp.sh script does not already exist, create it in the Burp Suite directory:
</br>

```bash
touch ~/Desktop/Burpsuite/burp.sh
```

> 3. Edit the burp.sh Script:

<br>
• Open the script in Pluma:
</br>

```bash
pluma ~/Desktop/Burpsuite/burp.sh`
```
<br>
• Add the following content to the script, ensuring it points to the correct JAR files:
</br>

```bash
`#!/bin/bash
java -Xbootclasspath/p:/home/arcmyst/Desktop/Burpsuite/ESEdition.jar -jar /home/arcmyst/Desktop/Burpsuite/burpsuite_pro_v1.7.34.jar
```

<br>
• This command uses Java to run Burp Suite with the necessary boot classpath.
</br>

> 4. Save and Close:

<br>
• Save the changes in Pluma and close the editor.
</br>

> **Note**: Replace `arcmyst` with your actual username in all file paths if your username is different.


- ### Step 2: Make the Script Executable

> To ensure the script can be run, you need to change its permissions:

> 1. Change Permissions:

<br>
• Run the following command in the terminal:
</br>

```bash
chmod +x ~/Desktop/Burpsuite/burp.sh
```


- ### Step 3: Create a Symbolic Link for Easy Access

> To run Burp Suite by typing BurpsuitePro, you need to create a symbolic link in a directory that is included in your system’s PATH.

> 1. Create the Symbolic Link:

<br>
•Run the following command in the terminal:
</br>

```bash
sudo ln -sf ~/Desktop/Burpsuite/burp.sh /usr/local/bin/BurpsuitePro
```

- ### Step 4: Running Burp Suite Pro

>Now you can launch Burp Suite Pro simply by typing:

```bash
BurpsuitePro
```
in your terminal and pressing Enter.

![Screenshot at 2024-11-05 17-45-04](https://github.com/user-attachments/assets/99a3ce45-6a37-478c-8153-ed5df25caf1f)



- ### Troubleshooting

> If you encounter issues, ensure:
<br>
• The burp.sh script has the correct content and is executable.
<br>
• You have the appropriate version of Java installed and configured.
<br>
• The paths to the JAR files in the burp.sh script are correct.
</br>

- ### Verifying Java Version

> To check your Java version, run:

```bash
java -version
```

> If you are using an older version (like OpenJDK 😎, consider installing a newer version:

```bash
sudo apt update
```

```bash
sudo apt install openjdk-11-jdk
```

By following these steps, you can successfully set up Burp Suite Professional on your Linux system for easy access.

