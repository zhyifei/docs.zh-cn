---
title: 如何：设计适合本地化的 Windows 窗体布局
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms]
- application design [Windows Forms], localization
- Windows Forms, localization
- localization [Windows Forms], Windows Forms layout
ms.assetid: d13eff2d-701c-4b6e-8838-3885cbfb7223
ms.openlocfilehash: c72cae58e8486f1187fd27d200522a43dca328ca
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "44031996"
---
# <a name="how-to-design-a-windows-forms-layout-that-responds-well-to-localization"></a><span data-ttu-id="c2144-102">如何：设计适合本地化的 Windows 窗体布局</span><span class="sxs-lookup"><span data-stu-id="c2144-102">How to: Design a Windows Forms Layout that Responds Well to Localization</span></span>
<span data-ttu-id="c2144-103">创建可供进行本地化的窗体极大地加速了国际市场的开发。</span><span class="sxs-lookup"><span data-stu-id="c2144-103">Creating forms that are ready to be localized greatly speeds development for international markets.</span></span> <span data-ttu-id="c2144-104">可以使用 <xref:System.Windows.Forms.TableLayoutPanel> 控件实现在控件因 <xref:System.Windows.Forms.Control.Text%2A> 属性值更改而调整大小时正常响应的布局。</span><span class="sxs-lookup"><span data-stu-id="c2144-104">You can use the <xref:System.Windows.Forms.TableLayoutPanel> control to implement layouts that respond gracefully as controls resize due to changes in their <xref:System.Windows.Forms.Control.Text%2A> property values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c2144-105">示例</span><span class="sxs-lookup"><span data-stu-id="c2144-105">Example</span></span>  
 <span data-ttu-id="c2144-106">此窗体演示如何创建在将显示的字符串值翻译成其它语言时按比例进行调整的布局。</span><span class="sxs-lookup"><span data-stu-id="c2144-106">This form demonstrates how to create a layout that proportionally adjusts when you translate displayed string values into other languages.</span></span> <span data-ttu-id="c2144-107">这一翻译过程称为*本地化*。</span><span class="sxs-lookup"><span data-stu-id="c2144-107">This process of translation is called *localization*.</span></span> <span data-ttu-id="c2144-108">有关详细信息，请参阅[本地化](../../../../docs/standard/globalization-localization/localization.md)。</span><span class="sxs-lookup"><span data-stu-id="c2144-108">For more information, see [Localization](../../../../docs/standard/globalization-localization/localization.md).</span></span>  
  
 <span data-ttu-id="c2144-109">Visual Studio 中对此任务提供广泛支持。</span><span class="sxs-lookup"><span data-stu-id="c2144-109">There is extensive support for this task in Visual Studio.</span></span>  <span data-ttu-id="c2144-110">另请参阅[演练：创建可根据本地化需要调整比例的布局](https://msdn.microsoft.com/library/7k9fa71y\(v=vs.110\))。</span><span class="sxs-lookup"><span data-stu-id="c2144-110">See also [Walkthrough: Creating a Layout That Adjusts Proportion for Localization](https://msdn.microsoft.com/library/7k9fa71y\(v=vs.110\)).</span></span>  
  
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.LocalizableForm#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.LocalizableForm/CS/localizableform.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.LocalizableForm#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.LocalizableForm/VB/localizableform.vb#1)]  
  
1.  [<span data-ttu-id="c2144-111">如何：在 TableLayoutPanel 控件中对齐和拉伸控件</span><span class="sxs-lookup"><span data-stu-id="c2144-111">How to: Align and Stretch a Control in a TableLayoutPanel Control</span></span>](how-to-align-and-stretch-a-control-in-a-tablelayoutpanel-control.md)  
  
2.  <span data-ttu-id="c2144-112">[演练：使用 FlowLayoutPanel 在 Windows 窗体上排列控件](https://msdn.microsoft.com/library/z9w7ek2f\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="c2144-112">[Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel](https://msdn.microsoft.com/library/z9w7ek2f\(v=vs.110\))</span></span>  
  
3.  [<span data-ttu-id="c2144-113">如何：在 TableLayoutPanel 控件中跨行和跨列</span><span class="sxs-lookup"><span data-stu-id="c2144-113">How to: Span Rows and Columns in a TableLayoutPanel Control</span></span>](how-to-span-rows-and-columns-in-a-tablelayoutpanel-control.md)  
  
4.  [<span data-ttu-id="c2144-114">如何：在 TableLayoutPanel 控件中编辑行和列</span><span class="sxs-lookup"><span data-stu-id="c2144-114">How to: Edit Columns and Rows in a TableLayoutPanel Control</span></span>](how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control.md)  
  
5.  <span data-ttu-id="c2144-115">[演练：使用 Windows 窗体控件上的智能标记执行常规任务](https://msdn.microsoft.com/library/xhz359sc\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="c2144-115">[Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls](https://msdn.microsoft.com/library/xhz359sc\(v=vs.110\))</span></span>  
  
6.  <span data-ttu-id="c2144-116">[演练：使用 TableLayoutPanel 在 Windows 窗体上排列控件](https://msdn.microsoft.com/library/w4yc3e8c\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="c2144-116">[Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](https://msdn.microsoft.com/library/w4yc3e8c\(v=vs.110\))</span></span>  
  
7.  <span data-ttu-id="c2144-117">[演练：使用 Padding、Margins 和 AutoSize 属性对 Windows 窗体控件进行布局](https://msdn.microsoft.com/library/3z3f9e8b\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="c2144-117">[Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property](https://msdn.microsoft.com/library/3z3f9e8b\(v=vs.110\))</span></span>  
  
8.  <span data-ttu-id="c2144-118">[如何：使用 AutoSize 属性和 TableLayoutPanel 控件支持对 Windows 窗体的本地化](https://msdn.microsoft.com/library/1zkt8b33\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="c2144-118">[How to: Support Localization on Windows Forms Using AutoSize and the TableLayoutPanel Control](https://msdn.microsoft.com/library/1zkt8b33\(v=vs.110\))</span></span>  
  
9. <span data-ttu-id="c2144-119">[演练：创建可根据数据输入需要调整大小的 Windows 窗体](https://msdn.microsoft.com/library/991eahec\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="c2144-119">[Walkthrough: Creating a Resizable Windows Form for Data Entry](https://msdn.microsoft.com/library/991eahec\(v=vs.110\))</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c2144-120">编译代码</span><span class="sxs-lookup"><span data-stu-id="c2144-120">Compiling the Code</span></span>  
 <span data-ttu-id="c2144-121">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="c2144-121">This example requires:</span></span>  
  
-   <span data-ttu-id="c2144-122">对 System、System.Data、System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="c2144-122">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="c2144-123">Visual Basic 或 Visual C# 生成命令行中的此示例的信息，请参阅[从命令行生成](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[命令行上使用 csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="c2144-123">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="c2144-124">也可以通过将代码粘贴到新的项目中生成此示例在 Visual Studio 中。</span><span class="sxs-lookup"><span data-stu-id="c2144-124">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="c2144-125">另请参阅[如何：使用 Visual Studio 编译和运行完整的 Windows 窗体代码示例](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\))。</span><span class="sxs-lookup"><span data-stu-id="c2144-125">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2144-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="c2144-126">See Also</span></span>  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 <xref:System.Windows.Forms.FlowLayoutPanel>  
 [<span data-ttu-id="c2144-127">本地化</span><span class="sxs-lookup"><span data-stu-id="c2144-127">Localization</span></span>](../../../../docs/standard/globalization-localization/localization.md)
