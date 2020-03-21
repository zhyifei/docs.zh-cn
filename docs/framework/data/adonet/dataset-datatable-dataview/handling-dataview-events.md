---
title: 处理数据视图事件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e5675663-fc91-4e0d-87a9-481b25b64c0f
ms.openlocfilehash: b625fad846c4c6cf008843bff1f6b0eabe0e1de4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151099"
---
# <a name="handling-dataview-events"></a><span data-ttu-id="0b2dc-102">处理数据视图事件</span><span class="sxs-lookup"><span data-stu-id="0b2dc-102">Handling DataView Events</span></span>
<span data-ttu-id="0b2dc-103">可以使用 <xref:System.Data.DataView.ListChanged> 的 <xref:System.Data.DataView> 事件确定某个视图是否已更新。</span><span class="sxs-lookup"><span data-stu-id="0b2dc-103">You can use the <xref:System.Data.DataView.ListChanged> event of the <xref:System.Data.DataView> to determine if a view has been updated.</span></span> <span data-ttu-id="0b2dc-104">引发该事件的更新包括添加、删除或修改基础表中的某行；在基础表的架构中添加或删除某列；更改父或子关系。</span><span class="sxs-lookup"><span data-stu-id="0b2dc-104">Updates that raise the event include adding, deleting, or modifying a row in the underlying table; adding or deleting a column to the schema of the underlying table; and a change in a parent or child relationship.</span></span> <span data-ttu-id="0b2dc-105">如果由于应用了新的排序顺序或筛选器，您正在查看的行列表已发生重大变化，则 **"List更改"** 事件也会通知您。</span><span class="sxs-lookup"><span data-stu-id="0b2dc-105">The **ListChanged** event also notifies you if the list of rows you are viewing has changed significantly due to the application of a new sort order or a filter.</span></span>  
  
 <span data-ttu-id="0b2dc-106">**List"更改"** 事件实现<xref:System.ComponentModel>命名空间的<xref:System.ComponentModel.ListChangedEventArgs>**ListChanged 事件处理程序**委托，并将作为输入对象。</span><span class="sxs-lookup"><span data-stu-id="0b2dc-106">The **ListChanged** event implements the **ListChangedEventHandler** delegate of the <xref:System.ComponentModel> namespace and takes as input a <xref:System.ComponentModel.ListChangedEventArgs> object.</span></span> <span data-ttu-id="0b2dc-107">您可以使用<xref:System.ComponentModel.ListChangedType> **ListChangeEventArgs**对象的**ListChangeType**属性中的枚举值确定发生了哪些类型的更改。</span><span class="sxs-lookup"><span data-stu-id="0b2dc-107">You can determine what type of change has occurred using the <xref:System.ComponentModel.ListChangedType> enumeration value in the **ListChangedType** property of the **ListChangedEventArgs** object.</span></span> <span data-ttu-id="0b2dc-108">对于涉及添加、删除或移动行的更改，可以使用**ListChangesEventArgs**对象的**NewIndex**属性访问添加或移动行的新索引和已删除行的上一个索引。</span><span class="sxs-lookup"><span data-stu-id="0b2dc-108">For changes that involve adding, deleting, or moving rows, the new index of the added or moved row and the previous index of the deleted row can be accessed using the **NewIndex** property of the **ListChangedEventArgs** object.</span></span> <span data-ttu-id="0b2dc-109">在移动行的情况下，可以使用**ListChangedEventArgs**对象的**OldIndex**属性访问移动行的前一个索引。</span><span class="sxs-lookup"><span data-stu-id="0b2dc-109">In the case of a moved row, the previous index of the moved row can be accessed using the **OldIndex** property of the **ListChangedEventArgs** object.</span></span>  
  
 <span data-ttu-id="0b2dc-110">**DataViewManager**还会公开**ListChange**事件，以通知您是否已添加或删除表，或者对基础**DataSet**的 **"关系"** 集合进行了更改。</span><span class="sxs-lookup"><span data-stu-id="0b2dc-110">The **DataViewManager** also exposes a **ListChanged** event to notify you if a table has been added or removed, or if a change has been made to the **Relations** collection of the underlying **DataSet**.</span></span>  
  
 <span data-ttu-id="0b2dc-111">以下代码示例演示如何添加**ListChanged**事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="0b2dc-111">The following code example shows how to add a **ListChanged** event handler.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0b2dc-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0b2dc-112">See also</span></span>

- <xref:System.Data.DataView>
- <xref:System.ComponentModel.ListChangedEventHandler>
- [<span data-ttu-id="0b2dc-113">DataView</span><span class="sxs-lookup"><span data-stu-id="0b2dc-113">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="0b2dc-114">ADO.NET 概述</span><span class="sxs-lookup"><span data-stu-id="0b2dc-114">ADO.NET Overview</span></span>](../ado-net-overview.md)
