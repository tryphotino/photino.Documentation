# Photino.Native

## Audience
This document is for C++ developers who would like to understand or contribute to the Photino.Native project and for developers who would like to build Photino wrappers for their chosen language and/or development platform. The <span>Photino.</span>NET project is a reference implementation for the .NET development platform.

## Overview
Photino.Native is a C++ wrapper around the OS's default browser control on Windows, Mac and Linux which creates a native OS window, places the browser control in it and exposes both the window and control to the host application.

The source code can be found in a Visual Studio solution in the [GitHub repository](https://github.com/tryphotino/photino.Native). It contains Microsoft C++ code for Windows, gcc C++ code for Linux, and Objective C++ code for Mac as well as code and resources shared in all three environments. 

* The Windows code uses the Chromium-based Edge control in [WebView2]( https://docs.microsoft.com/en-us/microsoft-edge/webview2/?ranMID=24542&ranEAID=je6NUbpObpQ&ranSiteID=je6NUbpObpQ-T5b4unLww4VC4k9j9e_XIQ&epi=je6NUbpObpQ-T5b4unLww4VC4k9j9e_XIQ&irgwc=1&OCID=AID2000142_aff_7593_1243925&tduid=(ir__jmet23akugkftm1hkk0sohzibm2xpj1pijghddor00)(7593)(1243925)(je6NUbpObpQ-T5b4unLww4VC4k9j9e_XIQ)()&irclickid=_jmet23akugkftm1hkk0sohzibm2xpj1pijghddor00 )
  
* The Linux code uses the WebKit-based browser control in [WebKitGTK+2]( https://webkitgtk.org/ ).

* The Mac code uses the WebKit-based browser control in [WKWebView]( https://developer.apple.com/documentation/webkit/wkwebview ).

Because these controls are often included or already installed on Windows 11 and Mac, there is often no need to download or install the controls along with the application, making Photino applications lean and performant.

## Usage Instructions
If you just want to use the Photino.Native component, download or install the [NuGet package]( https://www.nuget.org/packages/Photino.Native/ ). The required executable files for all environments are contained in the package and can be extracted using a NuGet utility or by renaming the .nupkg file to .zip and treating it as a .zip file. See [Quick Start]( ../00a-QuickStart.md ) for details.

## Building
The GitHub repository includes .yml files for automated CI/CD builds, packaging and deployments via Azure DevOps Pipelines. Please refer to these files for the latest information on dependencies and build commands.

The source code also contains a .NET Test project used for testing and troubleshooting. In order to use the Test project, the Photino.NET source code must be downloaded under the same parent folder as the Photino.Native folder (as the Test project does not contain the Photino.NET source code, but rather links to the source in this adjacent folder). If you don't care to use the Test project, there is no need to download the Photino.NET source code.

* **Windows** - Open the solution in Visual Studio 2019 or later with the **Desktop development with C++** workload installed. The **Linux development with C++** workload is recommended, but not required. You *must* build in x64 configuration (*not* AnyCPU which is the default). You *must* install either the [WebView2 runtime]( https://go.microsoft.com/fwlink/p/?LinkId=2124703 ) or the [Edge Dev Channel]( https://www.microsoftedgeinsider.com/en-us/download ). Beta and Canary should work as well, but that hasn't been verified. Just having Edge Chromium installed will not work. The project will build, but will not work properly in a development environment.
  
* **Linux** - (Tested with Ubuntu 18.04 and 20.04) Install dependencies: `sudo apt-get update && sudo apt-get install libgtk-3-dev libwebkit2gtk-4.0-dev`.  <br> To compile, run `gcc -std=c++11 -shared -DOS_LINUX Exports.cpp Photino.Linux.cpp -o x64/$(buildConfiguration)/Photino.Native.so 'pkg-config --cflags --libs gtk+-3.0 webkit2gtk-4.0' -fPIC`

* **Mac** - Install Xcode. To compile, run `gcc -shared -lstdc++ -DOS_MAC -framework Cocoa -framework WebKit Photino.Mac.mm Exports.cpp Photino.Mac.AppDelegate.mm Photino.Mac.UiDelegate.mm Photino.Mac.UrlSchemeHandler.mm -o x64/$(buildConfiguration)/Photino.Native.dylib`.

