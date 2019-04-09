---
title: 如何：将 ContextMenuStrip 与控件相关联
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- context menus [Windows Forms], relating
- ContextMenuStrips [Windows Forms], associating with controls
- context menus [Windows Forms], associating with controls
- ContextMenuStrips [Windows Forms], relating
ms.assetid: 6fc40a42-5d69-427f-aa30-0a146193226b
ms.openlocfilehash: 4e39769621c46ead92076489014f6e0e9dc7863d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59122364"
---
# <a name="how-to-associate-a-contextmenustrip-with-a-control"></a><span data-ttu-id="f3d52-102">如何：将 ContextMenuStrip 与控件相关联</span><span class="sxs-lookup"><span data-stu-id="f3d52-102">How to: Associate a ContextMenuStrip with a Control</span></span>
<span data-ttu-id="f3d52-103">创建控件和快捷菜单后，使用以下过程在用户右键单击控件时显示给定的快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="f3d52-103">After creating your controls and shortcut menus, use the following procedures to display a given shortcut menu when the user right-clicks the control.</span></span> <span data-ttu-id="f3d52-104">这些过程将 <xref:System.Windows.Forms.ContextMenuStrip> 与 Windows 窗体和 <xref:System.Windows.Forms.ToolStrip> 控件相关联。</span><span class="sxs-lookup"><span data-stu-id="f3d52-104">These procedures associate a <xref:System.Windows.Forms.ContextMenuStrip> with a Windows Form and with a <xref:System.Windows.Forms.ToolStrip> control.</span></span>  
  
### <a name="to-associate-a-contextmenustrip-with-a-windows-form"></a><span data-ttu-id="f3d52-105">将 ContextMenuStrip 与 Windows 窗体关联</span><span class="sxs-lookup"><span data-stu-id="f3d52-105">To associate a ContextMenuStrip with a Windows Form</span></span>  
  
1.  <span data-ttu-id="f3d52-106">将 <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> 属性设置为关联的 <xref:System.Windows.Forms.ContextMenuStrip> 的名称。</span><span class="sxs-lookup"><span data-stu-id="f3d52-106">Set the <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> property to the name of the associated <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>  
  
### <a name="to-associate-a-contextmenustrip-with-a-toolstrip-control"></a><span data-ttu-id="f3d52-107">将 ContextMenuStrip 与 ToolStrip 控件关联</span><span class="sxs-lookup"><span data-stu-id="f3d52-107">To associate a ContextMenuStrip with a ToolStrip control</span></span>  
  
1.  <span data-ttu-id="f3d52-108">将控件的 <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> 属性设置为关联的 <xref:System.Windows.Forms.ContextMenuStrip> 的名称。</span><span class="sxs-lookup"><span data-stu-id="f3d52-108">Set the control's <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> property to the name of the associated <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3d52-109">示例</span><span class="sxs-lookup"><span data-stu-id="f3d52-109">Example</span></span>  
 <span data-ttu-id="f3d52-110">下面的代码示例创建了 Windows 窗体和 <xref:System.Windows.Forms.ToolStrip>，并将不同的 <xref:System.Windows.Forms.ContextMenuStrip> 与其中每个控件关联。</span><span class="sxs-lookup"><span data-stu-id="f3d52-110">The following code example creates a Windows Form and a <xref:System.Windows.Forms.ToolStrip>, and associates a different <xref:System.Windows.Forms.ContextMenuStrip> control with each of them.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ContextMenuStrip#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ContextMenuStrip/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ContextMenuStrip#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ContextMenuStrip/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f3d52-111">编译代码</span><span class="sxs-lookup"><span data-stu-id="f3d52-111">Compiling the Code</span></span>  
 <span data-ttu-id="f3d52-112">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="f3d52-112">This example requires:</span></span>  
  
-   <span data-ttu-id="f3d52-113">对 System、System.Data、System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="f3d52-113">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="f3d52-114">Visual Basic 或 Visual C# 生成命令行中的此示例的信息，请参阅[从命令行生成](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[命令行上使用 csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="f3d52-114">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="f3d52-115">也可以通过将代码粘贴到新的项目中生成此示例在 Visual Studio 中。</span><span class="sxs-lookup"><span data-stu-id="f3d52-115">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3d52-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="f3d52-116">See also</span></span>

- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.Control.ContextMenuStrip%2A>
- <xref:System.Windows.Forms.ToolStrip>
- [<span data-ttu-id="f3d52-117">如何：向 ContextMenuStrip 添加菜单项</span><span class="sxs-lookup"><span data-stu-id="f3d52-117">How to: Add Menu Items to a ContextMenuStrip</span></span>](how-to-add-menu-items-to-a-contextmenustrip.md)
- [<span data-ttu-id="f3d52-118">ContextMenuStrip 控件</span><span class="sxs-lookup"><span data-stu-id="f3d52-118">ContextMenuStrip Control</span></span>](contextmenustrip-control.md)
