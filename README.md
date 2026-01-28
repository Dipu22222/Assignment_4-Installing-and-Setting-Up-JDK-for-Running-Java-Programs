# JDK Installation and Test Program

**Name:** Dipu Mondol  
**ID:** IT-24040

## Description

This assignment demonstrates the complete process of downloading and installing JDK 20 (or later version), setting up the system PATH environment variable, verifying the installation, and running a simple test Java program that outputs "It's a rainy day!". This is a fundamental requirement for Java development.

## Assignment Steps

### Step 1: Download JDK 20 or Later

1. Go to Oracle's official website: https://www.oracle.com/java/technologies/downloads/
2. Select **JDK 20** or later version (e.g., JDK 21, JDK 22)
3. Choose your operating system:
   - Windows (x64 Installer)
   - macOS (ARM64 DMG or x64 DMG)
   - Linux (x64 Compressed Archive)
4. Download the installer

**Alternative:** You can also use OpenJDK from https://jdk.java.net/

### Step 2: Install JDK

**For Windows:**
1. Run the downloaded `.exe` file
2. Click "Next" through the installation wizard
3. Note the installation path (usually `C:\Program Files\Java\jdk-20`)
4. Click "Install" and wait for completion
5. Click "Close" when finished

**For macOS:**
1. Open the downloaded `.dmg` file
2. Follow the installation prompts
3. Installation path is usually `/Library/Java/JavaVirtualMachines/jdk-20.jdk`

**For Linux:**
1. Extract the downloaded archive: `tar -xzvf jdk-20_linux-x64_bin.tar.gz`
2. Move to `/opt/`: `sudo mv jdk-20 /opt/`

### Step 3: Set PATH Environment Variable

**For Windows:**

1. Right-click on "This PC" → Properties
2. Click "Advanced system settings"
3. Click "Environment Variables"
4. Under "System Variables", find "Path" and click "Edit"
5. Click "New" and add: `C:\Program Files\Java\jdk-20\bin`
6. Click "OK" on all windows
7. Restart Command Prompt

**Alternative Windows Method:**
```cmd
setx JAVA_HOME "C:\Program Files\Java\jdk-20"
setx PATH "%PATH%;%JAVA_HOME%\bin"
```

**For macOS/Linux:**

Add to `~/.bash_profile` or `~/.zshrc`:
```bash
export JAVA_HOME=/Library/Java/JavaVirtualMachines/jdk-20.jdk/Contents/Home
export PATH=$JAVA_HOME/bin:$PATH
```

Then run:
```bash
source ~/.bash_profile
```

### Step 4: Check Java Version

Open Command Prompt (Windows) or Terminal (macOS/Linux) and run:

```bash
java -version
```

**Expected Output:**
```
java version "20.0.1" 2023-04-18
Java(TM) SE Runtime Environment (build 20.0.1+9-29)
Java HotSpot(TM) 64-Bit Server VM (build 20.0.1+9-29, mixed mode, sharing)
```

Also check the compiler:
```bash
javac -version
```

**Expected Output:**
```
javac 20.0.1
```

If you see the version numbers, installation is successful! ✅

### Step 5: Write and Run Test Code

## Test Code

```java
public class RainyDay {
    public static void main(String[] args) {
        System.out.println("It's a rainy day!");
        
    }
}
```

## How to Run

1. Save the code as `RainyDay.java`
2. Open Command Prompt/Terminal
3. Navigate to the file location:
   ```bash
   cd path/to/file
   ```
4. Compile:
   ```bash
   javac RainyDay.java
   ```
5. Run:
   ```bash
   java RainyDay
   ```

## Expected Output

```
It's a rainy day!
```

## Complete Session Example

```bash
C:\Users\Dipu\Desktop> javac RainyDay.java
C:\Users\Dipu\Desktop> java RainyDay
It's a rainy day!
C:\Users\Dipu\Desktop>
```

## Verification Checklist

- [x] JDK 20 or later downloaded
- [x] JDK installed successfully
- [x] PATH environment variable set
- [x] `java -version` shows correct version
- [x] `javac -version` shows correct version
- [x] Test program compiles without errors
- [x] Test program runs and shows correct output

## Troubleshooting

### Problem 1: "java is not recognized as an internal or external command"
**Solution:**
- JDK not installed properly
- PATH not set correctly
- Restart Command Prompt/Terminal after setting PATH
- Verify installation path matches PATH variable

### Problem 2: Wrong Java version showing
**Solution:**
- Multiple Java versions installed
- Update PATH to point to correct JDK
- Remove old Java versions from PATH

### Problem 3: javac works but java doesn't (or vice versa)
**Solution:**
- PATH might be pointing to JRE instead of JDK
- Make sure PATH points to JDK bin folder, not JRE

### Problem 4: Permission denied (Linux/macOS)
**Solution:**
- Use `sudo` for installation
- Check file permissions
- Make sure you have admin rights

## Why Set PATH?

The PATH environment variable tells your operating system where to find executable programs. Without setting PATH:
- You'd need to type the full path every time: `C:\Program Files\Java\jdk-20\bin\javac RainyDay.java`
- With PATH set, you can simply type: `javac RainyDay.java`

## Difference Between JDK, JRE, and JVM

| Component | Full Name | Purpose |
|-----------|-----------|---------|
| **JDK** | Java Development Kit | Complete package for development (includes JRE + development tools) |
| **JRE** | Java Runtime Environment | For running Java programs (includes JVM + libraries) |
| **JVM** | Java Virtual Machine | Executes Java bytecode |

**For Development:** You need JDK  
**For Running Only:** JRE is enough

## Important Notes

1. **File name must match class name:** `RainyDay.java` for `class RainyDay`
2. **Java is case-sensitive:** `RainyDay` ≠ `rainyday`
3. **Always compile before running:** `javac` first, then `java`
4. **Don't include .class extension when running:** Use `java RainyDay`, not `java RainyDay.class`

## What Happens When You Run?

1. **javac RainyDay.java**
   - Compiler reads source code
   - Checks for syntax errors
   - Generates bytecode (RainyDay.class)

2. **java RainyDay**
   - JVM loads the .class file
   - Finds main() method
   - Executes the program
   - Output appears in console

## System Requirements

- **Operating System:** Windows 10+, macOS 10.14+, or Linux
- **RAM:** Minimum 2GB (4GB recommended)
- **Disk Space:** 300-400MB for JDK
- **Processor:** Intel/AMD 64-bit processor

## Useful Commands

```bash
# Check Java version
java -version

# Check compiler version
javac -version

# See where Java is installed (Windows)
where java

# See where Java is installed (Linux/macOS)
which java

# Display Java home directory
echo %JAVA_HOME%        # Windows
echo $JAVA_HOME         # Linux/macOS
```
