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
# <a name="net-core-run-time-configuration-settings"></a><span data-ttu-id="8a091-103">.NET Core 运行时配置设置</span><span class="sxs-lookup"><span data-stu-id="8a091-103">.NET Core run-time configuration settings</span></span>

<span data-ttu-id="8a091-104">.NET Core 支持使用配置文件和环境变量在运行时配置 .NET Core 应用程序的行为。</span><span class="sxs-lookup"><span data-stu-id="8a091-104">.NET Core supports the use of configuration files and environment variables to configure the behavior of .NET Core applications at run time.</span></span> <span data-ttu-id="8a091-105">如果出现以下情况，则运行时配置是一个不错的选择：</span><span class="sxs-lookup"><span data-stu-id="8a091-105">Run-time configuration is an attractive option if:</span></span>

- <span data-ttu-id="8a091-106">你不拥有或控制应用程序的源代码，因此无法以编程方式对其进行配置。</span><span class="sxs-lookup"><span data-stu-id="8a091-106">You don't own or control the source code for an application and therefore are unable to configure it programmatically.</span></span>

- <span data-ttu-id="8a091-107">应用程序的多个实例在单个系统上同时运行，并且你想要将每个实例配置为获得最佳性能。</span><span class="sxs-lookup"><span data-stu-id="8a091-107">Multiple instances of your application run at the same time on a single system, and you want to configure each for optimum performance.</span></span>

> [!NOTE]
> <span data-ttu-id="8a091-108">本文档正在编写中。</span><span class="sxs-lookup"><span data-stu-id="8a091-108">This documentation is a work in progress.</span></span> <span data-ttu-id="8a091-109">如果你注意到此处提供的信息不完整或不准确，可以[创建一个问题](https://github.com/dotnet/docs/issues)告知我们，或[提交拉取请求](https://github.com/dotnet/docs/pulls)以解决问题。</span><span class="sxs-lookup"><span data-stu-id="8a091-109">If you notice that the information presented here is either incomplete or inaccurate, either [open an issue](https://github.com/dotnet/docs/issues) to let us know about it, or [submit a pull request](https://github.com/dotnet/docs/pulls) to address the issue.</span></span> <span data-ttu-id="8a091-110">要了解如何为 dotnet/docs 存储库提交拉取请求，请参阅[参与者指南](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md)。</span><span class="sxs-lookup"><span data-stu-id="8a091-110">For information on submitting pull requests for the dotnet/docs repository, see the [contributor's guide](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md).</span></span>

<span data-ttu-id="8a091-111">.NET Core 提供了以下用于在运行时配置应用程序的机制：</span><span class="sxs-lookup"><span data-stu-id="8a091-111">.NET Core provides the following mechanisms for configuring applications at run time:</span></span>

- <span data-ttu-id="8a091-112">[runtimeconfig.json 文件](#runtimeconfigjson)</span><span class="sxs-lookup"><span data-stu-id="8a091-112">The [runtimeconfig.json file](#runtimeconfigjson)</span></span>

- [<span data-ttu-id="8a091-113">环境变量</span><span class="sxs-lookup"><span data-stu-id="8a091-113">Environment variables</span></span>](#environment-variables)

<span data-ttu-id="8a091-114">文档此部分的文章根据类别组织，例如调试和垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="8a091-114">The articles in this section of the documentation include are organized by category, for example, debugging and garbage collection.</span></span> <span data-ttu-id="8a091-115">可用的配置选项针对 runtimeconfig.json（仅限 .NET Core）、app.config（仅限 .NET Framework）和环境变量显示   。</span><span class="sxs-lookup"><span data-stu-id="8a091-115">Available configuration options are shown for *runtimeconfig.json* (.NET Core only), *app.config* (.NET Framework only), and environment variables.</span></span>

## <a name="runtimeconfigjson"></a><span data-ttu-id="8a091-116">runtimeconfig.json</span><span class="sxs-lookup"><span data-stu-id="8a091-116">runtimeconfig.json</span></span>

<span data-ttu-id="8a091-117">在 runtimeconfig.json 文件的 configProperties 部分指定运行时配置选项   。</span><span class="sxs-lookup"><span data-stu-id="8a091-117">Specify run-time configuration options in the **configProperties** section of the *runtimeconfig.json* file.</span></span> <span data-ttu-id="8a091-118">此部分包含窗体：</span><span class="sxs-lookup"><span data-stu-id="8a091-118">This section has the form:</span></span>

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

<span data-ttu-id="8a091-119">下面是示例文件：</span><span class="sxs-lookup"><span data-stu-id="8a091-119">Here is an example file:</span></span>

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

<span data-ttu-id="8a091-120">runtimeconfig.json  文件在生成目录中由 [dotnet build](../tools/dotnet-build.md) 命令自动创建。</span><span class="sxs-lookup"><span data-stu-id="8a091-120">The *runtimeconfig.json* file is automatically created in the build directory by the [dotnet build](../tools/dotnet-build.md) command.</span></span> <span data-ttu-id="8a091-121">在 Visual Studio 中选择“生成”菜单选项时，也会创建此文件  。</span><span class="sxs-lookup"><span data-stu-id="8a091-121">It's also created when you select the **Build** menu option in Visual Studio.</span></span> <span data-ttu-id="8a091-122">然后，可以在创建文件后对其进行编辑。</span><span class="sxs-lookup"><span data-stu-id="8a091-122">You can then edit the file once it's created.</span></span>

<span data-ttu-id="8a091-123">某些配置值还可以通过调用 <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> 方法以编程方式进行设置。</span><span class="sxs-lookup"><span data-stu-id="8a091-123">Some configuration values can also be set programmatically by calling the <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> method.</span></span>

## <a name="environment-variables"></a><span data-ttu-id="8a091-124">环境变量</span><span class="sxs-lookup"><span data-stu-id="8a091-124">Environment variables</span></span>

<span data-ttu-id="8a091-125">环境变量可用于提供一些运行时配置信息。</span><span class="sxs-lookup"><span data-stu-id="8a091-125">Environment variables can be used to supply some run-time configuration information.</span></span> <span data-ttu-id="8a091-126">指定为环境变量的配置旋钮通常有 COMPlus_ 前缀  。</span><span class="sxs-lookup"><span data-stu-id="8a091-126">Configuration knobs specified as environment variables generally have the prefix **COMPlus_**.</span></span>

<span data-ttu-id="8a091-127">可以使用 Windows 控制面板、命令行或通过在 Windows 和 Unix 系统上调用 <xref:System.Environment.SetEnvironmentVariable(System.String,System.String)?displayProperty=nameWithType> 方法以编程方式定义环境变量。</span><span class="sxs-lookup"><span data-stu-id="8a091-127">You can define environment variables from the Windows Control Panel, at the command line, or programmatically by calling the <xref:System.Environment.SetEnvironmentVariable(System.String,System.String)?displayProperty=nameWithType> method on both Windows and Unix-based systems.</span></span>

<span data-ttu-id="8a091-128">下面的示例演示如何在命令行中设置环境变量：</span><span class="sxs-lookup"><span data-stu-id="8a091-128">The following examples show how to set an environment variable at the command line:</span></span>

```shell
# Windows
set COMPlus_GCRetainVM=1

# Powershell
$env:COMPlus_GCRetainVM="1"

# Unix
export COMPlus_GCRetainVM=1
```
