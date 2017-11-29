---
title: "如何：创建具有专业样式的 ToolStrip 控件"
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
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStripRenderer class [Windows Forms]
- ToolStrip control [Windows Forms]
ms.assetid: c208b2f6-8105-474b-9075-d582e1792870
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0199bad54d7b4ed4f1ed63b22914f8f99bbf6e85
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-professionally-styled-toolstrip-control"></a><span data-ttu-id="910c5-102">如何：创建具有专业样式的 ToolStrip 控件</span><span class="sxs-lookup"><span data-stu-id="910c5-102">How to: Create a Professionally Styled ToolStrip Control</span></span>
<span data-ttu-id="910c5-103">可以通过编写自己的派生自 <xref:System.Windows.Forms.ToolStripProfessionalRenderer> 类型的类，赋予应用程序的 <xref:System.Windows.Forms.ToolStrip> 控件一个专业的外观和行为（外观和感受）。</span><span class="sxs-lookup"><span data-stu-id="910c5-103">You can give your application’s <xref:System.Windows.Forms.ToolStrip> controls a professional appearance and behavior (look and feel) by writing your own class derived from the <xref:System.Windows.Forms.ToolStripProfessionalRenderer> type.</span></span>  
  
 <span data-ttu-id="910c5-104">在 [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]中，对此功能提供广泛支持。</span><span class="sxs-lookup"><span data-stu-id="910c5-104">There is extensive support for this feature in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].</span></span>  
  
 <span data-ttu-id="910c5-105">请参阅[演练：创建具有专业样式的 ToolStrip 控件](../../../../docs/framework/winforms/controls/walkthrough-creating-a-professionally-styled-toolstrip-control.md)。</span><span class="sxs-lookup"><span data-stu-id="910c5-105">See [Walkthrough: Creating a Professionally Styled ToolStrip Control](../../../../docs/framework/winforms/controls/walkthrough-creating-a-professionally-styled-toolstrip-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="910c5-106">示例</span><span class="sxs-lookup"><span data-stu-id="910c5-106">Example</span></span>  
 <span data-ttu-id="910c5-107">下面的代码示例演示如何使用<xref:System.Windows.Forms.ToolStrip>控件，创建复合控件，以模拟**导航窗格中**Microsoft Outlook® 提供的。</span><span class="sxs-lookup"><span data-stu-id="910c5-107">The following code example demonstrates how to use <xref:System.Windows.Forms.ToolStrip> controls to create a composite control that mimics the **Navigation Pane** provided by Microsoft® Outlook®.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.StackView#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.StackView#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="910c5-108">编译代码</span><span class="sxs-lookup"><span data-stu-id="910c5-108">Compiling the Code</span></span>  
 <span data-ttu-id="910c5-109">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="910c5-109">This example requires:</span></span>  
  
-   <span data-ttu-id="910c5-110">对 System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="910c5-110">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="910c5-111">有关从 [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] 或 [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] 的命令行生成此示例的信息，请参阅[从命令行生成](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[在命令行上使用 csc.exe 生成](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="910c5-111">For information about building this example from the command line for [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] or [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="910c5-112">还可以通过将代码粘贴到新项目，在 [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] 中生成此示例。</span><span class="sxs-lookup"><span data-stu-id="910c5-112">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="910c5-113">另请参阅[演练：创建具有专业样式的 ToolStrip 控件](http://msdn.microsoft.com/library/ms233664\(v=vs.110\))。</span><span class="sxs-lookup"><span data-stu-id="910c5-113">Also see [Walkthrough: Creating a Professionally Styled ToolStrip Control](http://msdn.microsoft.com/library/ms233664\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="910c5-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="910c5-114">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.StatusStrip>  
 [<span data-ttu-id="910c5-115">ToolStrip 控件</span><span class="sxs-lookup"><span data-stu-id="910c5-115">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)  
 [<span data-ttu-id="910c5-116">如何：向窗体提供标准菜单项</span><span class="sxs-lookup"><span data-stu-id="910c5-116">How to: Provide Standard Menu Items to a Form</span></span>](../../../../docs/framework/winforms/controls/how-to-provide-standard-menu-items-to-a-form.md)
