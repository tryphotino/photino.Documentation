# Photino vs. Electron

*This documentation compares the architecture, distribution, and capabilities of Electron and Photino. Photino is a lightweight alternative to Electron for building cross-platform desktop applications using web technologies.*

[Electron Documentation](https://electronjs.org/docs) | [Photino Documentation](https://www.tryphotino.io/)

## Browser Control Used in Native Window
**Electron** calls this the Renderer process and uses Chromium in a native window. A full version of Chromium is bundled and downloaded with each application, ensuring consistent rendering across platforms but increasing file size.

**Photino** uses the "OS-Native" web control already present on the user's machine, significantly reducing the installer size: 
* **Windows** - Chromium-based Edge [WebView2](https://docs.microsoft.com/en-us/microsoft-edge/webview2/) 
* **Linux** - [WebKitGTK+2](https://webkitgtk.org/) 
* **Mac** - [WKWebView](https://developer.apple.com/documentation/webkit/wkwebview)

## Host Application
**Electron** calls this the Main process and uses [Node.js](https://nodejs.org/en/) which is bundled with each app. All backend logic is written in JavaScript/TypeScript.

**Photino.Native** is a C++ wrapper that can be utilized by various backends (C++, Rust, Go, etc.).

**Photino.NET** uses [.NET 5, 6, 7, or 8+](https://dotnet.microsoft.com/). This allows developers to use C# and the full power of the .NET ecosystem for the backend.

## Host Application / Browser Control Communication
**Electron** uses custom inter-process communication (IPC). The `ipcMain` and `ipcRenderer` modules use "channels" (strings) to send messages. Because both sides are JavaScript, objects can be serialized and marshalled between processes relatively easily.

**Photino.NET** uses high-performance memory streams to communicate with the Photino.Native process. It uses a message-passing interface where JSON payloads are sent between the .NET backend and the frontend. 

In addition, it's common for **Photino.NET** projects to host local REST services or WebSockets within the .NET process, which can be called from the browser control using standard `fetch` or `XMLHttpRequest` calls.

## Distribution
### Tools
**Electron** uses `electron-forge`, `electron-builder`, or `electron-packager` to bundle the Chromium runtime, Node.js, and app code into an executable.

**Photino** uses standard .NET distribution methods. Applications can be published as "Self-Contained" (includes the .NET runtime) or "Framework-Dependent." Because it doesn't bundle a browser, a Photino executable is typically < 1MB, whereas Electron apps start at ~80MB+.

## OS Integration
### Notifications
**Electron** supports a JavaScript notification API for the Renderer process and a `Notification` module for the Main process for native OS toasts.
**Photino** can trigger native notifications using standard .NET libraries or OS-specific APIs accessible via C#.

### Recent Documents (Windows, Mac)
**Electron** supports the recent document functionality built into Windows and Mac via the `app.addRecentDocument` API.

### Taskbar Progress (Windows, Mac, Unity)
**Electron** supports taskbar/dock icon progress indicators.
**Photino** allows for taskbar customization through the underlying .NET implementation of Windows Forms or via native interop (P/Invoke).

### Project Templates
**Electron** supports BoilerPlate-CLI and various community-driven starters (React, Vue, etc.).
**Photino.NET** supports official project templates available in Visual Studio, as well as the `dotnet new` CLI (e.g., `dotnet new photinoapp`).

### Native Node Modules (native to OS)
**Electron** modules must be built specifically for the Electron version's internal V8 header files.
**Photino** uses standard NuGet packages. Any C# library or native DLL can be used without special compilation for Photino.

## Performance
**Electron** has a higher memory overhead because it runs a dedicated instance of Chromium for every window and a Node.js runtime. 

**Photino** is significantly more lightweight in terms of RAM and Disk Space. By sharing the OS's existing web engine, the memory footprint is often 70-90% smaller than a comparable Electron app.

## Debugging
**Electron** provides built-in access to Chromium DevTools for the renderer and Node.js inspectors for the main process.

**Photino** allows developers to right-click in the window to open the native platform's DevTools (Edge DevTools on Windows, Safari Inspector on Mac). .NET code is debugged using Visual Studio, VS Code, or JetBrains Rider.

## Shell Access
**Electron** supports the `shell` module to open files or URLs in default external applications.
**Photino.NET** supports anything you can do in .NET, including `System.Diagnostics.Process` for shelling out to the operating system or opening files.

## Custom Window Title Bar
Both **Electron** and **Photino** support "frameless" windows, allowing developers to hide the native title bar and create a custom UI in HTML/CSS to handle window dragging, minimizing, and closing.
