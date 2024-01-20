# JDK installation in WSL 2
1. Download JDK deb 64 bit from Oracle website [Link](https://www.oracle.com/java/technologies/downloads) Note: Latest - 2 is more stable.
2. Copy the `.deb` file to the wsl `/home/neon/java`.
3. Install the `.deb` file using `sudo dpkg -i jdk-17_linux-x64_bin.deb`
4. Link the `java` and `javac` in `/usr/lib/jvm`:
```bash
sudo update-alternatives --install /usr/bin/java java /usr/lib/jvm/jdk-17-oracle-x64/bin/java 1
sudo update-alternatives --install /usr/bin/javac javac /usr/lib/jvm/jdk-17-oracle-x64/bin/javac 1
```
5. Update the `JAVA_HOME` environemnt variable.
 ```bash
 sudo vim /etc/environment
 JAVA_HOME="/usr/lib/jvm/jdk-17-oracle-x64"
 source /etc/environment
 ```

## Working with multiple versions of JDK
- Select the `java` and `javac` as using follwing commands.
```bash
sudo update-alternatives --config java
sudo update-alternatives --config javac #Select javac according to the java selected above
```
__NOTE__: Make sure you installed the `JDK` not `JRE` since JRE does not contain `javac`.


# Configuring VS Code for Java development
- First install `Extension Pack for Java` extension in the wsl.
- Update the User settings(JSON) for WSL `Ctrl + Shift + P`.
```json
{
  "java.configuration.runtimes": [
    {
      "name": "JavaSE-17",
      "path": "/usr/lib/jvm/jdk-17-oracle-x64"
    }
  ],
  "java.debug.settings.console": "internalConsole"
}
```