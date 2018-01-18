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
# <a name="handling-dataview-events"></a>处理数据视图事件
可以使用 <xref:System.Data.DataView.ListChanged> 的 <xref:System.Data.DataView> 事件确定某个视图是否已更新。 引发该事件的更新包括添加、删除或修改基础表中的某行；在基础表的架构中添加或删除某列；更改父或子关系。 **ListChanged**事件还将通知你如果你正在查看的行的列表已显著更改由于新的排序顺序或筛选器的应用程序。  
  
 **ListChanged**事件实现**ListChangedEventHandler**委托的<xref:System.ComponentModel>命名空间和接受的输入<xref:System.ComponentModel.ListChangedEventArgs>对象。 你可以确定哪种类型的更改发生使用<xref:System.ComponentModel.ListChangedType>中的枚举值**ListChangedType**属性**ListChangedEventArgs**对象。 对于涉及添加的更改，删除或移动行，添加或移动行的新索引以及已删除的行的先前索引可以访问使用**NewIndex**属性**ListChangedEventArgs**对象。 在移动行的情况下移动行的先前索引可以访问使用**OldIndex**属性**ListChangedEventArgs**对象。  
  
 **DataViewManager**还公开**ListChanged**事件来通知您如果表已添加或删除，或者如果已对进行了更改**关系**的集合基础**数据集**。  
  
 下面的代码示例演示如何添加**ListChanged**事件处理程序。  
  
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
  
## <a name="see-also"></a>请参阅  
 <xref:System.Data.DataView>  
 <xref:System.ComponentModel.ListChangedEventHandler>  
 [数据视图](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [ADO.NET 托管提供程序和数据集开发人员中心](http://go.microsoft.com/fwlink/?LinkId=217917)
