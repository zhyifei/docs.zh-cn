---
title: 如何：处理 Windows 窗体控件中的用户输入的事件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, user input
- user input [Windows Forms], Windows Forms controls
ms.assetid: 3de74dcf-fae3-42d0-92b5-bc04a61a6888
ms.openlocfilehash: ae4a6f7087c82be6531a91980e2fee0108298a46
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54738704"
---
# <a name="how-to-handle-user-input-events-in-windows-forms-controls"></a><span data-ttu-id="55025-102">如何：处理 Windows 窗体控件中的用户输入的事件</span><span class="sxs-lookup"><span data-stu-id="55025-102">How to: Handle User Input Events in Windows Forms Controls</span></span>
<span data-ttu-id="55025-103">此示例演示如何处理大多数键盘、鼠标、焦点和 Windows 窗体控件中可能会发生的验证事件。</span><span class="sxs-lookup"><span data-stu-id="55025-103">This example demonstrates how to handle most keyboard, mouse, focus, and validation events that can occur in a Windows Forms control.</span></span> <span data-ttu-id="55025-104">命名为 `TextBoxInput` 的文本框在其具有焦点时接收事件，有关每个事件的信息将以事件发生的顺序写入被命名为 `TextBoxOutput` 的文本框中。</span><span class="sxs-lookup"><span data-stu-id="55025-104">The text box named `TextBoxInput` receives the events when it has focus, and information about each event is written in the text box named `TextBoxOutput` in the order in which the events are raised.</span></span> <span data-ttu-id="55025-105">该应用程序还包括一组复选框，可用于筛选要报告的事件。</span><span class="sxs-lookup"><span data-stu-id="55025-105">The application also includes a set of check boxes that can be used to filter which events to report.</span></span>  
  
## <a name="example"></a><span data-ttu-id="55025-106">示例</span><span class="sxs-lookup"><span data-stu-id="55025-106">Example</span></span>  
 [!code-cpp[System.Windows.Forms.UserInputWalkthrough#0](../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.UserInputWalkthrough/cpp/form1.cpp#0)]
 [!code-csharp[System.Windows.Forms.UserInputWalkthrough#0](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.UserInputWalkthrough/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.UserInputWalkthrough#0](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.UserInputWalkthrough/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="55025-107">编译代码</span><span class="sxs-lookup"><span data-stu-id="55025-107">Compiling the Code</span></span>  
 <span data-ttu-id="55025-108">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="55025-108">This example requires:</span></span>  
  
-   <span data-ttu-id="55025-109">对 System、System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="55025-109">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="55025-110">Visual Basic 或 Visual C# 生成命令行中的此示例的信息，请参阅[从命令行生成](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[命令行上使用 csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="55025-110">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="55025-111">也可以通过将代码粘贴到新的项目中生成此示例在 Visual Studio 中。</span><span class="sxs-lookup"><span data-stu-id="55025-111">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="55025-112">另请参阅[如何：编译和运行完整的 Windows 窗体代码示例使用 Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\))。</span><span class="sxs-lookup"><span data-stu-id="55025-112">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55025-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="55025-113">See also</span></span>
- [<span data-ttu-id="55025-114">Windows 窗体中的用户输入</span><span class="sxs-lookup"><span data-stu-id="55025-114">User Input in Windows Forms</span></span>](../../../docs/framework/winforms/user-input-in-windows-forms.md)
