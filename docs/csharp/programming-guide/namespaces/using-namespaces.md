---
title: 使用命名空间（C# 编程指南）
ms.date: 07/20/2015
f1_keywords:
- cs.names
helpviewer_keywords:
- fully qualified names [C#]
- namespaces [C#], how to use
ms.assetid: 1fe8bf39-addc-438a-bd9e-86410e32381d
ms.openlocfilehash: 773add221317a2154ac620acf766607ec22c629d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="using-namespaces-c-programming-guide"></a><span data-ttu-id="5647e-102">使用命名空间（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="5647e-102">Using Namespaces (C# Programming Guide)</span></span>
<span data-ttu-id="5647e-103">在 C# 编程中，命名空间在两个方面被大量使用。</span><span class="sxs-lookup"><span data-stu-id="5647e-103">Namespaces are heavily used within C# programs in two ways.</span></span> <span data-ttu-id="5647e-104">首先，.NET Framework 类使用命名空间来组织它的众多类。</span><span class="sxs-lookup"><span data-stu-id="5647e-104">Firstly, the .NET Framework classes use namespaces to organize its many classes.</span></span> <span data-ttu-id="5647e-105">其次，在较大的编程项目中，声明自己的命名空间可以帮助控制类名称和方法名称的范围。</span><span class="sxs-lookup"><span data-stu-id="5647e-105">Secondly, declaring your own namespaces can help control the scope of class and method names in larger programming projects.</span></span>  
  
## <a name="accessing-namespaces"></a><span data-ttu-id="5647e-106">访问命名空间</span><span class="sxs-lookup"><span data-stu-id="5647e-106">Accessing Namespaces</span></span>  
 <span data-ttu-id="5647e-107">大多数 C# 应用程序以 `using` 指令开头。</span><span class="sxs-lookup"><span data-stu-id="5647e-107">Most C# applications begin with a section of `using` directives.</span></span> <span data-ttu-id="5647e-108">本部分列出了应用程序将频繁使用的命名空间，使程序员避免在每次使用包含在命名空间中的方法时都要指定完全限定名称。</span><span class="sxs-lookup"><span data-stu-id="5647e-108">This section lists the namespaces that the application will be using frequently, and saves the programmer from specifying a fully qualified name every time that a method that is contained within is used.</span></span>  
  
 <span data-ttu-id="5647e-109">例如，通过包括行：</span><span class="sxs-lookup"><span data-stu-id="5647e-109">For example, by including the line:</span></span>  
  
 [!code-csharp[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/using-namespaces_1.cs)]  
  
 <span data-ttu-id="5647e-110">在程序的开始，程序员可以使用代码：</span><span class="sxs-lookup"><span data-stu-id="5647e-110">At the start of a program, the programmer can use the code:</span></span>  
  
 [!code-csharp[csProgGuide#31](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/using-namespaces_2.cs)]  
  
 <span data-ttu-id="5647e-111">而不是：</span><span class="sxs-lookup"><span data-stu-id="5647e-111">Instead of:</span></span>  
  
 [!code-csharp[csProgGuide#30](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/using-namespaces_3.cs)]  
  
## <a name="namespace-aliases"></a><span data-ttu-id="5647e-112">命名空间别名</span><span class="sxs-lookup"><span data-stu-id="5647e-112">Namespace Aliases</span></span>  
 <span data-ttu-id="5647e-113">[Using 指令](../../../csharp/language-reference/keywords/using-directive.md)还可用于创建[命名空间](../../../csharp/language-reference/keywords/namespace.md)的别名。</span><span class="sxs-lookup"><span data-stu-id="5647e-113">The [using Directive](../../../csharp/language-reference/keywords/using-directive.md) can also be used to create an alias for a [namespace](../../../csharp/language-reference/keywords/namespace.md).</span></span> <span data-ttu-id="5647e-114">例如，如果使用之前编写的含嵌套命名空间的命名空间，建议你声明一个别名，特别提供一种快速的引用方法，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="5647e-114">For example, if you are using a previously written namespace that contains nested namespaces, you might want to declare an alias to provide a shorthand way of referencing one in particular, as in the following example:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#7](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_4.cs)]  
  
## <a name="using-namespaces-to-control-scope"></a><span data-ttu-id="5647e-115">使用命名空间控制范围</span><span class="sxs-lookup"><span data-stu-id="5647e-115">Using Namespaces to control scope</span></span>  
 <span data-ttu-id="5647e-116">`namespace` 关键字用于声明范围。</span><span class="sxs-lookup"><span data-stu-id="5647e-116">The `namespace` keyword is used to declare a scope.</span></span> <span data-ttu-id="5647e-117">在项目内创建范围有助于整理代码，并允许创建全局唯一类型。</span><span class="sxs-lookup"><span data-stu-id="5647e-117">The ability to create scopes within your project helps organize code and lets you create globally-unique types.</span></span> <span data-ttu-id="5647e-118">在下面的示例中，名为 `SampleClass` 的类在两个命名空间中定义，其中一个嵌套在另一个之中。</span><span class="sxs-lookup"><span data-stu-id="5647e-118">In the following example, a class titled `SampleClass` is defined in two namespaces, one nested inside the other.</span></span> <span data-ttu-id="5647e-119">[。运算符](../../../csharp/language-reference/operators/member-access-operator.md) 用于区分调用的方法。</span><span class="sxs-lookup"><span data-stu-id="5647e-119">The [. Operator](../../../csharp/language-reference/operators/member-access-operator.md) is used to differentiate which method gets called.</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#8](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_5.cs)]  
  
## <a name="fully-qualified-names"></a><span data-ttu-id="5647e-120">完全限定名</span><span class="sxs-lookup"><span data-stu-id="5647e-120">Fully Qualified Names</span></span>  
 <span data-ttu-id="5647e-121">命名空间和类型具有指示逻辑层次结构的完全限定名称所描述的唯一标题。</span><span class="sxs-lookup"><span data-stu-id="5647e-121">Namespaces and types have unique titles described by fully qualified names that indicate a logical hierarchy.</span></span> <span data-ttu-id="5647e-122">例如，语句 `A.B` 意味着 `A` 是命名空间或类型的名称，而 `B` 嵌套在其中。</span><span class="sxs-lookup"><span data-stu-id="5647e-122">For example, the statement `A.B` implies that `A` is the name of the namespace or type, and `B` is nested inside it.</span></span>  
  
 <span data-ttu-id="5647e-123">以下示例中具有嵌套的类和命名空间。</span><span class="sxs-lookup"><span data-stu-id="5647e-123">In the following example, there are nested classes and namespaces.</span></span> <span data-ttu-id="5647e-124">完全限定名称表示为跟随每个实体的注释。</span><span class="sxs-lookup"><span data-stu-id="5647e-124">The fully qualified name is indicated as a comment following each entity.</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#9](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_6.cs)]  
  
 <span data-ttu-id="5647e-125">在前面的代码片段中：</span><span class="sxs-lookup"><span data-stu-id="5647e-125">In the previous code segment:</span></span>  
  
-   <span data-ttu-id="5647e-126">命名空间 `N1` 是全局命名空间的成员。</span><span class="sxs-lookup"><span data-stu-id="5647e-126">The namespace `N1` is a member of the global namespace.</span></span> <span data-ttu-id="5647e-127">其完全限定名称为 `N1`。</span><span class="sxs-lookup"><span data-stu-id="5647e-127">Its fully qualified name is `N1`.</span></span>  
  
-   <span data-ttu-id="5647e-128">命名空间 `N2` 是 `N1` 的成员。</span><span class="sxs-lookup"><span data-stu-id="5647e-128">The namespace `N2` is a member of `N1`.</span></span> <span data-ttu-id="5647e-129">其完全限定名称为 `N1.N2`。</span><span class="sxs-lookup"><span data-stu-id="5647e-129">Its fully qualified name is `N1.N2`.</span></span>  
  
-   <span data-ttu-id="5647e-130">类 `C1` 是 `N1` 的成员。</span><span class="sxs-lookup"><span data-stu-id="5647e-130">The class `C1` is a member of `N1`.</span></span> <span data-ttu-id="5647e-131">其完全限定名称为 `N1.C1`。</span><span class="sxs-lookup"><span data-stu-id="5647e-131">Its fully qualified name is `N1.C1`.</span></span>  
  
-   <span data-ttu-id="5647e-132">类名 `C2` 在此代码中使用了两次。</span><span class="sxs-lookup"><span data-stu-id="5647e-132">The class name `C2` is used two times in this code.</span></span> <span data-ttu-id="5647e-133">但完全限定名称是唯一的。</span><span class="sxs-lookup"><span data-stu-id="5647e-133">However, the fully qualified names are unique.</span></span> <span data-ttu-id="5647e-134">`C2` 的第一个实例在 `C1` 中声明；因此，其完全限定名称是：`N1.C1.C2`。</span><span class="sxs-lookup"><span data-stu-id="5647e-134">The first instance of `C2` is declared inside `C1`; therefore, its fully qualified name is: `N1.C1.C2`.</span></span> <span data-ttu-id="5647e-135">`C2` 的第二个实例在命名空间 `N2` 中声明；因此，其完全限定名称是 `N1.N2.C2`。</span><span class="sxs-lookup"><span data-stu-id="5647e-135">The second instance of `C2` is declared inside a namespace `N2`; therefore, its fully qualified name is `N1.N2.C2`.</span></span>  
  
 <span data-ttu-id="5647e-136">使用前面的代码段，可向命名空间 `N1.N2` 添加新的类成员 `C3`，如下所示：</span><span class="sxs-lookup"><span data-stu-id="5647e-136">Using the previous code segment, you can add a new class member, `C3`, to the namespace `N1.N2` as follows:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#10](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_7.cs)]  
  
 <span data-ttu-id="5647e-137">一般情况下，使用 `::` 来引用命名空间别名，或使用 `global::` 来引用全局命名空间，以及使用 `.` 来限定类型或成员。</span><span class="sxs-lookup"><span data-stu-id="5647e-137">In general, use `::` to reference a namespace alias or `global::` to reference the global namespace and `.` to qualify types or members.</span></span>  
  
 <span data-ttu-id="5647e-138">将 `::` 与引用类型而非引用命名空间的别名一起使用是错误的。</span><span class="sxs-lookup"><span data-stu-id="5647e-138">It is an error to use `::` with an alias that references a type instead of a namespace.</span></span> <span data-ttu-id="5647e-139">例如:</span><span class="sxs-lookup"><span data-stu-id="5647e-139">For example:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#11](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_8.cs)]  
  
 [!code-csharp[csProgGuideNamespaces#12](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_9.cs)]  
  
 <span data-ttu-id="5647e-140">请记住，单词 `global` 不是预定义的别名；因此，`global.X` 不具有任何特殊含义。</span><span class="sxs-lookup"><span data-stu-id="5647e-140">Remember that the word `global` is not a predefined alias; therefore, `global.X` does not have any special meaning.</span></span> <span data-ttu-id="5647e-141">仅当将其与 `::` 一起使用时，它才具有特殊意义。</span><span class="sxs-lookup"><span data-stu-id="5647e-141">It acquires a special meaning only when it is used with `::`.</span></span>  
  
 <span data-ttu-id="5647e-142">定义名为 global 的别名时将生成编译器警告 CS0440，因为 `global::` 始终引用全局命名空间而非别名。</span><span class="sxs-lookup"><span data-stu-id="5647e-142">Compiler warning CS0440 is generated if you define an alias named global because `global::` always references the global namespace and not an alias.</span></span> <span data-ttu-id="5647e-143">例如，以下行将生成该警告：</span><span class="sxs-lookup"><span data-stu-id="5647e-143">For example, the following line generates the warning:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#13](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_10.cs)]  
  
 <span data-ttu-id="5647e-144">将 `::` 与别名一起使用是一个不错的主意，可防止意外引入其他类型。</span><span class="sxs-lookup"><span data-stu-id="5647e-144">Using `::` with aliases is a good idea and protects against the unexpected introduction of additional types.</span></span> <span data-ttu-id="5647e-145">例如，请考虑以下示例：</span><span class="sxs-lookup"><span data-stu-id="5647e-145">For example, consider this example:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#14](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_11.cs)]  
  
 [!code-csharp[csProgGuideNamespaces#15](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_12.cs)]  
  
 <span data-ttu-id="5647e-146">这是可行的，但如果随后要引入名为 `Alias` 的类型，`Alias.` 将改为绑定到该类型。</span><span class="sxs-lookup"><span data-stu-id="5647e-146">This works, but if a type named `Alias` were to subsequently be introduced, `Alias.` would bind to that type instead.</span></span> <span data-ttu-id="5647e-147">使用 `Alias::Exception` 确保 `Alias` 被视为命名空间别名，而不被误解为类型。</span><span class="sxs-lookup"><span data-stu-id="5647e-147">Using `Alias::Exception` insures that `Alias` is treated as a namespace alias and not mistaken for a type.</span></span>  
  
 <span data-ttu-id="5647e-148">有关 `global` 别名的详细信息，请参阅主题[如何：使用全局命名空间别名](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)。</span><span class="sxs-lookup"><span data-stu-id="5647e-148">See the topic [How to: Use the Global Namespace Alias](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md) for more information regarding the `global` alias.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5647e-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="5647e-149">See Also</span></span>  
 [<span data-ttu-id="5647e-150">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="5647e-150">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="5647e-151">命名空间</span><span class="sxs-lookup"><span data-stu-id="5647e-151">Namespaces</span></span>](../../../csharp/programming-guide/namespaces/index.md)  
 [<span data-ttu-id="5647e-152">命名空间关键字</span><span class="sxs-lookup"><span data-stu-id="5647e-152">Namespace Keywords</span></span>](../../../csharp/language-reference/keywords/namespace-keywords.md)  
 [<span data-ttu-id="5647e-153">。运算符</span><span class="sxs-lookup"><span data-stu-id="5647e-153">. Operator</span></span>](../../../csharp/language-reference/operators/member-access-operator.md)  
 [<span data-ttu-id="5647e-154">:: 运算符</span><span class="sxs-lookup"><span data-stu-id="5647e-154">:: Operator</span></span>](../../../csharp/language-reference/operators/namespace-alias-qualifer.md)  
 [<span data-ttu-id="5647e-155">extern</span><span class="sxs-lookup"><span data-stu-id="5647e-155">extern</span></span>](../../../csharp/language-reference/keywords/extern.md)
