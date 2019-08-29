---
title: 在 Windows 窗体 DataGridView 控件中实现实时数据加载的虚拟模式
ms.date: 03/30/2017
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
ms.openlocfilehash: fa40f1657a433f5f4ade3de25648ca04c37dfa67
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962600"
---
# <a name="implementing-virtual-mode-with-just-in-time-data-loading-in-the-windows-forms-datagridview-control"></a>在 Windows 窗体 DataGridView 控件中实现实时数据加载的虚拟模式
在<xref:System.Windows.Forms.DataGridView>控件中实现虚拟模式的一个原因是只在需要时才检索数据。 这称为 *"实时数据加载"* 。  
  
 例如, 如果您在远程数据库中使用非常大的表, 则您可能希望仅在用户将新行滚动到视图中时, 只检索显示和检索其他数据所需的数据, 从而避免启动延迟。 如果运行应用程序的客户端计算机有有限数量的内存可用于存储数据, 则在从数据库检索新值时, 您可能还需要丢弃未使用的数据。  
  
 以下各节介绍如何将<xref:System.Windows.Forms.DataGridView>控件与实时缓存结合使用。  
  
 要将本主题中的代码作为单个列表进行复制，请参阅[如何：在 Windows 窗体 DataGridView 控件](virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md)中实现包含实时数据加载的虚拟模式。  
  
## <a name="the-form"></a>窗体  
 下面的代码示例定义一个窗体, 该窗体<xref:System.Windows.Forms.DataGridView>包含一个只读控件, `Cache`该控件通过<xref:System.Windows.Forms.DataGridView.CellValueNeeded>事件处理程序与对象进行交互。 对象管理本地存储的值, 并`DataRetriever`使用对象从示例 Northwind 数据库的 Orders 表中检索值。 `Cache` 对象 (该对象实现`IDataPageRetriever` 类所需`Cache`的接口) 还用于初始化控件行和列。<xref:System.Windows.Forms.DataGridView> `DataRetriever`  
  
 本主题`DataRetriever`后面将`Cache`介绍、和类型。`IDataPageRetriever`  
  
> [!NOTE]
> 将敏感信息（如密码）存储在连接字符串中可能会影响应用程序的安全性。 若要控制对数据库的访问，一种较为安全的方法是使用 Windows 身份验证（也称为集成安全性）。 有关详细信息，请参阅[保护连接信息](../../data/adonet/protecting-connection-information.md)。  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#100)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#100)]  
  
## <a name="the-idatapageretriever-interface"></a>IDataPageRetriever 接口  
 下面的代码示例定义`IDataPageRetriever`了接口, 该接口`DataRetriever`由类实现。 此接口中声明的唯一方法是`SupplyPageOfData`方法, 该方法需要一个初始行索引和一个数据页中的行数计数。 实施者使用这些值来检索数据源中的数据子集。  
  
 `Cache`对象在构造过程中使用此接口的实现来加载两页初始数据。 只要需要非缓存值, 缓存就会丢弃其中的一个页面, 并请求包含中`IDataPageRetriever`的值的新页面。  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#201](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#201)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#201](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#201)]  
  
## <a name="the-dataretriever-class"></a>DataRetriever 类  
 下面的代码示例定义`DataRetriever`类, 该类`IDataPageRetriever`实现接口以检索服务器中的数据页。 `Columns` <xref:System.Windows.Forms.DataGridView.Rows%2A>类还提供<xref:System.Windows.Forms.DataGridView>和属性, 控件使用该属性来创建所需的列并向集合中添加适当数量的空行。 `RowCount` `DataRetriever` 需要添加空行, 以使控件的行为如同包含表中的所有数据一样。 这意味着滚动条中的滚动框将具有适当的大小, 并且用户将可以访问表中的任何行。 仅当行滚动到视图<xref:System.Windows.Forms.DataGridView.CellValueNeeded>中时, 事件处理程序才会填充这些行。  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#200](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#200)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#200](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#200)]  
  
## <a name="the-cache-class"></a>缓存类  
 下面的代码示例定义`Cache`类, 该类管理`IDataPageRetriever`通过实现填充的两页数据。 类定义一个内部`DataPage` <xref:System.Data.DataTable>结构, 其中包含用于将值存储在单个缓存页中, 并计算表示页面的上边界和下边界的行索引。 `Cache`  
  
 `Cache`类在构造时加载两个数据页。 每当事件请求某个值时, 该`Cache`对象就会确定该值是否在其两个页中的一个页上可用, 如果是, 则返回该值。 <xref:System.Windows.Forms.DataGridView.CellValueNeeded> 如果值在本地不可用, 则`Cache`对象将确定其两个页面中的哪一页离当前显示的行最远, 并使用包含请求值的新页面替换页面, 然后返回。  
  
 假设数据页中的行数与可以在屏幕上同时显示的行数相同, 则此模型允许用户分页查看表, 以便有效地返回到最近查看的页。  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#300](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#300)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#300](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#300)]  
  
## <a name="additional-considerations"></a>其他注意事项  
 前面的代码示例作为实时数据加载的演示提供。 你需要根据自己的需要修改代码以获得最大效率。 至少需要为缓存中每页数据的行数选择适当的值。 此值将传递到`Cache`构造函数中。 每页的行数应小于<xref:System.Windows.Forms.DataGridView>控件中可同时显示的行数。  
  
 为了获得最佳结果, 你将需要执行性能测试和可用性测试, 以确定你的系统和用户的要求。 需要考虑的几个因素包括运行应用程序的客户端计算机上的内存量、所用网络连接的可用带宽, 以及所使用服务器的延迟时间。 带宽和延迟应在高峰使用时间进行确定。  
  
 若要提高应用程序的滚动性能, 可以增加本地存储的数据量。 然而, 若要改善启动时间, 必须避免最初加载过多数据。 你可能想要修改`Cache`类以增加它可以存储的数据页的数目。 使用更多数据页可以提高滚动效率, 但需要确定数据页中的理想行数, 具体取决于可用带宽和服务器延迟。 使用较小的页, 将会更频繁地访问服务器, 但需要更少的时间来返回所请求的数据。 如果延迟是比带宽更多的问题, 则可能需要使用较大的数据页。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>
- [Windows 窗体 DataGridView 控件中的性能调整](performance-tuning-in-the-windows-forms-datagridview-control.md)
- [有关缩放 Windows 窗体 DataGridView 控件的最佳做法](best-practices-for-scaling-the-windows-forms-datagridview-control.md)
- [Windows 窗体 DataGridView 控件中的虚拟模式](virtual-mode-in-the-windows-forms-datagridview-control.md)
- [演练：在 Windows 窗体 DataGridView 控件中实现虚拟模式](implementing-virtual-mode-wf-datagridview-control.md)
- [如何：在 Windows 窗体 DataGridView 控件中实现实时数据加载的虚拟模式](virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md)
