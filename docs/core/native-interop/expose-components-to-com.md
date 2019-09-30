---
title: 向 COM 公开 .NET Core 组件
ms.date: 07/12/2019
helpviewer_keywords:
- exposing .NET Core components to COM
- interoperation with unmanaged code, exposing .NET Core components
- COM interop, exposing COM components
ms.assetid: 21271167-fe7f-46ba-a81f-a6812ea649d4
author: jkoritzinsky
ms.author: jekoritz
ms.openlocfilehash: 8f9624414a2b423bd43e8790d11b70ae1ca6286d
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216223"
---
# <a name="exposing-net-core-components-to-com"></a>向 COM 公开 .NET Core 组件

在 .NET Core 中，与 .NET Framework 相比，向 COM 公开 .NET 对象的过程已明显简化。 下面的过程将引导你如何向 COM 公开类。 本教程介绍了如何：

- 从 .NET Core 向 COM 公开类。
- 生成 COM 服务器作为构建 .NET Core 库的一部分。
- 自动为无注册表 COM 生成并行服务器清单。

## <a name="prerequisites"></a>系统必备

- 安装 [.NET Core 3.0 SDK](https://dotnet.microsoft.com/download) 或更高版本。

## <a name="create-the-library"></a>创建库

第一步是创建库。

1. 创建新文件夹，并在该文件夹中运行以下命令：
    
    ```dotnetcli
    dotnet new classlib
    ```

2. 打开 `Class1.cs`。
3. 将 `using System.Runtime.InteropServices;` 添加到文件顶部。
4. 创建名为 `IServer` 的接口。 例如:

   [!code-csharp[The IServer interface](~/samples/core/extensions/COMServerDemo/COMContract/IServer.cs)]

5. 将 `[Guid("<IID>")]` 属性添加到接口，包含要实现的 COM 接口的接口 GUID。 例如 `[Guid("fe103d6e-e71b-414c-80bf-982f18f6c1c7")]`。 请注意，此 GUID 必须唯一，因为它是 COM 的此接口的唯一标识符。 在 Visual Studio 中，可通过转到“工具”>“创建 GUID”以打开“创建 GUID”工具来生成 GUID。
6. 将 `[InterfaceType]` 属性添加到接口，并指定接口应实现的基本 COM 接口。
7. 创建用于实现 `IServer` 的名为 `Server` 的类。
8. 将 `[Guid("<CLSID>")]` 属性添加到类，包含要实现的 COM 类的类标识符 GUID。 例如 `[Guid("9f35b6f5-2c05-4e7f-93aa-ee087f6e7ab6")]`。 与接口 GUID 一样，此 GUID 必须唯一，因为它是 COM 的此接口的唯一标识符。
9. 将 `[ComVisible(true)]` 属性添加到接口和类。

> [!IMPORTANT]
> 与 .NET Framework 不同，.NET Core 要求指定想要通过 COM 激活的任何类的 CLSID。

## <a name="generate-the-com-host"></a>生成 COM 主机

1. 打开 `.csproj` 项目文件并在 `<PropertyGroup></PropertyGroup>` 标记中添加 `<EnableComHosting>true</EnableComHosting>`。
2. 生成项目。

生成的输出将具有 `ProjectName.dll`、`ProjectName.deps.json`、`ProjectName.runtimeconfig.json` 和 `ProjectName.comhost.dll` 文件。

## <a name="register-the-com-host-for-com"></a>为 COM 注册 COM 主机

打开提升的命令提示符，然后运行 `regsvr32 ProjectName.comhost.dll`。 这将使用 COM 注册所有公开的 .NET 对象。

## <a name="enabling-regfree-com"></a>启用 RegFree COM

1. 打开 `.csproj` 项目文件并在 `<PropertyGroup></PropertyGroup>` 标记中添加 `<EnableRegFreeCom>true</EnableRegFreeCom>`。
2. 生成项目。

生成的输出现在还将具有 `ProjectName.X.manifest` 文件。 此文件是用于无注册表的 COM 的并行清单。

## <a name="sample"></a>示例

GitHub 上的 dotnet/samples 存储库中有一个正常运行的 [COM 服务器示例](https://github.com/dotnet/samples/tree/master/core/extensions/COMServerDemo)。

## <a name="additional-notes"></a>附加说明

与 .NET Framework 不同，.NET Core 不支持从 .NET Core 程序集生成 COM 类型库 (TLB)。 对于接口的本机声明，必须手动编写 IDL 文件或 C++ 标头。

此外，不支持将 .NET Framework 和 .NET Core 加载到同一进程中，因此，不支持将 .NET Core COM 服务器加载到 .NET Framework COM 客户端进程，反之亦然。
