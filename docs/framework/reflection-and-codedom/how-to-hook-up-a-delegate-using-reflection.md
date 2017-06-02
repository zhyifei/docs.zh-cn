---
title: "如何：使用反射将委托挂钩 | Microsoft Docs"
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
  - "委托 [.NET Framework], 使用反射添加事件处理程序"
  - "事件 [.NET Framework], 使用反射添加事件处理程序"
  - "反射, 添加事件处理程序委托"
ms.assetid: 076ee62d-a964-449e-a447-c31b33518b81
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# 如何：使用反射将委托挂钩
当使用反射来加载和运行程序集时，不能使用 C\# `+=` 运算符或 Visual Basic [AddHandler 语句](../../../ocs/visual-basic/language-reference/statements/addhandler-statement.md)等语言功能将事件挂钩。  以下过程显示如何通过用反射获取所需的全部类型将现有方法挂钩到事件，以及如何使用反射发出来创建动态方法并将其挂钩到事件。  
  
> [!NOTE]
>  有关事件处理委托的其他挂钩方式，请参见 <xref:System.Reflection.EventInfo> 类的 <xref:System.Reflection.EventInfo.AddEventHandler%2A> 方法的代码示例。  
  
### 使用反射挂钩委托  
  
1.  加载包含引发事件的类型的程序集。  程序集通常使用 <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> 方法加载。  为了使此示例尽量简单，在当前程序集中使用了派生窗体，所以使用 <xref:System.Reflection.Assembly.GetExecutingAssembly%2A> 方法来加载当前程序集。  
  
     [!code-cpp[HookUpDelegate#3](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#3)]
     [!code-csharp[HookUpDelegate#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#3)]
     [!code-vb[HookUpDelegate#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#3)]  
  
2.  获取表示类型的 <xref:System.Type> 对象，并创建一个该类型的实例。  由于窗体具有默认构造函数，所以在下面的代码中使用了 <xref:System.Activator.CreateInstance%28System.Type%29> 方法。  如果您创建的类型没有默认构造函数，<xref:System.Activator.CreateInstance%2A> 方法还有其他几种重载可供使用。  新实例存储为类型 <xref:System.Object>，以保持对程序集一无所知的状态。（通过反射可以获取程序集中的类型，而无需事先了解其名称。）  
  
     [!code-cpp[HookUpDelegate#4](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#4)]
     [!code-csharp[HookUpDelegate#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#4)]
     [!code-vb[HookUpDelegate#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#4)]  
  
3.  获取表示该事件的 <xref:System.Reflection.EventInfo> 对象，并使用 <xref:System.Reflection.EventInfo.EventHandlerType%2A> 属性来获取用于处理事件的委托类型。  在下面的代码中，获取了 <xref:System.Windows.Forms.Control.Click> 事件的 <xref:System.Reflection.EventInfo>。  
  
     [!code-cpp[HookUpDelegate#5](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#5)]
     [!code-csharp[HookUpDelegate#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#5)]
     [!code-vb[HookUpDelegate#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#5)]  
  
4.  获取表示处理事件的方法的 <xref:System.Reflection.MethodInfo> 对象。  本主题后面 Example部分中的完整程序代码包含一个与 <xref:System.EventHandler> 委托的签名匹配的方法，该方法处理 <xref:System.Windows.Forms.Control.Click> 事件，但您也可以在运行时生成动态方法。  有关详细信息，请参见附带的使用动态方法在运行时生成事件处理程序过程。  
  
     [!code-cpp[HookUpDelegate#6](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#6)]
     [!code-csharp[HookUpDelegate#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#6)]
     [!code-vb[HookUpDelegate#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#6)]  
  
5.  使用 <xref:System.Delegate.CreateDelegate%2A> 方法创建委托的实例。  此方法是静态的（在 Visual Basic 中为 `Shared`），所以必须提供委托类型。  建议使用带有 <xref:System.Reflection.MethodInfo> 的 <xref:System.Delegate.CreateDelegate%2A> 重载。  
  
     [!code-cpp[HookUpDelegate#7](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#7)]
     [!code-csharp[HookUpDelegate#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#7)]
     [!code-vb[HookUpDelegate#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#7)]  
  
6.  获取 `add` 访问器方法，并调用该方法以将事件挂钩。  所有事件都具有一个 `add` 访问器或 `remove` 访问器，这些访问器被高级语言的语法隐藏。  例如，C\# 使用 `+=` 运算符将事件挂钩，而 Visual Basic 则使用 [AddHandler 语句](../../../ocs/visual-basic/language-reference/statements/addhandler-statement.md)。  下面的代码获取 <xref:System.Windows.Forms.Control.Click> 事件的 `add` 访问器并以后期绑定方式调用它，并在委托实例中传递。  参数必须作为数组传递。  
  
     [!code-cpp[HookUpDelegate#8](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#8)]
     [!code-csharp[HookUpDelegate#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#8)]
     [!code-vb[HookUpDelegate#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#8)]  
  
7.  测试事件。  下面的代码显示了在代码示例中定义的窗体。  单击该窗体将调用事件处理程序。  
  
     [!code-cpp[HookUpDelegate#12](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#12)]
     [!code-csharp[HookUpDelegate#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#12)]
     [!code-vb[HookUpDelegate#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#12)]  
  
<a name="procedureSection1"></a>   
### 使用动态方法在运行时生成事件处理程序  
  
1.  使用轻量动态方法和反射发出可在运行时生成事件处理程序方法。  若要构造事件处理程序，您需要知道返回类型和委托的参数类型。  可以通过检查委托的 `Invoke` 方法来获取这些类型。  下面的代码使用 `GetDelegateReturnType` 和 `GetDelegateParameterTypes` 方法获取此信息。  在本主题后面的示例部分中可以找到这些方法的代码。  
  
     不需要命名 <xref:System.Reflection.Emit.DynamicMethod>，所以可以使用空字符串。  在下面的代码中，最后一个参数将动态方法与当前类型相关联，从而允许委托访问 `Example` 类的所有公共和私有成员。  
  
     [!code-cpp[HookUpDelegate#9](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#9)]
     [!code-csharp[HookUpDelegate#9](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#9)]
     [!code-vb[HookUpDelegate#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#9)]  
  
2.  生成方法体。  此方法加载字符串、调用带有字符串的 <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=fullName> 方法重载、从堆栈弹出返回值（因为处理程序没有返回类型）并返回这些值。  若要了解有关发出动态方法的更多信息，请参见[如何：定义和执行动态方法](../../../docs/framework/reflection-and-codedom/how-to-define-and-execute-dynamic-methods.md)。  
  
     [!code-cpp[HookUpDelegate#10](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#10)]
     [!code-csharp[HookUpDelegate#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#10)]
     [!code-vb[HookUpDelegate#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#10)]  
  
3.  通过调用动态方法的 <xref:System.Reflection.Emit.DynamicMethod.CreateDelegate%2A> 方法完成动态方法。  使用 `add` 访问器向事件的调用列表中添加委托。  
  
     [!code-cpp[HookUpDelegate#11](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#11)]
     [!code-csharp[HookUpDelegate#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#11)]
     [!code-vb[HookUpDelegate#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#11)]  
  
4.  测试事件。  下面的代码将加载在代码示例中定义的窗体。  单击该窗体将同时调用预定义的事件处理程序和发出的事件处理程序。  
  
     [!code-cpp[HookUpDelegate#12](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#12)]
     [!code-csharp[HookUpDelegate#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#12)]
     [!code-vb[HookUpDelegate#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#12)]  
  
## 示例  
 下面的代码示例显示如何使用反射将现有方法挂钩到事件，以及如何使用 <xref:System.Reflection.Emit.DynamicMethod> 类在运行时发出方法并将其挂钩到事件。  
  
 [!code-cpp[HookUpDelegate#1](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#1)]
 [!code-csharp[HookUpDelegate#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#1)]
 [!code-vb[HookUpDelegate#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#1)]  
  
## 编译代码  
  
-   代码包含编译所需的 C\# `using` 语句（在 Visual Basic 中为 `Imports`）。  
  
-   从命令行编译时，不再需要其他的程序集引用。  由于此示例是一个控制台应用程序，所以在 Visual Studio 中必须添加对 System.Windows.Forms.dll 的引用。  
  
-   在命令行使用 csc.exe、vbc.exe 或 cl.exe 编译代码。  若要在 Visual Studio 中编译代码，请将代码置于控制台应用程序项目模板中。  
  
## 请参阅  
 <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName>   
 <xref:System.Reflection.Emit.DynamicMethod>   
 <xref:System.Activator.CreateInstance%2A>   
 <xref:System.Delegate.CreateDelegate%2A>   
 [如何：定义和执行动态方法](../../../docs/framework/reflection-and-codedom/how-to-define-and-execute-dynamic-methods.md)   
 [反射](../../../docs/framework/reflection-and-codedom/reflection.md)