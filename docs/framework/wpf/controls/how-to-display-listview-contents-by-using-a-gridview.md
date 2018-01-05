---
title: "如何：使用 GridView 显示 ListView 内容"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ListView controls [WPF], displaying contents with GridView
- GridView [WPF], displaying ListView contents
ms.assetid: 5bc1e767-ab46-4f14-bd41-3d5d39e1d000
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ee2885868c07b00f16290b6414e7f7bdd64fd68c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-display-listview-contents-by-using-a-gridview"></a><span data-ttu-id="7043d-102">如何：使用 GridView 显示 ListView 内容</span><span class="sxs-lookup"><span data-stu-id="7043d-102">How to: Display ListView Contents by Using a GridView</span></span>
<span data-ttu-id="7043d-103">此示例演示如何定义<xref:System.Windows.Controls.GridView>视图模式<xref:System.Windows.Controls.ListView>控件。</span><span class="sxs-lookup"><span data-stu-id="7043d-103">This example shows how to define a <xref:System.Windows.Controls.GridView> view mode for a <xref:System.Windows.Controls.ListView> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7043d-104">示例</span><span class="sxs-lookup"><span data-stu-id="7043d-104">Example</span></span>  
 <span data-ttu-id="7043d-105">你可以定义的视图模式<xref:System.Windows.Controls.GridView>通过指定<xref:System.Windows.Controls.GridViewColumn>对象。</span><span class="sxs-lookup"><span data-stu-id="7043d-105">You can define the view mode of a <xref:System.Windows.Controls.GridView> by specifying <xref:System.Windows.Controls.GridViewColumn> objects.</span></span> <span data-ttu-id="7043d-106">下面的示例演示如何定义<xref:System.Windows.Controls.GridViewColumn>对象绑定到为指定的数据内容<xref:System.Windows.Controls.ListView>控件。</span><span class="sxs-lookup"><span data-stu-id="7043d-106">The following example shows how to define <xref:System.Windows.Controls.GridViewColumn> objects that bind to the data content that is specified for the <xref:System.Windows.Controls.ListView> control.</span></span> <span data-ttu-id="7043d-107">这<xref:System.Windows.Controls.GridView>示例指定三个<xref:System.Windows.Controls.GridViewColumn>映射到的对象`FirstName`， `LastName`，和`EmployeeNumber`字段`EmployeeInfoDataSource`设置为<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>的<xref:System.Windows.Controls.ListView>控件。</span><span class="sxs-lookup"><span data-stu-id="7043d-107">This <xref:System.Windows.Controls.GridView> example specifies three <xref:System.Windows.Controls.GridViewColumn> objects that map to the `FirstName`, `LastName`, and `EmployeeNumber` fields of the `EmployeeInfoDataSource` that is set as the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> of the <xref:System.Windows.Controls.ListView> control.</span></span>  
  
 [!code-xaml[ListViewCode#ListViewEmployee](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 <span data-ttu-id="7043d-108">下图显示了此示例中的显示方式。</span><span class="sxs-lookup"><span data-stu-id="7043d-108">The following illustration shows how this example appears.</span></span>  
  
 <span data-ttu-id="7043d-109">![具有 GridView 输出的 ListView](../../../../docs/framework/wpf/controls/media/listviewgridview.JPG "ListViewGridView")</span><span class="sxs-lookup"><span data-stu-id="7043d-109">![ListView with GridView output](../../../../docs/framework/wpf/controls/media/listviewgridview.JPG "ListViewGridView")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7043d-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="7043d-110">See Also</span></span>  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [<span data-ttu-id="7043d-111">ListView 概述</span><span class="sxs-lookup"><span data-stu-id="7043d-111">ListView Overview</span></span>](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [<span data-ttu-id="7043d-112">GridView 概述</span><span class="sxs-lookup"><span data-stu-id="7043d-112">GridView Overview</span></span>](../../../../docs/framework/wpf/controls/gridview-overview.md)  
 [<span data-ttu-id="7043d-113">帮助主题</span><span class="sxs-lookup"><span data-stu-id="7043d-113">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)
