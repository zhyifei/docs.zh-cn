---
title: 如何：确定按下了哪个修改键
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- keyboard input
- shift keys
- events [Windows Forms], mouse
- Keys.ControlKey enumeration member
- keys [Windows Forms], control keys
- user input [Windows Forms], checking for keyboard
- keys [Windows Forms], determining last pressed
- keys [Windows Forms], shift keys
- keys [Windows Forms], modifier keys
- control keys
- keys [Windows Forms], alt keys
- alt keys
- Keys.Shift enumeration member
- events [Windows Forms], keyboard
- keyboards [Windows Forms], keyboard input
- Keys.Alt enumeration member
- modifier keys
ms.assetid: 1e184048-0ae3-4067-a200-d4ba31dbc2cb
ms.openlocfilehash: 37fa897f5a2e1c65cbd5db9189f1500e3427c920
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964311"
---
# <a name="how-to-determine-which-modifier-key-was-pressed"></a>如何：确定按下了哪个修改键
当创建接受用户击键的应用程序时, 可能还需要监视修改键, 如 SHIFT、ALT 和 CTRL 键。 当修改键与其他键结合使用时, 或通过鼠标单击时, 应用程序可以相应地做出响应。 例如, 如果按下字母, 这可能只是导致屏幕上出现 "S", 但如果按下键 CTRL + S, 则可能会保存当前文档。 如果处理<xref:System.Windows.Forms.Control.KeyDown>事件<xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A> , 事件处理程序接收的的<xref:System.Windows.Forms.KeyEventArgs>属性将指定按下的修改键。 或者, <xref:System.Windows.Forms.KeyEventArgs.KeyData%2A>的<xref:System.Windows.Forms.KeyEventArgs>属性指定按下的字符以及与按位 "或" 组合的所有修改键。 但是, 如果要处理<xref:System.Windows.Forms.Control.KeyPress>事件或鼠标事件, 事件处理程序不会收到此信息。 在这种情况下, 必须使用<xref:System.Windows.Forms.Control.ModifierKeys%2A> <xref:System.Windows.Forms.Control>类的属性。 在任一情况下, 都必须对适当<xref:System.Windows.Forms.Keys>的值和要测试的值执行按位 "与" 运算。 <xref:System.Windows.Forms.Keys>枚举提供每个修改键的变体, 因此, 请务必按正确的值执行按位 "与"。 例如, shift 键由<xref:System.Windows.Forms.Keys.Shift> <xref:System.Windows.Forms.Keys.RShiftKey> 、 <xref:System.Windows.Forms.Keys.ShiftKey>和<xref:System.Windows.Forms.Keys.LShiftKey>表示, 用于测试移位作为修改键的正确值为<xref:System.Windows.Forms.Keys.Shift>。 同样, 若要测试 CTRL 和 ALT 作为修饰符, 应分别使用<xref:System.Windows.Forms.Keys.Control>和<xref:System.Windows.Forms.Keys.Alt>值。  
  
> [!NOTE]
> Visual Basic 程序员还可以通过<xref:Microsoft.VisualBasic.Devices.Computer.Keyboard%2A>属性访问密钥信息  
  
### <a name="to-determine-which-modifier-key-was-pressed"></a>确定按下了哪个修改键  
  
- 对<xref:System.Windows.Forms.Control.ModifierKeys%2A>属性使用`AND`位运算符<xref:System.Windows.Forms.Keys> , 并使用枚举的值来确定是否按下某个特定的修改键。 下面的代码示例演示如何确定<xref:System.Windows.Forms.Control.KeyPress>事件处理程序中是否按下了 SHIFT 键。  
  
     [!code-cpp[System.Windows.Forms.DetermineModifierKey#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/cpp/form1.cpp#5)]
     [!code-csharp[System.Windows.Forms.DetermineModifierKey#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/CS/form1.cs#5)]
     [!code-vb[System.Windows.Forms.DetermineModifierKey#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/VB/form1.vb#5)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.Keys>
- <xref:System.Windows.Forms.Control.ModifierKeys%2A>
- [Windows 窗体应用程序中的键盘输入](keyboard-input-in-a-windows-forms-application.md)
- [如何：确定 CapsLock 是否在 Visual Basic](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9c9d1fz9(v=vs.100))
