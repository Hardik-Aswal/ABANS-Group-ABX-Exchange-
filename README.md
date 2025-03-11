# ABANS-Group-ABX-Exchange-

## Overview
ABXExchangeClient is a C++ client application that connects to a Node.js server, receives data packets, and generates an `output.json` file. This README provides step-by-step instructions to set up, build, and run the project.

## Prerequisites
Ensure you have the following software installed before proceeding:

### Required Software:
- **Visual Studio 2022** (with C++ development tools)
- **Node.js** (for the server)
- **Git** (for cloning the repository)
- **vcpkg** (for package management)

## Installation

### 1. Clone the Repository
```sh
# Open a terminal (Command Prompt or PowerShell)
cd C:\Users\YourName\Documents

git clone https://github.com/Hardik-Aswal/ABANS-Group-ABX-Exchange-
cd ABANS-Group-ABX-Exchange-
```

### 2. Install Node.js and Dependencies
Download and install **Node.js** from [https://nodejs.org/](https://nodejs.org/).

Verify installation:
```sh
node -v
npm -v
```

### 3. Install Boost (Required for C++)
Boost is required for handling JSON in C++. We will install it using `vcpkg`.

#### Install vcpkg
```sh
git clone https://github.com/microsoft/vcpkg.git
cd vcpkg
bootstrap-vcpkg.bat
```

#### Install Boost JSON
```sh
vcpkg install boost-json
```

#### Integrate vcpkg with Visual Studio
```sh
vcpkg integrate install
```

## Building the Project

### 1. Open the Project in Visual Studio
1. Open **Visual Studio 2022**.
2. Click **File → Open → Project/Solution**.
3. Navigate to the **ABXExchangeClient** folder.
4. Select the `ABXExchangeClient.vcxproj` file and click **Open**.

### 2. Configure Build Settings
1. In **Visual Studio**, locate the **Build Configuration** dropdown at the top.
2. Select:
   - **Debug** (for testing) or **Release** (for optimized performance).
   - **x64** as the platform.
3. If **x64** is missing:
   - Click **Configuration Manager → Active Solution Platform → New**.
   - Select **x64** and click **OK**.

### 3. Set Include and Library Directories
1. Go to **Project → Properties**.
2. Under **C/C++ → General**, set **Additional Include Directories**:
   ```
   C:\vcpkg\installed\x64-windows\include
   ```
3. Under **Linker → General**, set **Additional Library Directories**:
   ```
   C:\vcpkg\installed\x64-windows\lib
   ```
4. Click **Apply** and **OK**.

### 4. Build the Solution
```sh
# In Visual Studio, go to:
Build → Build Solution (Ctrl + Shift + B)
```
If successful, you will see **"Build: 1 succeeded"**.

## Running the Project

### 1. Start the Node.js Server
```sh
# Open a new terminal and navigate to the project folder
cd path\to\ABXExchangeClient

# Start the server
node main.js
```

### 2. Run the C++ Client
In **Visual Studio**:
```sh
Debug → Start Without Debugging (Ctrl + F5)
```
The client will connect to the server and generate `output.json`.

## Output Verification
After successful execution, check the `ABXExchangeClient` folder for `output.json`.
