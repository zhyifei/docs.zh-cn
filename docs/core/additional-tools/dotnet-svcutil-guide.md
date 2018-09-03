---
title: Microsoft WCF dotnet-svcutil 工具
description: Microsoft WCF dotnet-svcutil 工具概述，该工具添加了 .NET Core 和 ASP.NET Core 项目的功能，类似于 .NET Framework 项目的 WCF svcutil 工具。
author: mlacouture
ms.author: jralexander
ms.date: 08/20/2018
ms.openlocfilehash: bb4d8e5f3997318b720535b0f1e07fc33d13338a
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2018
ms.locfileid: "43484116"
---
# <a name="microsoft-wcf-dotnet-svcutil-tool"></a>Microsoft WCF dotnet-svcutil 工具

Windows Communication Foundation (WCF) dotnet-svcutil 工具是一种 .NET Core CLI 工具，此工具从网络位置上的 Web 服务中或从 WSDL 文件中检索元数据，并生成包含访问 Web 服务操作的客户端代理方法的 WCF 类。

类似于 .NET Framework 项目的[服务模型元数据 - svcutil](../../framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 工具，dotnet svcutil 是用于生成 Web 服务引用的命令行工具，与 .NET Core 和 .NET Standard 项目兼容。

dotnet-svcutil 工具是 [WCF Web 服务引用](wcf-web-service-reference-guide.md) Visual Studio 连接服务提供程序（随 Visual Studio 2017 v15.5 首次推出）的替代选项。 dotnet-svcutil 工具作为一种 .NET Core CLI 工具，可跨平台地用于 Linux、macOS 和 Windows。

> [!IMPORTANT]
> 应仅从受信任源引用服务。 从不受信任的源添加引用可能会危及安全性。

## <a name="prerequisites"></a>系统必备

* [.NET Core SDK](https://www.microsoft.com/net/download) 版本 1.0.4 或更高版本
* 你最喜欢的代码编辑器

## <a name="getting-started"></a>入门

下面的示例将指导你完成将 Web 服务引用添加到 .NET Core 控制台项目并调用该服务所需的步骤。 你将创建名为“HelloSvcutil”的 .NET Core 控制台应用程序，并将引用添加到实现以下协定的 Web 服务：

```csharp
[ServiceContract]
public interface ISayHello
{
    [OperationContract]
    string Hello(string name);
}
```

在此示例中，将假定 Web 服务托管在以下地址中：`http://contoso.com/SayHello.svc`

从 Windows、macOS 或 Linux 命令窗口执行以下步骤：

1. 为项目创建一个名为“HelloSvcutil”的目录，并将其设置为当前目录，如以下示例所示：

```console
mkdir HelloSvcutil
cd HelloSvcutil
```

2. 在该目录中使用 [`dotnet new`](../tools/dotnet-new.md) 命令创建新的 C# 控制台项目项目，如下所示：

```console
dotnet new console
```

3. 在编辑器中打开 `HelloSvcutil.csproj` 项目文件，编辑 `Project` 元素，并使用下面的代码添加 [`dotnet-svcutil` NuGet 包](https://nuget.org/packages/dotnet-svcutil)作为 CLI 工具引用：

```xml
<ItemGroup>
  <DotNetCliToolReference Include="dotnet-svcutil" Version="1.0.*" />
</ItemGroup>
```

4. 使用 [`dotnet restore`](../tools/dotnet-restore.md) 命令还原 dotnet-svcutil 包，如下所示：

```console
dotnet restore
```

5. 运行 _dotnet_ 与 _svcutil_ 命令生成 Web 服务引用文件，如下所示：

```console
dotnet svcutil http://contoso.com/SayHello.svc
```
生成的文件保存为 _HelloSvcutil/ServiceReference1/Reference.cs_。 _dotnet_svcutil_ 工具还向项目添加代理代码所需的适当 WCF 包作为包引用。

6. 使用 [`dotnet restore`](../tools/dotnet-restore.md) 命令还原 WCF 包，如下所示：

```console
dotnet restore
```

7. 在编辑器中打开 `Program.cs` 文件，编辑 `Main()` 方法，然后使用下列代码替换自动生成的代码来调用 Web 服务：

```csharp
static void Main(string[] args)
{
    var client = new SayHelloClient();
    Console.WriteLine(client.HelloAsync("dotnet-svcutil").Result);
}
```

8. 使用 [`dotnet run`](../tools/dotnet-run.md) 命令运行应用程序，如下所示：

```console
dotnet run
```
你将看到以下输出：“Hello dotnet-svcutil!”

有关 `dotnet-svcutil` 工具参数的详细说明，请调用传递帮助参数的工具，如下所示：

```console
dotnet svcutil --help
```

## <a name="next-steps"></a>后续步骤

### <a name="feedback--questions"></a>反馈和问题

如果有任何问题或反馈，请[在 GitHub 上提问](https://github.com/dotnet/wcf/issues/new)。 也可以在 [GitHub 上的 WCF 存储库](https://github.com/dotnet/wcf/issues?utf8=%E2%9C%93&q=is:issue%20label:tooling)中查看任何现有问题。

### <a name="release-notes"></a>发行说明

* 请参阅[发行说明](https://github.com/dotnet/wcf/blob/master/release-notes/dotnet-svcutil-notes.md)，了解更新的版本信息（包括已知问题）。

### <a name="information"></a>信息

* [dotnet-svcutil NuGet 包](https://nuget.org/packages/dotnet-svcutil)
