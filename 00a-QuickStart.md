## Quick Start for .NET Developers
<span>Photino.</span>NET and Photino.Blazor are available as NuGet packages for .NET developers. However, we recommend installing the Photino Project Templates and using those as a starting point for learning as well as for developing new projects. 

## Dependencies
The only dependency on all operating systems is the .NET SDK.

On Linux this cannot be installed through the Snap package manager and must be installed using the <a href="https://docs.microsoft.com/en-us/dotnet/core/install/linux-scripted-manual#scripted-install" target="_blank">scripted install method described here</a>.

On Windows 10, the Edge Dev Channel version needs to be installed from <a href="https://www.microsoftedgeinsider.com/en-us/download" target="_blank">Microsoft Edge Insider</a>.


### Visual Studio Users
Visual Studio users should install the [Visual Studio Photino Project Templates Extension]( https://marketplace.visualstudio.com/items?itemName=TryPhotino.PhotinoSamplesVSExtension ) and search for Photino in the New Project dialog.

 ### dotnet CLI Users
dotnet CLI and Visual Studio Code users should install the [Photino for .NET CLI and VS Code Project Templates NuGet Package]( https://www.nuget.org/packages/TryPhotino.VSCode.Project.Templates/ ). 

```
# Install .NET templates
$ dotnet new -i TryPhotino.VSCode.Project.Templates

# See a list of available templates
$ dotnet new -l

# Navigate to the folder in which to create a new sub-folder for the new project
$ cd MyProjects

# Create a new sample app from the Photino.HelloPhotino.NET template
# A folder will be created to match your -o parameter
$ dotnet new photinoapp -o MyPhotinoApp

# Navigate into the new folder you just created
$ cd MyPhotinoApp

# Run the application
$ dotnet run
```
### Sample Project Templates
The following templates are available and new samples are being added:
* **photinoapp** - basic .NET 5 sample
* **photinotestbench** - test every available setting and option 
* **photinoangular** - basic sample with Angular framework
* **photinoreact** - basic sample with React.js framework
* **photinovue** - basic sample with Vue.js framework
* **photino3d** - uses 3.js library to render 3d graphics
* **photino3dreact** - uses 3.js library to render 3d graphics in the React.js framework
* **photinogrpc** - make gRPC calls from UI to application (single project)
* **photinomultiwindow** - create multiple child windows from parent window
