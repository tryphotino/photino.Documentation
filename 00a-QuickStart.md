## Quick Start for .NET Developers
<span>Photino.</span>NET and Photino.Blazor are available as NuGet packages for .NET developers. However, we recommend installing the Photino Project Templates and using those as a starting point for learning as well as for developing new projects. 

### Visual Studio Users
Visual Studio users should install the [Visual Studio Photino Project Templates Extension]( https://marketplace.visualstudio.com/items?itemName=TryPhotino.PhotinoSamplesVSExtension ) and search for Photino in the New Project dialog.

 ### dotnet CLI Users
dotnet CLI and Visual Studio Code users should install the [Photino for .NET CLI and VS Code Project Templates NuGet Package]( https://www.nuget.org/packages/TryPhotino.VSCode.Project.Templates/ ). Use `dotnet new --install TryPhotino.VSCode.Project.Templates` to install the templates, `dotnet new -l` to list installed templates, ` dotnet new photinoxxxxxx` to create new projects from the templates, and `dotnet run` to run the samples.

### Sample Projects
The following templates are available and new samples are being added:
* **photinoapp** - basic .NET 5 sample
* **photinoangular** - basic sample with Angular UI
* **photinoreact** - basic sample with React.js UI
* **photinovue** - basic sample with Vue.js UI
* **photino3d** - uses 3.js library to render 3d graphics
* **photinoappwithapi** - make WebAPI calls from UI to application (separate WebAPI project)
* **photinogrpc** - make gRPC calls from UI to application (single project)
* **photinoadvanced** - OS interactions, powershell commands and system dialogs
* **photinoblazor** - Blazor UI
