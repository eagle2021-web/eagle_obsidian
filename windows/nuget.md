### 
#### sdk
https://dotnet.microsoft.com/zh-cn/download/dotnet/thank-you/sdk-8.0.100-windows-x64-installer?journey=vs-code
https://download.visualstudio.microsoft.com/download/pr/93961dfb-d1e0-49c8-9230-abcba1ebab5a/811ed1eb63d7652325727720edda26a8/dotnet-sdk-8.0.100-win-x64.exe

https://dotnet.microsoft.com/zh-cn/download/dotnet/8.0
#### runtime
https://dotnet.microsoft.com/zh-cn/download/dotnet/thank-you/runtime-desktop-6.0.25-windows-x64-installer?cid=getdotnetcore

#### demo
https://dotnet.microsoft.com/zh-cn/learn/dotnet/hello-world-tutorial/create
#### nuget
https://www.nuget.org/downloads 下载
https://www.nuget.org/ 仓库
https://www.mono-project.com/download/stable/#download-lin 安装mono
/etc/profile 配置 
```shell
alias nuget="$HOME/nuget/nuget.exe"
```

hello.csproj
```csproj
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netstandard1.0</TargetFramework>
  </PropertyGroup>

</Project>
```

```shell
dotnet add package Newtonsoft.Json --version 13.0.3
```
