---
title: 如何：创建具有菜单合并功能和 ToolStrip 控件的 MDI 窗体
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStripPanel control [Windows Forms]
- ToolStrip control [Windows Forms]
- MenuStrip control [Windows Forms]
ms.assetid: 64992ed9-44af-4baf-b45f-863e6ab35711
ms.openlocfilehash: 0edcc27968c55908cda0e881ed66f83323316711
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591301"
---
# <a name="how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls"></a><span data-ttu-id="8011d-102">如何：创建具有菜单合并功能和 ToolStrip 控件的 MDI 窗体</span><span class="sxs-lookup"><span data-stu-id="8011d-102">How to: Create an MDI Form with Menu Merging and ToolStrip Controls</span></span>
<span data-ttu-id="8011d-103"><xref:System.Windows.Forms?displayProperty=nameWithType> 命名空间支持多文档界面 (MDI) 应用程序，而 <xref:System.Windows.Forms.MenuStrip> 控件支持菜单合并。</span><span class="sxs-lookup"><span data-stu-id="8011d-103">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace supports multiple document interface (MDI) applications, and the <xref:System.Windows.Forms.MenuStrip> control supports menu merging.</span></span> <span data-ttu-id="8011d-104">MDI 窗体还可支持 <xref:System.Windows.Forms.ToolStrip> 控件。</span><span class="sxs-lookup"><span data-stu-id="8011d-104">MDI forms can also <xref:System.Windows.Forms.ToolStrip> controls.</span></span>  
  
 <span data-ttu-id="8011d-105">没有对此功能在 Visual Studio 中的广泛支持。</span><span class="sxs-lookup"><span data-stu-id="8011d-105">There is extensive support for this feature in Visual Studio.</span></span>  
  
 <span data-ttu-id="8011d-106">另请参阅[演练：创建具有菜单合并功能和 ToolStrip 控件的 MDI 窗体](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="8011d-106">Also see [Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8011d-107">示例</span><span class="sxs-lookup"><span data-stu-id="8011d-107">Example</span></span>  
 <span data-ttu-id="8011d-108">以下代码示例演示如何将 <xref:System.Windows.Forms.ToolStripPanel> 控件和 MDI 窗体配合使用。</span><span class="sxs-lookup"><span data-stu-id="8011d-108">The following code example demonstrates how to use <xref:System.Windows.Forms.ToolStripPanel> controls with an MDI form.</span></span> <span data-ttu-id="8011d-109">此窗体还支持菜单与子菜单合并。</span><span class="sxs-lookup"><span data-stu-id="8011d-109">The form also supports menu merging with child menus.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8011d-110">编译代码</span><span class="sxs-lookup"><span data-stu-id="8011d-110">Compiling the Code</span></span>  
 <span data-ttu-id="8011d-111">此代码示例需要：</span><span class="sxs-lookup"><span data-stu-id="8011d-111">This code example requires:</span></span>  
  
- <span data-ttu-id="8011d-112">对 System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="8011d-112">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8011d-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="8011d-113">See also</span></span>

- [<span data-ttu-id="8011d-114">ToolStrip 控件</span><span class="sxs-lookup"><span data-stu-id="8011d-114">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
