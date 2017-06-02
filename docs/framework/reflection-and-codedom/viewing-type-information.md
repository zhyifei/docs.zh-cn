---
title: "查看类型信息 | Microsoft Docs"
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
helpviewer_keywords: 
  - "反射, 查看类型信息"
  - "Type 对象"
  - "类型, 查看类型信息"
  - "查看类型信息"
ms.assetid: 7e7303a9-4064-4738-b4e7-b75974ed70d2
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# 查看类型信息
<xref:System.Type?displayProperty=fullName> 类对于反射起着核心的作用。  当反射请求加载的类型时，公共语言运行时将为它创建一个 **Type**。  您可以使用 **Type** 对象的方法、字段、属性和嵌套类来查找有关该类型的所有信息。  
  
 使用 <xref:System.Reflection.Assembly.GetType%2A?displayProperty=fullName> 或 <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=fullName> 从尚未加载的程序集中获取 **Type** 对象，并传入所需类型的名称。  使用 <xref:System.Type.GetType%2A?displayProperty=fullName> 可从已加载的程序集中获取 **Type** 对象。  使用 <xref:System.Reflection.Module.GetType%2A?displayProperty=fullName> 和 <xref:System.Reflection.Module.GetTypes%2A?displayProperty=fullName> 可获取模块 **Type** 对象。  
  
> [!NOTE]
>  如果想要检查和操作泛型类型和方法，请参见[反射类型和泛型类型](../../../docs/framework/reflection-and-codedom/reflection-and-generic-types.md)和[如何：使用反射检查和实例化泛型类型](../../../docs/framework/reflection-and-codedom/how-to-examine-and-instantiate-generic-types-with-reflection.md)中提供的附加信息。  
  
 下面的示例显示在获取程序集的 <xref:System.Reflection.Assembly> 对象和模块时所必需的语法。  
  
 [!code-cpp[Conceptual.Types.ViewInfo#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source5.cpp#6)]
 [!code-csharp[Conceptual.Types.ViewInfo#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source5.cs#6)]
 [!code-vb[Conceptual.Types.ViewInfo#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source5.vb#6)]  
  
 下面的示例说明如何从已加载的程序集中获取 **Type** 对象。  
  
 [!code-cpp[Conceptual.Types.ViewInfo#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source5.cpp#7)]
 [!code-csharp[Conceptual.Types.ViewInfo#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source5.cs#7)]
 [!code-vb[Conceptual.Types.ViewInfo#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source5.vb#7)]  
  
 在获取了一个 **Type** 后，您可以采用许多方法来发现与该类型的成员有关的信息。  例如，通过调用 <xref:System.Type.GetMembers%2A?displayProperty=fullName> 方法（该方法将获取对当前类型的每个成员进行描述的一组 <xref:System.Reflection.MemberInfo> 对象），您可以找到有关该类型的所有成员的信息。  
  
 您也可以在 **Type** 类上使用方法，以检索有关按名称指定的一个或多个构造函数、方法、事件、字段或属性的信息。  例如，<xref:System.Type.GetConstructor%2A?displayProperty=fullName> 封装当前类的特定构造函数。  
  
 如果具有 **Type**，则可以使用 <xref:System.Type.Module%2A?displayProperty=fullName> 属性来获取一个封装该类型所在模块的对象。  使用 <xref:System.Reflection.Module.Assembly%2A?displayProperty=fullName> 属性可查找封装模块所在程序集的对象。  使用 <xref:System.Type.Assembly%2A?displayProperty=fullName> 属性可直接获取封装该类型的程序集。  
  
## System.Type 和 ConstructorInfo  
 下面的示例演示如何列出一个类（此示例中为 <xref:System.String> 类）的构造函数。  
  
 [!code-cpp[Conceptual.Types.ViewInfo#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source1.cpp#1)]
 [!code-csharp[Conceptual.Types.ViewInfo#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source1.cs#1)]
 [!code-vb[Conceptual.Types.ViewInfo#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source1.vb#1)]  
  
## MemberInfo、MethodInfo、FieldInfo 和 PropertyInfo  
 使用 <xref:System.Reflection.MemberInfo>、<xref:System.Reflection.MethodInfo>、<xref:System.Reflection.FieldInfo> 或 <xref:System.Reflection.PropertyInfo> 对象获取有关该类型的方法、属性、事件和字段的信息。  
  
 下面的示例使用 **MemberInfo** 列出 **System.IO.File** 类中的成员数量并使用 [System.Type.IsPublic](frlrfSystemTypeClassIsPublicTopic) 属性确定该类的可见性。  
  
 [!code-cpp[Conceptual.Types.ViewInfo#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source2.cpp#2)]
 [!code-csharp[Conceptual.Types.ViewInfo#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source2.cs#2)]
 [!code-vb[Conceptual.Types.ViewInfo#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source2.vb#2)]  
  
 下面的示例调查指定成员的类型。  它对 **MemberInfo** 类的一个成员执行反射，然后列出其类型。  
  
 [!code-cpp[Conceptual.Types.ViewInfo#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source3.cpp#3)]
 [!code-csharp[Conceptual.Types.ViewInfo#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source3.cs#3)]
 [!code-vb[Conceptual.Types.ViewInfo#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source3.vb#3)]  
  
 下面的示例使用所有的反射 **\*Info** 类以及 <xref:System.Reflection.BindingFlags> 来列出指定类的所有成员（构造函数、字段、属性、事件和方法），并将这些成员划分为静态和实例类别。  
  
 [!code-cpp[Conceptual.Types.ViewInfo#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source4.cpp#4)]
 [!code-csharp[Conceptual.Types.ViewInfo#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source4.cs#4)]
 [!code-vb[Conceptual.Types.ViewInfo#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source4.vb#4)]  
  
## 请参阅  
 <xref:System.Reflection.BindingFlags>   
 <xref:System.Reflection.Assembly.GetType%2A?displayProperty=fullName>   
 <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=fullName>   
 <xref:System.Type.GetType%2A?displayProperty=fullName>   
 <xref:System.Type.GetMembers%2A?displayProperty=fullName>   
 <xref:System.Type.GetFields%2A?displayProperty=fullName>   
 <xref:System.Reflection.Module.GetType%2A?displayProperty=fullName>   
 <xref:System.Reflection.Module.GetTypes%2A?displayProperty=fullName>   
 <xref:System.Reflection.MemberInfo>   
 <xref:System.Reflection.ConstructorInfo>   
 <xref:System.Reflection.MethodInfo>   
 <xref:System.Reflection.FieldInfo>   
 <xref:System.Reflection.EventInfo>   
 <xref:System.Reflection.ParameterInfo>   
 [反射类型和泛型类型](../../../docs/framework/reflection-and-codedom/reflection-and-generic-types.md)