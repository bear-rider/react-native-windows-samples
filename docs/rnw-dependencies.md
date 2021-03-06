---
id: rnw-dependencies
title: System Requirements
---


# Check and install dependencies

To check or install dependencies you'll need to build RNW and RNW apps, run the script [rnw-dependencies.ps1](https://github.com/microsoft/react-native-windows/blob/master/vnext/Scripts/rnw-dependencies.ps1) in an elevated PowerShell window.
Run this command: 
- `Start-Process -Verb RunAs powershell -ArgumentList @("-command", "iex ((New-Object System.Net.WebClient).DownloadString('https://raw.githubusercontent.com/microsoft/react-native-windows/master/vnext/Scripts/rnw-dependencies.ps1'))")`


### Advanced: full details

You can run React-Native for Windows apps only on Windows 10 devices with Windows version: 10.0.16299.0 (aka 1709, aka Redstone 3, aka Fall Creators Update) or higher. Some features may not work on all versions. See [Windows 10 Compatibility](win10-compat.md) for version support details.

To develop React-Native for Windows apps, you will need the following:

## Windows Development Dependencies

- Ensure Developer Mode is turned ON in Windows Settings App.
- Install [Visual Studio 2019](https://www.visualstudio.com/downloads) with the following options:
  - Workloads
    - Universal Windows Platform development
    - Desktop development with C++
  - Individual Components
    - Development activities
      - Node.js development support (optional)

## React Native Development Dependencies

- Install the [standard React Native dependencies](https://reactnative.dev/docs/getting-started#node-python2-jdk)
- Install [Node.js](https://nodejs.org) via one of the following methods:
  - Using [Chocolatey](https://chocolatey.org/) (_React Native recommended_). To use chocolately, from an elevated Command Prompt, run:
  ```
  choco install nodejs.install --version=12.9.1
  ```
  - Directly from [NodeJs](https://nodejs.org/en/download/)
  - By selecting the "Node.js development support" component in the Visual Studio 2019 installer (above)
  > For both of the non-choco installations, ensure that you are installing version 12.9.1 as that is the recommended version when building React Native Windows apps.
  
- Install [Chrome](https://www.google.com/chrome/) (_optional_, but needed for JS debugging)
- Install [Yarn](https://yarnpkg.com/en/docs/install) (_optional_ if only consuming react-native-windows, but **required** to contribute to react-native-windows)

## Troubleshooting

- If after running the app, the packager does not update (or) app does not show React Native content - close the packager command prompt window and the app, make sure browser is open, run `yarn start` and run the app from Visual Studio again.
- If you get a red error box in your UWP app window with the error message : `ERROR: Instance failed to start. A connection with the server cannot be established`, make sure you have the packager running using `yarn start` and run the app again.
