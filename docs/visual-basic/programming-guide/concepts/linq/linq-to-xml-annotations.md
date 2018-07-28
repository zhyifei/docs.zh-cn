---
title: LINQ to XML Annotations2
ms.date: 07/20/2015
ms.assetid: c3e8b3ff-fceb-4428-b0ca-1ed6f128aac8
ms.openlocfilehash: a7b81b8c1856c11cb0c5e777f31986a330cf115f
ms.sourcegitcommit: 869b5832b667915ac4a5dd8c86b1109ed26b6c08
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/28/2018
ms.locfileid: "39332917"
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
  
## <a name="see-also"></a>请参阅  
 [高级的 LINQ to XML 编程 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
