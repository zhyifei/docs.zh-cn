---
title: "LINQ to XML 批注 3"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 54e7b9d0-07f5-488f-9065-b6e6b870f810
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: eadbc55ac6188fa3634745bf8bb222f07675a308
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="linq-to-xml-annotations"></a>LINQ to XML 批注
[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 中的注释可将任意类型的任意对象与 XML 树中的任何 XML 组件相关联。  
  
 若要向 XML 组件（例如 <xref:System.Xml.Linq.XElement> 或 <xref:System.Xml.Linq.XAttribute>）中添加批注，需调用 <xref:System.Xml.Linq.XObject.AddAnnotation%2A> 方法。 批注是按类型检索的。  
  
 请注意，批注不是 XML 信息集的一部分，不对它们进行序列化和反序列化。  
  
## <a name="methods"></a>方法  
 处理批注时可以使用以下方法：  
  
|方法|描述|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XObject.AddAnnotation%2A>|向 <xref:System.Xml.Linq.XObject> 的批注列表中添加对象。|  
|<xref:System.Xml.Linq.XObject.Annotation%2A>|从 <xref:System.Xml.Linq.XObject> 获取指定类型的第一个批注对象。|  
|<xref:System.Xml.Linq.XObject.Annotations%2A>|获取 <xref:System.Xml.Linq.XObject> 的指定类型的批注集合。|  
|<xref:System.Xml.Linq.XObject.RemoveAnnotations%2A>|从 <xref:System.Xml.Linq.XObject> 移除指定类型的批注。|  
  
## <a name="see-also"></a>另请参阅  
 [高级 LINQ to XML 编程 (C#)](../../../../csharp/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
