---
title: "using static 指令（C# 参考）"
ms.date: 2017-03-10
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- using static directive [C#]
ms.assetid: 8b8f9e34-c75e-469b-ba85-6f2eb4090314
author: rpetrusha
ms.author: ronpet
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b7d69d0262ba6f450e2cc0d5b30692bba181f9d9
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="using-static-directive-c-reference"></a><span data-ttu-id="af3e2-102">using static 指令（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="af3e2-102">using static Directive (C# Reference)</span></span>

<span data-ttu-id="af3e2-103">`using static` 指令指定无需指定类型名称即可访问其静态成员的类型。</span><span class="sxs-lookup"><span data-stu-id="af3e2-103">The `using static` directive designates a type whose static members you can access without specifying a type name.</span></span> <span data-ttu-id="af3e2-104">语法为：</span><span class="sxs-lookup"><span data-stu-id="af3e2-104">Its syntax is:</span></span>

```csharp
using static <fully-qualified-type-name>
```

<span data-ttu-id="af3e2-105">其中，*fully-qualified-type-name* 是无需指定类型名称即可访问其静态成员的类型的名称。</span><span class="sxs-lookup"><span data-stu-id="af3e2-105">where *fully-qualified-type-name* is the name of the type whose static members can be referenced without specifying a type name.</span></span> <span data-ttu-id="af3e2-106">如果不提供完全限定的类型名称（完整的命名空间名称以及类型名称），则 C# 将生成编译器错误 CS0246：“找不到‘<type-name>’的类型或命名空间名称。”</span><span class="sxs-lookup"><span data-stu-id="af3e2-106">If you do not provide a fully qualified type name (the full namespace name along with the type name), C# generates compiler error CS0246: "The type or namespace name '<type-name>' could not be found."</span></span>

<span data-ttu-id="af3e2-107">`using static` 指令适用于任何具有静态成员的类型，即使该类型还具有实例成员。</span><span class="sxs-lookup"><span data-stu-id="af3e2-107">The `using static` directive applies to any type that has static members, even if it also has instance members.</span></span> <span data-ttu-id="af3e2-108">但是，只能通过类型实例来调用实例成员。</span><span class="sxs-lookup"><span data-stu-id="af3e2-108">However, instance members can only be invoked through the type instance.</span></span>

<span data-ttu-id="af3e2-109">`using static` 指令是在 C# 6 中引入的。</span><span class="sxs-lookup"><span data-stu-id="af3e2-109">The `using static` directive was introduced in C# 6.</span></span>

## <a name="remarks"></a><span data-ttu-id="af3e2-110">备注</span><span class="sxs-lookup"><span data-stu-id="af3e2-110">Remarks</span></span>
 
<span data-ttu-id="af3e2-111">通常，调用某个静态成员时，即会提供类型名称以及成员名称。</span><span class="sxs-lookup"><span data-stu-id="af3e2-111">Ordinarily, when you call a static member, you provide the type name along with the member name.</span></span> <span data-ttu-id="af3e2-112">重复输入相同的类型名称来调用该类型的成员将生成详细的晦涩代码。</span><span class="sxs-lookup"><span data-stu-id="af3e2-112">Repeatedly entering the same type name to invoke members of the type can result in verbose, obscure code.</span></span> <span data-ttu-id="af3e2-113">例如，`Circle` 类的以下定义引用 @System.Math 类的成员数。</span><span class="sxs-lookup"><span data-stu-id="af3e2-113">For example, the following definition of a `Circle` class references a number of members of the @System.Math class.</span></span>
  
<span data-ttu-id="af3e2-114">[!code-cs[using-static#1](../../../../samples/snippets/csharp/language-reference/keywords/using/using-static1.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="af3e2-114">[!code-cs[using-static#1](../../../../samples/snippets/csharp/language-reference/keywords/using/using-static1.cs#1)]</span></span>

<span data-ttu-id="af3e2-115">通过消除每次引用成员时，显式引用 @System.Math 类的需求，`using static` 指令将生成更简洁的代码：</span><span class="sxs-lookup"><span data-stu-id="af3e2-115">By eliminating the need to explicitly reference the @System.Math class each time a member is referenced, the `using static` directive produces much cleaner code:</span></span>

<span data-ttu-id="af3e2-116">[!code-cs[using-static#2](../../../../samples/snippets/csharp/language-reference/keywords/using/using-static2.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="af3e2-116">[!code-cs[using-static#2](../../../../samples/snippets/csharp/language-reference/keywords/using/using-static2.cs#1)]</span></span>

<span data-ttu-id="af3e2-117">`using static` 仅导入可访问的静态成员和指定类型中声明的嵌套类型。</span><span class="sxs-lookup"><span data-stu-id="af3e2-117">`using static` imports only accessible static members and nested types declared in the specified type.</span></span>  <span data-ttu-id="af3e2-118">不导入继承的成员。</span><span class="sxs-lookup"><span data-stu-id="af3e2-118">Inherited members are not imported.</span></span>  <span data-ttu-id="af3e2-119">可以从任何带 using static 指令的已命名类型导入，包括 Visual Basic 模块。</span><span class="sxs-lookup"><span data-stu-id="af3e2-119">You can import from any named type with a using static directive, including Visual Basic modules.</span></span>  <span data-ttu-id="af3e2-120">如果 F# 顶级函数在元数据中显示为一个已命名类型（其名称是有效的 C# 标识符）的静态成员，则可以导入该 F# 函数。</span><span class="sxs-lookup"><span data-stu-id="af3e2-120">If F# top-level functions appear in metadata as static members of a named type whose name is a valid C# identifier, then the F# functions can be imported.</span></span>  
  
 <span data-ttu-id="af3e2-121">`using static` 使指定类型中声明的扩展方法可用于扩展方法查找。</span><span class="sxs-lookup"><span data-stu-id="af3e2-121">`using static` makes extension methods declared in the specified type available for extension method lookup.</span></span>  <span data-ttu-id="af3e2-122">但是，扩展方法的名称不导入到代码中非限定引用的作用域中。</span><span class="sxs-lookup"><span data-stu-id="af3e2-122">However, the names of the extension methods are not imported into scope for unqualified reference in code.</span></span>  
  
 <span data-ttu-id="af3e2-123">同一编译单元或命名空间中通过不同 `using static` 命令从不同类型导入的具有相同名称的方法组成一个方法组。</span><span class="sxs-lookup"><span data-stu-id="af3e2-123">Methods with the same name imported from different types by different `using static` directives in the same compilation unit or namespace form a method group.</span></span>  <span data-ttu-id="af3e2-124">这些方法组内的重载解决方法遵循一般 C# 规则。</span><span class="sxs-lookup"><span data-stu-id="af3e2-124">Overload resolution within these method groups follows normal C# rules.</span></span>  
  
## <a name="example"></a><span data-ttu-id="af3e2-125">示例</span><span class="sxs-lookup"><span data-stu-id="af3e2-125">Example</span></span>

<span data-ttu-id="af3e2-126">以下示例使用 `using static` 指令来提供 @System.Console、@System.Math 和 @System.String 类的静态成员，而无需指定其类型名称。</span><span class="sxs-lookup"><span data-stu-id="af3e2-126">The following example uses the `using static` directive to make the static members of the @System.Console, @System.Math, and @System.String classes available without having to specify their type name.</span></span>

<span data-ttu-id="af3e2-127">[!code-cs[using-static#3](../../../../samples/snippets/csharp/language-reference/keywords/using/using-static3.cs)]</span><span class="sxs-lookup"><span data-stu-id="af3e2-127">[!code-cs[using-static#3](../../../../samples/snippets/csharp/language-reference/keywords/using/using-static3.cs)]</span></span>

<span data-ttu-id="af3e2-128">在此示例中，`using static` 指令也已经应用于 @System.Double 类型。</span><span class="sxs-lookup"><span data-stu-id="af3e2-128">In the example, the `using static` directive could also have been applied to the @System.Double type.</span></span> <span data-ttu-id="af3e2-129">这使得在未指定类型名称情况下调用 @System.Double.TryParse(System.String,System.Double@) 方法成为可能。</span><span class="sxs-lookup"><span data-stu-id="af3e2-129">This would have made it possible to call the @System.Double.TryParse(System.String,System.Double@) method without specifying a type name.</span></span> <span data-ttu-id="af3e2-130">但是，如此创建的代码可读性较差，因为这样有必要检查 `using static` 语句，以确定所调用的数值类型的 `TryParse` 方法。</span><span class="sxs-lookup"><span data-stu-id="af3e2-130">However, this creates less readable code, since it becomes necessary to check the `using static` statements to determine which numeric type's `TryParse` method is called.</span></span>

## <a name="see-also"></a><span data-ttu-id="af3e2-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="af3e2-131">See also</span></span>

<span data-ttu-id="af3e2-132">[using 指令](using-directive.md) </span><span class="sxs-lookup"><span data-stu-id="af3e2-132">[using directive](using-directive.md) </span></span>  
<span data-ttu-id="af3e2-133">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="af3e2-133">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
<span data-ttu-id="af3e2-134">[C# 关键字](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="af3e2-134">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
<span data-ttu-id="af3e2-135">[Using 命名空间](../../../csharp/programming-guide/namespaces/using-namespaces.md) </span><span class="sxs-lookup"><span data-stu-id="af3e2-135">[Using Namespaces](../../../csharp/programming-guide/namespaces/using-namespaces.md) </span></span>  
<span data-ttu-id="af3e2-136">[命名空间关键字](../../../csharp/language-reference/keywords/namespace-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="af3e2-136">[Namespace Keywords](../../../csharp/language-reference/keywords/namespace-keywords.md) </span></span>  
[<span data-ttu-id="af3e2-137">命名空间</span><span class="sxs-lookup"><span data-stu-id="af3e2-137">Namespaces</span></span>](../../../csharp/programming-guide/namespaces/index.md)   

