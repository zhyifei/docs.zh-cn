---
title: "如何：用反射发出定义泛型方法 | Microsoft Docs"
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
  - "泛型 [.NET Framework], 动态类型"
  - "泛型 [.NET Framework], 反射发出"
  - "反射发出, 泛型方法"
ms.assetid: 93892fa4-90b3-4ec4-b147-4bec9880de2b
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 13
---
# 如何：用反射发出定义泛型方法
第一个过程演示如何使用两个类型参数创建一个简单的泛型方法，以及如何对类型参数应用类约束、接口约束和特殊约束。  
  
 第二个过程演示如何发出方法体，以及如何使用泛型方法的类型参数创建泛型类型的实例以及调用其方法。  
  
 第三个过程演示如何调用泛型方法。  
  
> [!IMPORTANT]
>  不能仅因为某个方法属于泛型类型且使用泛型类型的类型参数，就称该方法是泛型方法。  只有当方法具有自己的类型参数列表时，才能称其为泛型方法。  泛型方法可以出现在非泛型类型上，在本例中就是如此。  有关泛型类型上的非泛型方法的示例，请参见[如何：用反射发出定义泛型类型](../../../docs/framework/reflection-and-codedom/how-to-define-a-generic-type-with-reflection-emit.md)。  
  
### 定义泛型方法  
  
1.  首先，如果使用高级语言编写，则查看泛型方法的显示方式会十分有用。  下面的代码包含在此主题的代码示例中，用于调用泛型方法的代码同样也包含在其中。  该方法具有两个类型参数 `TInput` 和 `TOutput`，后者必须为引用类型 \(`class`\)，必须具有无参数构造函数 \(`new`\)，并且必须实现 `ICollection(Of TInput)`（在 C\# 中为 `ICollection<TInput>`）。  此接口约束确保 <xref:System.Collections.Generic.ICollection%601.Add%2A?displayProperty=fullName> 方法可用于将元素添加到该方法创建的 `TOutput` 集合中。  该方法具有一个形参 `input`，这是一个 `TInput` 的数组。  该方法创建类型 `TOutput` 的集合，并将 `input` 的元素复制到该集合中。  
  
     [!code-csharp[GenericMethodHowTo#20](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#20)]
     [!code-vb[GenericMethodHowTo#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#20)]  
  
2.  定义一个动态程序集和一个动态模块，以包含该泛型方法所属的类型。  在本例中，该程序集仅拥有一个模块（名为 `DemoMethodBuilder1`），模块名称即为程序集名称加上一个扩展名。  在此示例中，将程序集保存到磁盘中并执行，因此指定了 <xref:System.Reflection.Emit.AssemblyBuilderAccess?displayProperty=fullName>。  您可以使用 [Ildasm.exe（IL 反汇编程序）](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) 检查 DemoMethodBuilder1.dll，并将其与步骤 1 中显示的方法的 Microsoft 中间语言 \(MSIL\) 进行比较。  
  
     [!code-csharp[GenericMethodHowTo#2](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#2)]
     [!code-vb[GenericMethodHowTo#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#2)]  
  
3.  定义该泛型方法所属的类型。  该类型不一定为泛型类型。  泛型方法可以属于泛型类型，也可以属于非泛型类型。  在此示例中，该类型为一个类，它不是泛型类型，名称为 `DemoType`。  
  
     [!code-csharp[GenericMethodHowTo#3](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#3)]
     [!code-vb[GenericMethodHowTo#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#3)]  
  
4.  定义泛型方法。  如果泛型方法的形参的类型由该泛型方法的泛型类型参数指定，请使用 <xref:System.Reflection.Emit.TypeBuilder.DefineMethod%28System.String%2CSystem.Reflection.MethodAttributes%29> 方法重载定义该方法。  该方法的泛型类型参数尚未定义，因此不能在对 <xref:System.Reflection.Emit.TypeBuilder.DefineMethod%2A> 的调用中指定该方法的形参的类型。  在此示例中，该方法名为 `Factory`。  该方法是公共方法，并且是 `static`（在 Visual Basic 中为 `Shared`）的。  
  
     [!code-csharp[GenericMethodHowTo#4](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#4)]
     [!code-vb[GenericMethodHowTo#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#4)]  
  
5.  通过将包含参数名称的字符串数组传递给 <xref:System.Reflection.Emit.MethodBuilder.DefineGenericParameters%2A?displayProperty=fullName> 方法来定义 `DemoMethod` 的泛型类型参数。  这使得该方法成为泛型方法。  下面的代码使得 `Factory` 成为具有类型参数 `TInput` 和 `TOutput` 的泛型方法。  若要使代码更易于阅读，可创建具有这些名称的变量，以保存表示这两个类型参数的 <xref:System.Reflection.Emit.GenericTypeParameterBuilder> 对象。  
  
     [!code-csharp[GenericMethodHowTo#5](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#5)]
     [!code-vb[GenericMethodHowTo#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#5)]  
  
6.  可以选择为类型参数添加特殊约束。  特殊约束是通过使用 <xref:System.Reflection.Emit.GenericTypeParameterBuilder.SetGenericParameterAttributes%2A> 方法添加的。  在此示例中，`TOutput` 被约束为引用类型，并且具有无参数构造函数。  
  
     [!code-csharp[GenericMethodHowTo#6](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#6)]
     [!code-vb[GenericMethodHowTo#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#6)]  
  
7.  可以选择为类型参数添加类约束和接口约束。  在此示例中，类型参数 `TOutput` 被约束为实现 `ICollection(Of TInput)`（在 C\# 中为 `ICollection<TInput>`）接口的类型。  这确保 <xref:System.Collections.Generic.ICollection%601.Add%2A> 方法可用于添加元素。  
  
     [!code-csharp[GenericMethodHowTo#7](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#7)]
     [!code-vb[GenericMethodHowTo#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#7)]  
  
8.  使用 <xref:System.Reflection.Emit.MethodBuilder.SetParameters%2A> 方法定义该方法的形参。  在此示例中，`Factory` 方法具有一个参数，即 `TInput` 的数组。  此类型是通过对表示 `TInput` 的 <xref:System.Reflection.Emit.GenericTypeParameterBuilder> 调用 <xref:System.Type.MakeArrayType%2A> 方法创建的。  <xref:System.Reflection.Emit.MethodBuilder.SetParameters%2A> 的参数是 <xref:System.Type> 对象的数组。  
  
     [!code-csharp[GenericMethodHowTo#8](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#8)]
     [!code-vb[GenericMethodHowTo#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#8)]  
  
9. 使用 <xref:System.Reflection.Emit.MethodBuilder.SetReturnType%2A> 方法定义该方法的返回类型。  在此示例中，返回 `TOutput` 的一个实例。  
  
     [!code-csharp[GenericMethodHowTo#9](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#9)]
     [!code-vb[GenericMethodHowTo#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#9)]  
  
10. 使用 <xref:System.Reflection.Emit.ILGenerator> 发出该方法体。  有关详细信息，请参见附带的发出方法体的过程。  
  
    > [!IMPORTANT]
    >  发出对泛型类型的方法的调用，而且这些类型的类型变量为该泛型方法的类型参数时，您必须使用 <xref:System.Reflection.Emit.TypeBuilder> 类的 `static` <xref:System.Reflection.Emit.TypeBuilder.GetConstructor%28System.Type%2CSystem.Reflection.ConstructorInfo%29>、<xref:System.Reflection.Emit.TypeBuilder.GetMethod%28System.Type%2CSystem.Reflection.MethodInfo%29> 和 <xref:System.Reflection.Emit.TypeBuilder.GetField%28System.Type%2CSystem.Reflection.FieldInfo%29> 方法重载，以获取这些方法的构造形式。  发出方法体的附带过程对此进行了演示。  
  
11. 完成包含该方法的类型并保存程序集。  附带的调用泛型方法过程演示了调用完整方法的两种方式。  
  
     [!code-csharp[GenericMethodHowTo#14](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#14)]
     [!code-vb[GenericMethodHowTo#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#14)]  
  
<a name="procedureSection1"></a>   
### 发出方法体  
  
1.  获取代码生成器并声明局部变量和标签。  <xref:System.Reflection.Emit.ILGenerator.DeclareLocal%2A> 方法用于声明局部变量。  `Factory` 方法具有四个局部变量：`retVal` 用于保存该方法返回的新 `TOutput`，`ic` 用于在 `TOutput` 转换为  `ICollection(Of TInput)`（在 C\# 中为 `ICollection<TInput>`）时将其保存，`input` 用于保存 `TInput` 对象的输入数组，而 `index` 用于循环访问该数组。  该方法还具有使用 <xref:System.Reflection.Emit.ILGenerator.DefineLabel%2A> 方法定义的两个标签，一个用于进入循环 \(`enterLoop`\)，另一个用于循环的顶部 \(`loopAgain`\)。  
  
     该方法首先使用 <xref:System.Reflection.Emit.OpCodes.Ldarg_0> 操作码加载其参数，然后使用 <xref:System.Reflection.Emit.OpCodes.Stloc_S> 操作码将参数存储在局部变量 `input` 中。  
  
     [!code-csharp[GenericMethodHowTo#10](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#10)]
     [!code-vb[GenericMethodHowTo#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#10)]  
  
2.  使用 <xref:System.Activator.CreateInstance%2A?displayProperty=fullName> 方法的泛型方法重载发出代码以创建 `TOutput` 的实例。  使用此重载需要指定类型具有无参数构造函数，这也是向 `TOutput` 添加该约束的原因。  通过将 `TOutput` 传递到 <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A> 创建构造的泛型方法。  发出代码以调用该方法后，发出代码以使用 <xref:System.Reflection.Emit.OpCodes.Stloc_S> 将其存储在局部变量 `retVal` 中  
  
     [!code-csharp[GenericMethodHowTo#11](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#11)]
     [!code-vb[GenericMethodHowTo#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#11)]  
  
3.  发出代码以将新的 `TOutput` 对象强制转换为 `ICollection(Of TInput)`，并将其存储在局部变量 `ic` 中。  
  
     [!code-csharp[GenericMethodHowTo#31](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#31)]
     [!code-vb[GenericMethodHowTo#31](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#31)]  
  
4.  获取表示 <xref:System.Collections.Generic.ICollection%601.Add%2A?displayProperty=fullName> 方法的 <xref:System.Reflection.MethodInfo>。  此方法对 `ICollection(Of TInput)`（在 C\# 中为 `ICollection<TInput>`）进行操作，因此有必要获取特定于该构造类型的 `Add` 方法。  不能使用 <xref:System.Type.GetMethod%2A> 方法直接从 `icollOfTInput` 获取此 <xref:System.Reflection.MethodInfo>，因为 <xref:System.Type.GetMethod%2A> 在已使用 <xref:System.Reflection.Emit.GenericTypeParameterBuilder> 构造的类型上不受支持。  而应该对包含 <xref:System.Collections.Generic.ICollection%601> 泛型接口的泛型类型定义的 `icoll` 调用 <xref:System.Type.GetMethod%2A>。  然后使用 <xref:System.Reflection.Emit.TypeBuilder.GetMethod%28System.Type%2CSystem.Reflection.MethodInfo%29> `static` 方法生成构造类型的 <xref:System.Reflection.MethodInfo>。  下面的代码对此进行了演示。  
  
     [!code-csharp[GenericMethodHowTo#12](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#12)]
     [!code-vb[GenericMethodHowTo#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#12)]  
  
5.  发出代码以初始化 `index` 变量（通过加载 32 位整数 0 并将其存储在变量中）。  发出代码以分支到标签 `enterLoop`。  因为此标签位于循环内，所以尚未进行标记。  该循环的代码在下一步中发出。  
  
     [!code-csharp[GenericMethodHowTo#32](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#32)]
     [!code-vb[GenericMethodHowTo#32](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#32)]  
  
6.  发出该循环的代码。  第一步是标记循环的顶部，方法是用 `loopAgain` 标签调用 <xref:System.Reflection.Emit.ILGenerator.MarkLabel%2A>。  使用该标签的分支语句现在将分支到代码中的这个点。  下一步是将强制转换为 `ICollection(Of TInput)` 的 `TOutput` 对象推入堆栈。  这不需要立即进行，但需要在调用 `Add` 方法之前完成。  接下来，输入数组被推入堆栈，然后是包含该数组的当前索引的 `index` 变量。  <xref:System.Reflection.Emit.OpCodes.Ldelem> 操作码从堆栈中弹出该索引和数组，然后将索引数组元素推入堆栈。  堆栈现在准备好调用 <xref:System.Collections.Generic.ICollection%601.Add%2A?displayProperty=fullName> 方法，该方法从堆栈中弹出集合和新的元素，并将该元素添加到该集合中。  
  
     循环中的其他代码会使索引递增，并通过测试查看循环是否完成：将索引和 32 位整数 1 推入堆栈并相加，在堆栈上保留总和；总和存储在 `index` 中。  然后调用 <xref:System.Reflection.Emit.ILGenerator.MarkLabel%2A> 将该点设置为循环的入口点。  再次加载该索引。  将输入数组推入堆栈，然后发出 <xref:System.Reflection.Emit.OpCodes.Ldlen> 以获取其长度。  索引和长度现在位于堆栈中，并发出 <xref:System.Reflection.Emit.OpCodes.Clt> 对二者进行比较。  如果索引小于长度，<xref:System.Reflection.Emit.OpCodes.Brtrue_S> 会重新返回到循环的起始点。  
  
     [!code-csharp[GenericMethodHowTo#13](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#13)]
     [!code-vb[GenericMethodHowTo#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#13)]  
  
7.  发出代码以将 `TOutput` 对象推入堆栈，并从该方法返回。  局部变量 `retVal` 和 `ic` 均包含对新的 `TOutput` 的引用；`ic` 仅用于访问 <xref:System.Collections.Generic.ICollection%601.Add%2A?displayProperty=fullName> 方法。  
  
     [!code-csharp[GenericMethodHowTo#33](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#33)]
     [!code-vb[GenericMethodHowTo#33](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#33)]  
  
<a name="procedureSection2"></a>   
### 调用泛型方法  
  
1.  `Factory` 为泛型方法定义。  若要调用泛型方法，您必须为泛型方法的泛型类型参数分配类型。  使用 <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A> 方法可完成此操作。  下面的代码通过为 `TInput` 指定 <xref:System.String> 并为 `TOutput` 指定 `List(Of String)`（在 C\# 中为 `List<string>`）创建一个构造的泛型方法，并显示该方法的字符串表示形式。  
  
     [!code-csharp[GenericMethodHowTo#21](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#21)]
     [!code-vb[GenericMethodHowTo#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#21)]  
  
2.  若要以后期绑定的形式调用该方法，请使用 <xref:System.Reflection.MethodBase.Invoke%2A> 方法。  下面的代码创建 <xref:System.Object>（包含的唯一元素为字符串数组）的数组，并将其作为泛型方法的参数列表传递。  <xref:System.Reflection.MethodBase.Invoke%2A> 的第一个参数为空引用，因为该方法为 `static` 的。  返回值被强制转换为 `List(Of String)`，并显示它的第一个元素。  
  
     [!code-csharp[GenericMethodHowTo#22](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#22)]
     [!code-vb[GenericMethodHowTo#22](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#22)]  
  
3.  若要使用委托调用该方法，您必须具有与该构造的泛型方法的签名匹配的委托。  实现上述目标的一种简便方式是创建一个泛型委托。  下面的代码使用 <xref:System.Delegate.CreateDelegate%28System.Type%2CSystem.Reflection.MethodInfo%29?displayProperty=fullName> 方法重载，创建在代码示例中定义的泛型委托 `D` 的一个实例，然后调用该委托。  委托的性能比后期绑定调用好。  
  
     [!code-csharp[GenericMethodHowTo#23](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#23)]
     [!code-vb[GenericMethodHowTo#23](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#23)]  
  
4.  发出的方法也可以从引用保存的程序集的程序调用。  
  
## 示例  
 下面的代码示例使用泛型方法 `Factory` 创建一个非泛型类型 `DemoType`。  此方法具有两个泛型类型参数：`TInput` 用于指定输入类型，`TOutput` 用于指定输出类型。  `TOutput` 类型参数被限制为实现 `ICollection<TInput>`（在 Visual Basic 中为 `ICollection(Of TInput)`），限制为引用类型，并且限制为具有无参数构造函数。  
  
 该方法具有一个形参，这是一个 `TInput` 的数组。  该方法返回 `TOutput` 的实例，该实例包含输入数组中的所有元素。  `TOutput` 可以是实现 <xref:System.Collections.Generic.ICollection%601> 泛型接口的任意泛型集合类型。  
  
 代码执行时，该动态程序集会保存为 DemoGenericMethod1.dll，并可使用 [Ildasm.exe（IL 反汇编程序）](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) 对其进行检查。  
  
> [!NOTE]
>  学习如何发出代码的一种好方法是编写执行您要发出的任务的 Visual Basic、C\# 或 Visual C\+\+ 程序，然后使用反汇编程序检查编译器生成的 MSIL。  
  
 该代码示例包含等效于发出的方法的源代码。  发出的方法是以后期绑定的形式进行调用的，同时也使用了在该代码示例中声明的泛型委托。  
  
 [!code-csharp[GenericMethodHowTo#1](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#1)]
 [!code-vb[GenericMethodHowTo#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#1)]  
  
## 编译代码  
  
-   代码包含编译所需的 C\# `using` 语句（在 Visual Basic 中为 `Imports`）。  
  
-   不需要其他程序集引用。  
  
-   在命令行使用 csc.exe、vbc.exe 或 cl.exe 编译代码。  若要在 Visual Studio 中编译代码，请将代码置于控制台应用程序项目模板中。  
  
## 请参阅  
 <xref:System.Reflection.Emit.MethodBuilder>   
 [如何：用反射发出定义泛型类型](../../../docs/framework/reflection-and-codedom/how-to-define-a-generic-type-with-reflection-emit.md)