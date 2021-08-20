# Photino.NET
## Audience
This document is for .NET developers who would like to understand or contribute to the <span>Photino.</span>NET project. It is a reference implementation of the Photino.Native project for the .NET development platform.

## Overview
<span>Photino.</span>NET is a wrapper around the Photino.Native C++ control using the Photino.Native NuGet package. It's purpose is to make it easy for .NET developers to create .NET 5 and later desktop applications using a web (HTML5/CSS/JavaScript) UI that can work cross-platform on Windows, Linux and Mac instead of building OS-specific UIs with technologies like Windows Forms, Windows Presentation Foundation (WPF), Xcode, Swift, or GTK.

If Blazor UIs are desired, please see the Photino.Blazor documentation which builds on <span>Photino.</span>NET.<br>
NOTE: Photino.Blazor is no longer being maintained by this group. We envision it be superceded by .NET 6 and MAUI (Xamarin Forms vNext).

The Visual Studio solution source code can be found in the [GitHub repository]( https://github.com/tryphotino/photino.NET ) and you can download a .zip file from there.

## Usage Instructions 
If you just want to use the <span>Photino.</span>NET component, download or install the [NuGet package]( https://www.nuget.org/packages/Photino.NET/ ). If you only want to build and run Photino.Net-based projects, we recommend you install the Project Templates for Visual Studio and/or for dotnet CLI & VS Code as described [here]( ../00a-QuickStart.md )

## Building
The GitHub repository includes .yml files for automated CI/CD builds, packaging and deployments via Azure DevOps Pipelines. Please refer to these files for the latest information on dependencies and build commands.

Use standard Visual Studio build procedures for Visual Studio. If you're using the dotnet CLI (with or without VS CODE), use the standard `dotnet restore`, `dotnet build`, and `dotnet run` commands. 
