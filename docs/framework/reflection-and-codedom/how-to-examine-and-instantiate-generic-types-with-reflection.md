---
title: "如何：使用反射检查和实例化泛型类型 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "泛型 [.NET Framework], 反射"
  - "反射, 泛型类型"
ms.assetid: f93b03b0-1778-43fc-bc6d-35983d210e74
caps.latest.revision: 16
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 16
---
# 如何：使用反射检查和实例化泛型类型
与其他类型的信息一样，泛型类型的信息的获取方式为：检查表示泛型类型的 <xref:System.Type> 对象。  主要的差异在于，泛型类型具有一组表示其泛型类型参数的 <xref:System.Type> 对象。  本部分的第一个步骤是检查泛型类型。  
  
 通过将类型变量绑定到泛型类型定义的类型参数，可以创建表示构造类型的 <xref:System.Type> 对象。  第二个步骤演示此过程。  
  
### 检查泛型类型及其类型参数  
  
1.  获取表示泛型类型的 <xref:System.Type> 实例。  在下面的代码中，使用 C\# 的 `typeof` 运算符（在 Visual Basic 中为 `GetType`，在 Visual C\+\+ 中为 `typeid`）获取类型。  有关获取 <xref:System.Type> 对象的其他方法，请参见 <xref:System.Type> 类主题。  注意，余下的步骤中，类型包含在名为 `t` 的方法参数中。  
  
     [!code-cpp[HowToGeneric#2](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#2)]
     [!code-csharp[HowToGeneric#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#2)]
     [!code-vb[HowToGeneric#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#2)]  
  
2.  使用 <xref:System.Type.IsGenericType%2A> 属性确定类型是否为泛型，然后使用 <xref:System.Type.IsGenericTypeDefinition%2A> 属性确定类型是否为泛型类型定义。  
  
     [!code-cpp[HowToGeneric#3](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#3)]
     [!code-csharp[HowToGeneric#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#3)]
     [!code-vb[HowToGeneric#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#3)]  
  
3.  使用 <xref:System.Type.GetGenericArguments%2A> 方法获取包含泛型类型参数的数组。  
  
     [!code-cpp[HowToGeneric#4](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#4)]
     [!code-csharp[HowToGeneric#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#4)]
     [!code-vb[HowToGeneric#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#4)]  
  
4.  对每个类型变量，使用 <xref:System.Type.IsGenericParameter%2A> 属性确定其是不是类型参数（例如，在泛型类型定义中），是不是已为类型参数指定的类型（例如，在构造类型中）。  
  
     [!code-cpp[HowToGeneric#5](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#5)]
     [!code-csharp[HowToGeneric#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#5)]
     [!code-vb[HowToGeneric#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#5)]  
  
5.  在类型系统中，和普通类型一样，泛型类型参数是由 <xref:System.Type> 的实例表示的。  下面的代码演示表示泛型类型参数的 <xref:System.Type> 对象的名称和参数位置。  此处，参数位置无足轻重；它在检查类型参数（用作其他泛型类型的类型变量）时更有价值。  
  
     [!code-cpp[HowToGeneric#6](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#6)]
     [!code-csharp[HowToGeneric#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#6)]
     [!code-vb[HowToGeneric#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#6)]  
  
6.  通过使用 <xref:System.Type.GetGenericParameterConstraints%2A> 方法获取单个数组中的所有约束，确定泛型类型参数的基类型约束和接口约束。  不保证约束处于任何特定顺序。  
  
     [!code-cpp[HowToGeneric#7](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#7)]
     [!code-csharp[HowToGeneric#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#7)]
     [!code-vb[HowToGeneric#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#7)]  
  
7.  使用 <xref:System.Type.GenericParameterAttributes%2A> 属性获取类型参数的特殊约束，如要求其为引用类型。  该属性还包含表示方差的值，该值可屏蔽，如下面的代码所示。  
  
     [!code-cpp[HowToGeneric#8](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#8)]
     [!code-csharp[HowToGeneric#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#8)]
     [!code-vb[HowToGeneric#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#8)]  
  
8.  特殊约束的特性为标志，表示没有任何特殊约束的标志 \(<xref:System.Reflection.GenericParameterAttributes?displayProperty=fullName>\) 还表示没有协变或逆变。  因此，若要测试其中一个条件，必须使用适当的屏蔽。  在此情况下，请使用 <xref:System.Reflection.GenericParameterAttributes?displayProperty=fullName> 隔离特殊约束标志。  
  
     [!code-cpp[HowToGeneric#9](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#9)]
     [!code-csharp[HowToGeneric#9](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#9)]
     [!code-vb[HowToGeneric#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#9)]  
  
## 构造泛型类型的实例  
 泛型类型和模板类似。  除非指定其泛型类型参数的实际类型，否则不能创建泛型类型的实例。  若要在运行时使用反射创建实例，需要使用 <xref:System.Type.MakeGenericType%2A> 方法。  
  
#### 构造泛型类型的实例  
  
1.  获取表示泛型类型的 <xref:System.Type> 对象。  下面的代码以两种不同方式获取泛型类型 <xref:System.Collections.Generic.Dictionary%602>：一种方法使用 <xref:System.Type.GetType%28System.String%29?displayProperty=fullName> 方法重载和描述类型的字符串，另一种方法调用构造类型 `Dictionary\<String, Example>`（在 Visual Basic 中为 `Dictionary(Of String, Example)`）的 <xref:System.Type.GetGenericTypeDefinition%2A> 方法。  <xref:System.Type.MakeGenericType%2A> 方法需要泛型类型定义。  
  
     [!code-cpp[HowToGeneric#10](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#10)]
     [!code-csharp[HowToGeneric#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#10)]
     [!code-vb[HowToGeneric#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#10)]  
  
2.  构造一组用于替换类型参数的类型变量。  数组必须包含正确数目的 <xref:System.Type> 对象，并且顺序和对象在类型参数列表中的顺序相同。  在这种情况下，键（第一个类型参数）的类型为 <xref:System.String>，字典中的值是名为 `Example` 的类的实例。  
  
     [!code-cpp[HowToGeneric#11](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#11)]
     [!code-csharp[HowToGeneric#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#11)]
     [!code-vb[HowToGeneric#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#11)]  
  
3.  调用 <xref:System.Type.MakeGenericType%2A> 方法将类型变量绑定到类型参数，然后构造类型。  
  
     [!code-cpp[HowToGeneric#12](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#12)]
     [!code-csharp[HowToGeneric#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#12)]
     [!code-vb[HowToGeneric#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#12)]  
  
4.  使用 <xref:System.Activator.CreateInstance%28System.Type%29> 方法重载来创建构造类型的对象。  下面的代码在生成的 `Dictionary<String, Example>` 对象中存储 `Example` 类的两个实例。  
  
     [!code-cpp[HowToGeneric#13](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#13)]
     [!code-csharp[HowToGeneric#13](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#13)]
     [!code-vb[HowToGeneric#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#13)]  
  
## 示例  
 下面的代码示例定义 `DisplayGenericType` 方法来检查泛型类型定义和代码中使用的构造类型，并显示它们的信息。  `DisplayGenericType` 方法演示如何使用 <xref:System.Type.IsGenericType%2A>、<xref:System.Type.IsGenericParameter%2A> 和 <xref:System.Type.GenericParameterPosition%2A> 属性以及 <xref:System.Type.GetGenericArguments%2A> 方法。  
  
 该示例还定义 `DisplayGenericParameter` 方法来检查泛型类型参数并显示其约束。  
  
 代码示例定义一组测试类型，包括说明类型参数约束的泛型类型，并演示如何显示这些类型的信息。  
  
 示例通过创建一组类型参数并调用 <xref:System.Type.MakeGenericType%2A> 方法，从 <xref:System.Collections.Generic.Dictionary%602> 类构造类型。  程序对使用 <xref:System.Type.MakeGenericType%2A> 构造的 <xref:System.Type> 对象和使用 `typeof`（Visual Basic 中为 `GetType`）获取的 <xref:System.Type> 对象进行比较，演示这两个对象是相同的。  类似地，程序使用 <xref:System.Type.GetGenericTypeDefinition%2A> 方法获取构造类型的泛型类型定义，并将其与表示 <xref:System.Collections.Generic.Dictionary%602> 类的 <xref:System.Type> 对象进行比较。  
  
 [!code-cpp[HowToGeneric#1](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#1)]
 [!code-csharp[HowToGeneric#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#1)]
 [!code-vb[HowToGeneric#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#1)]  
  
## 编译代码  
  
-   代码包含编译所需的 C\# `using` 语句（在 Visual Basic 中为 `Imports`）。  
  
-   不需要其他程序集引用。  
  
-   在命令行使用 csc.exe、vbc.exe 或 cl.exe 编译代码。  若要在 Visual Studio 中编译代码，请将代码置于控制台应用程序项目模板中。  
  
## 请参阅  
 <xref:System.Type>   
 <xref:System.Reflection.MethodInfo>   
 [反射类型和泛型类型](../../../docs/framework/reflection-and-codedom/reflection-and-generic-types.md)   
 [查看类型信息](../../../docs/framework/reflection-and-codedom/viewing-type-information.md)   
 [泛型](../../../docs/standard/generics/index.md)