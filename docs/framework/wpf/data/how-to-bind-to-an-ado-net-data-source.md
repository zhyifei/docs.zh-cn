---
title: "如何：绑定到 ADO.NET 数据源"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], binding to ADO.NET data sources
- ADO.NET data sources [WPF], binding to
- binding [WPF], to ADO.NET data sources
ms.assetid: a70c6d7b-7b38-4fdf-b655-4804db7c8315
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0eb555bb9f21385d2d0b66fe0dd39112c8350dec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-bind-to-an-adonet-data-source"></a><span data-ttu-id="fb48b-102">如何：绑定到 ADO.NET 数据源</span><span class="sxs-lookup"><span data-stu-id="fb48b-102">How to: Bind to an ADO.NET Data Source</span></span>
<span data-ttu-id="fb48b-103">此示例演示如何将绑定[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<xref:System.Windows.Controls.ListBox>控制转移到[!INCLUDE[TLA#tla_adonet](../../../../includes/tlasharptla-adonet-md.md)] `DataSet`。</span><span class="sxs-lookup"><span data-stu-id="fb48b-103">This example shows how to bind a [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Controls.ListBox> control to an [!INCLUDE[TLA#tla_adonet](../../../../includes/tlasharptla-adonet-md.md)] `DataSet`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fb48b-104">示例</span><span class="sxs-lookup"><span data-stu-id="fb48b-104">Example</span></span>  
 <span data-ttu-id="fb48b-105">在本示例中，`OleDbConnection` 对象用于连接到数据源，该数据源是在连接字符串中指定的 `Access MDB` 文件。</span><span class="sxs-lookup"><span data-stu-id="fb48b-105">In this example, an `OleDbConnection` object is used to connect to the data source which is an `Access MDB` file that is specified in the connection string.</span></span> <span data-ttu-id="fb48b-106">建立连接后，会创建一个 `OleDbDataAdpater` 对象。</span><span class="sxs-lookup"><span data-stu-id="fb48b-106">After the connection is established, an `OleDbDataAdpater` object is created.</span></span> <span data-ttu-id="fb48b-107">`OleDbDataAdpater` 对象执行一个 select [!INCLUDE[TLA#tla_sql](../../../../includes/tlasharptla-sql-md.md)] 语句，以便从数据库中检索记录集。</span><span class="sxs-lookup"><span data-stu-id="fb48b-107">The `OleDbDataAdpater` object executes a select [!INCLUDE[TLA#tla_sql](../../../../includes/tlasharptla-sql-md.md)] statement to retrieve the recordset from the database.</span></span> <span data-ttu-id="fb48b-108">通过调用 `OleDbDataAdapter` 的 `Fill` 方法，此 [!INCLUDE[TLA2#tla_sql](../../../../includes/tla2sharptla-sql-md.md)] 命令的结果存储在 `DataSet` 的 `DataTable` 中。</span><span class="sxs-lookup"><span data-stu-id="fb48b-108">The results from the [!INCLUDE[TLA2#tla_sql](../../../../includes/tla2sharptla-sql-md.md)] command are stored in a `DataTable` of the `DataSet` by calling the `Fill` method of the `OleDbDataAdapter`.</span></span> <span data-ttu-id="fb48b-109">本示例中，`DataTable` 命名为 `BookTable`。</span><span class="sxs-lookup"><span data-stu-id="fb48b-109">The `DataTable` in this example is named `BookTable`.</span></span> <span data-ttu-id="fb48b-110">然后，示例设置<xref:System.Windows.FrameworkElement.DataContext%2A>属性<xref:System.Windows.Controls.ListBox>到`DataSet`对象。</span><span class="sxs-lookup"><span data-stu-id="fb48b-110">The example then sets the <xref:System.Windows.FrameworkElement.DataContext%2A> property of the <xref:System.Windows.Controls.ListBox> to the `DataSet` object.</span></span>  
  
 [!code-csharp[ADODataSet#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 <span data-ttu-id="fb48b-111">然后，我们可以绑定<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>属性<xref:System.Windows.Controls.ListBox>到`BookTable`的`DataSet`:</span><span class="sxs-lookup"><span data-stu-id="fb48b-111">We can then bind the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property of the <xref:System.Windows.Controls.ListBox> to `BookTable` of the `DataSet`:</span></span>  
  
 [!code-xaml[ADODataSet#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="fb48b-112">`BookItemTemplate`是<xref:System.Windows.DataTemplate>定义数据的显示方式：</span><span class="sxs-lookup"><span data-stu-id="fb48b-112">`BookItemTemplate` is the <xref:System.Windows.DataTemplate> that defines how the data appears:</span></span>  
  
 [!code-xaml[ADODataSet#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml#3)]  
  
 <span data-ttu-id="fb48b-113">`IntColorConverter` 将 `int` 转换为颜色。</span><span class="sxs-lookup"><span data-stu-id="fb48b-113">The `IntColorConverter` converts an `int` to a color.</span></span> <span data-ttu-id="fb48b-114">此转换器，使用<xref:System.Windows.Controls.TextBlock.Background%2A>颜色的第三个<xref:System.Windows.Controls.TextBlock>会显示为绿色如果的值`NumPages`否则是小于 350 和红色。</span><span class="sxs-lookup"><span data-stu-id="fb48b-114">With the use of this converter, the <xref:System.Windows.Controls.TextBlock.Background%2A> color of the third <xref:System.Windows.Controls.TextBlock> appears green if the value of `NumPages` is less than 350 and red otherwise.</span></span> <span data-ttu-id="fb48b-115">此处未显示此转换器的实现。</span><span class="sxs-lookup"><span data-stu-id="fb48b-115">The implementation of the converter is not shown here.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb48b-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fb48b-116">See Also</span></span>  
 <xref:System.Windows.Data.BindingListCollectionView>  
 [<span data-ttu-id="fb48b-117">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="fb48b-117">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="fb48b-118">操作说明主题</span><span class="sxs-lookup"><span data-stu-id="fb48b-118">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
