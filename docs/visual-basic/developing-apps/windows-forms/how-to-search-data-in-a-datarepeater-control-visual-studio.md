---
title: "如何：在 DataRepeater 控件中搜索数据 (Visual Studio)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, implementing search
- DataRepeater, searching data
ms.assetid: a8ab5d17-b94f-43c4-8dd7-d0450226d73f
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a3ed7138c142a83584ecd19ccaebe0e31e421ce3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-search-data-in-a-datarepeater-control-visual-studio"></a><span data-ttu-id="90bc2-102">如何：在 DataRepeater 控件中搜索数据 (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="90bc2-102">How to: Search Data in a DataRepeater Control (Visual Studio)</span></span>
<span data-ttu-id="90bc2-103">如果要使用<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>包含多个记录，你可能想让的用户搜索特定记录的控件。</span><span class="sxs-lookup"><span data-stu-id="90bc2-103">When you are using a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control that contains many records, you may want to let users search for a specific record.</span></span> <span data-ttu-id="90bc2-104">而不是在该控件本身中搜索数据，你可以通过查询基础实现搜索<xref:System.Windows.Forms.BindingSource>。</span><span class="sxs-lookup"><span data-stu-id="90bc2-104">Rather than searching the data in the control itself, you can implement a search by querying the underlying <xref:System.Windows.Forms.BindingSource>.</span></span> <span data-ttu-id="90bc2-105">如果找到该项，则可以使用<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CurrentItemIndex%2A>属性选择的项并滚动到视图。</span><span class="sxs-lookup"><span data-stu-id="90bc2-105">If the item is found, you can then use the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CurrentItemIndex%2A> property to select the item and scroll it into view.</span></span>  
  
### <a name="to-implement-search"></a><span data-ttu-id="90bc2-106">若要实现搜索</span><span class="sxs-lookup"><span data-stu-id="90bc2-106">To implement search</span></span>  
  
1.  <span data-ttu-id="90bc2-107">拖动<xref:System.Windows.Forms.TextBox>控件从**工具箱**拖到窗体包含<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。</span><span class="sxs-lookup"><span data-stu-id="90bc2-107">Drag a <xref:System.Windows.Forms.TextBox> control from the **Toolbox** onto the form that contains the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
2.  <span data-ttu-id="90bc2-108">在属性窗口中，更改**名称**属性**SearchTextBox**。</span><span class="sxs-lookup"><span data-stu-id="90bc2-108">In the Properties window, change the **Name** property to **SearchTextBox**.</span></span>  
  
3.  <span data-ttu-id="90bc2-109">拖动<xref:System.Windows.Forms.Button>控件从**工具箱**拖到窗体包含<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。</span><span class="sxs-lookup"><span data-stu-id="90bc2-109">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto the form that contains the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
4.  <span data-ttu-id="90bc2-110">在属性窗口中，更改**名称**属性**SearchButton**。</span><span class="sxs-lookup"><span data-stu-id="90bc2-110">In the Properties window, change the **Name** property to **SearchButton**.</span></span> <span data-ttu-id="90bc2-111">更改**文本**属性**搜索**。</span><span class="sxs-lookup"><span data-stu-id="90bc2-111">Change the **Text** property to **Search**.</span></span>  
  
5.  <span data-ttu-id="90bc2-112">双击 <xref:System.Windows.Forms.Button> 控件打开代码编辑器，并将以下代码添加到 `SearchButton_Click` 事件处理程序中。</span><span class="sxs-lookup"><span data-stu-id="90bc2-112">Double-click the <xref:System.Windows.Forms.Button> control to open the Code Editor, and add the following code to the `SearchButton_Click` event handler.</span></span>  
  
     [!code-vb[VbPowerPacksDataRepeaterSearch#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-search-data-in-a-datarepeater-control-visual-studio_1.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterSearch#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-search-data-in-a-datarepeater-control-visual-studio_1.cs)]  
  
     <span data-ttu-id="90bc2-113">替换*ProductsBindingSource*同名的<xref:System.Windows.Forms.BindingSource>为你<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>，并将*ProductID*替换为你想要搜索的字段的名称。</span><span class="sxs-lookup"><span data-stu-id="90bc2-113">Replace *ProductsBindingSource* with the name of the <xref:System.Windows.Forms.BindingSource> for your <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, and replace *ProductID* with the name of the field that you want to search.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90bc2-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="90bc2-114">See Also</span></span>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [<span data-ttu-id="90bc2-115">DataRepeater 控件简介</span><span class="sxs-lookup"><span data-stu-id="90bc2-115">Introduction to the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="90bc2-116">DataRepeater 控件疑难解答</span><span class="sxs-lookup"><span data-stu-id="90bc2-116">Troubleshooting the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="90bc2-117">如何：更改 DataRepeater 控件的外观</span><span class="sxs-lookup"><span data-stu-id="90bc2-117">How to: Change the Appearance of a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)
