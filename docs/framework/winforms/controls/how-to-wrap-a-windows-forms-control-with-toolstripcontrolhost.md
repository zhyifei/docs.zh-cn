---
title: 如何：使用 ToolStripControlHost 包装 Windows 窗体控件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ToolStrip control [Windows Forms], wrapping controls
- toolbars [Windows Forms], wrapping controls
- ToolStrip control [Windows Forms], hosting controls
ms.assetid: e2ce4990-661d-4882-a116-8a9eb575dc84
ms.openlocfilehash: ccf82b2ea767d69797af1ffa38381a7cc0fd3b67
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59307998"
---
# <a name="how-to-wrap-a-windows-forms-control-with-toolstripcontrolhost"></a><span data-ttu-id="850c5-102">如何：使用 ToolStripControlHost 包装 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="850c5-102">How to: Wrap a Windows Forms Control with ToolStripControlHost</span></span>
<xref:System.Windows.Forms.ToolStripControlHost> <span data-ttu-id="850c5-103">旨在允许使用任意 Windows 窗体控件的托管<xref:System.Windows.Forms.ToolStripControlHost>构造函数或通过扩展<xref:System.Windows.Forms.ToolStripControlHost>本身。</span><span class="sxs-lookup"><span data-stu-id="850c5-103">is designed to enable hosting of arbitrary Windows Forms controls by using the <xref:System.Windows.Forms.ToolStripControlHost> constructor or by extending <xref:System.Windows.Forms.ToolStripControlHost> itself.</span></span> <span data-ttu-id="850c5-104">通过扩展 <xref:System.Windows.Forms.ToolStripControlHost> 并实现公开控件常用属性和方法的属性和方法，可轻松包装控件。</span><span class="sxs-lookup"><span data-stu-id="850c5-104">It is easier to wrap the control by extending <xref:System.Windows.Forms.ToolStripControlHost> and implementing properties and methods that expose frequently used properties and methods of the control.</span></span> <span data-ttu-id="850c5-105">还可以公开控件在 <xref:System.Windows.Forms.ToolStripControlHost> 级别的事件。</span><span class="sxs-lookup"><span data-stu-id="850c5-105">You can also expose events for the control at the <xref:System.Windows.Forms.ToolStripControlHost> level.</span></span>  
  
### <a name="to-host-a-control-in-a-toolstripcontrolhost-by-derivation"></a><span data-ttu-id="850c5-106">若要在 ToolStripControlHost 中通过派生承载控件</span><span class="sxs-lookup"><span data-stu-id="850c5-106">To host a control in a ToolStripControlHost by derivation</span></span>  
  
1. <span data-ttu-id="850c5-107">扩展 <xref:System.Windows.Forms.ToolStripControlHost>。</span><span class="sxs-lookup"><span data-stu-id="850c5-107">Extend <xref:System.Windows.Forms.ToolStripControlHost>.</span></span> <span data-ttu-id="850c5-108">实现可调用所需控件中传递的基类构造函数的默认构造函数。</span><span class="sxs-lookup"><span data-stu-id="850c5-108">Implement a default constructor that calls the base class constructor passing in the desired control.</span></span>  
  
     [!code-cpp[System.Windows.Forms.ToolStripControlHost#10](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CPP/form1.cpp#10)]
     [!code-csharp[System.Windows.Forms.ToolStripControlHost#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CS/form1.cs#10)]
     [!code-vb[System.Windows.Forms.ToolStripControlHost#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/VB/form1.vb#10)]  
  
2. <span data-ttu-id="850c5-109">声明与包装控件类型相同的属性，并将 `Control` 作为属性取值函数中的正确控件类型返回。</span><span class="sxs-lookup"><span data-stu-id="850c5-109">Declare a property of the same type as the wrapped control and return `Control` as the correct type of control in the property's accessor.</span></span>  
  
     [!code-cpp[System.Windows.Forms.ToolStripControlHost#11](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CPP/form1.cpp#11)]
     [!code-csharp[System.Windows.Forms.ToolStripControlHost#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CS/form1.cs#11)]
     [!code-vb[System.Windows.Forms.ToolStripControlHost#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/VB/form1.vb#11)]  
  
3. <span data-ttu-id="850c5-110">使用扩展类中的属性和方法公开包装控件的其他常用属性和方法。</span><span class="sxs-lookup"><span data-stu-id="850c5-110">Expose other frequently used properties and methods of the wrapped control with properties and methods in the extended class.</span></span>  
  
     [!code-cpp[System.Windows.Forms.ToolStripControlHost#12](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CPP/form1.cpp#12)]
     [!code-csharp[System.Windows.Forms.ToolStripControlHost#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CS/form1.cs#12)]
     [!code-vb[System.Windows.Forms.ToolStripControlHost#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/VB/form1.vb#12)]  
  
4. <span data-ttu-id="850c5-111">（可选）重写 <xref:System.Windows.Forms.ToolStripControlHost.OnSubscribeControlEvents%2A> 和 <xref:System.Windows.Forms.ToolStripControlHost.OnUnsubscribeControlEvents%2A> 方法并添加想要公开的控件事件。</span><span class="sxs-lookup"><span data-stu-id="850c5-111">Optionally, override the <xref:System.Windows.Forms.ToolStripControlHost.OnSubscribeControlEvents%2A>, and <xref:System.Windows.Forms.ToolStripControlHost.OnUnsubscribeControlEvents%2A> methods and add the control events you want to expose.</span></span>  
  
     [!code-cpp[System.Windows.Forms.ToolStripControlHost#16](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CPP/form1.cpp#16)]
     [!code-csharp[System.Windows.Forms.ToolStripControlHost#16](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CS/form1.cs#16)]
     [!code-vb[System.Windows.Forms.ToolStripControlHost#16](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/VB/form1.vb#16)]  
  
5. <span data-ttu-id="850c5-112">为想要公开的事件提供必要的包装。</span><span class="sxs-lookup"><span data-stu-id="850c5-112">Provide the necessary wrapping for the events you want to expose.</span></span>  
  
     [!code-cpp[System.Windows.Forms.ToolStripControlHost#17](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CPP/form1.cpp#17)]
     [!code-csharp[System.Windows.Forms.ToolStripControlHost#17](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CS/form1.cs#17)]
     [!code-vb[System.Windows.Forms.ToolStripControlHost#17](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/VB/form1.vb#17)]  
  
## <a name="example"></a><span data-ttu-id="850c5-113">示例</span><span class="sxs-lookup"><span data-stu-id="850c5-113">Example</span></span>  
 [!code-cpp[System.Windows.Forms.ToolStripControlHost#13](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CPP/form1.cpp#13)]
 [!code-csharp[System.Windows.Forms.ToolStripControlHost#13](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CS/form1.cs#13)]
 [!code-vb[System.Windows.Forms.ToolStripControlHost#13](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/VB/form1.vb#13)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="850c5-114">编译代码</span><span class="sxs-lookup"><span data-stu-id="850c5-114">Compiling the Code</span></span>  
  
-   <span data-ttu-id="850c5-115">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="850c5-115">This example requires:</span></span>  
  
-   <span data-ttu-id="850c5-116">对 System 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="850c5-116">References to the System and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="850c5-117">Visual Basic 或 Visual C# 生成命令行中的此示例的信息，请参阅[从命令行生成](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[命令行上使用 csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="850c5-117">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="850c5-118">也可以通过将代码粘贴到新的项目中生成此示例在 Visual Studio 中。</span><span class="sxs-lookup"><span data-stu-id="850c5-118">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="850c5-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="850c5-119">See also</span></span>

- <xref:System.Windows.Forms.ToolStripControlHost>
- [<span data-ttu-id="850c5-120">ToolStrip 控件概述</span><span class="sxs-lookup"><span data-stu-id="850c5-120">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="850c5-121">ToolStrip 控件体系结构</span><span class="sxs-lookup"><span data-stu-id="850c5-121">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="850c5-122">ToolStrip 技术摘要</span><span class="sxs-lookup"><span data-stu-id="850c5-122">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
