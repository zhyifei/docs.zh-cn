---
title: 内置引用类型 - C# 引用
description: 了解具有 C# 关键字的引用类型，可使用这些关键字进行声明。
ms.date: 06/25/2019
f1_keywords:
- object_CSharpKeyword
- object
- delegate_CSharpKeyword
- delegate
- dynamic_CSharpKeyword
- string
- string_CSharpKeyword
helpviewer_keywords:
- object keyword [C#]
- delegate keyword [C#]
- function pointers [C#]
- dynamic [C#]
- dynamic keyword [C#]
- strings [C#], reference
- '@ string literal'
- string literals [C#]
- string keyword [C#]
ms.openlocfilehash: fcfe2dafe588dce57628bff63e3519f70d7a7725
ms.sourcegitcommit: 29a9b29d8b7d07b9c59d46628da754a8bff57fa4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/17/2019
ms.locfileid: "69566254"
---
# <a name="built-in-reference-types-c-reference"></a><span data-ttu-id="c6419-103">内置引用类型（C# 引用）</span><span class="sxs-lookup"><span data-stu-id="c6419-103">Built-in reference types (C# reference)</span></span>

<span data-ttu-id="c6419-104">C# 具有多个内置引用类型。</span><span class="sxs-lookup"><span data-stu-id="c6419-104">C# has a number of built-in reference types.</span></span> <span data-ttu-id="c6419-105">这些类型包含的关键字或运算符是 .NET 库中的类型的同义词。</span><span class="sxs-lookup"><span data-stu-id="c6419-105">They have keywords or operators that are synonyms for a type in the .NET library.</span></span> 

## <a name="the-object-type"></a><span data-ttu-id="c6419-106">对象类型</span><span class="sxs-lookup"><span data-stu-id="c6419-106">The object type</span></span>

<span data-ttu-id="c6419-107">`object` 类型是 <xref:System.Object?displayProperty=nameWithType> 在 .NET 中的别名。</span><span class="sxs-lookup"><span data-stu-id="c6419-107">The `object` type is an alias for <xref:System.Object?displayProperty=nameWithType> in .NET.</span></span> <span data-ttu-id="c6419-108">在 C# 的统一类型系统中，所有类型（预定义类型、用户定义类型、引用类型和值类型）都是直接或间接从 <xref:System.Object?displayProperty=nameWithType> 继承的。</span><span class="sxs-lookup"><span data-stu-id="c6419-108">In the unified type system of C#, all types, predefined and user-defined, reference types and value types, inherit directly or indirectly from <xref:System.Object?displayProperty=nameWithType>.</span></span> <span data-ttu-id="c6419-109">可以将任何类型的值赋给 `object` 类型的变量。</span><span class="sxs-lookup"><span data-stu-id="c6419-109">You can assign values of any type to variables of type `object`.</span></span> <span data-ttu-id="c6419-110">可以使用文本 `null` 将任何 `object` 变量赋值给其默认值。</span><span class="sxs-lookup"><span data-stu-id="c6419-110">Any `object` variable can be assigned to its default value using the literal `null`.</span></span> <span data-ttu-id="c6419-111">将值类型的变量转换为对象的过程称为*装箱*。</span><span class="sxs-lookup"><span data-stu-id="c6419-111">When a variable of a value type is converted to object, it is said to be *boxed*.</span></span> <span data-ttu-id="c6419-112">将对象类型的变量转换为值类型的过程称为*取消装箱*。</span><span class="sxs-lookup"><span data-stu-id="c6419-112">When a variable of type object is converted to a value type, it is said to be *unboxed*.</span></span> <span data-ttu-id="c6419-113">有关详细信息，请参阅[装箱和取消装箱](../../programming-guide/types/boxing-and-unboxing.md)。</span><span class="sxs-lookup"><span data-stu-id="c6419-113">For more information, see [Boxing and Unboxing](../../programming-guide/types/boxing-and-unboxing.md).</span></span> 

## <a name="the-string-type"></a><span data-ttu-id="c6419-114">字符串类型</span><span class="sxs-lookup"><span data-stu-id="c6419-114">The string type</span></span>

<span data-ttu-id="c6419-115">`string` 类型表示零个或多个 Unicode 字符的序列。</span><span class="sxs-lookup"><span data-stu-id="c6419-115">The `string` type represents a sequence of zero or more Unicode characters.</span></span> <span data-ttu-id="c6419-116">`string` 是 <xref:System.String?displayProperty=nameWithType> 在 .NET 中的别名。</span><span class="sxs-lookup"><span data-stu-id="c6419-116">`string` is an alias for <xref:System.String?displayProperty=nameWithType> in .NET.</span></span>

<span data-ttu-id="c6419-117">尽管 `string` 为引用类型，但是定义[相等运算符 `==` 和 `!=`](../operators/equality-operators.md#string-equality) 是为了比较 `string` 对象（而不是引用）的值。</span><span class="sxs-lookup"><span data-stu-id="c6419-117">Although `string` is a reference type, the [equality operators `==` and `!=`](../operators/equality-operators.md#string-equality) are defined to compare the values of `string` objects, not references.</span></span> <span data-ttu-id="c6419-118">这使得对字符串相等性的测试更为直观。</span><span class="sxs-lookup"><span data-stu-id="c6419-118">This makes testing for string equality more intuitive.</span></span> <span data-ttu-id="c6419-119">例如:</span><span class="sxs-lookup"><span data-stu-id="c6419-119">For example:</span></span>

```csharp-interactive
string a = "hello";
string b = "h";
// Append to contents of 'b'
b += "ello";
Console.WriteLine(a == b);
Console.WriteLine(object.ReferenceEquals(a, b));
```

<span data-ttu-id="c6419-120">此时将显示“True”，然后显示“False”，因为字符串的内容是相等的，但 `a` 和 `b` 并不指代同一字符串实例。</span><span class="sxs-lookup"><span data-stu-id="c6419-120">This displays "True" and then "False" because the content of the strings are equivalent, but `a` and `b` do not refer to the same string instance.</span></span>

<span data-ttu-id="c6419-121">[+ 运算符](../operators/addition-operator.md#string-concatenation)连接字符串：</span><span class="sxs-lookup"><span data-stu-id="c6419-121">The [+ operator](../operators/addition-operator.md#string-concatenation) concatenates strings:</span></span>

```csharp
string a = "good " + "morning";
```

<span data-ttu-id="c6419-122">这将创建包含“good morning”的字符串对象。</span><span class="sxs-lookup"><span data-stu-id="c6419-122">This creates a string object that contains "good morning".</span></span>

<span data-ttu-id="c6419-123">字符串是不可变的  ，即：字符串对象在创建后，尽管从语法上看似乎可以更改其内容，但事实上并不可行。</span><span class="sxs-lookup"><span data-stu-id="c6419-123">Strings are *immutable*--the contents of a string object cannot be changed after the object is created, although the syntax makes it appear as if you can do this.</span></span> <span data-ttu-id="c6419-124">例如，编写此代码时，编译器实际上会创建一个新的字符串对象来保存新的字符序列，且该新对象将赋给 `b`。</span><span class="sxs-lookup"><span data-stu-id="c6419-124">For example, when you write this code, the compiler actually creates a new string object to hold the new sequence of characters, and that new object is assigned to `b`.</span></span> <span data-ttu-id="c6419-125">已为 `b` 分配的内存（当它包含字符串“h”时）可用于垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="c6419-125">The memory that had been allocated for `b` (when it contained the string "h") is then eligible for garbage collection.</span></span>

```csharp
string b = "h";
b += "ello";
```

<span data-ttu-id="c6419-126">`[]` [运算符](../operators/member-access-operators.md#indexer-operator-)可用于只读访问 `string` 的个别字符。</span><span class="sxs-lookup"><span data-stu-id="c6419-126">The `[]` [operator](../operators/member-access-operators.md#indexer-operator-) can be used for readonly access to individual characters of a `string`.</span></span> <span data-ttu-id="c6419-127">有效值从 `0` 开始，且必须小于 `string` 的长度：</span><span class="sxs-lookup"><span data-stu-id="c6419-127">Valid values start at `0` and must be less than the length of the `string`:</span></span>

```csharp
string str = "test";
char x = str[2];  // x = 's';
```

<span data-ttu-id="c6419-128">同样，`[]` 运算符也可用于循环访问 `string` 中的每个字符：</span><span class="sxs-lookup"><span data-stu-id="c6419-128">In similar fashion, the `[]` operator can also be used for iterating over each character in a `string`:</span></span>

```csharp-interactive
string str = "test";

for (int i = 0; i < str.Length; i++)
{
  Console.Write(str[i] + " ");
}
// Output: t e s t
``` 

<span data-ttu-id="c6419-129">字符串文本属于 `string` 类型且可以两种形式编写（带引号和仅 `@` 带引号）。</span><span class="sxs-lookup"><span data-stu-id="c6419-129">String literals are of type `string` and can be written in two forms, quoted and `@`-quoted.</span></span> <span data-ttu-id="c6419-130">带引号字符串括在双引号 (") 内。</span><span class="sxs-lookup"><span data-stu-id="c6419-130">Quoted string literals are enclosed in double quotation marks ("):</span></span>

```csharp
"good morning"  // a string literal
```

<span data-ttu-id="c6419-131">字符串文本可包含任何字符文本。</span><span class="sxs-lookup"><span data-stu-id="c6419-131">String literals can contain any character literal.</span></span> <span data-ttu-id="c6419-132">包括转义序列。</span><span class="sxs-lookup"><span data-stu-id="c6419-132">Escape sequences are included.</span></span> <span data-ttu-id="c6419-133">下面的示例使用转义序列 `\\` 表示反斜杠，使用 `\u0066` 表示字母 f，以及使用 `\n` 表示换行符。</span><span class="sxs-lookup"><span data-stu-id="c6419-133">The following example uses escape sequence `\\` for backslash, `\u0066` for the letter f, and `\n` for newline.</span></span>

```csharp-interactive
string a = "\\\u0066\n F";
Console.WriteLine(a);
\\ Output:
\\ \f
\\  F
```

> [!NOTE]
> <span data-ttu-id="c6419-134">转义码 `\udddd`（其中 `dddd` 是一个四位数字）表示 Unicode 字符 U+`dddd`。</span><span class="sxs-lookup"><span data-stu-id="c6419-134">The escape code `\udddd` (where `dddd` is a four-digit number) represents the Unicode character U+`dddd`.</span></span> <span data-ttu-id="c6419-135">另外，还可识别八位 Unicode 转义码：`\Udddddddd`。</span><span class="sxs-lookup"><span data-stu-id="c6419-135">Eight-digit Unicode escape codes are also recognized: `\Udddddddd`.</span></span>

<span data-ttu-id="c6419-136">[逐字字符串文本](../tokens/verbatim.md)以 `@` 开头，并且也括在双引号内。</span><span class="sxs-lookup"><span data-stu-id="c6419-136">[Verbatim string literals](../tokens/verbatim.md) start with `@` and are also enclosed in double quotation marks.</span></span> <span data-ttu-id="c6419-137">例如:</span><span class="sxs-lookup"><span data-stu-id="c6419-137">For example:</span></span>

```csharp
@"good morning"  // a string literal
```

<span data-ttu-id="c6419-138">逐字字符串的优点是不处理转义序列，这样就可轻松编写完全限定的 Windows 文件名等  ：</span><span class="sxs-lookup"><span data-stu-id="c6419-138">The advantage of verbatim strings is that escape sequences are *not* processed, which makes it easy to write, for example, a fully qualified Windows file name:</span></span>

```csharp
@"c:\Docs\Source\a.txt"  // rather than "c:\\Docs\\Source\\a.txt"
```

<span data-ttu-id="c6419-139">若要在 @-quoted 字符串中包含双引号，双倍添加即可：</span><span class="sxs-lookup"><span data-stu-id="c6419-139">To include a double quotation mark in an @-quoted string, double it:</span></span>

```csharp
@"""Ahoy!"" cried the captain." // "Ahoy!" cried the captain.
```

## <a name="the-delegate-type"></a><span data-ttu-id="c6419-140">委托类型</span><span class="sxs-lookup"><span data-stu-id="c6419-140">The delegate type</span></span>

<span data-ttu-id="c6419-141">委托类型的声明与方法签名相似。</span><span class="sxs-lookup"><span data-stu-id="c6419-141">The declaration of a delegate type is similar to a method signature.</span></span> <span data-ttu-id="c6419-142">它有一个返回值和任意数目任意类型的参数：</span><span class="sxs-lookup"><span data-stu-id="c6419-142">It has a return value and any number of parameters of any type:</span></span>

```csharp
public delegate void MessageDelegate(string message);
public delegate int AnotherDelegate(MyType m, long num);
```

<span data-ttu-id="c6419-143">在 .NET 中，`System.Action` 和 `System.Func` 类型为许多常见委托提供泛型定义。</span><span class="sxs-lookup"><span data-stu-id="c6419-143">In .NET, `System.Action` and `System.Func` types provide generic definitions for many common delegates.</span></span> <span data-ttu-id="c6419-144">可能不需要定义新的自定义委托类型。</span><span class="sxs-lookup"><span data-stu-id="c6419-144">You likely don't need to define new custom delegate types.</span></span> <span data-ttu-id="c6419-145">相反，可以创建提供的泛型类型的实例化。</span><span class="sxs-lookup"><span data-stu-id="c6419-145">Instead, you can create instantiations of the provided generic types.</span></span>

<span data-ttu-id="c6419-146">`delegate` 是一种可用于封装命名方法或匿名方法的引用类型。</span><span class="sxs-lookup"><span data-stu-id="c6419-146">A `delegate` is a reference type that can be used to encapsulate a named or an anonymous method.</span></span> <span data-ttu-id="c6419-147">委托类似于 C++ 中的函数指针；但是，委托是类型安全和可靠的。</span><span class="sxs-lookup"><span data-stu-id="c6419-147">Delegates are similar to function pointers in C++; however, delegates are type-safe and secure.</span></span> <span data-ttu-id="c6419-148">有关委托的应用，请参阅[委托](../../programming-guide/delegates/index.md)和[泛型委托](../../programming-guide/generics/generic-delegates.md)。</span><span class="sxs-lookup"><span data-stu-id="c6419-148">For applications of delegates, see [Delegates](../../programming-guide/delegates/index.md) and [Generic Delegates](../../programming-guide/generics/generic-delegates.md).</span></span> <span data-ttu-id="c6419-149">委托是[事件](../../programming-guide/events/index.md)的基础。</span><span class="sxs-lookup"><span data-stu-id="c6419-149">Delegates are the basis for [Events](../../programming-guide/events/index.md).</span></span> <span data-ttu-id="c6419-150">通过将委托与命名方法或匿名方法关联，可以实例化委托。</span><span class="sxs-lookup"><span data-stu-id="c6419-150">A delegate can be instantiated by associating it either with a named or anonymous method.</span></span>

<span data-ttu-id="c6419-151">必须使用具有兼容返回类型和输入参数的方法或 lambda 表达式实例化委托。</span><span class="sxs-lookup"><span data-stu-id="c6419-151">The delegate must be instantiated with a method or lambda expression that has a compatible return type and input parameters.</span></span> <span data-ttu-id="c6419-152">有关方法签名中允许的差异程度的详细信息，请参阅[委托中的变体](../../programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md)。</span><span class="sxs-lookup"><span data-stu-id="c6419-152">For more information on the degree of variance that is allowed in the method signature, see [Variance in Delegates](../../programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md).</span></span> <span data-ttu-id="c6419-153">为了与匿名方法一起使用，委托和与之关联的代码必须一起声明。</span><span class="sxs-lookup"><span data-stu-id="c6419-153">For use with anonymous methods, the delegate and the code to be associated with it are declared together.</span></span> 

## <a name="the-dynamic-type"></a><span data-ttu-id="c6419-154">动态类型</span><span class="sxs-lookup"><span data-stu-id="c6419-154">The dynamic type</span></span>

<span data-ttu-id="c6419-155">`dynamic` 类型表示变量的使用和对其成员的引用绕过编译时类型检查。</span><span class="sxs-lookup"><span data-stu-id="c6419-155">The `dynamic` type indicates that use of the variable and references to its members bypass compile-time type checking.</span></span> <span data-ttu-id="c6419-156">改为在运行时解析这些操作。</span><span class="sxs-lookup"><span data-stu-id="c6419-156">Instead, these operations are resolved at run time.</span></span> <span data-ttu-id="c6419-157">`dynamic` 类型简化了对 COM API（例如 Office Automation API）、动态 API（例如 IronPython 库）和 HTML 文档对象模型 (DOM) 的访问。</span><span class="sxs-lookup"><span data-stu-id="c6419-157">The `dynamic` type simplifies access to COM APIs such as the Office Automation APIs, to dynamic APIs such as IronPython libraries, and to the HTML Document Object Model (DOM).</span></span>

<span data-ttu-id="c6419-158">在大多数情况下，`dynamic` 类型与 `object` 类型的行为类似。</span><span class="sxs-lookup"><span data-stu-id="c6419-158">Type `dynamic` behaves like type `object` in most circumstances.</span></span> <span data-ttu-id="c6419-159">具体而言，任何非 Null 表达式都可以转换为 `dynamic` 类型。</span><span class="sxs-lookup"><span data-stu-id="c6419-159">In particular, any non-null expression can be converted to the `dynamic` type.</span></span> <span data-ttu-id="c6419-160">`dynamic` 类型与 `object` 的不同之处在于，编译器不会对包含类型 `dynamic` 的表达式的操作进行解析或类型检查。</span><span class="sxs-lookup"><span data-stu-id="c6419-160">The `dynamic` type differs from `object` in that operations that contain expressions of type `dynamic` are not resolved or type checked by the compiler.</span></span> <span data-ttu-id="c6419-161">编译器将有关该操作信息打包在一起，之后这些信息会用于在运行时评估操作。</span><span class="sxs-lookup"><span data-stu-id="c6419-161">The compiler packages together information about the operation, and that information is later used to evaluate the operation at run time.</span></span> <span data-ttu-id="c6419-162">在此过程中，`dynamic` 类型的变量会编译为 `object` 类型的变量。</span><span class="sxs-lookup"><span data-stu-id="c6419-162">As part of the process, variables of type `dynamic` are compiled into variables of type `object`.</span></span> <span data-ttu-id="c6419-163">因此，`dynamic` 类型只在编译时存在，在运行时则不存在。</span><span class="sxs-lookup"><span data-stu-id="c6419-163">Therefore, type `dynamic` exists only at compile time, not at run time.</span></span>

<span data-ttu-id="c6419-164">下面的示例将 `dynamic` 类型的变量与 `object` 类型的变量进行对比。</span><span class="sxs-lookup"><span data-stu-id="c6419-164">The following example contrasts a variable of type `dynamic` to a variable of type `object`.</span></span> <span data-ttu-id="c6419-165">若要在编译时验证每个变量的类型，请将鼠标指针放在 `WriteLine` 语句中的 `dyn` 或 `obj` 上。</span><span class="sxs-lookup"><span data-stu-id="c6419-165">To verify the type of each variable at compile time, place the mouse pointer over `dyn` or `obj` in the `WriteLine` statements.</span></span> <span data-ttu-id="c6419-166">请将下面的代码复制到可以使用 IntelliSense 的编辑器中。</span><span class="sxs-lookup"><span data-stu-id="c6419-166">Copy the following code into an editor where IntelliSense is available.</span></span> <span data-ttu-id="c6419-167">IntelliSense 对 `dyn` 显示“dynamic”  ，对 `obj` 显示“object”  。</span><span class="sxs-lookup"><span data-stu-id="c6419-167">IntelliSense shows **dynamic** for `dyn` and **object** for `obj`.</span></span>

[!code-csharp[csrefKeywordsTypes#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/dynamic1.cs#21)]

<span data-ttu-id="c6419-168"><xref:System.Console.WriteLine%2A> 语句显示 `dyn` 和 `obj` 的运行时类型。</span><span class="sxs-lookup"><span data-stu-id="c6419-168">The <xref:System.Console.WriteLine%2A> statements display the run-time types of `dyn` and `obj`.</span></span> <span data-ttu-id="c6419-169">此时，两者的类型均为整数。</span><span class="sxs-lookup"><span data-stu-id="c6419-169">At that point, both have the same type, integer.</span></span> <span data-ttu-id="c6419-170">将生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="c6419-170">The following output is produced:</span></span>

```console
System.Int32
System.Int32
```

<span data-ttu-id="c6419-171">若要查看编译时 `dyn` 与 `obj` 之间的区别，请在前面示例的声明和 `WriteLine` 语句之间添加下列两行。</span><span class="sxs-lookup"><span data-stu-id="c6419-171">To see the difference between `dyn` and `obj` at compile time, add the following two lines between the declarations and the `WriteLine` statements in the previous example.</span></span>

```csharp
dyn = dyn + 3;
obj = obj + 3;
```

 <span data-ttu-id="c6419-172">尝试在表达式 `obj + 3` 中添加整数和对象时，将报告编译器错误。</span><span class="sxs-lookup"><span data-stu-id="c6419-172">A compiler error is reported for the attempted addition of an integer and an object in expression `obj + 3`.</span></span> <span data-ttu-id="c6419-173">但是，对于 `dyn + 3`，不会报告任何错误。</span><span class="sxs-lookup"><span data-stu-id="c6419-173">However, no error is reported for `dyn + 3`.</span></span> <span data-ttu-id="c6419-174">在编译时不会检查包含 `dyn` 的表达式，原因是 `dyn` 的类型为 `dynamic`。</span><span class="sxs-lookup"><span data-stu-id="c6419-174">The expression that contains `dyn` is not checked at compile time because the type of `dyn` is `dynamic`.</span></span>

<span data-ttu-id="c6419-175">下面的示例在多个声明中使用 `dynamic`。</span><span class="sxs-lookup"><span data-stu-id="c6419-175">The following example uses `dynamic` in several declarations.</span></span> <span data-ttu-id="c6419-176">`Main` 方法也将编译时类型检查与运行时类型检查进行了对比。</span><span class="sxs-lookup"><span data-stu-id="c6419-176">The `Main` method also contrasts compile-time type checking with run-time type checking.</span></span>

[!code-csharp[csrefKeywordsTypes#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/dynamic2.cs#25)]

### <a name="see-also"></a><span data-ttu-id="c6419-177">请参阅</span><span class="sxs-lookup"><span data-stu-id="c6419-177">See also</span></span>

- [<span data-ttu-id="c6419-178">C# 参考</span><span class="sxs-lookup"><span data-stu-id="c6419-178">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="c6419-179">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="c6419-179">C# Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="c6419-180">事件</span><span class="sxs-lookup"><span data-stu-id="c6419-180">Events</span></span>](../../../csharp/programming-guide/events/index.md)
- [<span data-ttu-id="c6419-181">使用类型 dynamic</span><span class="sxs-lookup"><span data-stu-id="c6419-181">Using Type dynamic</span></span>](../../programming-guide/types/using-type-dynamic.md)
- [<span data-ttu-id="c6419-182">有关使用字符串的最佳做法</span><span class="sxs-lookup"><span data-stu-id="c6419-182">Best Practices for Using Strings</span></span>](../../../standard/base-types/best-practices-strings.md)
- [<span data-ttu-id="c6419-183">基本字符串操作</span><span class="sxs-lookup"><span data-stu-id="c6419-183">Basic String Operations</span></span>](../../../standard/base-types/basic-string-operations.md)
- [<span data-ttu-id="c6419-184">新建字符串</span><span class="sxs-lookup"><span data-stu-id="c6419-184">Creating New Strings</span></span>](../../../standard/base-types/creating-new.md)
- [<span data-ttu-id="c6419-185">类型测试和强制转换运算符</span><span class="sxs-lookup"><span data-stu-id="c6419-185">Type-testing and cast operators</span></span>](../operators/type-testing-and-cast.md)
- [<span data-ttu-id="c6419-186">如何：使用模式匹配以及 is 和 as 运算符安全地进行强制转换</span><span class="sxs-lookup"><span data-stu-id="c6419-186">How to: safely cast using pattern matching and the as and is operators</span></span>](../../how-to/safely-cast-using-pattern-matching-is-and-as-operators.md)
- [<span data-ttu-id="c6419-187">演练：创建和使用动态对象</span><span class="sxs-lookup"><span data-stu-id="c6419-187">Walkthrough: creating and using dynamic objects</span></span>](../../programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)
- <xref:System.Object?displayProperty=nameWithType>
- <xref:System.String?displayProperty=nameWithType>
- <xref:System.Dynamic.DynamicObject?displayProperty=nameWithType>
