---
title: 类型提供程序安全性
description: '了解如何在 F # 中，包括如何更改类型提供程序的信任设置的类型提供程序安全性。'
ms.date: 05/16/2016
ms.openlocfilehash: 66a873a32029d706f1f6fab50dd4f93bc29bca03
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="type-provider-security"></a>类型提供程序安全性

类型提供程序是包含程序集 (Dll) 引用的 F # 项目或脚本代码以连接到外部数据源并呈现到 F # 类型环境的此类型信息。 通常情况下，引用的程序集中的代码是仅运行时则在编译，然后执行代码 （或对于脚本，将代码发送至 F # Interactive）。 但是，类型提供程序程序集将运行在 Visual Studio 中，是仅在编辑器中浏览代码时。 这是因为类型提供程序需要运行将额外信息添加到编辑器中，如快速信息工具提示，IntelliSense 完成，依次类推。 因此，有额外的安全注意事项类型提供程序程序集，因为它们自动运行 Visual Studio 进程内。


## <a name="security-warning-dialog"></a>安全警告对话框
在首次使用特定类型提供程序程序集，Visual Studio 将显示一个安全对话框，警告你类型提供程序即将运行。 Visual Studio 加载类型提供程序之前，它使你可以决定是否信任此特定的提供程序。 如果您信任的源类型提供程序，然后选择"我信任此类型提供程序"。 如果你不信任的源类型提供程序，然后选择"我不信任此类型提供程序。" 信任提供程序使它能够在 Visual Studio 内运行和提供 IntelliSense 和生成功能。 但如果恶意类型提供程序本身，运行其代码可能会危害你的计算机。

如果你的项目包含引用类型提供程序选择在对话框中不信任的代码，然后在编译时，编译器将报告错误，该值指示类型提供程序不受信任。 由红色波形曲线指示依赖于不受信任的类型提供程序的任何类型。 则可以安全地浏览在编辑器中的代码。

如果你决定要更改直接在 Visual Studio 中的信任设置，请执行以下步骤。


#### <a name="to-change-the-trust-settings-for-type-providers"></a>若要更改类型提供程序的信任设置

1. 上`Tools`菜单上，选择`Options`，然后展开`F# Tools`节点。
<br />

2. 选择`Type Providers`，和在类型提供程序列表中，选择复选框适用于类型提供程序信任，并为那些不信任清除该复选框。
<br />


## <a name="see-also"></a>请参阅
[类型提供程序](index.md)
