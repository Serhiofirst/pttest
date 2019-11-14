---
ID: 226426
post_title: 'Azure IoT Tools July Update: IoT Edge tooling GA and more!'
author: Jun Han
post_excerpt: ""
layout: post
permalink: >
  https://qadevblogs.wpengine.com/visualstudio/azure-iot-dev-experience-july-update-iot-edge-tooling-ga-and-more/
published: true
post_date: 2019-08-02 08:00:19
---
Welcome to the July update of IoT Tooling! In the release, we have made a lot of features and improvements for our IoT developers! **General Availability of IoT Edge tooling** [Azure IoT Edge][1] was released in the year of 2017. With near two years’ continuous working on the Azure IoT Edge Tooling, we are happy to announce that Azure IoT Edge Tooling is now general available. Azure IoT Edge Tooling includes: 
*   [Azure IoT Edge extension for Visual Studio Code][2]
*   [Azure IoT Edge extension for Visual Studio 2019][3]
*   [Azure IoT Edge for Azure DevOps Project][4]
*   [Azure IoT Edge for Azure DevOps][5]
*   [Azure IoT Edge Jenkins plugin][6]

**ARM64 support in Azure IoT Edge extension for Visual Studio Code** With the [release of IoT Edge 1.0.8][7], Azure IoT Edge is supported on ARM64 IoT Edge devices. In the meanwhile, I’m glad to share the steps of developing and debugging ARM64 IoT Edge custom modules in VS Code. For details, you could checkout [this blog post][8] for more information. **Containerized tool chain to simplify IoT device development** In early this month, we announced the preview of a new feature enabled in [Azure IoT Tools][9] extension in VS Code to simplify the device cross-compiling tool chain acquisition effort for device developers working on embedded Linux devices (e.g. Debian, Ubuntu, Yocto Linux…) with Azure IoT by encapsulating the compilers, [device SDK][10] and essential libraries in Containers. All you need is to install or upgrade the IoT Device Workbench and get started developing within the container, just like today you are using a local environment. For details, you could checkout [this blog post][11] for more information. **Try it out** Please don’t hesitate to give it a try! We will continuously improve our IoT developer experience to empower every IoT developers on the planet to achieve more!

 [1]: https://azure.microsoft.com/services/iot-edge/
 [2]: https://marketplace.visualstudio.com/items?itemName=vsciot-vscode.azure-iot-edge
 [3]: https://marketplace.visualstudio.com/items?itemName=vsc-iot.vs16iotedgetools
 [4]: https://docs.microsoft.com/azure/iot-edge/how-to-devops-project
 [5]: https://docs.microsoft.com/en-us/azure/iot-edge/how-to-ci-cd
 [6]: https://plugins.jenkins.io/azure-iot-edge
 [7]: https://github.com/Azure/azure-iotedge/releases
 [8]: https://devblogs.microsoft.com/iotdev/develop-and-debug-arm64-iot-edge-modules-in-visual-studio-code-preview/
 [9]: https://marketplace.visualstudio.com/items?itemName=vsciot-vscode.azure-iot-tools
 [10]: https://github.com/Azure/azure-iot-sdk-c
 [11]: https://devblogs.microsoft.com/iotdev/containerized-tool-chain-to-simplify-iot-device-development/