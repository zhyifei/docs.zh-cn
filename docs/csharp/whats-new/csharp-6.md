---
title: C# 6 中的新增功能 - C# 指南
description: 了解 C# 版本 6 中的新增功能
keywords: .NET, .NET Core
author: BillWagner
ms.date: 09/22/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 4d879f69-f889-4d3f-a781-75194e143400
ms.openlocfilehash: ea54e9a05120134eea8e1bc9d82302a7513b43e7
ms.sourcegitcommit: 935d5267c44f9bce801468ef95f44572f1417e8c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="whats-new-in-c-6"></a><span data-ttu-id="c247d-104">C# 6 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="c247d-104">What's New in C# 6</span></span>

<span data-ttu-id="c247d-105">C# 6.0 版本包含许多可提高开发人员工作效率的功能。</span><span class="sxs-lookup"><span data-stu-id="c247d-105">The 6.0 release of C# contained many features that improve productivity for developers.</span></span> <span data-ttu-id="c247d-106">此版本中的功能包括：</span><span class="sxs-lookup"><span data-stu-id="c247d-106">Features in this release include:</span></span>

* <span data-ttu-id="c247d-107">[只读自动属性](#read-only-auto-properties)：</span><span class="sxs-lookup"><span data-stu-id="c247d-107">[Read-only Auto-properties](#read-only-auto-properties):</span></span>
    - <span data-ttu-id="c247d-108">可以创建只能在构造函数中设置的只读自动属性。</span><span class="sxs-lookup"><span data-stu-id="c247d-108">You can create read-only auto-properties that can be set only in constructors.</span></span>
* <span data-ttu-id="c247d-109">[自动属性初始值设定项](#auto-property-initializers)：</span><span class="sxs-lookup"><span data-stu-id="c247d-109">[Auto-Property Initializers](#auto-property-initializers):</span></span>
    - <span data-ttu-id="c247d-110">可以编写初始化表达式来设置自动属性的初始值。</span><span class="sxs-lookup"><span data-stu-id="c247d-110">You can write initialization expressions to set the initial value of an auto-property.</span></span>
* <span data-ttu-id="c247d-111">[Expression-bodied 函数成员](#expression-bodied-function-members)：</span><span class="sxs-lookup"><span data-stu-id="c247d-111">[Expression-bodied function members](#expression-bodied-function-members):</span></span>
    - <span data-ttu-id="c247d-112">可以使用 lambda 表达式创建单行方法。</span><span class="sxs-lookup"><span data-stu-id="c247d-112">You can author one-line methods using lambda expressions.</span></span>
* <span data-ttu-id="c247d-113">[using static](#using-static)：</span><span class="sxs-lookup"><span data-stu-id="c247d-113">[using static](#using-static):</span></span>
    - <span data-ttu-id="c247d-114">可以将单个类的所有方法导入当前命名空间。</span><span class="sxs-lookup"><span data-stu-id="c247d-114">You can import all the methods of a single class into the current namespace.</span></span>
* <span data-ttu-id="c247d-115">[Null - 条件运算符](#null-conditional-operators)：</span><span class="sxs-lookup"><span data-stu-id="c247d-115">[Null - conditional operators](#null-conditional-operators):</span></span>
    - <span data-ttu-id="c247d-116">可以简洁、安全地访问对象的成员，同时仍能使用 null 条件运算符检查 null。</span><span class="sxs-lookup"><span data-stu-id="c247d-116">You can concisely and safely access members of an object while still checking for null with the null conditional operator.</span></span>
* <span data-ttu-id="c247d-117">[字符串内插](#string-interpolation)：</span><span class="sxs-lookup"><span data-stu-id="c247d-117">[String Interpolation](#string-interpolation):</span></span>
    - <span data-ttu-id="c247d-118">可以使用内联表达式（而不是位置参数）编写字符串格式设置表达式。</span><span class="sxs-lookup"><span data-stu-id="c247d-118">You can write string formatting expressions using inline expressions instead of positional arguments.</span></span>
* <span data-ttu-id="c247d-119">[异常筛选器](#exception-filters)：</span><span class="sxs-lookup"><span data-stu-id="c247d-119">[Exception filters](#exception-filters):</span></span>
    - <span data-ttu-id="c247d-120">可以基于异常或其他程序状态的属性捕获表达式。</span><span class="sxs-lookup"><span data-stu-id="c247d-120">You can catch expressions based on properties of the exception or other program state.</span></span> 
* <span data-ttu-id="c247d-121">[nameof 表达式](#nameof-expressions)：</span><span class="sxs-lookup"><span data-stu-id="c247d-121">[nameof Expressions](#nameof-expressions):</span></span>
    - <span data-ttu-id="c247d-122">可以让编译器生成符号的字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="c247d-122">You can let the compiler generate string representations of symbols.</span></span>
* <span data-ttu-id="c247d-123">[Catch 和 Finally 块中的 Await](#await-in-catch-and-finally-blocks)：</span><span class="sxs-lookup"><span data-stu-id="c247d-123">[await in catch and finally blocks](#await-in-catch-and-finally-blocks):</span></span>
    - <span data-ttu-id="c247d-124">可以在先前不允许使用 `await` 表达式的位置使用它们。</span><span class="sxs-lookup"><span data-stu-id="c247d-124">You can use `await` expressions in locations that previously disallowed them.</span></span>
* <span data-ttu-id="c247d-125">[索引初始值设定项](#index-initializers)：</span><span class="sxs-lookup"><span data-stu-id="c247d-125">[index initializers](#index-initializers):</span></span>
    - <span data-ttu-id="c247d-126">可以为关联容器及序列容器创建初始化表达式。</span><span class="sxs-lookup"><span data-stu-id="c247d-126">You can author initialization expressions for associative containers as well as sequence containers.</span></span>
* <span data-ttu-id="c247d-127">[集合初始值设定项的扩展方法](#extension-add-methods-in-collection-initializers)：</span><span class="sxs-lookup"><span data-stu-id="c247d-127">[Extension methods for collection initializers](#extension-add-methods-in-collection-initializers):</span></span>
    - <span data-ttu-id="c247d-128">除成员方法以外，集合初始值设定项还可以依赖可访问的扩展方法。</span><span class="sxs-lookup"><span data-stu-id="c247d-128">Collection initializers can rely on accessible extension methods, in addition to member methods.</span></span>
* <span data-ttu-id="c247d-129">[改进了重载解析](#improved-overload-resolution)：</span><span class="sxs-lookup"><span data-stu-id="c247d-129">[Improved overload resolution](#improved-overload-resolution):</span></span>
    - <span data-ttu-id="c247d-130">先前生成了不明确的方法调用的某些构造现在可以正确解析。</span><span class="sxs-lookup"><span data-stu-id="c247d-130">Some constructs that previously generated ambiguous method calls now resolve correctly.</span></span>

<span data-ttu-id="c247d-131">这些功能的总体效果是让你编写的代码更简洁、更具可读性。</span><span class="sxs-lookup"><span data-stu-id="c247d-131">The overall effect of these features is that you write more concise code that is also more readable.</span></span> <span data-ttu-id="c247d-132">该语法不像许多常见做法那样繁琐。</span><span class="sxs-lookup"><span data-stu-id="c247d-132">The syntax contains less ceremony for many common practices.</span></span> <span data-ttu-id="c247d-133">可以更轻松地看出设计意图。</span><span class="sxs-lookup"><span data-stu-id="c247d-133">It's easier to see the design intent with less ceremony.</span></span> <span data-ttu-id="c247d-134">好好了解这些功能有助于你提高工作效率、编写更具可读性的代码，并更专注于核心功能而不是语言的构造。</span><span class="sxs-lookup"><span data-stu-id="c247d-134">Learn these features well, and you'll be more productive, write more readable code, and concentrate more on your core features than on the constructs of the language.</span></span>

<span data-ttu-id="c247d-135">此主题的其余部分提供有关上述每种功能的详细信息。</span><span class="sxs-lookup"><span data-stu-id="c247d-135">The remainder of this topic provides details on each of these features.</span></span>

## <a name="auto-property-enhancements"></a><span data-ttu-id="c247d-136">自动属性增强功能</span><span class="sxs-lookup"><span data-stu-id="c247d-136">Auto-Property enhancements</span></span> 

<span data-ttu-id="c247d-137">通过自动实现属性的语法（通常称为“自动属性”），可轻松创建具有简单 get 和 set 访问器的属性：</span><span class="sxs-lookup"><span data-stu-id="c247d-137">The syntax for automatically implemented properties (usually referred to as 'auto-properties') made it very easy to create properties that had simple get and set accessors:</span></span>

[!code-csharp[ClassicAutoProperty](../../../samples/snippets/csharp/new-in-6/oldcode.cs#ClassicAutoProperty)]

<span data-ttu-id="c247d-138">但是，这种简单的语法限制了你可以使用自动属性支持的设计类型。</span><span class="sxs-lookup"><span data-stu-id="c247d-138">However, this simple syntax limited the kinds of designs you could support using auto-properties.</span></span> <span data-ttu-id="c247d-139">C# 6 改进了自动属性功能，以便用户可以在更多方案中使用它们。</span><span class="sxs-lookup"><span data-stu-id="c247d-139">C# 6 improves the auto-properties capabilities so that you can use them in more scenarios.</span></span> <span data-ttu-id="c247d-140">无需频繁地求助于手动声明和操纵支持字段的更详细的语法。</span><span class="sxs-lookup"><span data-stu-id="c247d-140">You won't need to fall back on the more verbose syntax of declaring and manipulating the backing field by hand so often.</span></span>

<span data-ttu-id="c247d-141">新语法可处理适用于只读属性的方案以及初始化自动属性后的变量存储的方案。</span><span class="sxs-lookup"><span data-stu-id="c247d-141">The new syntax addresses scenarios for read-only properties, and for initializing the variable storage behind an auto-property.</span></span>

### <a name="read-only-auto-properties"></a><span data-ttu-id="c247d-142">只读自动属性</span><span class="sxs-lookup"><span data-stu-id="c247d-142">Read-only auto-properties</span></span>

<span data-ttu-id="c247d-143">只读自动属性提供了更简洁的语法来创建不可变类型。</span><span class="sxs-lookup"><span data-stu-id="c247d-143">*Read-only auto-properties* provide a more concise syntax to create immutable types.</span></span> <span data-ttu-id="c247d-144">在 C# 的早期版本中，创建不可变类型的最直接方法是声明专用资源库：</span><span class="sxs-lookup"><span data-stu-id="c247d-144">The closest you could get to immutable types in earlier versions of C# was to declare private setters:</span></span>

[!code-csharp[ClassicReadOnlyAutoProperty](../../../samples/snippets/csharp/new-in-6/oldcode.cs#ClassicReadOnlyAutoProperty)]
 
<span data-ttu-id="c247d-145">使用此语法，编译器并不能确保类型是不可变的。</span><span class="sxs-lookup"><span data-stu-id="c247d-145">Using this syntax, the compiler doesn't ensure that the type really is immutable.</span></span> <span data-ttu-id="c247d-146">它仅强制规定不会从类外部的任何代码修改 `FirstName` 和 `LastName` 属性。</span><span class="sxs-lookup"><span data-stu-id="c247d-146">It only enforces that the `FirstName` and `LastName` properties are not modified from any code outside the class.</span></span>

<span data-ttu-id="c247d-147">只读自动属性实现真正的只读行为。</span><span class="sxs-lookup"><span data-stu-id="c247d-147">Read-only auto-properties enable true read-only behavior.</span></span> <span data-ttu-id="c247d-148">你声明仅具有 get 访问器的自动属性：</span><span class="sxs-lookup"><span data-stu-id="c247d-148">You declare the auto-property with only a get accessor:</span></span>

[!code-csharp[ReadOnlyAutoProperty](../../../samples/snippets/csharp/new-in-6/newcode.cs#ReadOnlyAutoProperty)]

<span data-ttu-id="c247d-149">`FirstName` 和 `LastName` 属性只能在构造函数的主体中设置：</span><span class="sxs-lookup"><span data-stu-id="c247d-149">The `FirstName` and `LastName` properties can be set only in the body of a constructor:</span></span>

[!code-csharp[ReadOnlyAutoPropertyConstructor](../../../samples/snippets/csharp/new-in-6/newcode.cs#ReadOnlyAutoPropertyConstructor)]

<span data-ttu-id="c247d-150">尝试在另一种方法中设置 `LastName` 会生成 `CS0200` 编译错误：</span><span class="sxs-lookup"><span data-stu-id="c247d-150">Trying to set `LastName` in another method generates a `CS0200` compilation error:</span></span>

```csharp
public class Student
{
    public string LastName { get;  }

    public void ChangeName(string newLastName)
    {
        // Generates CS0200: Property or indexer cannot be assigned to -- it is read only
        LastName = newLastName;
    }
}
```

<span data-ttu-id="c247d-151">此功能实现用于创建不可变类型和使用更简洁且方便的自动属性语法的真正语言支持。</span><span class="sxs-lookup"><span data-stu-id="c247d-151">This feature enables true language support for creating immutable types and using the more concise and convenient auto-property syntax.</span></span>

### <a name="auto-property-initializers"></a><span data-ttu-id="c247d-152">自动属性初始值设定项</span><span class="sxs-lookup"><span data-stu-id="c247d-152">Auto-Property Initializers</span></span>

<span data-ttu-id="c247d-153">自动属性初始值设定项可让你在属性声明中声明自动属性的初始值。</span><span class="sxs-lookup"><span data-stu-id="c247d-153">*Auto-Property Initializers* let you declare the initial value for an auto-property as part of the property declaration.</span></span>  <span data-ttu-id="c247d-154">在早期版本中，这些属性需要具有资源库，你需要使用该资源库来初始化支持字段使用的数据存储。</span><span class="sxs-lookup"><span data-stu-id="c247d-154">In earlier versions, these properties would need to have setters and you would need to use that setter to initialize the data storage used by the backing field.</span></span> <span data-ttu-id="c247d-155">对于包含姓名和学生成绩列表的学生，请考虑此类：</span><span class="sxs-lookup"><span data-stu-id="c247d-155">Consider this class for a student that contains the name and a list of the student's grades:</span></span>

[!code-csharp[Construction](../../../samples/snippets/csharp/new-in-6/oldcode.cs#Construction)]
 
<span data-ttu-id="c247d-156">随着此类的增长，你可以包含其他构造函数。</span><span class="sxs-lookup"><span data-stu-id="c247d-156">As this class grows, you may include other constructors.</span></span> <span data-ttu-id="c247d-157">每个构造函数都需要初始化此字段，否则将引入错误。</span><span class="sxs-lookup"><span data-stu-id="c247d-157">Each constructor needs to initialize this field, or you'll introduce errors.</span></span>

<span data-ttu-id="c247d-158">通过 C# 6，可为自动属性声明中的自动属性所使用的存储分配初始值：</span><span class="sxs-lookup"><span data-stu-id="c247d-158">C# 6 enables you to assign an initial value for the storage used by an auto-property in the auto-property declaration:</span></span>

[!code-csharp[Initialization](../../../samples/snippets/csharp/new-in-6/newcode.cs#Initialization)]

<span data-ttu-id="c247d-159">`Grades` 成员在声明它的位置处被初始化。</span><span class="sxs-lookup"><span data-stu-id="c247d-159">The `Grades` member is initialized where it is declared.</span></span> <span data-ttu-id="c247d-160">这样，就能更容易地仅执行一次初始化。</span><span class="sxs-lookup"><span data-stu-id="c247d-160">That makes it easier to perform the initialization exactly once.</span></span> <span data-ttu-id="c247d-161">初始化是属性声明的一部分，可更轻松地将存储分配等同于 `Student` 对象的公用接口。</span><span class="sxs-lookup"><span data-stu-id="c247d-161">The initialization is part of the property declaration, making it easier to equate the storage allocation with public interface for `Student` objects.</span></span>

<span data-ttu-id="c247d-162">属性初始化表达式可与读/写属性以及只读属性一起使用，如下所示。</span><span class="sxs-lookup"><span data-stu-id="c247d-162">Property Initializers can be used with read/write properties as well as read-only properties, as shown here.</span></span>

[!code-csharp[ReadWriteInitialization](../../../samples/snippets/csharp/new-in-6/newcode.cs#ReadWriteInitialization)]

## <a name="expression-bodied-function-members"></a><span data-ttu-id="c247d-163">Expression-bodied 函数成员</span><span class="sxs-lookup"><span data-stu-id="c247d-163">Expression-bodied function members</span></span>

<span data-ttu-id="c247d-164">我们编写的很多成员的主体只包含一条可以表示为表达式的语句。</span><span class="sxs-lookup"><span data-stu-id="c247d-164">The body of a lot of members that we write consist of only one statement that can be represented as an expression.</span></span> <span data-ttu-id="c247d-165">可通过改为编写 expression-bodied 成员来简化该语法。</span><span class="sxs-lookup"><span data-stu-id="c247d-165">You can reduce that syntax by writing an expression-bodied member instead.</span></span> <span data-ttu-id="c247d-166">这适用于方法和只读属性。</span><span class="sxs-lookup"><span data-stu-id="c247d-166">It works for methods and read-only properties.</span></span> <span data-ttu-id="c247d-167">例如，重写 `ToString()` 通常是理想之选：</span><span class="sxs-lookup"><span data-stu-id="c247d-167">For example, an override of `ToString()` is often a great candidate:</span></span>

[!code-csharp[ToStringExpressionMember](../../../samples/snippets/csharp/new-in-6/newcode.cs#ToStringExpressionMember)]

<span data-ttu-id="c247d-168">还可以在只读属性中使用 expression-bodied 成员：</span><span class="sxs-lookup"><span data-stu-id="c247d-168">You can also use expression-bodied members in read-only properties as well:</span></span>

[!code-csharp[FullNameExpressionMember](../../../samples/snippets/csharp/new-in-6/newcode.cs#FullNameExpressionMember)]

## <a name="using-static"></a><span data-ttu-id="c247d-169">using static</span><span class="sxs-lookup"><span data-stu-id="c247d-169">using static</span></span>

<span data-ttu-id="c247d-170">using static 增强功能可用于导入单个类的静态方法。</span><span class="sxs-lookup"><span data-stu-id="c247d-170">The *using static* enhancement enables you to import the static methods of a single class.</span></span> <span data-ttu-id="c247d-171">以前，`using` 语句将所有类型导入命名空间中。</span><span class="sxs-lookup"><span data-stu-id="c247d-171">Previously, the `using` statement imported all types in a namespace.</span></span> 

<span data-ttu-id="c247d-172">通常，我们在整个代码中使用类的静态方法。</span><span class="sxs-lookup"><span data-stu-id="c247d-172">Often we use a class' static methods throughout our code.</span></span> <span data-ttu-id="c247d-173">重复键入类名可能会导致代码的含义难以理解。</span><span class="sxs-lookup"><span data-stu-id="c247d-173">Repeatedly typing the class name can obscure the meaning of your code.</span></span> <span data-ttu-id="c247d-174">一个常见的例子是当你编写执行许多数值计算的类时。</span><span class="sxs-lookup"><span data-stu-id="c247d-174">A common example is when you write classes that perform many numeric calculations.</span></span>
<span data-ttu-id="c247d-175">你的代码中将充满 <xref:System.Math.Sin%2A>、<xref:System.Math.Sqrt%2A> 以及对 <xref:System.Math> 类中不同方法的其他调用。</span><span class="sxs-lookup"><span data-stu-id="c247d-175">Your code will be littered with <xref:System.Math.Sin%2A>, <xref:System.Math.Sqrt%2A> and other calls to different methods in the <xref:System.Math> class.</span></span> <span data-ttu-id="c247d-176">新的 `using static` 语法可以使这些类更简洁、更易读。</span><span class="sxs-lookup"><span data-stu-id="c247d-176">The new `using static` syntax can make these classes much cleaner to read.</span></span> <span data-ttu-id="c247d-177">指定要使用的类：</span><span class="sxs-lookup"><span data-stu-id="c247d-177">You specify the class you're using:</span></span>

[!code-csharp[UsingStaticMath](../../../samples/snippets/csharp/new-in-6/newcode.cs#UsingStaticMath)]

<span data-ttu-id="c247d-178">现在，可以使用 <xref:System.Math> 类中的任何静态方法而不必限定 <xref:System.Math> 类。</span><span class="sxs-lookup"><span data-stu-id="c247d-178">And now, you can use any static method in the <xref:System.Math> class without qualifying the <xref:System.Math> class.</span></span> <span data-ttu-id="c247d-179"><xref:System.Math> 类是此功能的一个很好的用例，因为它不包含任何实例方法。</span><span class="sxs-lookup"><span data-stu-id="c247d-179">The <xref:System.Math> class is a great use case for this feature because it does not contain any instance methods.</span></span> <span data-ttu-id="c247d-180">还可以使用 `using static` 为具有静态和实例方法的类导入类的静态方法。</span><span class="sxs-lookup"><span data-stu-id="c247d-180">You can also use `using static` to import a class' static methods for a class that has both static and instance methods.</span></span> <span data-ttu-id="c247d-181">最有用的示例之一是 <xref:System.String>：</span><span class="sxs-lookup"><span data-stu-id="c247d-181">One of the most useful examples is <xref:System.String>:</span></span>

[!code-csharp[UsingStatic](../../../samples/snippets/csharp/new-in-6/newcode.cs#UsingStatic)]

> [!NOTE]
> <span data-ttu-id="c247d-182">在 static using 语句中必须使用完全限定的类名 `System.String`。</span><span class="sxs-lookup"><span data-stu-id="c247d-182">You must use the fully qualified class name, `System.String` in a static using statement.</span></span> <span data-ttu-id="c247d-183">而不能使用 `string` 关键字。</span><span class="sxs-lookup"><span data-stu-id="c247d-183">You cannot use the `string` keyword instead.</span></span> 

<span data-ttu-id="c247d-184">现在可以调用 <xref:System.String> 类中定义的静态方法，而不必将这些方法限定为该类的成员：</span><span class="sxs-lookup"><span data-stu-id="c247d-184">You can now call static methods defined in the <xref:System.String> class without qualifying those methods as members of that class:</span></span>

[!code-csharp[UsingStaticString](../../../samples/snippets/csharp/new-in-6/newcode.cs#UsingStaticString)]

<span data-ttu-id="c247d-185">`static using` 功能和扩展方法以有趣的方式进行交互，并且该语言设计包含一些特定处理这些交互的规则。</span><span class="sxs-lookup"><span data-stu-id="c247d-185">The `static using` feature and extension methods interact in interesting ways, and the language design included some rules that specifically address those interactions.</span></span> <span data-ttu-id="c247d-186">目标是尽可能减少现有基本代码（包括你的基本代码）中发生重大更改的可能性。</span><span class="sxs-lookup"><span data-stu-id="c247d-186">The goal is to minimize any chances of breaking changes in existing codebases, including yours.</span></span>

<span data-ttu-id="c247d-187">仅在使用扩展方法调用语法调用扩展方法（而不是作为静态方法调用）时，扩展方法才在范围内。</span><span class="sxs-lookup"><span data-stu-id="c247d-187">Extension methods are only in scope when called using the extension method invocation syntax, not when called as a static method.</span></span>
<span data-ttu-id="c247d-188">你在 LINQ 查询中会经常看到这种情况。</span><span class="sxs-lookup"><span data-stu-id="c247d-188">You'll often see this in LINQ queries.</span></span> <span data-ttu-id="c247d-189">可以通过导入 <xref:System.Linq.Enumerable> 来导入 LINQ 模式。</span><span class="sxs-lookup"><span data-stu-id="c247d-189">You can import the LINQ pattern by importing <xref:System.Linq.Enumerable>.</span></span>

[!code-csharp[UsingStaticLinq](../../../samples/snippets/csharp/new-in-6/newcode.cs#usingStaticLinq)]

<span data-ttu-id="c247d-190">这将导入 <xref:System.Linq.Enumerable> 类中的所有方法。</span><span class="sxs-lookup"><span data-stu-id="c247d-190">This imports all the methods in the <xref:System.Linq.Enumerable> class.</span></span>
<span data-ttu-id="c247d-191">但是，扩展方法仅在作为扩展方法调用时才在范围内。</span><span class="sxs-lookup"><span data-stu-id="c247d-191">However, the extension methods are only in scope when called as extension methods.</span></span> <span data-ttu-id="c247d-192">如果使用静态方法语法调用扩展方法，则它们不在范围内：</span><span class="sxs-lookup"><span data-stu-id="c247d-192">They are not in scope if they are called using the static method syntax:</span></span>

[!code-csharp[UsingStaticLinqMethod](../../../samples/snippets/csharp/new-in-6/newcode.cs#UsingStaticLinkMethod)]

<span data-ttu-id="c247d-193">这个决定是因为扩展方法通常使用扩展方法调用表达式来调用。</span><span class="sxs-lookup"><span data-stu-id="c247d-193">This decision is because extension methods are typically called using extension method invocation expressions.</span></span> <span data-ttu-id="c247d-194">在使用静态方法调用语法调用它们的罕见情况下，是为了解析多义性。</span><span class="sxs-lookup"><span data-stu-id="c247d-194">In the rare case where they are called using the static method call syntax it is to resolve ambiguity.</span></span>
<span data-ttu-id="c247d-195">在调用中要求使用类名似乎是比较明智的做法。</span><span class="sxs-lookup"><span data-stu-id="c247d-195">Requiring the class name as part of the invocation seems wise.</span></span>

<span data-ttu-id="c247d-196">`static using` 还有最后一项功能。</span><span class="sxs-lookup"><span data-stu-id="c247d-196">There's one last feature of `static using`.</span></span> <span data-ttu-id="c247d-197">`static using` 指令还可以导入任何嵌套的类型。</span><span class="sxs-lookup"><span data-stu-id="c247d-197">The `static using` directive also imports any nested types.</span></span> <span data-ttu-id="c247d-198">这样，你可以引用任何嵌套的类型，而无需限定。</span><span class="sxs-lookup"><span data-stu-id="c247d-198">That enables you to reference any nested types without qualification.</span></span>

## <a name="null-conditional-operators"></a><span data-ttu-id="c247d-199">Null 条件运算符</span><span class="sxs-lookup"><span data-stu-id="c247d-199">Null-conditional operators</span></span>

<span data-ttu-id="c247d-200">Null 值使代码变得复杂。</span><span class="sxs-lookup"><span data-stu-id="c247d-200">Null values complicate code.</span></span> <span data-ttu-id="c247d-201">需要检查变量的每个访问，以确保没有取消对 `null` 的引用。</span><span class="sxs-lookup"><span data-stu-id="c247d-201">You need to check every access of variables to ensure you are not dereferencing `null`.</span></span> <span data-ttu-id="c247d-202">Null 条件运算符使这些检查更轻松、更流畅。</span><span class="sxs-lookup"><span data-stu-id="c247d-202">The *null conditional operator* makes those checks much easier and fluid.</span></span>

<span data-ttu-id="c247d-203">只需将成员访问 `.` 替换为 `?.`：</span><span class="sxs-lookup"><span data-stu-id="c247d-203">Simply replace the member access `.` with `?.`:</span></span>

[!code-csharp[NullConditional](../../../samples/snippets/csharp/new-in-6/program.cs#NullConditional)]

<span data-ttu-id="c247d-204">在前面的示例中，如果 Person 对象是 `null`，则将变量 `first` 赋值为 `null`。</span><span class="sxs-lookup"><span data-stu-id="c247d-204">In the preceding example, the variable `first` is assigned `null` if the person object is `null`.</span></span> <span data-ttu-id="c247d-205">否则，它将被分配 `FirstName` 属性的值。</span><span class="sxs-lookup"><span data-stu-id="c247d-205">Otherwise, it gets assigned the value of the `FirstName` property.</span></span> <span data-ttu-id="c247d-206">最重要的是，`?.` 意味着当 `person` 变量为 `null` 时，此行代码不会生成 `NullReferenceException`。</span><span class="sxs-lookup"><span data-stu-id="c247d-206">Most importantly, the `?.` means that this line of code does not generate a `NullReferenceException` when the `person` variable is `null`.</span></span> <span data-ttu-id="c247d-207">它会短路并生成 `null`。</span><span class="sxs-lookup"><span data-stu-id="c247d-207">Instead, it short-circuits and produces `null`.</span></span>

<span data-ttu-id="c247d-208">此外，请注意，无论 `person` 的值是什么，此表达式均返回 `string`。</span><span class="sxs-lookup"><span data-stu-id="c247d-208">Also, note that this expression returns a `string`, regardless of the value of `person`.</span></span>
<span data-ttu-id="c247d-209">在短路的情况下，键入返回的 `null` 值以匹配整个表达式。</span><span class="sxs-lookup"><span data-stu-id="c247d-209">In the case of short circuiting, the `null` value returned is typed to match the full expression.</span></span>

<span data-ttu-id="c247d-210">通常，可以将此构造与 null 合并运算符一起使用，以在其中一个属性为 `null` 时分配默认值：</span><span class="sxs-lookup"><span data-stu-id="c247d-210">You can often use this construct with the *null coalescing* operator to assign default values when one of the properties are `null`:</span></span>

[!code-csharp[NullCoalescing](../../../samples/snippets/csharp/new-in-6/program.cs#NullCoalescing)]

<span data-ttu-id="c247d-211">`?.` 运算符的右侧操作数不仅限于属性或字段。</span><span class="sxs-lookup"><span data-stu-id="c247d-211">The right hand side operand of the `?.` operator is not limited to properties or fields.</span></span>
<span data-ttu-id="c247d-212">还可以将其用于有条件地调用方法。</span><span class="sxs-lookup"><span data-stu-id="c247d-212">You can also use it to conditionally invoke methods.</span></span> <span data-ttu-id="c247d-213">具有 null 条件运算符的成员函数的最常见用法是用于安全地调用可能为 `null` 的委托（或事件处理程序）。</span><span class="sxs-lookup"><span data-stu-id="c247d-213">The most common use of member functions with the null conditional operator is to safely invoke delegates (or event handlers) that may be `null`.</span></span>  <span data-ttu-id="c247d-214">方法是使用 `?.` 运算符调用该委托的 `Invoke` 方法来访问成员。</span><span class="sxs-lookup"><span data-stu-id="c247d-214">You'll do this by calling the delegate's `Invoke` method using the `?.` operator to access the member.</span></span> <span data-ttu-id="c247d-215">可以在</span><span class="sxs-lookup"><span data-stu-id="c247d-215">You can see an example in the</span></span>  
<span data-ttu-id="c247d-216">[委托模式](../delegates-patterns.md#handling-null-delegates)主题中看到一个示例。</span><span class="sxs-lookup"><span data-stu-id="c247d-216">[delegate patterns](../delegates-patterns.md#handling-null-delegates) topic.</span></span>

<span data-ttu-id="c247d-217">`?.` 运算符的规则确保运算符的左侧仅计算一次。</span><span class="sxs-lookup"><span data-stu-id="c247d-217">The rules of the `?.` operator ensure that the left-hand side of the operator is evaluated only once.</span></span> <span data-ttu-id="c247d-218">这很重要，它可实现许多语法，包括使用事件处理程序的示例。</span><span class="sxs-lookup"><span data-stu-id="c247d-218">This is important and enables many idioms, including the example using event handlers.</span></span> <span data-ttu-id="c247d-219">让我们从事件处理程序的使用开始。</span><span class="sxs-lookup"><span data-stu-id="c247d-219">Let's start with the event handler usage.</span></span> <span data-ttu-id="c247d-220">在以前的 C# 版本中，建议编写与下面类似的代码：</span><span class="sxs-lookup"><span data-stu-id="c247d-220">In previous versions of C#, you were encouraged to write code like this:</span></span>

```csharp
var handler = this.SomethingHappened;
if (handler != null)
    handler(this, eventArgs);
```

<span data-ttu-id="c247d-221">它的推荐度高于以下较简单的语法：</span><span class="sxs-lookup"><span data-stu-id="c247d-221">This was preferred over a simpler syntax:</span></span>

```csharp
// Not recommended
if (this.SomethingHappened != null)
    this.SomethingHappened(this, eventArgs);
```

> [!IMPORTANT]
> <span data-ttu-id="c247d-222">前一个示例引入了一个争用条件。</span><span class="sxs-lookup"><span data-stu-id="c247d-222">The preceding example introduces a race condition.</span></span> <span data-ttu-id="c247d-223">在针对 `null` 进行检查时，`SomethingHappened` 事件可能具有订阅服务器，在引发该事件之前这些订阅服务器可能已被删除。</span><span class="sxs-lookup"><span data-stu-id="c247d-223">The `SomethingHappened` event may have subscribers when checked against `null`, and those subscribers may have been removed before the event is raised.</span></span> <span data-ttu-id="c247d-224">这会导致引发 <xref:System.NullReferenceException>。</span><span class="sxs-lookup"><span data-stu-id="c247d-224">That would cause a <xref:System.NullReferenceException> to be thrown.</span></span>

<span data-ttu-id="c247d-225">在第二个版本中，`SomethingHappened` 事件处理程序在测试时可能为非 null，但如果其他代码删除处理程序，则在调用事件处理程序时，它可能仍为 null。</span><span class="sxs-lookup"><span data-stu-id="c247d-225">In this second version, the `SomethingHappened` event handler might be non-null when tested, but if other code removes a handler, it could still be null when the event handler was called.</span></span>

<span data-ttu-id="c247d-226">编译器生成 `?.` 运算符的代码，以确保 `?.` 表达式的左侧 (`this.SomethingHappened`) 计算一次，并且缓存结果：</span><span class="sxs-lookup"><span data-stu-id="c247d-226">The compiler generates code for the `?.` operator that ensures the left side (`this.SomethingHappened`) of the `?.` expression is evaluated once, and the result is cached:</span></span>

```csharp
// preferred in C# 6:
this.SomethingHappened?.Invoke(this, eventArgs);
```

<span data-ttu-id="c247d-227">通过确保左侧仅计算一次，可在 `?.` 的左侧使用任何表达式（包括方法调用）。即使它们具有副作用，但因为只计算一次，所以副作用只产生一次 。</span><span class="sxs-lookup"><span data-stu-id="c247d-227">Ensuring that the left side is evaluated only once also enables you to use any expression, including method calls, on the left side of the `?.` Even if these have side-effects, they are evaluated once, so the side effects occur only once.</span></span> <span data-ttu-id="c247d-228">可以在有关[事件](../events-overview.md#language-support-for-events)的内容中看到一个示例。</span><span class="sxs-lookup"><span data-stu-id="c247d-228">You can see an example in our content on [events](../events-overview.md#language-support-for-events).</span></span>

## <a name="string-interpolation"></a><span data-ttu-id="c247d-229">字符串内插</span><span class="sxs-lookup"><span data-stu-id="c247d-229">String Interpolation</span></span>

<span data-ttu-id="c247d-230">C# 6 包含新语法，用于从格式字符串和表达式编写字符串，可以通过计算这些字符串来生成其他字符串值。</span><span class="sxs-lookup"><span data-stu-id="c247d-230">C# 6 contains new syntax for composing strings from a format string and expressions that are evaluated to produce other string values.</span></span>

<span data-ttu-id="c247d-231">传统上，需要在类似 `string.Format` 的方法中使用位置参数：</span><span class="sxs-lookup"><span data-stu-id="c247d-231">Traditionally, you needed to use positional parameters in a method like `string.Format`:</span></span>

[!code-csharp[stringFormat](../../../samples/snippets/csharp/new-in-6/oldcode.cs#stringFormat)]

<span data-ttu-id="c247d-232">使用 C# 6，新的[字符串内插](../language-reference/tokens/interpolated.md)功能可以在格式字符串中嵌入表达式。</span><span class="sxs-lookup"><span data-stu-id="c247d-232">With C# 6, the new [string interpolation](../language-reference/tokens/interpolated.md) feature enables you to embed the expressions in the format string.</span></span> <span data-ttu-id="c247d-233">只需在字符串前面加上 `$`：</span><span class="sxs-lookup"><span data-stu-id="c247d-233">Simply preface the string with `$`:</span></span>

[!code-csharp[stringInterpolation](../../../samples/snippets/csharp/new-in-6/newcode.cs#FullNameExpressionMember)]

<span data-ttu-id="c247d-234">此初始示例使用替代表达式的属性表达式。</span><span class="sxs-lookup"><span data-stu-id="c247d-234">This initial example uses property expressions for the substituted expressions.</span></span> <span data-ttu-id="c247d-235">可以扩展此语法以使用任何表达式。</span><span class="sxs-lookup"><span data-stu-id="c247d-235">You can expand on this syntax to use any expression.</span></span> <span data-ttu-id="c247d-236">例如，可以在内插过程中计算学生的成绩平均值：</span><span class="sxs-lookup"><span data-stu-id="c247d-236">For example, you could compute a student's grade point average as part of the interpolation:</span></span>

[!code-csharp[stringInterpolationExpression](../../../samples/snippets/csharp/new-in-6/newcode.cs#stringInterpolationExpression)]

<span data-ttu-id="c247d-237">运行前面的示例，你会发现 `Grades.Average()` 的输出的小数位数可能比你需要的多。</span><span class="sxs-lookup"><span data-stu-id="c247d-237">Running the preceding example, you would find that the output for `Grades.Average()` might have more decimal places than you would like.</span></span> <span data-ttu-id="c247d-238">字符串内插语法支持可使用前面的格式设置方法的所有格式字符串。</span><span class="sxs-lookup"><span data-stu-id="c247d-238">The string interpolation syntax supports all the format strings available using earlier formatting methods.</span></span> <span data-ttu-id="c247d-239">在大括号内添加格式字符串。</span><span class="sxs-lookup"><span data-stu-id="c247d-239">You add the format strings inside the braces.</span></span> <span data-ttu-id="c247d-240">在要设置格式的表达式后面添加 `:`：</span><span class="sxs-lookup"><span data-stu-id="c247d-240">Add a `:` following the expression to format:</span></span>

[!code-csharp[stringInterpolationFormat](../../../samples/snippets/csharp/new-in-6/newcode.cs#stringInterpolationFormat)]

<span data-ttu-id="c247d-241">上一行代码将 `Grades.Average()` 的值格式设置为具有两位小数的浮点数。</span><span class="sxs-lookup"><span data-stu-id="c247d-241">The preceding line of code formats the value for `Grades.Average()` as a floating-point number with two decimal places.</span></span>

<span data-ttu-id="c247d-242">`:` 始终解释为要设置格式的表达式和格式字符串之间的分隔符。</span><span class="sxs-lookup"><span data-stu-id="c247d-242">The `:` is always interpreted as the separator between the expression being formatted and the format string.</span></span> <span data-ttu-id="c247d-243">当表达式以另一种方式（如条件运算符）使用 `:` 时，这可能会产生问题：</span><span class="sxs-lookup"><span data-stu-id="c247d-243">This can introduce problems when your expression uses a `:` in another way, such as a conditional operator:</span></span>

```csharp
public string GetGradePointPercentages() =>
    $"Name: {LastName}, {FirstName}. G.P.A: {Grades.Any() ? Grades.Average() : double.NaN:F2}";
```

<span data-ttu-id="c247d-244">在上一示例中，`:` 解析为格式字符串的开头，而不是条件运算符的一部分。</span><span class="sxs-lookup"><span data-stu-id="c247d-244">In the preceding example, the `:` is parsed as the beginning of the format string, not part of the conditional operator.</span></span> <span data-ttu-id="c247d-245">在发生此问题的所有情况下，可以用括号将表达式括起来，强制编译器按照你的意图解释该表达式：</span><span class="sxs-lookup"><span data-stu-id="c247d-245">In all cases where this happens, you can surround the expression with parentheses to force the compiler to interpret the expression as you intend:</span></span>

[!code-csharp[stringInterpolationConditional](../../../samples/snippets/csharp/new-in-6/newcode.cs#stringInterpolationConditional)]

<span data-ttu-id="c247d-246">对可以放在大括号之间的表达式没有任何限制。</span><span class="sxs-lookup"><span data-stu-id="c247d-246">There aren't any limitations on the expressions you can place between the braces.</span></span> <span data-ttu-id="c247d-247">可以在内插字符串中执行复杂的 LINQ 查询，以执行计算并显示结果：</span><span class="sxs-lookup"><span data-stu-id="c247d-247">You can execute a complex LINQ query inside an interpolated string to perform computations and display the result:</span></span>

[!code-csharp[stringInterpolationLinq](../../../samples/snippets/csharp/new-in-6/newcode.cs#stringInterpolationLinq)]

<span data-ttu-id="c247d-248">可以从此示例中看出，甚至可以将字符串内插表达式嵌套在另一个字符串内插表达式中。</span><span class="sxs-lookup"><span data-stu-id="c247d-248">You can see from this sample that you can even nest a string interpolation expression inside another string interpolation expression.</span></span> <span data-ttu-id="c247d-249">此示例在生产代码中很有可能比你想的更加复杂。</span><span class="sxs-lookup"><span data-stu-id="c247d-249">This example is very likely more complex than you would want in production code.</span></span>
<span data-ttu-id="c247d-250">但它说明了该功能的范围。</span><span class="sxs-lookup"><span data-stu-id="c247d-250">Rather, it is illustrative of the breadth of the feature.</span></span> <span data-ttu-id="c247d-251">任何 C# 表达式都可以放置在内插字符串的大括号之间。</span><span class="sxs-lookup"><span data-stu-id="c247d-251">Any C# expression can be placed between the curly braces of an interpolated string.</span></span>

### <a name="string-interpolation-and-specific-cultures"></a><span data-ttu-id="c247d-252">字符串内插和特定区域性</span><span class="sxs-lookup"><span data-stu-id="c247d-252">String interpolation and specific cultures</span></span>

<span data-ttu-id="c247d-253">前面部分中显示的所有示例使用执行代码的计算机上的当前区域性和语言设置字符串格式。</span><span class="sxs-lookup"><span data-stu-id="c247d-253">All the examples shown in the preceding section format the strings using the current culture and language on the machine where the code executes.</span></span> <span data-ttu-id="c247d-254">通常，可能需要使用特定区域性设置生成的字符串的格式。</span><span class="sxs-lookup"><span data-stu-id="c247d-254">Often you may need to format the string produced using a specific culture.</span></span>
<span data-ttu-id="c247d-255">为此，请利用通过字符串内插生成的对象可以隐式转换为 <xref:System.FormattableString> 这一事实。</span><span class="sxs-lookup"><span data-stu-id="c247d-255">To do that use the fact that the object produced by a string interpolation can be implicitly converted to <xref:System.FormattableString>.</span></span>

<span data-ttu-id="c247d-256"><xref:System.FormattableString> 实例包含格式字符串，以及在将其转换为字符串之前评估表达式的结果。</span><span class="sxs-lookup"><span data-stu-id="c247d-256">The <xref:System.FormattableString> instance contains the format string, and the results of evaluating the expressions before converting them to strings.</span></span> <span data-ttu-id="c247d-257">在设置字符串的格式时，可以使用 <xref:System.FormattableString> 的公共方法指定区域性。</span><span class="sxs-lookup"><span data-stu-id="c247d-257">You can use public methods of <xref:System.FormattableString> to specify the culture when formatting a string.</span></span> <span data-ttu-id="c247d-258">例如，以下示例使用德国区域性生成字符串。</span><span class="sxs-lookup"><span data-stu-id="c247d-258">For example, the following example produces a string using German culture.</span></span> <span data-ttu-id="c247d-259">（它使用“,”字符作为小数分隔符，使用“.”字符作为千位分隔符。）</span><span class="sxs-lookup"><span data-stu-id="c247d-259">(It uses the ',' character for the decimal separator, and the '.' character as the thousands separator.)</span></span>

```csharp
FormattableString str = $"Average grade is {s.Grades.Average()}";
var gradeStr = str.ToString(new System.Globalization.CultureInfo("de-DE"));
```

<span data-ttu-id="c247d-260">有关详细信息，请参阅[字符串内插](../language-reference/tokens/interpolated.md)主题。</span><span class="sxs-lookup"><span data-stu-id="c247d-260">For more information, see the [String interpolation](../language-reference/tokens/interpolated.md) topic.</span></span>

## <a name="exception-filters"></a><span data-ttu-id="c247d-261">异常筛选器</span><span class="sxs-lookup"><span data-stu-id="c247d-261">Exception Filters</span></span>

<span data-ttu-id="c247d-262">C# 6 中的另一个新功能是异常筛选器。</span><span class="sxs-lookup"><span data-stu-id="c247d-262">Another new feature in C# 6 is *exception filters*.</span></span> <span data-ttu-id="c247d-263">异常筛选器是确定何时应该应用给定的 catch 子句的子句。</span><span class="sxs-lookup"><span data-stu-id="c247d-263">Exception Filters are clauses that determine when a given catch clause should be applied.</span></span>
<span data-ttu-id="c247d-264">如果用于异常筛选器的表达式计算结果为 `true`，则 catch 子句将对异常执行正常处理。</span><span class="sxs-lookup"><span data-stu-id="c247d-264">If the expression used for an exception filter evaluates to `true`, the catch clause performs its normal processing on an exception.</span></span> <span data-ttu-id="c247d-265">如果表达式计算结果为 `false`，则将跳过 `catch` 子句。</span><span class="sxs-lookup"><span data-stu-id="c247d-265">If the expression evaluates to `false`, then the `catch` clause is skipped.</span></span>

<span data-ttu-id="c247d-266">一种用途是检查有关异常的信息，以确定 `catch` 子句是否可以处理该异常：</span><span class="sxs-lookup"><span data-stu-id="c247d-266">One use is to examine information about an exception to determine if a `catch` clause can process the exception:</span></span>

[!code-csharp[ExceptionFilter](../../../samples/snippets/csharp/new-in-6/NetworkClient.cs#ExceptionFilter)]

<span data-ttu-id="c247d-267">由异常筛选器生成的代码提供了有关已引发且未处理的异常的更好信息。</span><span class="sxs-lookup"><span data-stu-id="c247d-267">The code generated by exception filters provides better information about an exception that is thrown and not processed.</span></span> <span data-ttu-id="c247d-268">在将异常筛选器添加到语言之前，需要创建如下所示的代码：</span><span class="sxs-lookup"><span data-stu-id="c247d-268">Before exception filters were added to the language, you would need to create code like the following:</span></span>

[!code-csharp[ExceptionFilterOld](../../../samples/snippets/csharp/new-in-6/NetworkClient.cs#ExceptionFilterOld)]

<span data-ttu-id="c247d-269">这两个示例中，引发异常的点发生了更改。</span><span class="sxs-lookup"><span data-stu-id="c247d-269">The point where the exception is thrown changes between these two examples.</span></span>
<span data-ttu-id="c247d-270">在前一个代码中，使用了 `throw` 子句，对故障转储的任何堆栈跟踪分析或检查都将显示异常是从 catch 子句中的 `throw` 语句引发的。</span><span class="sxs-lookup"><span data-stu-id="c247d-270">In the previous code, where a `throw` clause is used, any stack trace analysis or examination of crash dumps will show that the exception was thrown from the `throw` statement in your catch clause.</span></span> <span data-ttu-id="c247d-271">实际的异常对象将包含原始调用堆栈，但是在此引发点与原始引发点位置之间的调用堆栈中的任何变量的所有其他信息已丢失。</span><span class="sxs-lookup"><span data-stu-id="c247d-271">The actual exception object will contain the original call stack, but all other information about any variables in the call stack between this throw point and the location of the original throw point has been lost.</span></span> 

<span data-ttu-id="c247d-272">对比使用异常筛选器的代码的处理方式：异常筛选器表达式的计算结果为 `false`。</span><span class="sxs-lookup"><span data-stu-id="c247d-272">Contrast that with how the code using an exception filter is processed: the exception filter expression evaluates to `false`.</span></span> <span data-ttu-id="c247d-273">因此，执行决不会进入 `catch` 子句。</span><span class="sxs-lookup"><span data-stu-id="c247d-273">Therefore, execution never enters the `catch` clause.</span></span> <span data-ttu-id="c247d-274">因为 `catch` 子句不会执行，不会发生堆栈展开。</span><span class="sxs-lookup"><span data-stu-id="c247d-274">Because the `catch` clause does not execute, no stack unwinding takes place.</span></span> <span data-ttu-id="c247d-275">这表示将保留原始引发位置，以用于以后将会发生的任何调试活动。</span><span class="sxs-lookup"><span data-stu-id="c247d-275">That means the original throw location is preserved for any debugging activities that would take place later.</span></span>

<span data-ttu-id="c247d-276">每当需要评估异常的字段或属性，而不是仅仅依赖异常类型时，请使用异常筛选器保留更多调试信息。</span><span class="sxs-lookup"><span data-stu-id="c247d-276">Whenever you need to evaluate fields or properties of an exception, instead of relying solely on the exception type, use an exception filter to preserve more debugging information.</span></span>

<span data-ttu-id="c247d-277">使用异常筛选器的另一种推荐模式是将其用于日志记录例程。</span><span class="sxs-lookup"><span data-stu-id="c247d-277">Another recommended pattern with exception filters is to use them for logging routines.</span></span> <span data-ttu-id="c247d-278">这种用法还会利用当异常筛选器计算结果为 `false` 时，保留异常引发点的方式。</span><span class="sxs-lookup"><span data-stu-id="c247d-278">This usage also leverages the manner in which the exception throw point is preserved when an exception filter evaluates to `false`.</span></span>

<span data-ttu-id="c247d-279">日志记录方法将是这样一种方法：其参数为无条件返回 `false` 的异常：</span><span class="sxs-lookup"><span data-stu-id="c247d-279">A logging method would be a method whose argument is the exception that unconditionally returns `false`:</span></span>

[!code-csharp[ExceptionFilterLogging](../../../samples/snippets/csharp/new-in-6/ExceptionFilterHelpers.cs#ExceptionFilterLogging)]

<span data-ttu-id="c247d-280">每当要记录异常时，可以添加一个 catch 子句，并将此方法用作异常筛选器：</span><span class="sxs-lookup"><span data-stu-id="c247d-280">Whenever you want to log an exception, you can add a catch clause, and use this method as the exception filter:</span></span>

[!code-csharp[LogException](../../../samples/snippets/csharp/new-in-6/program.cs#LogException)]

<span data-ttu-id="c247d-281">永远不会捕获异常，因为 `LogException` 方法始终返回 `false`。</span><span class="sxs-lookup"><span data-stu-id="c247d-281">The exceptions are never caught, because the `LogException` method always returns `false`.</span></span> <span data-ttu-id="c247d-282">始终为 false 的异常筛选器意味着可以将此日志记录处理程序放置在任何其他异常处理程序之前：</span><span class="sxs-lookup"><span data-stu-id="c247d-282">That always false exception filter means that you can place this logging handler before any other exception handlers:</span></span>

[!code-csharp[LogExceptionRecovery](../../../samples/snippets/csharp/new-in-6/program.cs#LogExceptionRecovery)]

<span data-ttu-id="c247d-283">前一示例中强调了异常筛选器的一个非常重要的方面。</span><span class="sxs-lookup"><span data-stu-id="c247d-283">The preceding example highlights a very important facet of exception filters.</span></span>
<span data-ttu-id="c247d-284">通过异常筛选器，可实现以下方案：较常规的异常 catch 子句可出现在较具体的 catch 子句前。</span><span class="sxs-lookup"><span data-stu-id="c247d-284">The exception filters enable scenarios where a more general exception catch clause may appear before a more specific one.</span></span> <span data-ttu-id="c247d-285">也可以在多个 catch 子句中出现相同的异常类型：</span><span class="sxs-lookup"><span data-stu-id="c247d-285">It's also possible to have the same exception type appear in multiple catch clauses:</span></span>

[!code-csharp[HandleNotChanged](../../../samples/snippets/csharp/new-in-6/NetworkClient.cs#HandleNotChanged)]

<span data-ttu-id="c247d-286">另一种建议模式有助于防止 catch 子句在附加调试器时处理异常。</span><span class="sxs-lookup"><span data-stu-id="c247d-286">Another recommended pattern helps prevent catch clauses from processing exceptions when a debugger is attached.</span></span> <span data-ttu-id="c247d-287">通过此技术，可以使用调试器运行应用程序，并在引发异常时停止执行。</span><span class="sxs-lookup"><span data-stu-id="c247d-287">This technique enables you to run an application with the debugger, and stop execution when an exception is thrown.</span></span>

<span data-ttu-id="c247d-288">在代码中添加一个异常筛选器，使任何恢复代码仅在未附加调试器时执行：</span><span class="sxs-lookup"><span data-stu-id="c247d-288">In your code, add an exception filter so that any recovery code executes only when a debugger is not attached:</span></span>

[!code-csharp[LogExceptionDebugger](../../../samples/snippets/csharp/new-in-6/program.cs#LogExceptionDebugger)]

<span data-ttu-id="c247d-289">在代码中添加之后，将调试器设置为在所有未处理的异常处中断。</span><span class="sxs-lookup"><span data-stu-id="c247d-289">After adding this in code, you set your debugger to break on all unhandled exceptions.</span></span> <span data-ttu-id="c247d-290">在调试器下运行程序，每当 `PerformFailingOperation()` 引发 `RecoverableException` 时，调试器就会中断。</span><span class="sxs-lookup"><span data-stu-id="c247d-290">Run the program under the debugger, and the debugger breaks whenever `PerformFailingOperation()` throws a `RecoverableException`.</span></span>
<span data-ttu-id="c247d-291">调试器将中断程序，因为不会执行 catch 子句（由于异常筛选器返回 false）。</span><span class="sxs-lookup"><span data-stu-id="c247d-291">The debugger breaks your program, because the catch clause won't be executed due to the false-returning exception filter.</span></span>

## <a name="nameof-expressions"></a><span data-ttu-id="c247d-292">`nameof` 表达式</span><span class="sxs-lookup"><span data-stu-id="c247d-292">`nameof` Expressions</span></span>

<span data-ttu-id="c247d-293">`nameof` 表达式的计算结果为符号的名称。</span><span class="sxs-lookup"><span data-stu-id="c247d-293">The `nameof` expression evaluates to the name of a symbol.</span></span> <span data-ttu-id="c247d-294">每当需要变量、属性或成员字段的名称时，这是让工具正常运行的好办法。</span><span class="sxs-lookup"><span data-stu-id="c247d-294">It's a great way to get tools working whenever you need the name of a variable, a property, or a member field.</span></span>

<span data-ttu-id="c247d-295">`nameof` 的其中一个最常见的用途是提供引起异常的符号的名称：</span><span class="sxs-lookup"><span data-stu-id="c247d-295">One of the most common uses for `nameof` is to provide the name of a symbol that caused an exception:</span></span>

[!code-csharp[nameof](../../../samples/snippets/csharp/new-in-6/NewCode.cs#UsingStaticString)]

<span data-ttu-id="c247d-296">另一个用途是用于实现 `INotifyPropertyChanged` 接口的基于 XAML 的应用程序：</span><span class="sxs-lookup"><span data-stu-id="c247d-296">Another use is with XAML based applications that implement the `INotifyPropertyChanged` interface:</span></span>

[!code-csharp[nameofNotify](../../../samples/snippets/csharp/new-in-6/viewmodel.cs#nameofNotify)]

<span data-ttu-id="c247d-297">相较于使用常量字符串，使用 `nameof` 运算符的优点是工具可以了解符号。</span><span class="sxs-lookup"><span data-stu-id="c247d-297">The advantage of using the `nameof` operator over a constant string is that tools can understand the symbol.</span></span> <span data-ttu-id="c247d-298">如果使用重构工具重命名符号，会在 `nameof` 表达式中对其重命名。</span><span class="sxs-lookup"><span data-stu-id="c247d-298">If you use refactoring tools to rename the symbol, it will rename it in the `nameof` expression.</span></span> <span data-ttu-id="c247d-299">常量字符串没有这一优势。</span><span class="sxs-lookup"><span data-stu-id="c247d-299">Constant strings don't have that advantage.</span></span> <span data-ttu-id="c247d-300">请在你最喜爱的编辑器中亲自尝试一下：重命名一个变量，任何 `nameof` 表达式也将更新。</span><span class="sxs-lookup"><span data-stu-id="c247d-300">Try it yourself in your favorite editor: rename a variable, and any `nameof` expressions will update as well.</span></span>

<span data-ttu-id="c247d-301">`nameof` 表达式生成其参数（在前面的示例中为 `LastName`）的非限定名称，即使使用参数的完全限定名称也是如此：</span><span class="sxs-lookup"><span data-stu-id="c247d-301">The `nameof` expression produces the unqualified name of its argument (`LastName` in the previous examples) even if you use the fully qualified name for the argument:</span></span>

[!code-csharp[QualifiedNameofNotify](../../../samples/snippets/csharp/new-in-6/viewmodel.cs#QualifiedNameofNotify)]

<span data-ttu-id="c247d-302">此 `nameof` 表达式生成 `FirstName`，而不是 `UXComponents.ViewModel.FirstName`。</span><span class="sxs-lookup"><span data-stu-id="c247d-302">This `nameof` expression produces `FirstName`, not `UXComponents.ViewModel.FirstName`.</span></span>

## <a name="await-in-catch-and-finally-blocks"></a><span data-ttu-id="c247d-303">Catch 和 Finally 块中的 Await</span><span class="sxs-lookup"><span data-stu-id="c247d-303">Await in Catch and Finally blocks</span></span>

<span data-ttu-id="c247d-304">C# 5 对于可放置 `await` 表达式的位置有若干限制。</span><span class="sxs-lookup"><span data-stu-id="c247d-304">C# 5 had several limitations around where you could place `await` expressions.</span></span>
<span data-ttu-id="c247d-305">其中一个限制已在 C# 6 中删除。</span><span class="sxs-lookup"><span data-stu-id="c247d-305">One of those has been removed in C# 6.</span></span> <span data-ttu-id="c247d-306">现在，可以在 `catch` 或 `finally` 表达式中使用 `await`。</span><span class="sxs-lookup"><span data-stu-id="c247d-306">You can now use `await` in `catch` or `finally` expressions.</span></span> 

<span data-ttu-id="c247d-307">在 catch 和 finally 块中添加 await 表达式可能会使这些表达式的处理方式变得复杂。</span><span class="sxs-lookup"><span data-stu-id="c247d-307">The addition of await expressions in catch and finally blocks may appear to complicate how those are processed.</span></span> <span data-ttu-id="c247d-308">让我们添加一个示例对此进行讨论。</span><span class="sxs-lookup"><span data-stu-id="c247d-308">Let's add an example to discuss how this appears.</span></span> <span data-ttu-id="c247d-309">在任何异步方法中，都可以在 finally 子句中使用 await 表达式。</span><span class="sxs-lookup"><span data-stu-id="c247d-309">In any async method, you can use an await expression in a finally clause.</span></span>

<span data-ttu-id="c247d-310">使用 C# 6，还可以在 catch 表达式中使用 await。</span><span class="sxs-lookup"><span data-stu-id="c247d-310">With C# 6, you can also await in catch expressions.</span></span> <span data-ttu-id="c247d-311">这通常用于日志记录方案：</span><span class="sxs-lookup"><span data-stu-id="c247d-311">This is most often used with logging scenarios:</span></span>

[!code-csharp[AwaitFinally](../../../samples/snippets/csharp/new-in-6/NetworkClient.cs#AwaitFinally)]

<span data-ttu-id="c247d-312">在 `catch` 和 `finally` 子句中添加 `await` 支持的实现细节可确保该行为与同步代码的行为一致。</span><span class="sxs-lookup"><span data-stu-id="c247d-312">The implementation details for adding `await` support inside `catch` and `finally` clauses ensures that the behavior is consistent with the behavior for synchronous code.</span></span> <span data-ttu-id="c247d-313">当在 `catch` 或 `finally` 子句中执行的代码引发异常时，执行将在下一个外层块中查找合适的 `catch` 子句。</span><span class="sxs-lookup"><span data-stu-id="c247d-313">When code executed in a `catch` or `finally` clause throws, execution looks for a suitable `catch` clause in the next surrounding block.</span></span> <span data-ttu-id="c247d-314">如果存在当前异常，则该异常将丢失。</span><span class="sxs-lookup"><span data-stu-id="c247d-314">If there was a current exception, that exception is lost.</span></span> <span data-ttu-id="c247d-315">`catch` 和 `finally` 子句中的 awaited 表达式也会发生同样的情况：搜索合适的 `catch`，并且当前异常（如果有）将丢失。</span><span class="sxs-lookup"><span data-stu-id="c247d-315">The same happens with awaited expressions in `catch` and `finally` clauses: a suitable `catch` is searched for, and the current exception, if any, is lost.</span></span>  

> [!NOTE]
> <span data-ttu-id="c247d-316">鉴于此行为，建议仔细编写 `catch` 和 `finally` 子句，避免引入新的异常。</span><span class="sxs-lookup"><span data-stu-id="c247d-316">This behavior is the reason it's recommended to write `catch` and `finally` clauses carefully, to avoid introducing new exceptions.</span></span>

## <a name="index-initializers"></a><span data-ttu-id="c247d-317">索引初始值设定项</span><span class="sxs-lookup"><span data-stu-id="c247d-317">Index Initializers</span></span>

<span data-ttu-id="c247d-318">索引初始值设定项是提高集合初始值设定项一致性的两个功能之一。</span><span class="sxs-lookup"><span data-stu-id="c247d-318">*Index Initializers* is one of two features that make collection initializers more consistent.</span></span> <span data-ttu-id="c247d-319">在早期版本的 C# 中，只能将集合初始值设定项用于序列样式集合：</span><span class="sxs-lookup"><span data-stu-id="c247d-319">In earlier releases of C#, you could use *collection initializers* only with sequence style collections:</span></span>

[!code-csharp[ListInitializer](../../../samples/snippets/csharp/new-in-6/initializers.cs#ListInitializer)]

<span data-ttu-id="c247d-320">现在，还可以将它们用于 <xref:System.Collections.Generic.Dictionary%602> 集合及类似的类型：</span><span class="sxs-lookup"><span data-stu-id="c247d-320">Now, you can also use them with <xref:System.Collections.Generic.Dictionary%602> collections and similar types:</span></span>

[!code-csharp[DictionaryInitializer](../../../samples/snippets/csharp/new-in-6/initializers.cs#DictionaryInitializer)]

<span data-ttu-id="c247d-321">此功能意味着，可以使用与多个版本中已有的序列容器语法类似的语法初始化关联容器。</span><span class="sxs-lookup"><span data-stu-id="c247d-321">This feature means that associative containers can be initialized using syntax similar to what's been in place for sequence containers for several versions.</span></span>

### <a name="extension-add-methods-in-collection-initializers"></a><span data-ttu-id="c247d-322">集合初始值设定项中的扩展 `Add` 方法</span><span class="sxs-lookup"><span data-stu-id="c247d-322">Extension `Add` methods in collection initializers</span></span>

<span data-ttu-id="c247d-323">使集合初始化更容易的另一个功能是对 `Add` 方法使用扩展方法。</span><span class="sxs-lookup"><span data-stu-id="c247d-323">Another feature that makes collection initialization easier is the ability to use an *extension method* for the `Add` method.</span></span> <span data-ttu-id="c247d-324">添加此功能的目的是进行 Visual Basic 的奇偶校验。</span><span class="sxs-lookup"><span data-stu-id="c247d-324">This feature was added for parity with Visual Basic.</span></span> 

<span data-ttu-id="c247d-325">如果自定义集合类的方法具有通过语义方式添加新项的名称，则此功能非常有用。</span><span class="sxs-lookup"><span data-stu-id="c247d-325">The feature is most useful when you have a custom collection class that has a method with a different name to semantically add new items.</span></span>

<span data-ttu-id="c247d-326">例如，请思考以下学生集合：</span><span class="sxs-lookup"><span data-stu-id="c247d-326">For example, consider a collection of students like this:</span></span>

[!code-csharp[Enrollment](../../../samples/snippets/csharp/new-in-6/enrollment.cs#Enrollment)]

<span data-ttu-id="c247d-327">`Enroll` 方法会添加一个学生。</span><span class="sxs-lookup"><span data-stu-id="c247d-327">The `Enroll` method adds a student.</span></span> <span data-ttu-id="c247d-328">但它不遵循 `Add` 模式。</span><span class="sxs-lookup"><span data-stu-id="c247d-328">But it doesn't follow the `Add` pattern.</span></span>
<span data-ttu-id="c247d-329">在以前的 C# 版本中，你不能对 `Enrollment` 对象使用集合初始值设定项：</span><span class="sxs-lookup"><span data-stu-id="c247d-329">In previous versions of C#, you could not use collection initializers with an `Enrollment` object:</span></span>

[!code-csharp[InitializeEnrollment](../../../samples/snippets/csharp/new-in-6/classList.cs#InitializeEnrollment)]

<span data-ttu-id="c247d-330">现在可以，但前提是你创建将 `Add` 映射到 `Enroll` 的扩展方法：</span><span class="sxs-lookup"><span data-stu-id="c247d-330">Now you can, but only if you create an extension method that maps `Add` to `Enroll`:</span></span>

[!code-csharp[ExtensionAdd](../../../samples/snippets/csharp/new-in-6/classList.cs#ExtensionAdd)]

<span data-ttu-id="c247d-331">你对此功能执行的操作是通过创建扩展方法，将把项添加到集合的任何方法映射到一个名为 `Add` 方法：</span><span class="sxs-lookup"><span data-stu-id="c247d-331">What you are doing with this feature is to map whatever method adds items to a collection to a method named `Add` by creating an extension method:</span></span> 

[!code-csharp[Enrollment](../../../samples/snippets/csharp/new-in-6/enrollment.cs#Enrollment)]
[!code-csharp[ExtensionAddSample](../../../samples/snippets/csharp/new-in-6/classList.cs#ExtensionAddSample)]

## <a name="improved-overload-resolution"></a><span data-ttu-id="c247d-332">改进了重载解析</span><span class="sxs-lookup"><span data-stu-id="c247d-332">Improved overload resolution</span></span>

<span data-ttu-id="c247d-333">你可能不会注意到这最后一项功能。</span><span class="sxs-lookup"><span data-stu-id="c247d-333">This last feature is one you probably won't notice.</span></span> <span data-ttu-id="c247d-334">在以前的一些构造中，以前版本的 C# 编译器可能会发现涉及 lambda 表达式的一些方法不明确。</span><span class="sxs-lookup"><span data-stu-id="c247d-334">There were constructs where the previous version of the C# compiler may have found some method calls involving lambda expressions ambiguous.</span></span> <span data-ttu-id="c247d-335">请考虑此方法：</span><span class="sxs-lookup"><span data-stu-id="c247d-335">Consider this method:</span></span>

[!code-csharp[AsyncMethod](../../../samples/snippets/csharp/new-in-6/overloads.cs#AsyncMethod)]

<span data-ttu-id="c247d-336">在早期版本的 C# 中，使用方法组语法调用该方法将失败：</span><span class="sxs-lookup"><span data-stu-id="c247d-336">In earlier versions of C#, calling that method using the method group syntax would fail:</span></span>

[!code-csharp[MethodGroup](../../../samples/snippets/csharp/new-in-6/overloads.cs#MethodGroup)]
 
<span data-ttu-id="c247d-337">早期的编译器无法正确区分 `Task.Run(Action)` 和 `Task.Run(Func<Task>())`。</span><span class="sxs-lookup"><span data-stu-id="c247d-337">The earlier compiler could not distinguish correctly between `Task.Run(Action)` and `Task.Run(Func<Task>())`.</span></span> <span data-ttu-id="c247d-338">在早期版本中，需要使用 lambda 表达式作为参数：</span><span class="sxs-lookup"><span data-stu-id="c247d-338">In previous versions, you'd need to use a lambda expression as an argument:</span></span>

[!code-csharp[Lambda](../../../samples/snippets/csharp/new-in-6/overloads.cs#Lambda)]

<span data-ttu-id="c247d-339">C# 6 编译器正确地确定 `Task.Run(Func<Task>())` 是更好的选择。</span><span class="sxs-lookup"><span data-stu-id="c247d-339">The C# 6 compiler correctly determines that `Task.Run(Func<Task>())` is a better choice.</span></span>
