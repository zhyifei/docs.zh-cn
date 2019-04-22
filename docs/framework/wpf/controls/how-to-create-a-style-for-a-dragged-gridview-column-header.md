---
title: 如何：创建拖动的 GridView 列标头的样式
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], styling
ms.assetid: 0b999645-0313-4b33-80b9-19ece08b5459
ms.openlocfilehash: dbcdd38e0397b8e637aff962420a2959f33203df
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59090090"
---
# <a name="how-to-create-a-style-for-a-dragged-gridview-column-header"></a><span data-ttu-id="cd1b8-102">如何：创建拖动的 GridView 列标头的样式</span><span class="sxs-lookup"><span data-stu-id="cd1b8-102">How to: Create a Style for a Dragged GridView Column Header</span></span>
<span data-ttu-id="cd1b8-103">此示例演示如何更改外观的拖动<xref:System.Windows.Controls.GridViewColumnHeader>当用户更改的列位置。</span><span class="sxs-lookup"><span data-stu-id="cd1b8-103">This example shows how to change the appearance of a dragged <xref:System.Windows.Controls.GridViewColumnHeader> when the user changes the position of a column.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cd1b8-104">示例</span><span class="sxs-lookup"><span data-stu-id="cd1b8-104">Example</span></span>  
 <span data-ttu-id="cd1b8-105">当将列标题拖到其他位置<xref:System.Windows.Controls.ListView>，它使用<xref:System.Windows.Controls.GridView>作为其视图模式，在列移至新位置。</span><span class="sxs-lookup"><span data-stu-id="cd1b8-105">When you drag a column header to another location in a <xref:System.Windows.Controls.ListView> that uses <xref:System.Windows.Controls.GridView> for its view mode, the column moves to the new position.</span></span> <span data-ttu-id="cd1b8-106">当您拖动列标题时，标头的浮点副本会显示除了原始标头。</span><span class="sxs-lookup"><span data-stu-id="cd1b8-106">While you are dragging the column header, a floating copy of the header appears in addition to the original header.</span></span> <span data-ttu-id="cd1b8-107">中的列标题<xref:System.Windows.Controls.GridView>为由<xref:System.Windows.Controls.GridViewColumnHeader>对象。</span><span class="sxs-lookup"><span data-stu-id="cd1b8-107">A column header in a <xref:System.Windows.Controls.GridView> is represented by a <xref:System.Windows.Controls.GridViewColumnHeader> object.</span></span>  
  
 <span data-ttu-id="cd1b8-108">若要自定义这两个浮点型和原始标头的外观，可以设置<xref:System.Windows.Controls.ControlTemplate.Triggers%2A>修改<xref:System.Windows.Controls.GridViewColumnHeader> <xref:System.Windows.Style>。</span><span class="sxs-lookup"><span data-stu-id="cd1b8-108">To customize the appearance of both the floating and original headers, you can set <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> to modify the <xref:System.Windows.Controls.GridViewColumnHeader> <xref:System.Windows.Style>.</span></span> <span data-ttu-id="cd1b8-109">这些<xref:System.Windows.Controls.ControlTemplate.Triggers%2A>时应用<xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A>属性值是`true`并且<xref:System.Windows.Controls.GridViewColumnHeader.Role%2A>属性值是<xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>。</span><span class="sxs-lookup"><span data-stu-id="cd1b8-109">These <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> are applied when the <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> property value is `true` and the <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> property value is <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>.</span></span>  
  
 <span data-ttu-id="cd1b8-110">当用户按下鼠标左键和鼠标悬停在按住<xref:System.Windows.Controls.GridViewColumnHeader>，则<xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A>属性值更改为`true`。</span><span class="sxs-lookup"><span data-stu-id="cd1b8-110">When the user presses the mouse button and holds it down while the mouse pauses on the <xref:System.Windows.Controls.GridViewColumnHeader>, the <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> property value changes to `true`.</span></span> <span data-ttu-id="cd1b8-111">同样，当用户开始拖动操作时，才<xref:System.Windows.Controls.GridViewColumnHeader.Role%2A>属性更改为<xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>。</span><span class="sxs-lookup"><span data-stu-id="cd1b8-111">Likewise, when the user begins the drag operation, the <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> property changes to <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>.</span></span>  
  
 <span data-ttu-id="cd1b8-112">下面的示例演示如何设置<xref:System.Windows.Controls.ControlTemplate.Triggers%2A>若要更改<xref:System.Windows.Controls.Control.Foreground%2A>和<xref:System.Windows.Controls.Control.Background%2A>原始窗口和浮动的标头时用户将列拖至新位置的颜色。</span><span class="sxs-lookup"><span data-stu-id="cd1b8-112">The following example shows how to set <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> to change the <xref:System.Windows.Controls.Control.Foreground%2A> and <xref:System.Windows.Controls.Control.Background%2A> colors of the original and floating headers when the user drags a column to a new position.</span></span>  
  
 [!code-xaml[ListViewHeaderRoleStyle#GVCHControlTemplateStart](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#gvchcontroltemplatestart)]  
[!code-xaml[ListViewHeaderRoleStyle#ControlTemplateTriggersStart](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#controltemplatetriggersstart)]  
[!code-xaml[ListViewHeaderRoleStyle#IsPressed](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#ispressed)]  
[!code-xaml[ListViewHeaderRoleStyle#Floating](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#floating)]  
[!code-xaml[ListViewHeaderRoleStyle#ControlTemplateTriggersEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#controltemplatetriggersend)]  
[!code-xaml[ListViewHeaderRoleStyle#GVCHControlTemplateEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#gvchcontroltemplateend)]  
  
## <a name="see-also"></a><span data-ttu-id="cd1b8-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="cd1b8-113">See also</span></span>

- <xref:System.Windows.Controls.GridViewColumnHeader>
- <xref:System.Windows.Controls.GridViewColumnHeaderRole>
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="cd1b8-114">帮助主题</span><span class="sxs-lookup"><span data-stu-id="cd1b8-114">How-to Topics</span></span>](listview-how-to-topics.md)
- [<span data-ttu-id="cd1b8-115">ListView 概述</span><span class="sxs-lookup"><span data-stu-id="cd1b8-115">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="cd1b8-116">GridView 概述</span><span class="sxs-lookup"><span data-stu-id="cd1b8-116">GridView Overview</span></span>](gridview-overview.md)
