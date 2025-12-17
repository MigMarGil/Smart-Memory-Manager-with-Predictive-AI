# Installation Guide

Complete installation instructions for Smart Memory Manager on different platforms.

## Table of Contents

- [Prerequisites](#prerequisites)
- [Linux Installation](#linux-installation)
- [macOS Installation](#macos-installation)
- [Windows Installation](#windows-installation)
- [Verification](#verification)
- [Troubleshooting](#troubleshooting)

## Prerequisites

### Required
- C++17 compatible compiler
- CMake 3.15 or higher (recommended)
- Git

### Compiler Versions
- **GCC**: 7.0 or higher
- **Clang**: 5.0 or higher  
- **MSVC**: Visual Studio 2017 or higher

## Linux Installation

### Ubuntu/Debian

```bash
# Install dependencies
sudo apt-get update
sudo apt-get install -y build-essential cmake git

# Clone repository
git clone https://github.com/your-username/smart-memory-manager.git
cd smart-memory-manager

# Build with CMake
mkdir build && cd build
cmake ..
make -j$(nproc)

# Run
./smart_memory_manager
```

### Fedora/RHEL/CentOS

```bash
# Install dependencies
sudo dnf install -y gcc-c++ cmake git

# Clone and build (same as above)
git clone https://github.com/your-username/smart-memory-manager.git
cd smart-memory-manager
mkdir build && cd build
cmake ..
make -j$(nproc)
./smart_memory_manager
```

### Arch Linux

```bash
# Install dependencies
sudo pacman -S base-devel cmake git

# Clone and build (same as above)
git clone https://github.com/your-username/smart-memory-manager.git
cd smart-memory-manager
mkdir build && cd build
cmake ..
make -j$(nproc)
./smart_memory_manager
```

### Alternative: Direct Compilation (No CMake)

```bash
# Using Make
make
./smart_memory_manager

# Or direct g++ command
g++ -std=c++17 -O3 -pthread main.cpp -o smart_memory_manager
./smart_memory_manager
```

## macOS Installation

### Using Homebrew

```bash
# Install dependencies
brew install cmake git

# Clone repository
git clone https://github.com/your-username/smart-memory-manager.git
cd smart-memory-manager

# Build with CMake
mkdir build && cd build
cmake ..
make -j$(sysctl -n hw.ncpu)

# Run
./smart_memory_manager
```

### Using Xcode Command Line Tools

```bash
# Install Xcode Command Line Tools
xcode-select --install

# Clone and build
git clone https://github.com/your-username/smart-memory-manager.git
cd smart-memory-manager
mkdir build && cd build
cmake ..
make -j$(sysctl -n hw.ncpu)
./smart_memory_manager
```

### Alternative: Direct Compilation

```bash
# Using Make
make
./smart_memory_manager

# Or direct clang++ command
clang++ -std=c++17 -O3 -pthread main.cpp -o smart_memory_manager
./smart_memory_manager
```

## Windows Installation

### Using Visual Studio

#### Prerequisites
- Visual Studio 2017 or higher
- CMake (download from [cmake.org](https://cmake.org/download/))
- Git for Windows

#### Steps

```cmd
# Clone repository
git clone https://github.com/your-username/smart-memory-manager.git
cd smart-memory-manager

# Create build directory
mkdir build
cd build

# Generate Visual Studio project
cmake ..

# Build
cmake --build . --config Release

# Run
.\Release\smart_memory_manager.exe
```

### Using Visual Studio IDE

1. Open Visual Studio
2. Select "Clone a repository"
3. Enter repository URL
4. Open CMakeLists.txt
5. Build > Build All
6. Run from Debug or Release folder

### Using MinGW-w64

```cmd
# Install MinGW-w64 and add to PATH

# Clone repository
git clone https://github.com/your-username/smart-memory-manager.git
cd smart-memory-manager

# Compile directly
g++ -std=c++17 -O3 -pthread main.cpp -o smart_memory_manager.exe

# Run
smart_memory_manager.exe
```

## Verification

After installation, verify the build:

```bash
# Linux/macOS
./smart_memory_manager

# Windows
smart_memory_manager.exe
```

Expected output should start with:

```
==================================================================
                                                              
     SMART MEMORY MANAGER WITH PREDICTIVE AI                 
     Revolutionary Memory Management System            
     ...
```

The program will run for approximately 30-40 seconds, displaying real-time monitoring data.

## Troubleshooting

### Common Issues

#### 1. Compiler Not Found

**Linux:**
```bash
# Install GCC
sudo apt-get install build-essential
```

**macOS:**
```bash
xcode-select --install
```

**Windows:**
Install Visual Studio with C++ support

#### 2. CMake Not Found

**Linux:**
```bash
sudo apt-get install cmake
```

**macOS:**
```bash
brew install cmake
```

**Windows:**
Download from [cmake.org](https://cmake.org/download/)

#### 3. C++17 Not Supported

Update your compiler:
- **GCC**: Upgrade to 7.0+
- **Clang**: Upgrade to 5.0+
- **MSVC**: Use Visual Studio 2017+

#### 4. Threading Errors

Make sure pthread library is linked:
```bash
g++ -std=c++17 -O3 -pthread main.cpp -o smart_memory_manager
```

#### 5. Permission Denied (Linux/macOS)

```bash
chmod +x smart_memory_manager
./smart_memory_manager
```

#### 6. Missing Dependencies

**Ubuntu/Debian:**
```bash
sudo apt-get install -y build-essential cmake libpthread-stubs0-dev
```

**Fedora/RHEL:**
```bash
sudo dnf install -y gcc-c++ cmake glibc-devel
```

### Build Configuration Options

#### Debug Build

```bash
mkdir build-debug && cd build-debug
cmake -DCMAKE_BUILD_TYPE=Debug ..
make
```

#### Release Build (Default)

```bash
mkdir build-release && cd build-release
cmake -DCMAKE_BUILD_TYPE=Release ..
make
```

#### Custom Compiler

```bash
# Use specific compiler
cmake -DCMAKE_CXX_COMPILER=g++-10 ..

# Or
cmake -DCMAKE_CXX_COMPILER=clang++ ..
```

## Performance Optimization

For maximum performance:

```bash
# Enable native CPU optimizations
g++ -std=c++17 -O3 -march=native -pthread main.cpp -o smart_memory_manager

# Or with CMake
cmake -DCMAKE_BUILD_TYPE=Release -DCMAKE_CXX_FLAGS="-march=native" ..
```

## Getting Help

If you encounter issues:

1. Check [GitHub Issues](https://github.com/your-username/smart-memory-manager/issues)
2. Read [CONTRIBUTING.md](CONTRIBUTING.md)
3. Contact: [@MiguelM_dev0](https://twitter.com/MiguelM_dev0)

## Next Steps

After successful installation:

1. Read the [README.md](README.md) for usage examples
2. Explore the code in `main.cpp`
3. Try modifying parameters
4. Consider contributing (see [CONTRIBUTING.md](CONTRIBUTING.md))
