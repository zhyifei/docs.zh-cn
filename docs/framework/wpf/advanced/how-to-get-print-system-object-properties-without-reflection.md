---
title: 如何：在不使用反射的情况下获得打印系统对象属性
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PrintSystemObject [WPF], getting properties
ms.assetid: 43560f28-183d-41c1-b9d1-de7c2552273e
caps.latest.revision: 6
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5f1aa6025c2b8a00dd170a674a1bdea25d76a9a1
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-get-print-system-object-properties-without-reflection"></a>如何：在不使用反射的情况下获得打印系统对象属性
使用反射对象上列举的属性 （以及这些属性的类型） 会降低应用程序性能。 <xref:System.Printing.IndexedProperties>命名空间提供一种方式获取此信息与使用反射。  
  
## <a name="example"></a>示例  
 执行此操作的步骤如下所示。  
  
1.  创建类型的实例。 在下面的示例中，类型是<xref:System.Printing.PrintQueue>附带 Microsoft.NET Framework，但几乎完全相同的代码的类型应该适用于类型派生自<xref:System.Printing.PrintSystemObject>。  
  
2.  创建<xref:System.Printing.IndexedProperties.PrintPropertyDictionary>从该类型的<xref:System.Printing.PrintSystemObject.PropertiesCollection%2A>。 <xref:System.Collections.DictionaryEntry.Value%2A>此字典中的每个条目的属性是一个派生自的类型的对象<xref:System.Printing.IndexedProperties.PrintProperty>。  
  
3.  枚举字典中的成员。 为每个，执行以下操作。  
  
4.  向上转换到每个条目的值<xref:System.Printing.IndexedProperties.PrintProperty>并用它来创建<xref:System.Printing.IndexedProperties.PrintProperty>对象。  
  
5.  获取类型的<xref:System.Printing.IndexedProperties.PrintProperty.Value%2A>的每个<xref:System.Printing.IndexedProperties.PrintProperty>对象。  
  
 [!code-csharp[GetPrintObjectPropertyTypesWithoutReflection#ShowPropertyTypesWithoutReflection](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GetPrintObjectPropertyTypesWithoutReflection/CSharp/Program.cs#showpropertytypeswithoutreflection)]
 [!code-vb[GetPrintObjectPropertyTypesWithoutReflection#ShowPropertyTypesWithoutReflection](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GetPrintObjectPropertyTypesWithoutReflection/visualbasic/program.vb#showpropertytypeswithoutreflection)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Printing.IndexedProperties.PrintProperty>  
 <xref:System.Printing.PrintSystemObject>  
 <xref:System.Printing.IndexedProperties>  
 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>  
 <xref:System.Printing.LocalPrintServer>  
 <xref:System.Printing.PrintQueue>  
 <xref:System.Collections.DictionaryEntry>  
 [WPF 中的文档](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [打印概述](../../../../docs/framework/wpf/advanced/printing-overview.md)
