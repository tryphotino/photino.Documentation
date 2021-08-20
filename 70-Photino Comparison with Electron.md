# Photino vs. Electron

*This documentation is in still being developed and we think these sections should be added. Feel free to contribute.*

[Electron Documentation]( https://electronjs.org/docs )

## Browser Control Used in Native Window
**Electron** calls this the Renderer process and uses Chromium in a native window. Chromium is downloaded with each app. 

**Photino** tries to use whatever is normally included in the OS: 
* Windows - Chromium Edge [WebView2]( https://docs.microsoft.com/en-us/microsoft-edge/webview2/?ranMID=24542&ranEAID=je6NUbpObpQ&ranSiteID=je6NUbpObpQ-T5b4unLww4VC4k9j9e_XIQ&epi=je6NUbpObpQ-T5b4unLww4VC4k9j9e_XIQ&irgwc=1&OCID=AID2000142_aff_7593_1243925&tduid=(ir__jmet23akugkftm1hkk0sohzibm2xpj1pijghddor00)(7593)(1243925)(je6NUbpObpQ-T5b4unLww4VC4k9j9e_XIQ)()&irclickid=_jmet23akugkftm1hkk0sohzibm2xpj1pijghddor00 ) 
* Linux - [WebKitGTK+2]( https://webkitgtk.org/ ) 
* Mac - [WKWebView]( https://developer.apple.com/documentation/webkit/wkwebview )

## Host Application
**Electron** calls this the Main process and uses [Node.js]( https://nodejs.org/en/ ) which is downloaded with each app. 

**Photino.Native** can be wrapped for any back end (C++, Rust, etc.).

**<span>Photino.</span>NET** uses [.NET 5]( https://dotnet.microsoft.com/ ).

## Host Application / Browser Control Communication
**Electron** uses custom inter-process communication (IPC). The ipcMain and ipcRenderer libraries use ‘channels’- strings that identify which listener to use on the other end. ipcRenderer – can call all Node.js APIs e.g. `const root = fs.readdirSync(‘/’)` because everything is JavaScript in **Electron** applications and JavaScript code can be marshalled between processes as strings.

**<span>Photino.</span>NET** uses memory streams to communicate with the Photino.Native process and ‘schemes’; which are outlet points in the HTML. The standard is to transfer a JSON payload which includes a unique message id, the name of the method to call, any parameters to pass and to receive a JSON payload containing the unique message id of the original call and any response data.

In addition, it's common for **<span>Photino.</span>NET** projects to host REST services which can be called from the browser control using standard JavaScript in a commonly used communication pattern.
<br>

## Distribution
### Tools
Electron uses electron-forge, or electron-builder, or electron-packager. Photino uses standard .NET distribution methods.
Manual Distribution

### Code Signing

### Mac App Store

### Windows App Store

### Snapcraft
<br>

## Automatic Updates
**Electron** maintains update.electron.js, free open-source webservice for self-updating. Developers can use the update-electron-app module package to initiate updates from the application. Alternately, deploy your own update server (3 to choose from). 

**Photino**
<br>

## OS Integration
### Notifications
**Electron** Supports a JavaScript notification API for the Renderer process and a Notification module for the main process.

### Recent Documents (Windows, Mac)
**Electron** supports the recent document functionality built into Windows and Mac.

### Taskbar Progress (Windows, Mac, Unity)
**Electron** supports icon with progress indicators on Windows, Mac & Unity.

### Mac Doc
**Electron** supports the Mac Doc.

### Windows Taskbar
**Electron** supports the Windows task bar.

### Linux Desktop Launcher

### Local and Global Keyboard Shortcuts

### Online/Offline Event Detection

### Represented File (Mac)
**Electron** supports Represented Files on Mac OS Browser Windows

### OS Native Drag & Drop

### Offscreen Rendering

### Dark Mode for OS Dialogs, etc.

### Web Embeds
**Electron** supports iFrame, WebView (deprecated), BrowserView (overlaid on top of DOM)

### Project Templates
**Electron** supports BoilerPlate-CLI and there are various tools to help users create new projects.
**<span>Photino.</span>NET** supports project templates in Visual Studio as well as the dotnet CLI

### Native Node Modules (native to OS)
Must be built specifically for Electron. 

## Performance

## Security

## Accessibility Features

## Debugging
<br>

## Native Menus
Menu | Electron (electronjs.org)  MenuItem | Electron (electronjs.org)

## Native Dialogs
dialog | Electron (electronjs.org)

## Crash Reporting
crashReporter
crashReporter | Electron (electronjs.org)

## Shell Access
**Electron** supports Shell shell | Electron (electronjs.org)
**<span>Photino.</span>NET supports anything you can do in .NET, including shelling out to the operating system.

## Custom Window Title Bar
Both **Electron** and **Photino** support hiding the native window's title bar and creating a custom title bar in HTML.
