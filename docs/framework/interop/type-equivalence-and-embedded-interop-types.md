---
title: "类型等效性和嵌入的互操作类型 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "嵌入的互操作类型"
  - "NoPIA"
  - "主互操作程序集, 在 CLR 版本 4 中不是必需的"
  - "类型等效性"
ms.assetid: 78892eba-2a58-4165-b4b1-0250ee2f41dc
caps.latest.revision: 17
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 17
---
# 类型等效性和嵌入的互操作类型
从 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]开始，公共语言运行时支持将 COM 类型的类型信息直接嵌入到托管程序集中，而不是要求托管程序集从互操作程序集中获取 COM 类型的类型信息。  由于嵌入的类型信息只包含托管程序集实际所使用的类型和成员，因此两个托管程序集可能会具有相同 COM 类型的截然不同的视图。  每个托管程序集使用不同的 <xref:System.Type> 对象来表示各自的 COM 类型视图。  公共语言运行时支持这些不同视图之间的类型等效性，这些类型包括接口、结构、枚举和委托。  
  
 类型等效性意味着，在两个托管程序集之间传递的 COM 对象在接收程序集中可以转换为适当的托管类型。  
  
> [!NOTE]
>  类型等效性和嵌入的互操作类型可简化使用 COM 组件的应用程序和外接程序的部署过程，这是因为不需要使用应用程序来部署互操作程序集。  共享 COM 组件的开发人员若想使其组件可供早期版本的 .NET Framework 使用，则他们仍然必须创建主互操作程序集 \(PIA\)。  
  
## 类型等效性  
 COM 类型等效性支持的类型包括接口、结构、枚举和委托。  如果满足下面的所有条件，则 COM 类型符合等效要求：  
  
-   两个类型同时为接口、结构、枚举或委托。  
  
-   两个类型具有相同的标识，如下一节中所述。  
  
-   两个类型符合类型等效性要求，如[针对类型等效性标记 COM 类型](#type_equiv)一节中所述。  
  
### 类型标识  
 当两个类型的范围和标识相匹配时，确定这两个类型具有相同的标识；也就是说，如果两个类型中的每个类型都具有 <xref:System.Runtime.InteropServices.TypeIdentifierAttribute> 特性，则这两个特性具有匹配的 <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Scope%2A> 和 <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Identifier%2A> 属性。  <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Scope%2A> 的比较不区分大小写。  
  
 如果某个类型不具有 <xref:System.Runtime.InteropServices.TypeIdentifierAttribute> 特性，或者具有未指定范围和标识符的 <xref:System.Runtime.InteropServices.TypeIdentifierAttribute> 特性，则仍可以将该类型视为符合等效性，如下所示：  
  
-   对于接口，使用 <xref:System.Runtime.InteropServices.GuidAttribute> 的值来代替使用 <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Scope%2A?displayProperty=fullName> 属性，并使用 <xref:System.Type.FullName%2A?displayProperty=fullName> 属性（即，包括命名空间的类型名称）来代替使用 <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Identifier%2A?displayProperty=fullName> 属性。  
  
-   对于结构、枚举和委托，使用包含程序集的 <xref:System.Runtime.InteropServices.GuidAttribute> 来代替使用 <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Scope%2A> 属性，并使用 <xref:System.Type.FullName%2A?displayProperty=fullName> 属性来代替使用 <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Identifier%2A> 属性。  
  
<a name="type_equiv"></a>   
### 针对类型等效性标记 COM 类型  
 可以通过以下两种方式将一个类型标记为符合类型等效性：  
  
-   将 <xref:System.Runtime.InteropServices.TypeIdentifierAttribute> 特性应用于类型。  
  
-   将类型标记为 COM 导入类型。  一个接口如果具有 <xref:System.Runtime.InteropServices.ComImportAttribute> 特性，则表示它为 COM 导入类型。  一个接口、结构、枚举或委托如果是在具有 <xref:System.Runtime.InteropServices.ImportedFromTypeLibAttribute> 特性的程序集中定义的，则表示它为 COM 导入类型。  
  
## 请参阅  
 <xref:System.Type.IsEquivalentTo%2A>   
 [Using COM Types in Managed Code](http://msdn.microsoft.com/zh-cn/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66)   
 [将类型库当作程序集导入](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md)