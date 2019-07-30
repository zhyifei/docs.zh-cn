---
title: .NET Framework 应用程序中的 COM 互操作性 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- interoperability, COM and .NET framework objects
- COM interop [Visual Basic]
- shared components
ms.assetid: f5a72143-c268-4dff-a019-974ad940e17d
ms.openlocfilehash: 758f065d2e0e7f8200529ef171dc89f94950b46e
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627087"
---
# <a name="com-interoperability-in-net-framework-applications-visual-basic"></a>.NET Framework 应用程序中的 COM 互操作性 (Visual Basic)

如果要在同一个应用程序中使用 COM 对象和 .NET Framework 对象, 则需要解决对象在内存中的存在情况之间的差异。 .NET Framework 对象位于托管内存 (由公共语言运行时控制的内存) 中, 可以根据需要在运行时中移动。 COM 对象位于非托管内存中, 不应移动到另一个内存位置。 Visual Studio 和 .NET Framework 提供用于控制这些托管和非托管组件的交互的工具。 有关托管代码的详细信息, 请参阅[公共语言运行时](../../../standard/clr.md)。

除了在 .NET 应用程序中使用 COM 对象之外, 还可以使用 Visual Basic 开发通过 COM 从非托管代码访问的对象。

此页上的链接提供有关 COM 和 .NET Framework 对象之间的交互的详细信息。

## <a name="related-sections"></a>相关章节

| | |
|---------|---------|
| [COM 互操作](../../../visual-basic/programming-guide/com-interop/index.md) | 提供与 Visual Basic 中的 COM 互操作性相关的主题的链接, 这些主题包括 COM 对象、ActiveX 控件、Win32 Dll、托管对象以及 COM 对象的继承。 |
| [与非托管代码交互操作](../../../framework/interop/index.md) | 简要介绍了托管和非托管代码之间的一些交互问题, 并提供了进一步研究的链接。 |
| [COM 包装](../../../standard/native-interop/com-wrappers.md) | 讨论允许托管代码调用 COM 方法的运行时可调用包装器, 以及允许 COM 客户端调用 .NET 对象方法的 COM 可调用包装器。 |
| [高级 COM 互操作性](../../../framework/interop/index.md) | 提供一些链接, 这些链接指向涵盖与包装、异常、继承、线程处理、事件、转换和封送处理相关的 COM 互操作性。 |
| [Tlbimp.exe（类型库导入程序）](../../../framework/tools/tlbimp-exe-type-library-importer.md) | 讨论可用于将 COM 类型库中找到的类型定义转换为公共语言运行时程序集中的等效定义的工具。 |
