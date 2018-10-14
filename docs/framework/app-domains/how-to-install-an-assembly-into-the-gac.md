---
title: 将程序集安装到 GAC 中
ms.date: 09/20/2018
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- Gacutil.exe
- strong-named assemblies, global assembly cache
- global assembly cache, installing assemblies
- Global Assembly Cache tool
- windows installer, global assembly cache
ms.assetid: a7e6f091-d02c-49ba-b736-7295cb0eb743
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d365ac77fe6cd7fc4fca36705729ec12b06d6830
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2018
ms.locfileid: "46584576"
---
# <a name="how-to-install-an-assembly-into-the-global-assembly-cache"></a>如何：将程序集安装到全局程序集缓存

可通过两种方法将强名称程序集安装到全局程序集缓存 (GAC) 中。

> [!IMPORTANT]
> 仅强名称程序集可安装到 GAC 中。 若要了解如何创建强名称程序集，请参阅[如何：使用强名称为程序集签名](how-to-sign-an-assembly-with-a-strong-name.md)。

## <a name="windows-installer"></a>Windows Installer

建议使用 [Windows Installer](/windows/desktop/Msi/installation-of-assemblies-to-the-global-assembly-cache)（即 Windows 安装引擎）将程序集添加到全局程序集缓存。 Windows Installer 可提供全局程序集缓存中程序集的引用计数，还具有其他优点。 你可以使用[适用于 Visual Studio 2017 的 WiX 工具集扩展](https://marketplace.visualstudio.com/items?itemName=RobMensching.WixToolsetVisualStudio2017Extension)为 Windows Installer 创建安装程序包。

## <a name="global-assembly-cache-tool"></a>全局程序集缓存工具

你可以使用[全局程序集缓存工具 (gacutil.exe)](../tools/gacutil-exe-gac-tool.md) 将强名称程序集添加到全局程序集缓存，并查看全局程序集缓存的内容。

   > [!NOTE]
   > Gacutil.exe 只用于开发，不应用于将产品程序集安装到全局程序集缓存中。

gacutil 的语法如下：

```shell
gacutil -i <assembly name>
```

在此命令中，“assembly name”是要在全局程序集缓存中安装的程序集的名称。

下面的示例将文件名为 `hello.dll` 的程序集安装到全局程序集缓存。

```shell
gacutil -i hello.dll
```

> [!NOTE]
> 在 .NET Framework 的早期版本中，可以使用 Shfusion.dll Windows 外壳扩展通过将程序集拖到文件资源管理器中来安装这些程序集。 从 .NET Framework 4 开始，Shfusion.dll 已淘汰。

## <a name="see-also"></a>请参阅

- [使用程序集和全局程序集缓存](working-with-assemblies-and-the-gac.md)
- [如何：从全局程序集缓存中删除程序集](how-to-remove-an-assembly-from-the-gac.md)
- [Gacutil.exe（全局程序集缓存工具）](../tools/gacutil-exe-gac-tool.md)
- [如何：使用强名称为程序集签名](how-to-sign-an-assembly-with-a-strong-name.md)