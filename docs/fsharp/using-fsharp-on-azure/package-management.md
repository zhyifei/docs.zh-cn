---
title: "使用 Azure 使用 F # 包管理"
description: "使用 Paket 或 Nuget 来管理 F # Azure 依赖关系"
keywords: "visual f #、 f # 中，函数编程，.NET，.NET 核心，Azure"
author: sylvanc
ms.author: phcart
ms.date: 09/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: dd32ef9c-5416-467e-9fa3-c9ee3bb08456
ms.openlocfilehash: 22dc94ea69e0dfb95e22da4bc64ce915398190d2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="package-management-for-f-azure-dependencies"></a>F# Azure 依赖项的包管理

当你使用的程序包管理器时，很容易获取进行 Azure 开发的包。 有两个选项[Paket](https://fsprojects.github.io/Paket/)和[NuGet](https://www.nuget.org/)。

## <a name="using-paket"></a>使用 Paket

如果你使用[Paket](https://fsprojects.github.io/Paket/)作为依赖项管理器中，你可以使用`paket.exe`工具，用于添加 Azure 依赖关系。 例如: 

    > paket add nuget WindowsAzure.Storage

或者，如果你使用[Mono](http://www.mono-project.com/)用于跨平台.NET 开发：

    > mono paket.exe add nuget WindowsAzure.Storage

这将添加`WindowsAzure.Storage`到当前目录中的项目的包依赖项集，修改`paket.dependencies`文件中，并下载包。 如果在以前设置了依赖项，或正在使用项目其中依赖项已经设置了由另一个开发人员，你可以解决并安装本地如下的依赖项：

    > paket install

或者，对于 Mono 开发：

    > mono paket.exe install

你可以像这样的最新版本更新所有包依赖项：

    > paket update

或者，对于 Mono 开发：

    > mono paket.exe update

## <a name="using-nuget"></a>使用 Nuget

如果你使用[NuGet](https://www.nuget.org/)作为依赖项管理器中，你可以使用`nuget.exe`工具，用于添加 Azure 依赖关系。 例如: 

    > nuget install WindowsAzure.Storage -ExcludeVersion

或者，对于 Mono 开发：

    > mono nuget.exe install WindowsAzure.Storage -ExcludeVersion

这将添加`WindowsAzure.Storage`到包中的当前目录，并下载包的项目的依赖项集。 如果在以前设置了依赖项，或正在使用项目其中依赖项已经设置了由另一个开发人员，你可以解决并安装本地如下的依赖项：

    > nuget restore 

或者，对于 Mono 开发：

    > mono nuget.exe restore

你可以像这样的最新版本更新所有包依赖项：

    > nuget update

或者，对于 Mono 开发：

    > mono nuget.exe update

## <a name="referencing-assemblies"></a>引用程序集

若要在 F # 脚本中使用的包，则需要引用中使用的包附带的程序集`#r`指令。 例如: 

    > #r "packages/WindowsAzure.Storage/lib/net40/Microsoft.WindowsAzure.Storage.dll"

如你所见，你将需要指定的 DLL，并可能不完全相同的包名称的完整 DLL 名称的相对路径。 路径将包括的 framework 版本和可能的包版本号。 若要查找所有已安装的程序集，可以在 Windows 命令行上使用类似如下内容：

    > cd packages/WindowsAzure.Storage
    > dir /s/b *.dll

或在 Unix shell，如下图所示：

    > find packages/WindowsAzure.Storage -name "*.dll"

这将为您路径到已安装的程序集。 在这里，你可以为 framework 版本选择正确的路径。
