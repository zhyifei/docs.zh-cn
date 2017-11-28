---
title: "面向 Windows 8 中的 .NET Framework 2.0"
description: "了解如何使用 F # 时以旧版本的.NET Framework 为目标。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 63989543-95c3-4ab7-81f3-3834a8b15010
ms.openlocfilehash: 2c0191267da5bee7b844c11cdee168ccfb3321c4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="targeting-older-versions-of-net"></a>面向 .NET 的较旧版本

> [!NOTE]
本文不是最新的 Visual Studio 最新的。  它将会更新。

如果你尝试面向.NET Framework 2.0，3.0 或 3.5 中的 F # 项目时在 Windows 8.1 上安装 Visual Studio 可能会出现以下错误： 

```
This project requires the 2.0 F# runtime, but that runtime is not installed.
```

此错误是已知在以下条件的组合下出现：


- 在 Windows 8.1 上安装了 Visual Studio。
<br />

- 在安装 Visual Studio 之前，未启用.NET Framework 3.5。
<br />

- 你的项目面向.NET Framework 2.0、 3.0 或 3.5。
<br />

在安装 Visual Studio 时，它检测到已安装的.NET Framework 版本，并安装 F # 2.0 运行时，仅当安装并启用.NET Framework 3.5。


## <a name="resolving-the-error"></a>解决错误
若要解决此错误，你可以任一目标.NET Framework 中，较新版本，或您可以启用 Windows 8.1 上的.NET Framework 3.5，然后安装 F # 2.0 运行时通过运行使用 Visual Studio 的安装程序**修复**选项。


#### <a name="to-enable-the-net-framework-35-on-windows-81"></a>若要启用 Windows 8.1 上的.NET Framework 3.5

1. 上**启动**屏幕上，开始输入**控制面板**。
<br />  该名称时，输入时**控制面板**图标显示在**应用**标题。
<br />

2. 选择**控制面板**图标，选择**程序**图标，然后选择**打开或关闭 Windows 功能**链接。
<br />

3. 请确保**.NET Framework 3.5 （包括.NET 2.0 和 3.0）**复选框被选中，并且然后选择**确定**按钮。
<br />  你不需要选择对应的.NET framework 的可选组件的任何子节点的复选框。
<br />  如果尚未，启用.NET Framework 3.5。
<br />


#### <a name="to-install-the-f-20-runtime"></a>若要安装 F # 2.0 运行时

1. 在控制面板中，选择**程序**链接，然后再选择**程序和功能**链接。
<br />

2. 在已安装的程序列表中，选择版本的 Visual Studio 的安装，然后依次**更改**按钮。
<br />

3. 安装程序启动后，请选择**修复**按钮。
<br />  有关详细信息，请参阅[安装 Visual Studio](https://msdn.microsoft.com/library/e2h7fzkw.aspx)。
<br />
## <a name="see-also"></a>另请参阅
[Visual F#](../index.md)
