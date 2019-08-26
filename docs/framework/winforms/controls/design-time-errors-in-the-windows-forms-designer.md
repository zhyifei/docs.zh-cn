---
title: Windows 窗体设计器中的设计时错误
ms.date: 03/30/2017
f1_keywords:
- DTELErrorList
- WhyDTELPage
helpviewer_keywords:
- errors [Windows Forms Designer]
- design-time errors [Windows Forms Designer]
ms.assetid: ad408380-825a-46d8-9a4a-531b130b88ce
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: cce9baf1523391e281593428b633c401103b42b5
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015974"
---
# <a name="design-time-errors-in-the-windows-forms-designer"></a>Windows 窗体设计器中的设计时错误

本主题说明在无法加载 Windows 窗体设计器时, 在 Visual Studio 中显示的设计时错误列表的含义和用法。 如果出现此错误列表，则不应将其视为设计器中的 Bug，而应作为纠正代码中的错误的辅助手段。

此错误列表提供有关错误的详细信息和建议的可能解决方案，对此错误列表有一个基本了解可帮助调试应用程序。

## <a name="the-design-time-error-list-interface"></a>设计时错误列表接口

如果 Windows 窗体设计器无法加载, 则设计器中将显示错误列表。 错误按类别进行分组。 例如，如果具有四个未声明变量的实例，则这些实例会归到同一错误类别中。 每个错误类别包含一个概述错误的简短说明。

通过单击错误类别标题或单击 V 形展开/折叠按钮，可展开或折叠错误类别。 展开错误类别时，将显示以下附加帮助信息：

- 此错误的实例。

- 有关此错误的帮助。

- 有关此错误的论坛帖子。

### <a name="instances-of-this-error"></a>此错误的实例

附加帮助信息中列出了当前项目中所含错误的所有实例。 许多错误包含用以下格式表示的确切位置：[项目名称] [窗体名称]行:[行号]列:[列号]。 单击“转到代码”链接可跳转到代码中发生错误的位置。

如果调用堆栈与错误关联，则可单击“显示调用堆栈”链接，这会进一步展开错误以显示调用堆栈。 检查堆栈可获取有价值的调试信息。 例如，可跟踪错误发生之前调用过的函数。 调用堆栈是可选定的，以便进行复制并保存。

> [!NOTE]
> 在 Visual Basic 中，设计时错误列表不显示多个错误，但可能显示同一错误的多个实例。 在 Visual C++ 中，错误不含“转到代码”链接/行号链接。

### <a name="forum-posts-about-this-error"></a>有关此错误的论坛帖子

其他帮助包含与该错误相关的论坛帖子的链接。 将基于错误消息字符串来搜索论坛。 你还可以尝试搜索以下论坛:

- [Windows 窗体设计器论坛](https://social.msdn.microsoft.com/Forums/windows/home?forum=winformsdesigner)

- [Windows 窗体论坛](https://social.msdn.microsoft.com/Forums/windows/home?category=windowsforms)

### <a name="ignore-and-continue"></a>忽略并继续

可选择忽略错误条件并继续加载设计器。 选择此操作可能会导致意外行为。 例如，控件可能不会显示在设计图面上。

## <a name="see-also"></a>请参阅

- [设计时开发疑难解答](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171843(v=vs.120))
- [控件和组件创作疑难解答](troubleshooting-control-and-component-authoring.md)
- [设计时开发 Windows 窗体控件](developing-windows-forms-controls-at-design-time.md)
- [Windows 窗体设计器错误信息](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233640(v=vs.100))
