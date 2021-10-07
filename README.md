# .NET 6 Preview - Sdk NuGet packages broken for WPF projects

[https://github.com/dotnet/wpf/issues/5463](https://github.com/dotnet/wpf/issues/5463)

## Issue Description

I have created a custom SDK. This SDK imports Microsoft.NET.Sdk to use its functionality and also extends the build with new functionality of its own. Whereas most projects build fine using the custom SDK, this is broken for WPF projects as of the .NET 6 preview (this worked in .NET 5). The error is as follows:

```
D:\GIT\sdk-test\WpfApp\WpfApp_z0ggbjqk_wpftmp.csproj(9,31): error MSB4236: The SDK 'MyCustomSdk/1.0.0' specified could not be found.
```

## Steps to Reproduce

Consume a custom SDK as a NuGet package instead of Microsoft.NET.Sdk in a WPF project. The custom SDK should import Microsoft.NET.Sdk. This repo is an example, to try, simply run the build script:

```powershell
.\build.ps1
```

## versions & Configurations

* MSBuild version: 17.0.0-preview-21460-01+8f208e609
* dotnet version: 6.0.100-rc.1.21463.6
* Windows 10 version: 1909