# Photino.Blazor
NOTE: Photino.Blazor has been updated by the community and now requires .NET 6.
## Audience
This document is for .NET developers who would like to understand or contribute to the Photino.Blazor and <span>Photino.</span>NET projects. It is a reference implementation of the Photino.Native project for the .NET development platform using Blazor.

## Overview
Photino.Blazor builds on <span>Photino.</span>NET by using the <span>Photino.</span>NET NuGet package. Its purpose is to make it easy for .NET developers to create .NET 6 and later desktop applications using a Blazor web UI that can work cross-platform on Windows, Linux and Mac instead of building OS specific UIs with technologies like Windows Forms, Windows Presentation Foundation (WPF), Xcode, Swift, or GTK. It simply adds Blazor capabilities to the .NET package.

If non-Blazor .NET web UIs are desired, please see the <span>Photino.</span>NET documentation.

The Visual Studio solution source code can be found in the [GitHub repository]( https://github.com/tryphotino/photino.Blazor )

## How it Works
Photino.Blazor is not Server-Side Blazor, nor is it WASM Client-Side Blazor. When the .NET (console) application starts, it uses the full .NET 6 framework. The framework can be pre-installed on the machine or it can come packaged with the application in the case of a "single file application." Execution of all .NET code in Blazor is redirected to the same framework as the console app.

Both the console application process and the process for the native windows and browser control utilize the same framework. This is accomplished by including some of the Blazor source code in the photnio.Blazor project and modifying it for this purpose.

## Usage Instructions 
If you just want to use the Photino.Blazor component, download or install the [NuGet package]( https://www.nuget.org/packages/Photino.Blazor/ ). If you only want to build and run Photino.Net-based projects, we recommend you install the Project Templates for Visual Studio and/or for dotnet CLI & VS Code as described [here]( ../00a-QuickStart.md )

## Building
The GitHub repository includes .yml files for automated CI/CD builds, packaging and deployments via Azure DevOps Pipelines. Please refer to these files for the latest information on dependencies and build commands.

Use standard Visual Studio build procedures for Visual Studio. If you're using the dotnet CLI (with or without VS CODE), use the standard `dotnet restore`, `dotnet build`, and `dotnet run` commands. 
