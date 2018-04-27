---
title: 如何：将 ContextMenuStrip 与控件关联
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- context menus [Windows Forms], relating
- ContextMenuStrips [Windows Forms], associating with controls
- context menus [Windows Forms], associating with controls
- ContextMenuStrips [Windows Forms], relating
ms.assetid: 6fc40a42-5d69-427f-aa30-0a146193226b
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 04b5394a5e5f64228635d7c23df150df9391fa44
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2018
---
# <a name="how-to-associate-a-contextmenustrip-with-a-control"></a><span data-ttu-id="b2ace-102">如何：将 ContextMenuStrip 与控件关联</span><span class="sxs-lookup"><span data-stu-id="b2ace-102">How to: Associate a ContextMenuStrip with a Control</span></span>
<span data-ttu-id="b2ace-103">创建控件和快捷菜单后，使用以下过程在用户右键单击控件时显示给定的快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="b2ace-103">After creating your controls and shortcut menus, use the following procedures to display a given shortcut menu when the user right-clicks the control.</span></span> <span data-ttu-id="b2ace-104">这些过程将 <xref:System.Windows.Forms.ContextMenuStrip> 与 Windows 窗体和 <xref:System.Windows.Forms.ToolStrip> 控件相关联。</span><span class="sxs-lookup"><span data-stu-id="b2ace-104">These procedures associate a <xref:System.Windows.Forms.ContextMenuStrip> with a Windows Form and with a <xref:System.Windows.Forms.ToolStrip> control.</span></span>  
  
### <a name="to-associate-a-contextmenustrip-with-a-windows-form"></a><span data-ttu-id="b2ace-105">将 ContextMenuStrip 与 Windows 窗体关联</span><span class="sxs-lookup"><span data-stu-id="b2ace-105">To associate a ContextMenuStrip with a Windows Form</span></span>  
  
1.  <span data-ttu-id="b2ace-106">将 <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> 属性设置为关联的 <xref:System.Windows.Forms.ContextMenuStrip> 的名称。</span><span class="sxs-lookup"><span data-stu-id="b2ace-106">Set the <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> property to the name of the associated <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>  
  
### <a name="to-associate-a-contextmenustrip-with-a-toolstrip-control"></a><span data-ttu-id="b2ace-107">将 ContextMenuStrip 与 ToolStrip 控件关联</span><span class="sxs-lookup"><span data-stu-id="b2ace-107">To associate a ContextMenuStrip with a ToolStrip control</span></span>  
  
1.  <span data-ttu-id="b2ace-108">将控件的 <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> 属性设置为关联的 <xref:System.Windows.Forms.ContextMenuStrip> 的名称。</span><span class="sxs-lookup"><span data-stu-id="b2ace-108">Set the control's <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> property to the name of the associated <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2ace-109">示例</span><span class="sxs-lookup"><span data-stu-id="b2ace-109">Example</span></span>  
 <span data-ttu-id="b2ace-110">下面的代码示例创建了 Windows 窗体和 <xref:System.Windows.Forms.ToolStrip>，并将不同的 <xref:System.Windows.Forms.ContextMenuStrip> 与其中每个控件关联。</span><span class="sxs-lookup"><span data-stu-id="b2ace-110">The following code example creates a Windows Form and a <xref:System.Windows.Forms.ToolStrip>, and associates a different <xref:System.Windows.Forms.ContextMenuStrip> control with each of them.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ContextMenuStrip#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ContextMenuStrip/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ContextMenuStrip#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ContextMenuStrip/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b2ace-111">编译代码</span><span class="sxs-lookup"><span data-stu-id="b2ace-111">Compiling the Code</span></span>  
 <span data-ttu-id="b2ace-112">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="b2ace-112">This example requires:</span></span>  
  
-   <span data-ttu-id="b2ace-113">对 System、System.Data、System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="b2ace-113">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="b2ace-114">为 Visual Basic 或 Visual C# 中生成此示例从命令行有关的信息，请参阅[从命令行生成](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[命令行上使用 csc.exe 生成](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="b2ace-114">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="b2ace-115">你也可以通过将代码粘贴到新项目中生成 Visual Studio 中的此示例。</span><span class="sxs-lookup"><span data-stu-id="b2ace-115">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="b2ace-116">另请参阅 [如何：使用 Visual Studio 编译和运行完整的 Windows 窗体代码示例](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))。</span><span class="sxs-lookup"><span data-stu-id="b2ace-116">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2ace-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="b2ace-117">See Also</span></span>  
 <xref:System.Windows.Forms.ContextMenuStrip>  
 <xref:System.Windows.Forms.Control.ContextMenuStrip%2A>  
 <xref:System.Windows.Forms.ToolStrip>  
 [<span data-ttu-id="b2ace-118">如何：向 ContextMenuStrip 添加菜单项</span><span class="sxs-lookup"><span data-stu-id="b2ace-118">How to: Add Menu Items to a ContextMenuStrip</span></span>](../../../../docs/framework/winforms/controls/how-to-add-menu-items-to-a-contextmenustrip.md)  
 [<span data-ttu-id="b2ace-119">ContextMenuStrip 控件</span><span class="sxs-lookup"><span data-stu-id="b2ace-119">ContextMenuStrip Control</span></span>](../../../../docs/framework/winforms/controls/contextmenustrip-control.md)
