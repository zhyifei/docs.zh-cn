---
title: 如何：在窗体级别处理键盘输入
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- keyboard input [Windows Forms], at form level
- Windows Forms, handling keyboard input
- keyboards [Windows Forms], form-level input
ms.assetid: d7f8b390-dc91-42d2-ae0f-2ffa388127ad
ms.openlocfilehash: a75c4f116b32499f9ba33dd863f2a5b6952a3e24
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43404728"
---
# <a name="how-to-handle-keyboard-input-at-the-form-level"></a><span data-ttu-id="45db7-102">如何：在窗体级别处理键盘输入</span><span class="sxs-lookup"><span data-stu-id="45db7-102">How to: Handle Keyboard Input at the Form Level</span></span>
<span data-ttu-id="45db7-103">Windows 窗体能够在消息到达控件之前处理窗体级别的键盘消息。</span><span class="sxs-lookup"><span data-stu-id="45db7-103">Windows Forms provides the ability to handle keyboard messages at the form level, before the messages reach a control.</span></span> <span data-ttu-id="45db7-104">本主题演示如何完成此任务。</span><span class="sxs-lookup"><span data-stu-id="45db7-104">This topic shows how to accomplish this task.</span></span>  
  
### <a name="to-handle-a-keyboard-message-at-the-form-level"></a><span data-ttu-id="45db7-105">处理窗体级别的键盘消息</span><span class="sxs-lookup"><span data-stu-id="45db7-105">To handle a keyboard message at the form level</span></span>  
  
-   <span data-ttu-id="45db7-106">处理启动窗体的 <xref:System.Windows.Forms.Control.KeyPress> 或 <xref:System.Windows.Forms.Control.KeyDown> 事件，并将该窗体的 <xref:System.Windows.Forms.Form.KeyPreview%2A> 属性设置为 `true`，以便在键盘消息到达窗体上的任何控件之前接收到键盘消息。</span><span class="sxs-lookup"><span data-stu-id="45db7-106">Handle the <xref:System.Windows.Forms.Control.KeyPress> or <xref:System.Windows.Forms.Control.KeyDown> event of the startup form, and set the <xref:System.Windows.Forms.Form.KeyPreview%2A> property of the form to `true` so that keyboard messages are received by the form before they reach any controls on the form.</span></span> <span data-ttu-id="45db7-107">以下代码示例通过检测所有的数字键以及使用“1”、“4”和“7”来处理 <xref:System.Windows.Forms.Control.KeyPress> 事件。</span><span class="sxs-lookup"><span data-stu-id="45db7-107">The following code example handles the <xref:System.Windows.Forms.Control.KeyPress> event by detecting all of the number keys and consuming '1', '4', and '7'.</span></span>  
  
     [!code-cpp[System.Windows.Forms.KeyboardInputForm#10](../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/cpp/form1.cpp#10)]
     [!code-csharp[System.Windows.Forms.KeyboardInputForm#10](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/CS/form1.cs#10)]
     [!code-vb[System.Windows.Forms.KeyboardInputForm#10](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/VB/form1.vb#10)]  
  
## <a name="example"></a><span data-ttu-id="45db7-108">示例</span><span class="sxs-lookup"><span data-stu-id="45db7-108">Example</span></span>  
 <span data-ttu-id="45db7-109">以下代码示例是上述示例的整个应用程序。</span><span class="sxs-lookup"><span data-stu-id="45db7-109">The following code example is the entire application for the above example.</span></span> <span data-ttu-id="45db7-110">此应用程序包括一个 <xref:System.Windows.Forms.TextBox> 和几个允许你从 <xref:System.Windows.Forms.TextBox> 中移动焦点的控件。</span><span class="sxs-lookup"><span data-stu-id="45db7-110">The application includes a <xref:System.Windows.Forms.TextBox> along with several other controls that allow you to move focus from the <xref:System.Windows.Forms.TextBox>.</span></span> <span data-ttu-id="45db7-111">显示剩余键时，主要 <xref:System.Windows.Forms.Form> 的 <xref:System.Windows.Forms.Control.KeyPress> 事件使用“1”、“4”和“7”，而 <xref:System.Windows.Forms.TextBox> 的 <xref:System.Windows.Forms.Control.KeyPress> 事件使用“2”、“5”和“8”。</span><span class="sxs-lookup"><span data-stu-id="45db7-111">The <xref:System.Windows.Forms.Control.KeyPress> event of the main <xref:System.Windows.Forms.Form> consumes '1', '4', and '7', and the <xref:System.Windows.Forms.Control.KeyPress> event of the <xref:System.Windows.Forms.TextBox> consumes '2', '5', and '8' while displaying the remaining keys.</span></span> <span data-ttu-id="45db7-112">比较在 <xref:System.Windows.Forms.TextBox> 具有焦点时按数字键的 <xref:System.Windows.Forms.MessageBox> 输出以及在焦点位于其他控件上时按数字键的 <xref:System.Windows.Forms.MessageBox> 输出。</span><span class="sxs-lookup"><span data-stu-id="45db7-112">Compare the <xref:System.Windows.Forms.MessageBox> output when you press a number key while the <xref:System.Windows.Forms.TextBox> has focus with the <xref:System.Windows.Forms.MessageBox> output when you press a number key while focus is on one of the other controls.</span></span>  
  
 [!code-cpp[System.Windows.Forms.KeyBoardInputForm#0](../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/cpp/form1.cpp#0)]
 [!code-csharp[System.Windows.Forms.KeyBoardInputForm#0](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.KeyBoardInputForm#0](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="45db7-113">编译代码</span><span class="sxs-lookup"><span data-stu-id="45db7-113">Compiling the Code</span></span>  
 <span data-ttu-id="45db7-114">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="45db7-114">This example requires:</span></span>  
  
-   <span data-ttu-id="45db7-115">对 System、System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="45db7-115">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="45db7-116">Visual Basic 或 Visual C# 生成命令行中的此示例的信息，请参阅[从命令行生成](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[命令行上使用 csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="45db7-116">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="45db7-117">也可以通过将代码粘贴到新的项目中生成此示例在 Visual Studio 中。</span><span class="sxs-lookup"><span data-stu-id="45db7-117">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="45db7-118">另请参阅[如何：使用 Visual Studio 编译和运行完整的 Windows 窗体代码示例](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\))。</span><span class="sxs-lookup"><span data-stu-id="45db7-118">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45db7-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="45db7-119">See Also</span></span>  
 [<span data-ttu-id="45db7-120">Windows 窗体应用程序中的键盘输入</span><span class="sxs-lookup"><span data-stu-id="45db7-120">Keyboard Input in a Windows Forms Application</span></span>](../../../docs/framework/winforms/keyboard-input-in-a-windows-forms-application.md)
