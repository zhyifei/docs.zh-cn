---
title: "动态加载和使用类型 | Microsoft Docs"
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
  - "动态加载和使用类型"
  - "早期绑定"
  - "隐式后期绑定"
  - "后期绑定, 关于后期绑定"
  - "反射, 动态使用类型"
ms.assetid: db985bec-5942-40ec-b13a-771ae98623dc
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 13
---
# 动态加载和使用类型
反射提供语言编译器（如 [!INCLUDE[vbprvbext](../../../includes/vbprvbext-md.md)] 和 JScript）用于实现隐式后期绑定的基础结构。  绑定是查找与唯一指定的类型相对应的声明（即实现）的过程。  如果此过程是在运行时而不是在编译时发生，则称其为“后期绑定”。  利用 [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)]，可以在代码中使用隐式后期绑定；Visual Basic 编译器会调用一个帮助器方法，该方法使用反射来获取对象类型。  传递给帮助器方法的参数有助于在运行时调用正确的方法。  这些参数包括：对其调用方法的实例（对象），被调用方法的名称（字符串），以及传递给被调用方法的参数（对象数组）。  
  
 在下面的示例中，Visual Basic 编译器使用反射隐式地对其类型在编译时未知的对象调用方法。  **HelloWorld** 类具有一个 **PrintHello** 方法，它输出与传递给 **PrintHello** 方法的某些文本串联的“Hello World”。  在此示例中调用的 **PrintHello** 方法实际上是 <xref:System.Type.InvokeMember%2A?displayProperty=fullName>；Visual Basic 代码允许按照对象 \(helloObj\) 的类型在编译时已知（早期绑定）而不是在运行时已知（后期绑定）的方式来调用 **PrintHello** 方法。  
  
```  
Imports System  
Module Hello  
    Sub Main()  
        ' Sets up the variable.  
        Dim helloObj As Object  
        ' Creates the object.  
        helloObj = new HelloWorld()  
        ' Invokes the print method as if it was early bound  
        ' even though it is really late bound.  
        helloObj.PrintHello("Visual Basic Late Bound")  
    End Sub  
End Module  
```  
  
## 自定义绑定  
 除了由编译器隐式地用来进行后期绑定之外，反射还可以在代码中显式地用来完成后期绑定。  
  
 [公共语言运行时](../../../docs/standard/clr.md)支持多种编程语言，但这些语言的绑定规则各不相同。  在早期绑定的情况下，代码生成器可以完全控制此绑定。  但是，当通过反射进行后期绑定时，必须用自定义绑定来控制绑定。  <xref:System.Reflection.Binder> 类提供了对成员选择和调用的自定义控制。  
  
 利用自定义绑定，您可以在运行时加载程序集，获取有关该程序集中类型的信息，然后对该类型调用方法或访问该类型的字段或属性。  如果您在编译时（例如当对象类型依赖于用户输入时）不知道对象的类型，就可以使用这种方法。  
  
 下面的示例说明不提供参数类型转换的简单的自定义联编程序。  `Simple_Type.dll` 的代码位于示例主体之前。  确保生成 `Simple_Type.dll`，然后在生成时在项目中包括对它的引用。  
  
 [!code-cpp[Conceptual.Types.Dynamic#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.dynamic/cpp/source1.cpp#1)]
 [!code-csharp[Conceptual.Types.Dynamic#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.dynamic/cs/source1.cs#1)]
 [!code-vb[Conceptual.Types.Dynamic#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.dynamic/vb/source1.vb#1)]  
  
### InvokeMember 和 CreateInstance  
 使用 <xref:System.Type.InvokeMember%2A?displayProperty=fullName> 可调用类型的成员。  各个类（如 [System.Activator](frlrfSystemActivatorClassCreateInstanceTopic) 和 [System.Reflection.Assembly](frlrfSystemReflectionAssemblyClassCreateInstanceTopic)）的 **CreateInstance** 方法是 **InvokeMember** 的特殊形式，它们可新建特定类型的实例。  **Binder** 类用于在这些方法中进行重载决策和参数强制。  
  
 下面的示例显示参数强制（类型转换）和成员选择的三种可能的组合。  在第 1 种情况中，不需要任何参数强制或成员选择。  在第 2 种情况中，只需要成员选择。  在第 3 种情况中，只需要参数强制。  
  
 [!code-cpp[Conceptual.Types.Dynamic#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.dynamic/cpp/source2.cpp#2)]
 [!code-csharp[Conceptual.Types.Dynamic#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.dynamic/cs/source2.cs#2)]
 [!code-vb[Conceptual.Types.Dynamic#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.dynamic/vb/source2.vb#2)]  
  
 当多个成员具有相同的名称时，将需要重载决策。  <xref:System.Reflection.Binder.BindToMethod%2A?displayProperty=fullName> 和 <xref:System.Reflection.Binder.BindToField%2A?displayProperty=fullName> 方法用于解析与单个成员的绑定。  **Binder.BindToMethod** 还通过 **get** 和 **set** 属性访问器提供了属性解析。  
  
 **BindToMethod** 返回要调用的 <xref:System.Reflection.MethodBase>；如果无法进行这种调用，则返回 null 引用（在 Visual Basic 中为 **Nothing**）。  虽然 **MethodBase** 返回值通常是 *match* 参数中所包含的值之一，但它并不必如此。  
  
 当存在 ByRef 参数时，调用方可能需要取回这些参数。  因此，如果 **BindToMethod** 已经操作参数数组，**Binder** 会允许客户端将参数数组映射回它的初始形式。  为了实现这一目的，必须向调用方保证参数的顺序不会改变。  当按名称传递参数时，**Binder** 将重新排列参数数组，这就是调用方所见的参数。  有关更多信息，请参见 <xref:System.Reflection.Binder.ReorderArgumentArray%2A?displayProperty=fullName>。  
  
 可用成员集包括在类型和任何基类型中定义的成员。  如果指定 [BindingFlags.NonPublic](frlrfSystemReflectionBindingFlagsClassTopic)，将返回该成员集中具有任何可访问性的成员。  如果未指定 **BindingFlags.NonPublic**，联编程序就必须强制可访问性规则。  当指定 **Public** 或 **NonPublic** 绑定标志时，还必须指定 **Instance** 或 **Static** 绑定标志，否则不会返回任何成员。  
  
 如果只有一个成员具有给定名称，则不必进行回调，而在该方法上进行绑定。  代码示例的第 1 种情况说明了这一点：只有一个 **PrintBob** 方法可用，因此不需要进行回调。  
  
 如果可用集中有多个成员，所有这些方法都将传递给 **BindToMethod**，它将选择正确的方法并将其返回。  在代码示例的第 2 种情况下，有两个名为 **PrintValue** 的方法。  对 **BindToMethod** 的调用将选择正确的方法。  
  
 <xref:System.Reflection.Binder.ChangeType%2A> 执行参数强制转换（类型转换），以便将实参转换为选定方法的形参的类型。  即使类型完全匹配，也会为每个参数调用 **ChangeType**。  
  
 在代码示例的第 3 种情况下，将类型为 **String** 值为“5.5”的实参传递给了具有类型为 **Double** 的形参的方法。  要使调用成功，必须将字符串值“5.5”转换为 double 值。  **ChangeType** 会执行此转换。  
  
 **ChangeType** 仅执行无损或[扩大强制](../../../docs/standard/base-types/type-conversion.md)，如下表所示。  
  
|源类型|目标类型|  
|---------|----------|  
|任何类型|它的基类型|  
|任何类型|它所实现的接口|  
|Char|UInt16、UInt32、Int32、UInt64、Int64、Single、Double|  
|Byte|Char、UInt16、Int16、UInt32、Int32、UInt64、Int64、Single、Double|  
|SByte|Int16、Int32、Int64、Single、Double|  
|UInt16|UInt32、Int32、UInt64、Int64、Single、Double|  
|Int16|Int32、Int64、Single、Double|  
|UInt32|UInt64、Int64、Single、Double|  
|Int32|Int64、Single、Double|  
|UInt64|Single、Double|  
|Int64|Single、Double|  
|Single|Double|  
|非引用类型|引用类型|  
  
 <xref:System.Type> 类具有 **Get** 方法，这些方法使用 **Binder** 类型的参数来解析对特定成员的引用。  <xref:System.Type.GetConstructor%2A?displayProperty=fullName>、<xref:System.Type.GetMethod%2A?displayProperty=fullName> 和 <xref:System.Type.GetProperty%2A?displayProperty=fullName> 通过提供当前类型的特定成员的签名信息来搜索该成员。  对 <xref:System.Reflection.Binder.SelectMethod%2A?displayProperty=fullName> 和 <xref:System.Reflection.Binder.SelectProperty%2A?displayProperty=fullName> 进行回调以选择适当方法的给定签名信息。  
  
## 请参阅  
 <xref:System.Type.InvokeMember%2A?displayProperty=fullName>   
 <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName>   
 [查看类型信息](../../../docs/framework/reflection-and-codedom/viewing-type-information.md)   
 [.NET Framework 中的类型转换](../../../docs/standard/base-types/type-conversion.md)