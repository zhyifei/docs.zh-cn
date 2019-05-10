---
title: 如何：向窗体提供标准菜单项
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- menu items [Windows Forms], standard
- ToolStrip control [Windows Forms]
ms.assetid: 75db9126-e70c-4e81-921d-b83c0a4a9f50
ms.openlocfilehash: 530e4185b065c9483f112146c496860f2c8a52c1
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662324"
---
# <a name="how-to-provide-standard-menu-items-to-a-form"></a><span data-ttu-id="73aa1-102">如何：向窗体提供标准菜单项</span><span class="sxs-lookup"><span data-stu-id="73aa1-102">How to: Provide Standard Menu Items to a Form</span></span>
<span data-ttu-id="73aa1-103">可使用 <xref:System.Windows.Forms.MenuStrip> 控件向窗体提供标准菜单。</span><span class="sxs-lookup"><span data-stu-id="73aa1-103">You can provide a standard menu for your forms with the <xref:System.Windows.Forms.MenuStrip> control.</span></span>  
  
 <span data-ttu-id="73aa1-104">没有对此功能在 Visual Studio 中的广泛支持。</span><span class="sxs-lookup"><span data-stu-id="73aa1-104">There is extensive support for this feature in Visual Studio.</span></span>  
  
 <span data-ttu-id="73aa1-105">另请参阅[演练：向窗体提供标准菜单项](walkthrough-providing-standard-menu-items-to-a-form.md)。</span><span class="sxs-lookup"><span data-stu-id="73aa1-105">Also see [Walkthrough: Providing Standard Menu Items to a Form](walkthrough-providing-standard-menu-items-to-a-form.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="73aa1-106">示例</span><span class="sxs-lookup"><span data-stu-id="73aa1-106">Example</span></span>  
 <span data-ttu-id="73aa1-107">下面的代码示例演示了如何使用 <xref:System.Windows.Forms.MenuStrip> 控件创建带有标准菜单的窗体。</span><span class="sxs-lookup"><span data-stu-id="73aa1-107">The following code example demonstrates how to use a <xref:System.Windows.Forms.MenuStrip> control to create a form with a standard menu.</span></span> <span data-ttu-id="73aa1-108"><xref:System.Windows.Forms.StatusStrip> 控件中将显示菜单项选择。</span><span class="sxs-lookup"><span data-stu-id="73aa1-108">Menu item selections are displayed in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="73aa1-109">编译代码</span><span class="sxs-lookup"><span data-stu-id="73aa1-109">Compiling the Code</span></span>  
 <span data-ttu-id="73aa1-110">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="73aa1-110">This example requires:</span></span>  
  
- <span data-ttu-id="73aa1-111">对 System、System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="73aa1-111">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="73aa1-112">Visual Basic 或 Visual C# 生成命令行中的此示例的信息，请参阅[从命令行生成](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[命令行上使用 csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="73aa1-112">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="73aa1-113">也可以通过将代码粘贴到新的项目中生成此示例在 Visual Studio 中。</span><span class="sxs-lookup"><span data-stu-id="73aa1-113">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73aa1-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="73aa1-114">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="73aa1-115">MenuStrip 控件</span><span class="sxs-lookup"><span data-stu-id="73aa1-115">MenuStrip Control</span></span>](menustrip-control-windows-forms.md)
