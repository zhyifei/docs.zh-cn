---
title: "在 Windows 窗体 DataGridView 控件中实现实时数据加载的虚拟模式"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], just-in-time data loading
- data [Windows Forms], managing large data sets
- DataGridView control [Windows Forms], virtual mode
- just-in-time data loading
- DataGridView control [Windows Forms], large data sets
- virtual mode [Windows Forms], just-in-time data loading
ms.assetid: c2a052b9-423c-4ff7-91dc-d8c7c79345f6
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0bddac01a0d85ae985b54587619bcac6de5f966f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="implementing-virtual-mode-with-just-in-time-data-loading-in-the-windows-forms-datagridview-control"></a>在 Windows 窗体 DataGridView 控件中实现实时数据加载的虚拟模式
若要实现中的虚拟模式的其中一个原因<xref:System.Windows.Forms.DataGridView>控件是仅在需要时仅检索数据。 这称为*中实时数据加载*。  
  
 如果你正在使用远程数据库中非常大的表，例如，你可能想要通过检索数据所需的显示和检索其他数据，仅当用户滚动到视图中新行时避免启动延迟。 如果运行你的应用程序的客户端计算机具有有限的内存可用于存储数据，你可能还想要从数据库检索新值时丢弃未使用的数据。  
  
 下列各节描述如何使用<xref:System.Windows.Forms.DataGridView>中实时缓存使用的控件。  
  
 若要将代码复制本主题中的一个单独的清单，请参阅[如何： 实现虚拟模式在 Windows 窗体 DataGridView 控件中的实时数据加载](../../../../docs/framework/winforms/controls/virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md)。  
  
## <a name="the-form"></a>窗体  
 下面的代码示例定义一个包含一个只读的窗体<xref:System.Windows.Forms.DataGridView>与交互的控件`Cache`对象通过<xref:System.Windows.Forms.DataGridView.CellValueNeeded>事件处理程序。 `Cache`对象管理的本地存储的值，并使用`DataRetriever`Northwind 示例数据库 Orders 表中检索值的对象。 `DataRetriever`对象，该实现对象`IDataPageRetriever`所需的接口`Cache`类中，还可用于初始化<xref:System.Windows.Forms.DataGridView>控制行和列。  
  
 `IDataPageRetriever`， `DataRetriever`，和`Cache`更高版本中本主题介绍了类型。  
  
> [!NOTE]
>  将敏感信息（如密码）存储在连接字符串中可能会影响应用程序的安全性。 若要控制对数据库的访问，一种较为安全的方法是使用 Windows 身份验证（也称为集成安全性）。 有关详细信息，请参阅[保护连接信息](../../../../docs/framework/data/adonet/protecting-connection-information.md)。  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#100)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#100)]  
  
## <a name="the-idatapageretriever-interface"></a>IDataPageRetriever 接口  
 下面的代码示例定义`IDataPageRetriever`接口，该实现的接口`DataRetriever`类。 在此接口中声明的唯一方法是`SupplyPageOfData`方法，它需要初始行索引和的一页中的数据的行数的计数。 这些值由实施者中用于从数据源检索数据的子集。  
  
 A`Cache`对象使用此接口的实现在构造期间加载的数据的两个初始页。 每当需要缓存的值时，缓存将放弃其中一个网页，并请求包含的值的新页`IDataPageRetriever`。  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#201](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#201)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#201](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#201)]  
  
## <a name="the-dataretriever-class"></a>DataRetriever 类  
 下面的代码示例定义`DataRetriever`类，该类实现`IDataPageRetriever`接口以从服务器检索的数据页。 `DataRetriever`类还提供了`Columns`和`RowCount`属性，其中<xref:System.Windows.Forms.DataGridView>控件使用以创建所需的列并将添加相应数量的空行<xref:System.Windows.Forms.DataGridView.Rows%2A>集合。 添加空的行是必需的因此，控件的行为就像它包含表中的所有数据。 这意味着，滚动条中的滚动框将有适当的大小，并且用户将能够访问表中的任何行。 通过行来填充<xref:System.Windows.Forms.DataGridView.CellValueNeeded>事件处理程序仅当它们滚动到视图时。  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#200](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#200)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#200](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#200)]  
  
## <a name="the-cache-class"></a>缓存类  
 下面的代码示例定义`Cache`类，它管理的数据填充通过两个页`IDataPageRetriever`实现。 `Cache`类定义内部`DataPage`结构，其中包含<xref:System.Data.DataTable>来在单个缓存中存储的值页，并且计算的行索引表示页的上限和下限边界。  
  
 `Cache`类在构造时将加载的数据的两个页。 每当<xref:System.Windows.Forms.DataGridView.CellValueNeeded>事件请求值时，`Cache`对象确定如果值为位于一个其两个页，如果是这样，则返回它。 如果值在本地，不可用`Cache`对象确定其其两个页中的距离最远的当前显示的行和页替换包含请求的值，然后返回一个新密码。  
  
 假定数据页中的行数是可以同时在屏幕显示的行数相同，此模型将允许用户浏览表分页有效地返回到最近查看的页。  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#300](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#300)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#300](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#300)]  
  
## <a name="additional-considerations"></a>其他注意事项  
 前面的代码示例提供在实时数据加载的演示。 你将需要修改你自己的需求，以实现最大效率的代码。 在最低限度上，你将需要在缓存中选择适当的值的数据的每页行数。 此值传递给`Cache`构造函数。 每页行数应不小于可以同时在显示的行数你<xref:System.Windows.Forms.DataGridView>控件。  
  
 为获得最佳结果，你将需要进行性能测试和可用性测试以确定你的系统和你的用户的要求。 你将需要考虑的几个因素包括在客户端计算机运行你的应用程序、 可用带宽的使用的网络连接和使用的服务器的延迟的内存量。 带宽和延迟应确定有时的使用率峰值。  
  
 若要提高你的应用程序的滚动性能，可以增加本地存储的数据的量。 若要提高启动时间，但是，你必须避免最初加载的数据太多。 你可能想要修改`Cache`类增加可以存储的数据页的数量。 使用更多数据页可以提高滚动效率，但你需要确定理想的数据页中，具体取决于可用带宽和服务器延迟时间中的行数。 具有较小的页面，服务器将更频繁地访问，但需要更少的时间才能返回请求的数据。 如果延迟的带宽比是问题的详细信息，你可能想要使用较大的数据页。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>  
 [Windows 窗体 DataGridView 控件中的性能调整](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)  
 [有关缩放 Windows 窗体 DataGridView 控件的最佳做法](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)  
 [Windows 窗体 DataGridView 控件中的虚拟模式](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)  
 [演练：在 Windows 窗体 DataGridView 控件中实现虚拟模式](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)  
 [如何：在 Windows 窗体 DataGridView 控件中实现实时数据加载的虚拟模式](../../../../docs/framework/winforms/controls/virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md)
