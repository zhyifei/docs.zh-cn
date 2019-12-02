---
title: 运行时配置
description: 了解如何使用运行时配置设置来配置 .NET Core 应用程序。
ms.date: 11/13/2019
ms.openlocfilehash: e3922f6df81198b5e122f16d5cfc4b6d15cbb4ae
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2019
ms.locfileid: "74567388"
---
# <a name="net-core-run-time-configuration-settings"></a>.NET Core 运行时配置设置

.NET Core 支持使用配置文件和环境变量在运行时配置 .NET Core 应用程序的行为。 如果出现以下情况，则运行时配置是一个不错的选择：

- 你不拥有或控制应用程序的源代码，因此无法以编程方式对其进行配置。

- 应用程序的多个实例在单个系统上同时运行，并且你想要将每个实例配置为获得最佳性能。

> [!NOTE]
> 本文档正在编写中。 如果你注意到此处提供的信息不完整或不准确，可以[创建一个问题](https://github.com/dotnet/docs/issues)告知我们，或[提交拉取请求](https://github.com/dotnet/docs/pulls)以解决问题。 要了解如何为 dotnet/docs 存储库提交拉取请求，请参阅[参与者指南](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md)。

.NET Core 提供了以下用于在运行时配置应用程序的机制：

- [runtimeconfig.json 文件](#runtimeconfigjson)

- [环境变量](#environment-variables)

文档此部分的文章根据类别组织，例如调试和垃圾回收。 可用的配置选项针对 runtimeconfig.json（仅限 .NET Core）、app.config（仅限 .NET Framework）和环境变量显示   。

## <a name="runtimeconfigjson"></a>runtimeconfig.json

在 runtimeconfig.json 文件的 configProperties 部分指定运行时配置选项   。 此部分包含窗体：

```json
{
   "runtimeOptions": {
      "configProperties": {
         "config-property-name1": "config-value1",
         "config-property-name2": "config-value2"
      }
   }
}
```

下面是示例文件：

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Concurrent": true,
         "System.GC.RetainVM": true,
         "System.Threading.ThreadPool.MinThreads": "4",
         "System.Threading.ThreadPool.MaxThreads": "25"
      }
   }
}
```

runtimeconfig.json  文件在生成目录中由 [dotnet build](../tools/dotnet-build.md) 命令自动创建。 在 Visual Studio 中选择“生成”菜单选项时，也会创建此文件  。 然后，可以在创建文件后对其进行编辑。

某些配置值还可以通过调用 <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> 方法以编程方式进行设置。

## <a name="environment-variables"></a>环境变量

环境变量可用于提供一些运行时配置信息。 指定为环境变量的配置旋钮通常有 COMPlus_ 前缀  。

可以使用 Windows 控制面板、命令行或通过在 Windows 和 Unix 系统上调用 <xref:System.Environment.SetEnvironmentVariable(System.String,System.String)?displayProperty=nameWithType> 方法以编程方式定义环境变量。

下面的示例演示如何在命令行中设置环境变量：

```shell
# Windows
set COMPlus_GCRetainVM=1

# Powershell
$env:COMPlus_GCRetainVM="1"

# Unix
export COMPlus_GCRetainVM=1
```
