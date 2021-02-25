# Photino.VSExtension

## Audience
This document is for .NET developers using Visual Studio 2019 or later who would like to get started building Photino projects in .NET or Blazor and for those who would like to contribute to the Visual Studio Project Templates created from the Samples.

## Overview
The Visual Studio Extension intalls project templates for creating the Photino.NET and Photino.Blazor sample projects.

Photino project templates create bare-bones sample applications for various Photino project flavors such as .NET (plain html), Angular, React, Vue, and Blazor. Installing the project templates for Visual Studio 2019, the dotnet CLI and/or VS Code is the easiest way to get up and running creating Photino apps for .NET 5.

The Visual Studio solution source code can be found in the [GitHub repository]( https://github.com/tryphotino/photino.VSExtension )

## Usage Instructions 
If you just want to use the project templates (not become a contributor), we recommend installing the project templates for Visual Studio 2019 and later through the Visual Studio Manage Extensions dialog by searching on Photino or from the [Visual Studio Marketplace]( https://marketplace.visualstudio.com/items?itemName=TryPhotino.PhotinoSamplesVSExtension ).

## Building
Open the solution in Visual Studio 2019 or later with the **ASP.NET and web development**, **.NET desktop development**, and **Visual Studio extension development** workloads installed.

1.	Open the Photino.Samples solution [GitHub]( https://github.com/tryphotino/photino.Samples )
2.	Update the samples as required and ensure they build and run correctly
3.	From the Project menu, select Export Template… 
4.  Select *Project Template*
5.	For each project, enter description as: “Photino.XXX Sample application with XXX UI”
6.	Set icon and preview images if you have them

Zip files are written to:
* C:\Users\xxxx\Documents\Visual Studio 2019\Templates\ProjectTemplates
* C:\Users\xxxx\Documents\Visual Studio 2019\My Exported Templates

Project templates will now be available on your dev machine and you can copy the .zip files from the My Exported Templates folder to the ProjectTemplates folder on other machines to ‘install them’ for testing.

1.	Open the PhotinoSamples.VSExtension solution [GitHub]( https://github.com/tryphotino/PhotinoSamples.VSExtension )
2.	Copy the .zip template files created above to the PhotinoSamples project folder
3.	Add any new .zip files to the project and set the Copy to Output properties to Copy Always
4.	Open the source.extension.vsixmanifest file and edit the Metadata properties
5.	On the Assets tab, add each new .zip file as a Microsoft.VisualStudio.ProjectTemplate file
6.	Update ReleaseNotes.txt putting changes since the last version at the top
7.	Save vsix.extension.manifest changes and build the project
8.	A new Visual Studio instance will open with the templates installed for testing. You will likely see 2 copies of each template since there is already a copy in the \ProjectTemplates folder from the steps above.

## Upload VSIX Extension to Visual Studio Gallery
* Sign in to https://marketplace.visualstudio.com with tryphotino@outlook.com Microsoft ID
* Click the “Publish Extensions” link


