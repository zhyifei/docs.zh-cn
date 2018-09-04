---
title: 处理数据集事件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 54edefe0-bc38-419b-b486-3d8a0c356f13
ms.openlocfilehash: ff684adcb4e23b91b3e59476299d277c90c22c51
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43560044"
---
# <a name="handling-dataset-events"></a><span data-ttu-id="63195-102">处理数据集事件</span><span class="sxs-lookup"><span data-stu-id="63195-102">Handling DataSet Events</span></span>
<span data-ttu-id="63195-103"><xref:System.Data.DataSet> 对象提供三个事件： <xref:System.ComponentModel.MarshalByValueComponent.Disposed>、 <xref:System.Data.DataSet.Initialized>和 <xref:System.Data.DataSet.MergeFailed>。</span><span class="sxs-lookup"><span data-stu-id="63195-103">The <xref:System.Data.DataSet> object provides three events: <xref:System.ComponentModel.MarshalByValueComponent.Disposed>, <xref:System.Data.DataSet.Initialized>, and <xref:System.Data.DataSet.MergeFailed>.</span></span>  
  
## <a name="the-mergefailed-event"></a><span data-ttu-id="63195-104">MergeFailed 事件</span><span class="sxs-lookup"><span data-stu-id="63195-104">The MergeFailed Event</span></span>  
 <span data-ttu-id="63195-105">`DataSet` 对象的最常用事件是 `MergeFailed`，当要合并的 `DataSet` 对象的架构发生冲突时，会引发该事件。</span><span class="sxs-lookup"><span data-stu-id="63195-105">The most commonly used event of the `DataSet` object is `MergeFailed`, which is raised when the schema of the `DataSet` objects being merged are in conflict.</span></span> <span data-ttu-id="63195-106">当目标和源 <xref:System.Data.DataRow> 有相同的主键值，且 <xref:System.Data.DataSet.EnforceConstraints%2A> 属性设置为 `true`时会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="63195-106">This occurs when a target and source <xref:System.Data.DataRow> have the same primary key value, and the <xref:System.Data.DataSet.EnforceConstraints%2A> property is set to `true`.</span></span> <span data-ttu-id="63195-107">例如，如果所合并表的主键列与两个 `DataSet` 对象中的表的相同，则将发生异常并引发 `MergeFailed` 事件。</span><span class="sxs-lookup"><span data-stu-id="63195-107">For example, if the primary key columns of a table being merged are the same between the tables in the two `DataSet` objects, an exception is thrown and the `MergeFailed` event is raised.</span></span> <span data-ttu-id="63195-108">传递给 <xref:System.Data.MergeFailedEventArgs> 事件的 `MergeFailed` 对象具有 <xref:System.Data.MergeFailedEventArgs.Conflict%2A> 属性（标识两个 `DataSet` 对象之间的架构冲突）和 <xref:System.Data.MergeFailedEventArgs.Table%2A> 属性（标识发生冲突的表的名称）。</span><span class="sxs-lookup"><span data-stu-id="63195-108">The <xref:System.Data.MergeFailedEventArgs> object passed to the `MergeFailed` event have a <xref:System.Data.MergeFailedEventArgs.Conflict%2A> property that identifies the conflict in schema between the two `DataSet` objects, and a <xref:System.Data.MergeFailedEventArgs.Table%2A> property that identifies the name of the table in conflict.</span></span>  
  
 <span data-ttu-id="63195-109">下面的代码段演示如何为 `MergeFailed` 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="63195-109">The following code fragment demonstrates how to add an event handler for the `MergeFailed` event.</span></span>  
  
```vb  
AddHandler workDS.MergeFailed, New MergeFailedEventHandler( _  
  AddressOf DataSetMergeFailed)  
  
Private Shared Sub DataSetMergeFailed(  _  
  sender As Object,args As MergeFailedEventArgs)  
  Console.WriteLine("Merge failed for table " & args.Table.TableName)  
  Console.WriteLine("Conflict = " & args.Conflict)  
End Sub  
```  
  
```csharp  
workDS.MergeFailed += new MergeFailedEventHandler(DataSetMergeFailed);  
  
private static void DataSetMergeFailed(  
  object sender, MergeFailedEventArgs args)  
{  
  Console.WriteLine("Merge failed for table " + args.Table.TableName);  
  Console.WriteLine("Conflict = " + args.Conflict);  
}  
```  
  
## <a name="the-initialized-event"></a><span data-ttu-id="63195-110">初始化事件</span><span class="sxs-lookup"><span data-stu-id="63195-110">The Initialized Event</span></span>  
 <span data-ttu-id="63195-111">在 <xref:System.Data.DataSet.Initialized> 构造函数初始化 `DataSet` 的新实例后会发生 `DataSet`事件。</span><span class="sxs-lookup"><span data-stu-id="63195-111">The <xref:System.Data.DataSet.Initialized> event occurs after the `DataSet` constructor initializes a new instance of the `DataSet`.</span></span>  
  
 <span data-ttu-id="63195-112">如果 <xref:System.Data.DataSet.IsInitialized%2A> 已完成初始化， `true` 属性会返回 `DataSet` ；否则，返回 `false`。</span><span class="sxs-lookup"><span data-stu-id="63195-112">The <xref:System.Data.DataSet.IsInitialized%2A> property returns `true` if the `DataSet` has completed initialization; otherwise it returns `false`.</span></span> <span data-ttu-id="63195-113"><xref:System.Data.DataSet.BeginInit%2A> 方法，它开始初始化 `DataSet`，将 <xref:System.Data.DataSet.IsInitialized%2A> 设置为 `false`。</span><span class="sxs-lookup"><span data-stu-id="63195-113">The <xref:System.Data.DataSet.BeginInit%2A> method, which begins the initialization of a `DataSet`, sets <xref:System.Data.DataSet.IsInitialized%2A> to `false`.</span></span> <span data-ttu-id="63195-114"><xref:System.Data.DataSet.EndInit%2A> 方法（用于结束 `DataSet`的初始化）将它设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="63195-114">The <xref:System.Data.DataSet.EndInit%2A> method, which ends the initialization of the `DataSet`, sets it to `true`.</span></span> <span data-ttu-id="63195-115">这些方法由 Visual Studio 设计环境，以初始化`DataSet`，正由另一个组件。</span><span class="sxs-lookup"><span data-stu-id="63195-115">These methods are used by the Visual Studio design environment to initialize a `DataSet` that is being used by another component.</span></span> <span data-ttu-id="63195-116">通常不会在代码中使用这些方法。</span><span class="sxs-lookup"><span data-stu-id="63195-116">You will not commonly use them in your code.</span></span>  
  
## <a name="the-disposed-event"></a><span data-ttu-id="63195-117">释放事件</span><span class="sxs-lookup"><span data-stu-id="63195-117">The Disposed Event</span></span>  
 <span data-ttu-id="63195-118">`DataSet` 派生自 <xref:System.ComponentModel.MarshalByValueComponent> 类，该类可公开 <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> 方法和 <xref:System.ComponentModel.MarshalByValueComponent.Disposed> 事件。</span><span class="sxs-lookup"><span data-stu-id="63195-118">`DataSet` is derived from the <xref:System.ComponentModel.MarshalByValueComponent> class, which exposes both the <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> method and the <xref:System.ComponentModel.MarshalByValueComponent.Disposed> event.</span></span> <span data-ttu-id="63195-119"><xref:System.ComponentModel.MarshalByValueComponent.Disposed>事件添加事件处理程序以侦听组件上已释放的事件。</span><span class="sxs-lookup"><span data-stu-id="63195-119">The <xref:System.ComponentModel.MarshalByValueComponent.Disposed> event adds an event handler to listen to the disposed event on the component.</span></span> <span data-ttu-id="63195-120">可以使用<xref:System.ComponentModel.MarshalByValueComponent.Disposed>的事件`DataSet`如果你想要执行代码时<xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A>调用方法。</span><span class="sxs-lookup"><span data-stu-id="63195-120">You can use the <xref:System.ComponentModel.MarshalByValueComponent.Disposed> event of a `DataSet` if you want to execute code when the <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> method is called.</span></span> <span data-ttu-id="63195-121"><xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> 释放使用的资源<xref:System.ComponentModel.MarshalByValueComponent>。</span><span class="sxs-lookup"><span data-stu-id="63195-121"><xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> releases the resources used by the <xref:System.ComponentModel.MarshalByValueComponent>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="63195-122">`DataSet`并`DataTable`对象继承自<xref:System.ComponentModel.MarshalByValueComponent>和支持<xref:System.Runtime.Serialization.ISerializable>远程处理的接口。</span><span class="sxs-lookup"><span data-stu-id="63195-122">The `DataSet` and `DataTable` objects inherit from <xref:System.ComponentModel.MarshalByValueComponent> and support the <xref:System.Runtime.Serialization.ISerializable> interface for remoting.</span></span> <span data-ttu-id="63195-123">这两个对象是唯一可远程处理的 ADO.NET 对象。</span><span class="sxs-lookup"><span data-stu-id="63195-123">These are the only ADO.NET objects that can be remoted.</span></span> <span data-ttu-id="63195-124">有关详细信息，请参阅[远程对象](https://msdn.microsoft.com/library/515686e6-0a8d-42f7-8188-73abede57c58)。</span><span class="sxs-lookup"><span data-stu-id="63195-124">For more information, see [Remote Objects](https://msdn.microsoft.com/library/515686e6-0a8d-42f7-8188-73abede57c58).</span></span>  
  
 <span data-ttu-id="63195-125">有关可用时使用的其他事件信息`DataSet`，请参阅[处理数据表事件](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md)并[处理 DataAdapter 事件](../../../../../docs/framework/data/adonet/handling-dataadapter-events.md)。</span><span class="sxs-lookup"><span data-stu-id="63195-125">For information about other events available when working with a `DataSet`, see [Handling DataTable Events](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md) and [Handling DataAdapter Events](../../../../../docs/framework/data/adonet/handling-dataadapter-events.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63195-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="63195-126">See Also</span></span>  
 [<span data-ttu-id="63195-127">数据集、数据表和数据视图</span><span class="sxs-lookup"><span data-stu-id="63195-127">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="63195-128">验证数据</span><span class="sxs-lookup"><span data-stu-id="63195-128">Validating Data</span></span>](https://msdn.microsoft.com/library/b3a9ee4e-5d4d-4411-9c56-c811f2b4ee7e)  
 [<span data-ttu-id="63195-129">在 ADO.NET 中检索和修改数据</span><span class="sxs-lookup"><span data-stu-id="63195-129">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="63195-130">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="63195-130">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
