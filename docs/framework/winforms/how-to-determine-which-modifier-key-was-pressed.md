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
ms.openlocfilehash: d5f749d22c09d166e81ea08068f760f24960ec83
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-determine-which-modifier-key-was-pressed"></a><span data-ttu-id="51853-102">如何：确定所按下的修改键</span><span class="sxs-lookup"><span data-stu-id="51853-102">How to: Determine Which Modifier Key Was Pressed</span></span>
<span data-ttu-id="51853-103">在创建的应用程序接受用户的键击时，可能想要修改键，例如 SHIFT、 ALT 和 CTRL 键的监视器。</span><span class="sxs-lookup"><span data-stu-id="51853-103">When you create an application that accepts the user's keystrokes, you may also want to monitor for modifier keys such as the SHIFT, ALT, and CTRL keys.</span></span> <span data-ttu-id="51853-104">当和其他键，或使用鼠标单击，修改键按下组合时，你的应用程序做出相应响应。</span><span class="sxs-lookup"><span data-stu-id="51853-104">When a modifier key is pressed in combination with other keys, or with mouse clicks, your application can respond appropriately.</span></span> <span data-ttu-id="51853-105">例如，如果按字母 S，这只是可能导致"s"出现在屏幕上，但如果同时按下 CTRL + S 键可能保存当前的文档。</span><span class="sxs-lookup"><span data-stu-id="51853-105">For example, if the letter S is pressed, this may simply cause an "s" to appear on the screen, but if the keys CTRL+S are pressed, the current document may be saved.</span></span> <span data-ttu-id="51853-106">如果你处理<xref:System.Windows.Forms.Control.KeyDown>事件，<xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A>属性<xref:System.Windows.Forms.KeyEventArgs>接收事件处理程序指定哪个修改键被按下。</span><span class="sxs-lookup"><span data-stu-id="51853-106">If you handle the <xref:System.Windows.Forms.Control.KeyDown> event, the <xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A> property of the <xref:System.Windows.Forms.KeyEventArgs> received by the event handler specifies which modifier keys are pressed.</span></span> <span data-ttu-id="51853-107">或者，<xref:System.Windows.Forms.KeyEventArgs.KeyData%2A>属性<xref:System.Windows.Forms.KeyEventArgs>指定按下也与按位 OR 组合的任何修改键的字符。</span><span class="sxs-lookup"><span data-stu-id="51853-107">Alternatively, the <xref:System.Windows.Forms.KeyEventArgs.KeyData%2A> property of <xref:System.Windows.Forms.KeyEventArgs> specifies the character that was pressed as well as any modifier keys combined with a bitwise OR.</span></span> <span data-ttu-id="51853-108">但是，如果你正在处理<xref:System.Windows.Forms.Control.KeyPress>事件或鼠标事件，事件处理程序不接收此信息。</span><span class="sxs-lookup"><span data-stu-id="51853-108">However, if you are handling the <xref:System.Windows.Forms.Control.KeyPress> event or a mouse event, the event handler does not receive this information.</span></span> <span data-ttu-id="51853-109">在这种情况下，你必须使用<xref:System.Windows.Forms.Control.ModifierKeys%2A>属性<xref:System.Windows.Forms.Control>类。</span><span class="sxs-lookup"><span data-stu-id="51853-109">In this case, you must use the <xref:System.Windows.Forms.Control.ModifierKeys%2A> property of the <xref:System.Windows.Forms.Control> class.</span></span> <span data-ttu-id="51853-110">在任一情况下，你必须执行的相应的按位 AND<xref:System.Windows.Forms.Keys>值和要测试的值。</span><span class="sxs-lookup"><span data-stu-id="51853-110">In either case, you must perform a bitwise AND of the appropriate <xref:System.Windows.Forms.Keys> value and the value you are testing.</span></span> <span data-ttu-id="51853-111"><xref:System.Windows.Forms.Keys>枚举提供变体的每个修饰符键，因此它很重要，你执行的按位与正确的值。</span><span class="sxs-lookup"><span data-stu-id="51853-111">The <xref:System.Windows.Forms.Keys> enumeration offers variations of each modifier key, so it is important that you perform the bitwise AND with the correct value.</span></span> <span data-ttu-id="51853-112">例如，由表示 SHIFT 键<xref:System.Windows.Forms.Keys.Shift>， <xref:System.Windows.Forms.Keys.ShiftKey>，<xref:System.Windows.Forms.Keys.RShiftKey>和<xref:System.Windows.Forms.Keys.LShiftKey>要测试 SHIFT，因为修饰符密钥的正确值<xref:System.Windows.Forms.Keys.Shift>。</span><span class="sxs-lookup"><span data-stu-id="51853-112">For example, the SHIFT key is represented by <xref:System.Windows.Forms.Keys.Shift>, <xref:System.Windows.Forms.Keys.ShiftKey>, <xref:System.Windows.Forms.Keys.RShiftKey> and <xref:System.Windows.Forms.Keys.LShiftKey> The correct value to test SHIFT as a modifier key is <xref:System.Windows.Forms.Keys.Shift>.</span></span> <span data-ttu-id="51853-113">同样，若要测试 CTLR 和 ALT 修饰符作为你应使用<xref:System.Windows.Forms.Keys.Control>和<xref:System.Windows.Forms.Keys.Alt>值，分别。</span><span class="sxs-lookup"><span data-stu-id="51853-113">Similarly, to test for CTLR and ALT as modifiers you should use the <xref:System.Windows.Forms.Keys.Control> and <xref:System.Windows.Forms.Keys.Alt> values, respectively.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="51853-114">Visual Basic 程序员提供还可以访问密钥信息通过<xref:Microsoft.VisualBasic.Devices.Computer.Keyboard%2A>属性</span><span class="sxs-lookup"><span data-stu-id="51853-114">Visual Basic programmers can also access key information through the <xref:Microsoft.VisualBasic.Devices.Computer.Keyboard%2A> property</span></span>  
  
### <a name="to-determine-which-modifier-key-was-pressed"></a><span data-ttu-id="51853-115">若要确定哪些修饰符曾按下键</span><span class="sxs-lookup"><span data-stu-id="51853-115">To determine which modifier key was pressed</span></span>  
  
-   <span data-ttu-id="51853-116">使用按位`AND`运算符具有<xref:System.Windows.Forms.Control.ModifierKeys%2A>属性和值的<xref:System.Windows.Forms.Keys>枚举，以确定是否按下某个特定修饰符键。</span><span class="sxs-lookup"><span data-stu-id="51853-116">Use the bitwise `AND` operator with the <xref:System.Windows.Forms.Control.ModifierKeys%2A> property and a value of the <xref:System.Windows.Forms.Keys> enumeration to determine whether a particular modifier key is pressed.</span></span> <span data-ttu-id="51853-117">下面的代码示例演示如何确定是否在按下 SHIFT 键<xref:System.Windows.Forms.Control.KeyPress>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="51853-117">The following code example shows how to determine whether the SHIFT key is pressed within a <xref:System.Windows.Forms.Control.KeyPress> event handler.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DetermineModifierKey#5](../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/cpp/form1.cpp#5)]
     [!code-csharp[System.Windows.Forms.DetermineModifierKey#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/CS/form1.cs#5)]
     [!code-vb[System.Windows.Forms.DetermineModifierKey#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/VB/form1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="51853-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="51853-118">See Also</span></span>  
 <xref:System.Windows.Forms.Keys>  
 <xref:System.Windows.Forms.Control.ModifierKeys%2A>  
 [<span data-ttu-id="51853-119">Windows 窗体应用程序中的键盘输入</span><span class="sxs-lookup"><span data-stu-id="51853-119">Keyboard Input in a Windows Forms Application</span></span>](../../../docs/framework/winforms/keyboard-input-in-a-windows-forms-application.md)  
 [<span data-ttu-id="51853-120">如何： 确定如果 CapsLock 上在 Visual Basic 中</span><span class="sxs-lookup"><span data-stu-id="51853-120">How to: Determine If CapsLock is On in Visual Basic</span></span>](http://msdn.microsoft.com/library/91e60f5c-dd61-4222-ba5f-39af803afd8c)
