---
title: "如何：确定所按下的修改键"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ffe09cc07b3eb36184a7242d418fd6782219806e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-determine-which-modifier-key-was-pressed"></a>如何：确定所按下的修改键
在创建的应用程序接受用户的键击时，可能想要修改键，例如 SHIFT、 ALT 和 CTRL 键的监视器。 当和其他键，或使用鼠标单击，修改键按下组合时，你的应用程序做出相应响应。 例如，如果按字母 S，这只是可能导致"s"出现在屏幕上，但如果同时按下 CTRL + S 键可能保存当前的文档。 如果你处理<xref:System.Windows.Forms.Control.KeyDown>事件，<xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A>属性<xref:System.Windows.Forms.KeyEventArgs>接收事件处理程序指定哪个修改键被按下。 或者，<xref:System.Windows.Forms.KeyEventArgs.KeyData%2A>属性<xref:System.Windows.Forms.KeyEventArgs>指定按下也与按位 OR 组合的任何修改键的字符。 但是，如果你正在处理<xref:System.Windows.Forms.Control.KeyPress>事件或鼠标事件，事件处理程序不接收此信息。 在这种情况下，你必须使用<xref:System.Windows.Forms.Control.ModifierKeys%2A>属性<xref:System.Windows.Forms.Control>类。 在任一情况下，你必须执行的相应的按位 AND<xref:System.Windows.Forms.Keys>值和要测试的值。 <xref:System.Windows.Forms.Keys>枚举提供变体的每个修饰符键，因此它很重要，你执行的按位与正确的值。 例如，由表示 SHIFT 键<xref:System.Windows.Forms.Keys.Shift>， <xref:System.Windows.Forms.Keys.ShiftKey>，<xref:System.Windows.Forms.Keys.RShiftKey>和<xref:System.Windows.Forms.Keys.LShiftKey>要测试 SHIFT，因为修饰符密钥的正确值<xref:System.Windows.Forms.Keys.Shift>。 同样，若要测试 CTLR 和 ALT 修饰符作为你应使用<xref:System.Windows.Forms.Keys.Control>和<xref:System.Windows.Forms.Keys.Alt>值，分别。  
  
> [!NOTE]
>  Visual Basic 程序员提供还可以访问密钥信息通过<xref:Microsoft.VisualBasic.Devices.Computer.Keyboard%2A>属性  
  
### <a name="to-determine-which-modifier-key-was-pressed"></a>若要确定哪些修饰符曾按下键  
  
-   使用按位`AND`运算符具有<xref:System.Windows.Forms.Control.ModifierKeys%2A>属性和值的<xref:System.Windows.Forms.Keys>枚举，以确定是否按下某个特定修饰符键。 下面的代码示例演示如何确定是否在按下 SHIFT 键<xref:System.Windows.Forms.Control.KeyPress>事件处理程序。  
  
     [!code-cpp[System.Windows.Forms.DetermineModifierKey#5](../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/cpp/form1.cpp#5)]
     [!code-csharp[System.Windows.Forms.DetermineModifierKey#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/CS/form1.cs#5)]
     [!code-vb[System.Windows.Forms.DetermineModifierKey#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/VB/form1.vb#5)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.Keys>  
 <xref:System.Windows.Forms.Control.ModifierKeys%2A>  
 [Windows 窗体应用程序中的键盘输入](../../../docs/framework/winforms/keyboard-input-in-a-windows-forms-application.md)  
 [如何： 确定如果 CapsLock 上在 Visual Basic 中](http://msdn.microsoft.com/en-us/91e60f5c-dd61-4222-ba5f-39af803afd8c)
