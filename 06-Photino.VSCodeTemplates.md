# Photino.VSExtension

## Audience
This document is for .NET developers using the dotnet CLI (with or without VS Code) who would like to get started building Photino projects in .NET and for those who would like to contribute to the Visual Studio Project Templates created from the Samples.

## Overview
The VS Code Templates project installs project templates for creating the Photino.NET and Photino.Blazor sample projects from the dotnet CLI (with or without VS Code).

Photino project templates create bare-bones sample applications for various Photino project flavors such as .NET (plain HTML), Angular, React, Vue, etc. Installing the project templates for Visual Studio 2019, the dotnet CLI and/or VS Code is the easiest way to get up and running creating Photino apps for .NET 5 (or later).

The Visual Studio solution source code can be found in the [GitHub repository]( https://github.com/tryphotino/PhotinoSamples.VSCodeTemplates ) and you can download a .zip file containing the samples there.

## Usage Instructions 
If you just want to use the project templates (not become a contributor), we recommend installing the project templates by using the dotnet CLI to install the templates NuGet package:
* Type `dotnet new install TryPhotino.VSCode.Project.Templates` (the NuGet package name) to install the templates.
* Type `dotnet new photinoangular` (or other sample short name) to create a new project using that template.
* Type `dotnet new -l` or `dotnet new -u` to list all installed project templates.
* Type `dotnet new -u TryPhotino.VSCode.Project.Templates` to uninstall the templates.

 The [NuGet Package]( https://www.nuget.org/packages/TryPhotino.VSCode.Project.Templates/ ).

## Building
Create/Test a Single Project Template
1.	Open a command prompt in the `<...>\PhotinoSamples.VSCodeTemplates\working\templates` folder [GitHub]( https://github.com/tryphotino/PhotinoSamples.VSCodeTemplates ).
2.	Copy the latest versions of the source code for the projects in the Photino.PhotinoSamples solution into the matching folders in PhotinoSamples.VSCodeTemplates\working\templates [GitHub]( https://github.com/tryphotino/photino.Samples ).
3.	Type `dotnet run` at the prompt to ensure each project builds and runs correctly.
4.	Verify the contents of the template.json files in the .template.config sub folders for each project.
5.	Delete any files and folders that should not be part of the template, like `./bin`, `./obj` and `.gitignore`. Warning: DO NOT delete the .template.config folders!
6.	From each project folder type `dotnet new -i ./` to install the template on your machine.
7.	Navigate to the `<...>\PhotinoSamples.VSCodeTemplates\test` folder and delete all contents. If there is no *\test* folder, create one.
8.	Type `dotnet new photinoangular` (or other sample, this is the shortName from the template.json file for each project) to test each template.
9.	Type `dotnet run` to test that the project is created correctly.
10.	Delete the contents of the test folder after testing each template.
11.	Type `dotnet new -u <...>\PhotinoSamples.VSCodeTemplates\working\templates\<project>` to uninstall each template.

Pack All Project Templates

1.	Ensure all individual templates are up to date and work correctly (per single template above).
2.	Open VS Code (or another editor) to the `<...>\PhotinoSamples.VSCodeTemplates\working` folder.
3.	Edit the templatepack.csproj file to set version number for the NuGet package.
4.	From a terminal window or shell prompt, type `dotnet pack -p:TargetFrameworks=net5.0` to create the NuGet package.
5.	Note that you will likely see warnings. This is normal.
6.	Assuming you have *NuGet Package Explorer* installed from the Microsoft Store (or some other package explorer utility), double-click on the NuGet package to inspect, update, and verify it.
7.  Fill in any missing information by editing it in th the NuGet Package Explorer tool.

## Upload Package to NuGet
* Log into <https://nuget.org> with your Microsoft ID.
* Click the Upload link and manually upload the package update.


