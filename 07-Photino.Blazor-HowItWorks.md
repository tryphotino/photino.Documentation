# Photino.Blazor - How it Works

Photino.Blazor is not Server-Side Blazor, nor is it WASM Client-Side Blazor. When the .NET (console) application starts, it uses the full .NET 5 framework. The framework can be pre-installed on the machine or it can come packaged with the application in the case of a "single file application". Execution of all .NET code in Blazor is redirected to the same framework as the console app.

Both the console application process and the process for the native windows and browser control utilize the same framework. This is accomplished by including some of the Blazor source code in the photnio.Blazor project and modifying it for this purpose.