# .NET 8 on Linux
=====================

### Summary

This document provides an in-depth guide to installing and using .NET 8 on Linux systems. It covers the basics of getting started with .NET 8, installation procedures for different Linux distributions, and advanced usage scenarios. The document also includes code examples and sources for further learning.

## Getting Started with .NET 8
=============================

### Introduction

.NET 8 is a cross-platform, open-source developer platform that allows you to build many different types of applications. It provides a unified API surface for building apps on Windows, macOS, and Linux platforms.

### Prerequisites

Before installing .NET 8, ensure your Linux distribution meets the following requirements:

*   Supported OS versions: <https://dotnet.microsoft.com/en-us/download/dotnet/8.0>
*   curl must be available on the system
*   A compatible package manager (e.g., apt-get, yum)

### Installation Steps

1.  Create a directory to use for the download location and change into that directory.
2.  Run `curl -L https://aka.ms/install-dotnet-preview -o install-dotnet-preview.sh`
3.  Run the script with `sudo bash install-dotnet-preview.sh`

### Example Code: Installing .NET 8 on Ubuntu

```bash
# Create a directory for the download location and change into it
mkdir $HOME/dotnet_install && cd $HOME/dotnet_install

# Download the installation script
curl -L https://aka.ms/install-dotnet-preview -o install-dotnet-preview.sh

# Run the script with sudo
sudo bash install-dotnet-preview.sh
```

## Using .NET 8 on Linux
=====================

### Overview of Available Distributions

The following distributions are available for Linux:

*   .NET SDK: includes tools for building and testing applications, and includes the runtime distributions that follow.
*   .NET Runtime: includes the .NET runtime and libraries, enabling running console applications.
*   ASP.NET Core Runtime: includes the .NET and ASP.NET Core runtimes, enabling running console and web applications.

### Choosing the Right Distribution

We recommend installing the .NET SDK to develop and build applications, and to install one of the runtimes packages (like ASP.NET Core) to exclusively run applications.

## Advanced Usage Scenarios
=====================

### Container Images for Linux (Alpine, Debian, and Ubuntu)

Container images are provided for Linux (Alpine, Debian, and Ubuntu). These images can be used to deploy .NET 8-based applications in containers.

### Example Code: Using Docker with .NET 8 on Ubuntu

```bash
# Pull the official .NET 8 image from Docker Hub
docker pull mcr.microsoft.com/dotnet/core/sdk:8.0

# Create a new container based on the pulled image
docker run -it --rm mcr.microsoft.com/dotnet/core/sdk:8.0 /bin/bash

# Inside the container, install .NET 8 using the script
curl -L https://aka.ms/install-dotnet-preview -o install-dotnet-preview.sh
sudo bash install-dotnet-preview.sh
```

## Troubleshooting and Common Issues
=====================================

### Installation Issues

If you encounter issues during installation, refer to the official .NET documentation for troubleshooting guides.

### Example Code: Resolving Package Manager Issues on Ubuntu

```bash
# Check if curl is available on your system
curl -L https://aka.ms/install-dotnet-preview -o install-dotnet-preview.sh || echo "curl not found"

# Run the installation script with sudo to resolve package manager issues
sudo bash install-dotnet-preview.sh
```

## Additional Resources
=====================

### Official .NET Documentation

For more information on using .NET 8 on Linux, refer to the official .NET documentation:

*   <https://dotnet.microsoft.com/en-us/download/dotnet/8.0>
*   <https://docs.microsoft.com/en-us/dotnet/core/tutorials/using-docker>

### Example Code: Running a .NET 8 Console Application on Ubuntu

```bash
# Create a new console application using the .NET CLI
dotnet new console -o hello-world

# Run the application using dotnet run
cd hello-world && dotnet run Hello World!
```

## Sources and Further Learning
=============================

### Official .NET Documentation

*   <https://dotnet.microsoft.com/en-us/download/dotnet/8.0>
*   <https://docs.microsoft.com/en-us/dotnet/core/tutorials/using-docker>

### Example Code: Running a .NET 8 Web Application on Ubuntu with ASP.NET Core Runtime

```bash
# Create a new web application using the dotnet CLI and the ASP.NET Core template
dotnet new web -o hello-web-app --template "ASP.NET Core Web App"

# Run the application using dotnet run
cd hello-web-app && dotnet run Hello World!
```

Sources:

*   <https://aka.ms/install-dotnet-preview>
*   <https://docs.microsoft.com/en-us/dotnet/core/tutorials/using-docker>