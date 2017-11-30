---
title: "检索存储在特性中的信息"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- retrieving attributes
- multiple attribute instances
- attributes [.NET Framework], retrieving
ms.assetid: 37dfe4e3-7da0-48b6-a3d9-398981524e1c
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9d3fd9a5a49d65b37d2cdb5107e9c516a6df5847
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="retrieving-information-stored-in-attributes"></a>检索存储在特性中的信息
检索的自定义特性是一个简单的过程。 首先，声明你想要检索的属性的实例。 然后，使用<xref:System.Attribute.GetCustomAttribute%2A?displayProperty=nameWithType>方法以初始化为你想要检索的属性值的新属性。 后在初始化新的属性时，只需使用其属性来获取值。  
  
> [!IMPORTANT]
>  本主题介绍如何检索加载到执行上下文的代码中的特性。 若要检索的代码加载到只反射上下文的特性，必须使用<xref:System.Reflection.CustomAttributeData>类，如下所示[如何： 将程序集加载到 Reflection-Only 上下文](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md)。  
  
 本部分介绍了以下方式来检索属性：  
  
-   [检索属性的一个实例](#cpconretrievingsingleinstanceofattribute)  
  
-   [检索属性应用于同一范围内的多个实例](#cpconretrievingmultipleinstancesofattributeappliedtosamescope)  
  
-   [检索应用到不同的作用域的属性的多个实例](#cpconretrievingmultipleinstancesofattributeappliedtodifferentscopes)  
  
<a name="cpconretrievingsingleinstanceofattribute"></a>   
## <a name="retrieving-a-single-instance-of-an-attribute"></a>检索属性的一个实例  
 在下面的示例中， `DeveloperAttribute` （上一节中所述） 应用于`MainApp`类级别上的类。 `GetAttribute`方法使用**GetCustomAttribute**检索中存储的值`DeveloperAttribute`之前向控制台显示它们的类级别上。  
  
 [!code-cpp[Conceptual.Attributes.Usage#18](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source3.cpp#18)]
 [!code-csharp[Conceptual.Attributes.Usage#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source3.cs#18)]
 [!code-vb[Conceptual.Attributes.Usage#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source3.vb#18)]  
  
 此程序显示以下文本时执行。  
  
```  
The Name Attribute is: Joan Smith.  
The Level Attribute is: 42.  
The Reviewed Attribute is: True.  
```  
  
 如果未找到该属性， **GetCustomAttribute**方法初始化`MyAttribute`为 null 值。 此示例检查`MyAttribute`的此类实例，并通知用户，如果不找到任何属性。 如果`DeveloperAttribute`找不到在类范围中，向控制台显示以下消息。  
  
```  
The attribute was not found.   
```  
  
 此示例假定属性定义是在当前命名空间。 请记住要导入的属性定义驻留如果它不在当前命名空间的命名空间。  
  
<a name="cpconretrievingmultipleinstancesofattributeappliedtosamescope"></a>   
## <a name="retrieving-multiple-instances-of-an-attribute-applied-to-the-same-scope"></a>检索属性应用于同一范围内的多个实例  
 在前面的示例中，要检查的类和要查找的特定属性将传递到<xref:System.Attribute.GetCustomAttribute%2A>。 如果也只在类级别上应用属性的一个实例，该代码将运行。 但是，如果属性的多个实例应用于相同的类级别， **GetCustomAttribute**方法未检索所有信息。 在其中将同一特性的多个实例应用于同一作用域的情况下，你可以使用<xref:System.Attribute.GetCustomAttributes%2A?displayProperty=nameWithType>放置到一个数组的所有实例的属性。 例如，如果两个实例的`DeveloperAttribute`同一类中，在类级别上应用`GetAttribute`方法可以修改，以显示在这两个属性中找到的信息。 请记住，在同一级别中，将多个属性必须与定义的属性**AllowMultiple**属性设置为**true**中<xref:System.AttributeUsageAttribute>。  
  
 下面的代码示例演示如何使用**GetCustomAttributes**方法来创建一个数组，其中引用的所有实例`DeveloperAttribute`在任何给定类。 所有属性的值将显示到控制台。  
  
 [!code-cpp[Conceptual.Attributes.Usage#19](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source3.cpp#19)]
 [!code-csharp[Conceptual.Attributes.Usage#19](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source3.cs#19)]
 [!code-vb[Conceptual.Attributes.Usage#19](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source3.vb#19)]  
  
 如果找不到任何属性，该代码将提醒用户。 否则，在两个实例中包含的信息`DeveloperAttribute`显示。  
  
<a name="cpconretrievingmultipleinstancesofattributeappliedtodifferentscopes"></a>   
## <a name="retrieving-multiple-instances-of-an-attribute-applied-to-different-scopes"></a>检索应用到不同的作用域的属性的多个实例  
 <xref:System.Attribute.GetCustomAttributes%2A>和<xref:System.Attribute.GetCustomAttribute%2A>方法不会搜索整个类和在该类中返回的属性的所有实例。 相反，它们一次搜索只能有一个指定的方法或成员。 如果类具有相同的属性应用于每个成员，并且你想要检索中应用于这些成员的所有属性的值，则必须为每个方法或成员单独向**GetCustomAttributes**和**GetCustomAttribute**。  
  
 下面的代码示例采用类作为一个参数，并搜索`DeveloperAttribute`（已定义以前） 和该类的每个单个方法的类级别上。  
  
 [!code-cpp[Conceptual.Attributes.Usage#20](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source3.cpp#20)]
 [!code-csharp[Conceptual.Attributes.Usage#20](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source3.cs#20)]
 [!code-vb[Conceptual.Attributes.Usage#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source3.vb#20)]  
  
 如果没有实例`DeveloperAttribute`上的方法级别或类级别上，找到`GetAttribute`方法，则通知用户，未找到特性，并显示方法或不包含属性的类的名称。 如果找到一个属性， `Name`， `Level`，和`Reviewed`字段显示到控制台。  
  
 你可以使用的成员<xref:System.Type>类，以传递的类中获取的各个方法和成员。 该示例首先查询**类型**对象以获取类级别的特性信息。 接下来，它使用<xref:System.Type.GetMethods%2A?displayProperty=nameWithType>将转换为数组的所有方法的实例放<xref:System.Reflection.MemberInfo?displayProperty=nameWithType>要检索的方法级别的属性信息的对象。 你还可以使用<xref:System.Type.GetProperties%2A?displayProperty=nameWithType>方法来检查在属性级别上的属性或<xref:System.Type.GetConstructors%2A?displayProperty=nameWithType>要检查的构造函数级别上的特性。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Type?displayProperty=nameWithType>  
 <xref:System.Attribute.GetCustomAttribute%2A?displayProperty=nameWithType>  
 <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=nameWithType>  
 [特性](../../../docs/standard/attributes/index.md)
