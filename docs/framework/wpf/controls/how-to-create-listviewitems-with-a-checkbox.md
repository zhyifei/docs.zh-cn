---
title: 如何：使用 CheckBox 创建 ListViewItem
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], ListView
- controls [WPF], CheckBox
- ListView controls [WPF], CheckBox controls
- CheckBox control [WPF], ListView control
ms.assetid: f6d66c7f-906c-4f65-a55a-0ede9d00e26a
ms.openlocfilehash: b09d5ad11b0961febf524cec1e19cb1e59832e44
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59083097"
---
# <a name="how-to-create-listviewitems-with-a-checkbox"></a><span data-ttu-id="d7e79-102">如何：使用 CheckBox 创建 ListViewItem</span><span class="sxs-lookup"><span data-stu-id="d7e79-102">How to: Create ListViewItems with a CheckBox</span></span>
<span data-ttu-id="d7e79-103">此示例演示如何显示的列<xref:System.Windows.Controls.CheckBox>中的控件<xref:System.Windows.Controls.ListView>控件，它使用<xref:System.Windows.Controls.GridView>。</span><span class="sxs-lookup"><span data-stu-id="d7e79-103">This example shows how to display a column of <xref:System.Windows.Controls.CheckBox> controls in a <xref:System.Windows.Controls.ListView> control that uses a <xref:System.Windows.Controls.GridView>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7e79-104">示例</span><span class="sxs-lookup"><span data-stu-id="d7e79-104">Example</span></span>  
 <span data-ttu-id="d7e79-105">若要创建包含的列<xref:System.Windows.Controls.CheckBox>中的控件<xref:System.Windows.Controls.ListView>，创建<xref:System.Windows.DataTemplate>，其中包含<xref:System.Windows.Controls.CheckBox>。</span><span class="sxs-lookup"><span data-stu-id="d7e79-105">To create a column that contains <xref:System.Windows.Controls.CheckBox> controls in a <xref:System.Windows.Controls.ListView>, create a <xref:System.Windows.DataTemplate> that contains a <xref:System.Windows.Controls.CheckBox>.</span></span> <span data-ttu-id="d7e79-106">然后设置<xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A>的<xref:System.Windows.Controls.GridViewColumn>到<xref:System.Windows.DataTemplate>。</span><span class="sxs-lookup"><span data-stu-id="d7e79-106">Then set the <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> of a <xref:System.Windows.Controls.GridViewColumn> to the <xref:System.Windows.DataTemplate>.</span></span>  
  
 <span data-ttu-id="d7e79-107">下面的示例演示<xref:System.Windows.DataTemplate>，其中包含<xref:System.Windows.Controls.CheckBox>。</span><span class="sxs-lookup"><span data-stu-id="d7e79-107">The following example shows a <xref:System.Windows.DataTemplate> that contains a <xref:System.Windows.Controls.CheckBox>.</span></span> <span data-ttu-id="d7e79-108">该示例将绑定<xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A>的属性<xref:System.Windows.Controls.CheckBox>到<xref:System.Windows.Controls.ListBoxItem.IsSelected%2A>属性值为<xref:System.Windows.Controls.ListViewItem>包含它。</span><span class="sxs-lookup"><span data-stu-id="d7e79-108">The example binds the <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> property of the <xref:System.Windows.Controls.CheckBox> to the <xref:System.Windows.Controls.ListBoxItem.IsSelected%2A> property value of the <xref:System.Windows.Controls.ListViewItem> that contains it.</span></span> <span data-ttu-id="d7e79-109">因此，当<xref:System.Windows.Controls.ListViewItem>，其中包含<xref:System.Windows.Controls.CheckBox>已选中<xref:System.Windows.Controls.CheckBox>检查。</span><span class="sxs-lookup"><span data-stu-id="d7e79-109">Therefore, when the <xref:System.Windows.Controls.ListViewItem> that contains the <xref:System.Windows.Controls.CheckBox> is selected, the <xref:System.Windows.Controls.CheckBox> is checked.</span></span>  
  
 [!code-xaml[ListViewChkBox#CheckBoxDataTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#checkboxdatatemplate)]  
  
 <span data-ttu-id="d7e79-110">下面的示例演示如何创建一列<xref:System.Windows.Controls.CheckBox>控件。</span><span class="sxs-lookup"><span data-stu-id="d7e79-110">The following example shows how to create a column of <xref:System.Windows.Controls.CheckBox> controls.</span></span> <span data-ttu-id="d7e79-111">若要将列，该示例设置<xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A>的属性<xref:System.Windows.Controls.GridViewColumn>到<xref:System.Windows.DataTemplate>。</span><span class="sxs-lookup"><span data-stu-id="d7e79-111">To make the column, the example sets the <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> property of the <xref:System.Windows.Controls.GridViewColumn> to the <xref:System.Windows.DataTemplate>.</span></span>  
  
 [!code-xaml[ListViewChkBox#GridViewColumnCheckBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#gridviewcolumncheckbox)]  
  
## <a name="see-also"></a><span data-ttu-id="d7e79-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="d7e79-112">See also</span></span>

- <xref:System.Windows.Controls.Control>
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="d7e79-113">ListView 概述</span><span class="sxs-lookup"><span data-stu-id="d7e79-113">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="d7e79-114">帮助主题</span><span class="sxs-lookup"><span data-stu-id="d7e79-114">How-to Topics</span></span>](listview-how-to-topics.md)
- [<span data-ttu-id="d7e79-115">GridView 概述</span><span class="sxs-lookup"><span data-stu-id="d7e79-115">GridView Overview</span></span>](gridview-overview.md)
