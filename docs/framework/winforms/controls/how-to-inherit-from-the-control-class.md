---
title: 如何：从 Control 类继承
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- Control class [Windows Forms], inheriting from
- custom controls [Windows Forms], inheritance
- OnPaint method [Windows Forms]
- custom controls [Windows Forms], creating
ms.assetid: 46ba0df3-5cf7-443c-a3b4-a72660172476
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 7af7d1fe8f14c71dfc90836d84023b98feb44961
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458387"
---
# <a name="how-to-inherit-from-the-control-class"></a>如何：从 Control 类继承

如果要创建完全自定义的控件以在 Windows 窗体上使用，应从 <xref:System.Windows.Forms.Control> 类继承。 从 <xref:System.Windows.Forms.Control> 类继承时，需要执行更多规划和实现，它还提供了最大范围的选项。 从 <xref:System.Windows.Forms.Control>继承时，将继承使控件工作的最基本的功能。 <xref:System.Windows.Forms.Control> 类中固有的功能通过键盘和鼠标处理用户输入，定义控件的边界和大小，提供 windows 句柄，并提供消息处理和安全性。 它没有纳入任何绘图功能（这里指的是控件的图形界面的实际呈现），也没有纳入任何特定的用户交互功能。 必须通过自定义代码提供所有的这些功能。

## <a name="to-create-a-custom-control"></a>创建自定义控件

1. 在 Visual Studio 中，创建一个新的 " **Windows 应用程序**" 或 " **windows 控件库**" 项目。

2. 从“项目”菜单中，选择“添加类”。

3. 在“添加新项”对话框中，单击“自定义控件”。

   一个新的自定义控件将被添加到项目中。

4. 按**F7**以打开自定义控件的**代码编辑器**。

5. 找到 <xref:System.Windows.Forms.Control.OnPaint%2A> 方法，该方法将为空，除非调用基类的 <xref:System.Windows.Forms.Control.OnPaint%2A> 方法。

6. 修改代码以纳入控件所需的任何自定义绘图。

   有关编写代码来呈现控件的图形的信息，请参阅[自定义控件的绘制和呈现](custom-control-painting-and-rendering.md)。

7. 实现控件将纳入的任何自定义方法、属性或事件。

8. 保存并测试控件。

## <a name="see-also"></a>请参阅

- [各种自定义控件](varieties-of-custom-controls.md)
- [如何：从 UserControl 类继承](how-to-inherit-from-the-usercontrol-class.md)
- [如何：从现有 Windows 窗体控件继承](how-to-inherit-from-existing-windows-forms-controls.md)
- [如何：创作 Windows 窗体的控件](how-to-author-controls-for-windows-forms.md)
- [Visual Basic 中继承的事件处理程序疑难解答](../../../visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
- [设计时开发 Windows 窗体控件](developing-windows-forms-controls-at-design-time.md)
