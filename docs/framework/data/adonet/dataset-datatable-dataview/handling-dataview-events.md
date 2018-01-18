---
title: "处理数据视图事件"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: e5675663-fc91-4e0d-87a9-481b25b64c0f
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: bf3b02227de5068a031cedb73269148c7d5262a0
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="handling-dataview-events"></a><span data-ttu-id="13eb3-102">处理数据视图事件</span><span class="sxs-lookup"><span data-stu-id="13eb3-102">Handling DataView Events</span></span>
<span data-ttu-id="13eb3-103">可以使用 <xref:System.Data.DataView.ListChanged> 的 <xref:System.Data.DataView> 事件确定某个视图是否已更新。</span><span class="sxs-lookup"><span data-stu-id="13eb3-103">You can use the <xref:System.Data.DataView.ListChanged> event of the <xref:System.Data.DataView> to determine if a view has been updated.</span></span> <span data-ttu-id="13eb3-104">引发该事件的更新包括添加、删除或修改基础表中的某行；在基础表的架构中添加或删除某列；更改父或子关系。</span><span class="sxs-lookup"><span data-stu-id="13eb3-104">Updates that raise the event include adding, deleting, or modifying a row in the underlying table; adding or deleting a column to the schema of the underlying table; and a change in a parent or child relationship.</span></span> <span data-ttu-id="13eb3-105">**ListChanged**事件还将通知你如果你正在查看的行的列表已显著更改由于新的排序顺序或筛选器的应用程序。</span><span class="sxs-lookup"><span data-stu-id="13eb3-105">The **ListChanged** event also notifies you if the list of rows you are viewing has changed significantly due to the application of a new sort order or a filter.</span></span>  
  
 <span data-ttu-id="13eb3-106">**ListChanged**事件实现**ListChangedEventHandler**委托的<xref:System.ComponentModel>命名空间和接受的输入<xref:System.ComponentModel.ListChangedEventArgs>对象。</span><span class="sxs-lookup"><span data-stu-id="13eb3-106">The **ListChanged** event implements the **ListChangedEventHandler** delegate of the <xref:System.ComponentModel> namespace and takes as input a <xref:System.ComponentModel.ListChangedEventArgs> object.</span></span> <span data-ttu-id="13eb3-107">你可以确定哪种类型的更改发生使用<xref:System.ComponentModel.ListChangedType>中的枚举值**ListChangedType**属性**ListChangedEventArgs**对象。</span><span class="sxs-lookup"><span data-stu-id="13eb3-107">You can determine what type of change has occurred using the <xref:System.ComponentModel.ListChangedType> enumeration value in the **ListChangedType** property of the **ListChangedEventArgs** object.</span></span> <span data-ttu-id="13eb3-108">对于涉及添加的更改，删除或移动行，添加或移动行的新索引以及已删除的行的先前索引可以访问使用**NewIndex**属性**ListChangedEventArgs**对象。</span><span class="sxs-lookup"><span data-stu-id="13eb3-108">For changes that involve adding, deleting, or moving rows, the new index of the added or moved row and the previous index of the deleted row can be accessed using the **NewIndex** property of the **ListChangedEventArgs** object.</span></span> <span data-ttu-id="13eb3-109">在移动行的情况下移动行的先前索引可以访问使用**OldIndex**属性**ListChangedEventArgs**对象。</span><span class="sxs-lookup"><span data-stu-id="13eb3-109">In the case of a moved row, the previous index of the moved row can be accessed using the **OldIndex** property of the **ListChangedEventArgs** object.</span></span>  
  
 <span data-ttu-id="13eb3-110">**DataViewManager**还公开**ListChanged**事件来通知您如果表已添加或删除，或者如果已对进行了更改**关系**的集合基础**数据集**。</span><span class="sxs-lookup"><span data-stu-id="13eb3-110">The **DataViewManager** also exposes a **ListChanged** event to notify you if a table has been added or removed, or if a change has been made to the **Relations** collection of the underlying **DataSet**.</span></span>  
  
 <span data-ttu-id="13eb3-111">下面的代码示例演示如何添加**ListChanged**事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="13eb3-111">The following code example shows how to add a **ListChanged** event handler.</span></span>  
  
```vb  
AddHandler custView.ListChanged, _  
  New System.ComponentModel.ListChangedEventHandler( _  
  AddressOf OnListChanged)  
  
Private Shared Sub OnListChanged( _  
  sender As Object, args As System.ComponentModel.ListChangedEventArgs)  
  Console.WriteLine("ListChanged:")  
  Console.WriteLine(vbTab & "    Type = " & _  
    System.Enum.GetName(args.ListChangedType.GetType(), _  
    args.ListChangedType))  
  Console.WriteLine(vbTab & "OldIndex = " & args.OldIndex)  
  Console.WriteLine(vbTab & "NewIndex = " & args.NewIndex)  
End Sub  
```  
  
```csharp  
custView.ListChanged  += new   
  System.ComponentModel.ListChangedEventHandler(OnListChanged);  
  
protected static void OnListChanged(object sender,   
  System.ComponentModel.ListChangedEventArgs args)  
{  
  Console.WriteLine("ListChanged:");  
  Console.WriteLine("\t    Type = " + args.ListChangedType);  
  Console.WriteLine("\tOldIndex = " + args.OldIndex);  
  Console.WriteLine("\tNewIndex = " + args.NewIndex);  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="13eb3-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="13eb3-112">See Also</span></span>  
 <xref:System.Data.DataView>  
 <xref:System.ComponentModel.ListChangedEventHandler>  
 [<span data-ttu-id="13eb3-113">数据视图</span><span class="sxs-lookup"><span data-stu-id="13eb3-113">DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [<span data-ttu-id="13eb3-114">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="13eb3-114">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
