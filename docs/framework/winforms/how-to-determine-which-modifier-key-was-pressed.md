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
ms.openlocfilehash: e2caf421e25dff3300b3d799582f4260d0aab320
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54586652"
---
# <a name="how-to-determine-which-modifier-key-was-pressed"></a><span data-ttu-id="77c28-102">如何：确定按下了哪个修改键</span><span class="sxs-lookup"><span data-stu-id="77c28-102">How to: Determine Which Modifier Key Was Pressed</span></span>
<span data-ttu-id="77c28-103">在创建接受用户的击键的应用程序时，可能还想要监视修改键，如 SHIFT、 ALT 和 CTRL 键。</span><span class="sxs-lookup"><span data-stu-id="77c28-103">When you create an application that accepts the user's keystrokes, you may also want to monitor for modifier keys such as the SHIFT, ALT, and CTRL keys.</span></span> <span data-ttu-id="77c28-104">修改键按下时结合使用其他密钥，或者单击鼠标，你的应用程序做出正确响应。</span><span class="sxs-lookup"><span data-stu-id="77c28-104">When a modifier key is pressed in combination with other keys, or with mouse clicks, your application can respond appropriately.</span></span> <span data-ttu-id="77c28-105">例如，如果按下字母 S 时，这只是可能导致"s"出现在屏幕上，但如果按下了 CTRL + S 的密钥，可能会保存当前文档。</span><span class="sxs-lookup"><span data-stu-id="77c28-105">For example, if the letter S is pressed, this may simply cause an "s" to appear on the screen, but if the keys CTRL+S are pressed, the current document may be saved.</span></span> <span data-ttu-id="77c28-106">如果处理<xref:System.Windows.Forms.Control.KeyDown>事件，<xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A>属性的<xref:System.Windows.Forms.KeyEventArgs>收到的事件处理程序指定哪个修改键被按下。</span><span class="sxs-lookup"><span data-stu-id="77c28-106">If you handle the <xref:System.Windows.Forms.Control.KeyDown> event, the <xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A> property of the <xref:System.Windows.Forms.KeyEventArgs> received by the event handler specifies which modifier keys are pressed.</span></span> <span data-ttu-id="77c28-107">或者，<xref:System.Windows.Forms.KeyEventArgs.KeyData%2A>属性的<xref:System.Windows.Forms.KeyEventArgs>指定按下了也与按位 OR 组合与任何修改键的字符。</span><span class="sxs-lookup"><span data-stu-id="77c28-107">Alternatively, the <xref:System.Windows.Forms.KeyEventArgs.KeyData%2A> property of <xref:System.Windows.Forms.KeyEventArgs> specifies the character that was pressed as well as any modifier keys combined with a bitwise OR.</span></span> <span data-ttu-id="77c28-108">但是，如果你是<xref:System.Windows.Forms.Control.KeyPress>事件或鼠标事件，事件处理程序不会接收此信息。</span><span class="sxs-lookup"><span data-stu-id="77c28-108">However, if you are handling the <xref:System.Windows.Forms.Control.KeyPress> event or a mouse event, the event handler does not receive this information.</span></span> <span data-ttu-id="77c28-109">在这种情况下，必须使用<xref:System.Windows.Forms.Control.ModifierKeys%2A>属性的<xref:System.Windows.Forms.Control>类。</span><span class="sxs-lookup"><span data-stu-id="77c28-109">In this case, you must use the <xref:System.Windows.Forms.Control.ModifierKeys%2A> property of the <xref:System.Windows.Forms.Control> class.</span></span> <span data-ttu-id="77c28-110">在任一情况下，您必须执行相应的按位 AND<xref:System.Windows.Forms.Keys>值和要测试的值。</span><span class="sxs-lookup"><span data-stu-id="77c28-110">In either case, you must perform a bitwise AND of the appropriate <xref:System.Windows.Forms.Keys> value and the value you are testing.</span></span> <span data-ttu-id="77c28-111"><xref:System.Windows.Forms.Keys>枚举提供了变体的每个修改键，因此，必须执行的按位并使用正确的值。</span><span class="sxs-lookup"><span data-stu-id="77c28-111">The <xref:System.Windows.Forms.Keys> enumeration offers variations of each modifier key, so it is important that you perform the bitwise AND with the correct value.</span></span> <span data-ttu-id="77c28-112">例如，由表示 SHIFT 键<xref:System.Windows.Forms.Keys.Shift>， <xref:System.Windows.Forms.Keys.ShiftKey>，<xref:System.Windows.Forms.Keys.RShiftKey>并<xref:System.Windows.Forms.Keys.LShiftKey>正确的值来测试 SHIFT 修改键原样<xref:System.Windows.Forms.Keys.Shift>。</span><span class="sxs-lookup"><span data-stu-id="77c28-112">For example, the SHIFT key is represented by <xref:System.Windows.Forms.Keys.Shift>, <xref:System.Windows.Forms.Keys.ShiftKey>, <xref:System.Windows.Forms.Keys.RShiftKey> and <xref:System.Windows.Forms.Keys.LShiftKey> The correct value to test SHIFT as a modifier key is <xref:System.Windows.Forms.Keys.Shift>.</span></span> <span data-ttu-id="77c28-113">同样，若要测试 CTRL 和 ALT 修饰符作为您应使用<xref:System.Windows.Forms.Keys.Control>和<xref:System.Windows.Forms.Keys.Alt>值，分别。</span><span class="sxs-lookup"><span data-stu-id="77c28-113">Similarly, to test for CTRL and ALT as modifiers you should use the <xref:System.Windows.Forms.Keys.Control> and <xref:System.Windows.Forms.Keys.Alt> values, respectively.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="77c28-114">Visual Basic 编程人员也可以访问密钥信息通过<xref:Microsoft.VisualBasic.Devices.Computer.Keyboard%2A>属性</span><span class="sxs-lookup"><span data-stu-id="77c28-114">Visual Basic programmers can also access key information through the <xref:Microsoft.VisualBasic.Devices.Computer.Keyboard%2A> property</span></span>  
  
### <a name="to-determine-which-modifier-key-was-pressed"></a><span data-ttu-id="77c28-115">若要确定哪个修改键已按下</span><span class="sxs-lookup"><span data-stu-id="77c28-115">To determine which modifier key was pressed</span></span>  
  
-   <span data-ttu-id="77c28-116">使用按位`AND`运算符，其中<xref:System.Windows.Forms.Control.ModifierKeys%2A>属性和值为<xref:System.Windows.Forms.Keys>枚举来确定是否按下某个特定修改键。</span><span class="sxs-lookup"><span data-stu-id="77c28-116">Use the bitwise `AND` operator with the <xref:System.Windows.Forms.Control.ModifierKeys%2A> property and a value of the <xref:System.Windows.Forms.Keys> enumeration to determine whether a particular modifier key is pressed.</span></span> <span data-ttu-id="77c28-117">下面的代码示例演示如何确定是否在按下 SHIFT 键<xref:System.Windows.Forms.Control.KeyPress>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="77c28-117">The following code example shows how to determine whether the SHIFT key is pressed within a <xref:System.Windows.Forms.Control.KeyPress> event handler.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DetermineModifierKey#5](../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/cpp/form1.cpp#5)]
     [!code-csharp[System.Windows.Forms.DetermineModifierKey#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/CS/form1.cs#5)]
     [!code-vb[System.Windows.Forms.DetermineModifierKey#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/VB/form1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="77c28-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="77c28-118">See also</span></span>
- <xref:System.Windows.Forms.Keys>
- <xref:System.Windows.Forms.Control.ModifierKeys%2A>
- [<span data-ttu-id="77c28-119">Windows 窗体应用程序中的键盘输入</span><span class="sxs-lookup"><span data-stu-id="77c28-119">Keyboard Input in a Windows Forms Application</span></span>](../../../docs/framework/winforms/keyboard-input-in-a-windows-forms-application.md)
- [<span data-ttu-id="77c28-120">如何：确定如果 CapsLock 在 Visual Basic 中已启用</span><span class="sxs-lookup"><span data-stu-id="77c28-120">How to: Determine If CapsLock is On in Visual Basic</span></span>](https://msdn.microsoft.com/library/91e60f5c-dd61-4222-ba5f-39af803afd8c)
