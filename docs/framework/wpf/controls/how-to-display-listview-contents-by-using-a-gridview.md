---
title: 如何：使用 GridView 显示 ListView 内容
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], displaying contents with GridView
- GridView [WPF], displaying ListView contents
ms.assetid: 5bc1e767-ab46-4f14-bd41-3d5d39e1d000
ms.openlocfilehash: 9b467c95d541c326a41d1ed4bd9eb5c87e25bd5c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61910489"
---
# <a name="how-to-display-listview-contents-by-using-a-gridview"></a><span data-ttu-id="8fb85-102">如何：使用 GridView 显示 ListView 内容</span><span class="sxs-lookup"><span data-stu-id="8fb85-102">How to: Display ListView Contents by Using a GridView</span></span>
<span data-ttu-id="8fb85-103">此示例演示如何定义<xref:System.Windows.Controls.GridView>视图模式<xref:System.Windows.Controls.ListView>控件。</span><span class="sxs-lookup"><span data-stu-id="8fb85-103">This example shows how to define a <xref:System.Windows.Controls.GridView> view mode for a <xref:System.Windows.Controls.ListView> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8fb85-104">示例</span><span class="sxs-lookup"><span data-stu-id="8fb85-104">Example</span></span>  
 <span data-ttu-id="8fb85-105">您可以定义的视图模式<xref:System.Windows.Controls.GridView>通过指定<xref:System.Windows.Controls.GridViewColumn>对象。</span><span class="sxs-lookup"><span data-stu-id="8fb85-105">You can define the view mode of a <xref:System.Windows.Controls.GridView> by specifying <xref:System.Windows.Controls.GridViewColumn> objects.</span></span> <span data-ttu-id="8fb85-106">下面的示例演示如何定义<xref:System.Windows.Controls.GridViewColumn>绑定到为指定的数据内容的对象<xref:System.Windows.Controls.ListView>控件。</span><span class="sxs-lookup"><span data-stu-id="8fb85-106">The following example shows how to define <xref:System.Windows.Controls.GridViewColumn> objects that bind to the data content that is specified for the <xref:System.Windows.Controls.ListView> control.</span></span> <span data-ttu-id="8fb85-107">这<xref:System.Windows.Controls.GridView>的示例指定三个<xref:System.Windows.Controls.GridViewColumn>映射到的对象`FirstName`， `LastName`，并`EmployeeNumber`的字段`EmployeeInfoDataSource`设置为<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>的<xref:System.Windows.Controls.ListView>控件。</span><span class="sxs-lookup"><span data-stu-id="8fb85-107">This <xref:System.Windows.Controls.GridView> example specifies three <xref:System.Windows.Controls.GridViewColumn> objects that map to the `FirstName`, `LastName`, and `EmployeeNumber` fields of the `EmployeeInfoDataSource` that is set as the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> of the <xref:System.Windows.Controls.ListView> control.</span></span>  
  
 [!code-xaml[ListViewCode#ListViewEmployee](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 <span data-ttu-id="8fb85-108">下图显示了此示例中的显示方式。</span><span class="sxs-lookup"><span data-stu-id="8fb85-108">The following illustration shows how this example appears.</span></span>  
  
 ![显示具有 GridView 输出的 ListView 的屏幕截图。](./media/gridview-overview/listview-gridview-output.jpg)  
  
## <a name="see-also"></a><span data-ttu-id="8fb85-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="8fb85-110">See also</span></span>

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="8fb85-111">ListView 概述</span><span class="sxs-lookup"><span data-stu-id="8fb85-111">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="8fb85-112">GridView 概述</span><span class="sxs-lookup"><span data-stu-id="8fb85-112">GridView Overview</span></span>](gridview-overview.md)
- [<span data-ttu-id="8fb85-113">帮助主题</span><span class="sxs-lookup"><span data-stu-id="8fb85-113">How-to Topics</span></span>](listview-how-to-topics.md)
