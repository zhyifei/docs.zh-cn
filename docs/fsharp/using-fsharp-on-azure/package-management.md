---
title: 使用包管理与F#适用于 Azure
description: 使用 paket 依存或 Nuget 来管理F#Azure 依赖关系
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: fd9c4a15ab0741d44d6d5cf909b7219d310affb0
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "33566961"
---
# <a name="package-management-for-f-azure-dependencies"></a>F# Azure 依赖项的包管理

当使用包管理器时，获取有关 Azure 开发的包很容易。 两个选项是[paket 依存](https://fsprojects.github.io/Paket/)并[NuGet](https://www.nuget.org/)。

## <a name="using-paket"></a>使用 paket 依存

如果您使用的[paket 依存](https://fsprojects.github.io/Paket/)作为依赖项管理器中，你可以使用`paket.exe`工具，用于添加 Azure 依赖关系。 例如：

    > paket add nuget WindowsAzure.Storage

或者，如果您使用[Mono](https://www.mono-project.com/)适用于跨平台.NET 开发：

    > mono paket.exe add nuget WindowsAzure.Storage

这将添加`WindowsAzure.Storage`到当前目录中的项目的包依赖项集，修改`paket.dependencies`文件，并下载包。 如果在以前设置了依赖项，或正在使用项目的依赖项已设置由另一个开发人员，您可以解决并安装依赖项本地如下：

    > paket install

或者，对于 Mono 开发：

    > mono paket.exe install

您可以像这样的最新版本更新所有包依赖项：

    > paket update

或者，对于 Mono 开发：

    > mono paket.exe update

## <a name="using-nuget"></a>使用 Nuget

如果您使用的[NuGet](https://www.nuget.org/)作为依赖项管理器中，你可以使用`nuget.exe`工具，用于添加 Azure 依赖关系。 例如：

    > nuget install WindowsAzure.Storage -ExcludeVersion

或者，对于 Mono 开发：

    > mono nuget.exe install WindowsAzure.Storage -ExcludeVersion

这将添加`WindowsAzure.Storage`到当前目录和下载包的项目中的包依赖项集。 如果在以前设置了依赖项，或正在使用项目的依赖项已设置由另一个开发人员，您可以解决并安装依赖项本地如下：

    > nuget restore 

或者，对于 Mono 开发：

    > mono nuget.exe restore

您可以像这样的最新版本更新所有包依赖项：

    > nuget update

或者，对于 Mono 开发：

    > mono nuget.exe update

## <a name="referencing-assemblies"></a>引用程序集

若要使用中的包在F#脚本，则需要引用使用的包中包括的程序集`#r`指令。 例如：

    > #r "packages/WindowsAzure.Storage/lib/net40/Microsoft.WindowsAzure.Storage.dll"

正如您所看到的您将需要指定给 DLL 的完整的 DLL 名称，这可能无法完全与包名称相同的相对路径。 路径将包含的 framework 版本和可能是包版本号。 若要查找所有已安装的程序集，可以在 Windows 命令行上使用类似如下：

    > cd packages/WindowsAzure.Storage
    > dir /s/b *.dll

或在 Unix 外壳中，如下图所示：

    > find packages/WindowsAzure.Storage -name "*.dll"

这将提供路径到已安装的程序集。 在这里，可以为 framework 版本来选择正确的路径。
