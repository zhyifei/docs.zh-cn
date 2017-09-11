---
title: "dynamic（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- dynamic_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- dynamic [C#]
- dynamic keyword [C#]
ms.assetid: 9e797102-cc83-4964-bf58-afe4f54d16bc
caps.latest.revision: 25
author: BillWagner
ms.author: wiwagn
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
ms.openlocfilehash: b68a6ef4dc3dda01638b9bb84db58ba77214f490
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="dynamic-c-reference"></a><span data-ttu-id="bcf50-102">dynamic（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="bcf50-102">dynamic (C# Reference)</span></span>
<span data-ttu-id="bcf50-103">在通过 `dynamic` 类型实现的操作中，该类型的作用是绕过编译时类型检查。</span><span class="sxs-lookup"><span data-stu-id="bcf50-103">The `dynamic` type enables the operations in which it occurs to bypass compile-time type checking.</span></span> <span data-ttu-id="bcf50-104">改为在运行时解析这些操作。</span><span class="sxs-lookup"><span data-stu-id="bcf50-104">Instead, these operations are resolved at run time.</span></span> <span data-ttu-id="bcf50-105">`dynamic` 类型简化了对 COM API（例如 Office Automation API）、动态 API（例如 IronPython 库）和 HTML 文档对象模型 (DOM) 的访问。</span><span class="sxs-lookup"><span data-stu-id="bcf50-105">The `dynamic` type simplifies access to COM APIs such as the Office Automation APIs, and also to dynamic APIs such as IronPython libraries, and to the HTML Document Object Model (DOM).</span></span>  
  
 <span data-ttu-id="bcf50-106">在大多数情况下，`dynamic` 类型与 `object` 类型的行为类似。</span><span class="sxs-lookup"><span data-stu-id="bcf50-106">Type `dynamic` behaves like type `object` in most circumstances.</span></span> <span data-ttu-id="bcf50-107">但是，如果操作包含 `dynamic` 类型的表达式，那么不会通过编译器对该操作进行解析或类型检查。</span><span class="sxs-lookup"><span data-stu-id="bcf50-107">However, operations that contain expressions of type `dynamic` are not resolved or type checked by the compiler.</span></span> <span data-ttu-id="bcf50-108">编译器将有关该操作信息打包在一起，之后这些信息会用于在运行时评估操作。</span><span class="sxs-lookup"><span data-stu-id="bcf50-108">The compiler packages together information about the operation, and that information is later used to evaluate the operation at run time.</span></span> <span data-ttu-id="bcf50-109">在此过程中，`dynamic` 类型的变量会编译为 `object` 类型的变量。</span><span class="sxs-lookup"><span data-stu-id="bcf50-109">As part of the process, variables of type `dynamic` are compiled into variables of type `object`.</span></span> <span data-ttu-id="bcf50-110">因此，`dynamic` 类型只在编译时存在，在运行时则不存在。</span><span class="sxs-lookup"><span data-stu-id="bcf50-110">Therefore, type `dynamic` exists only at compile time, not at run time.</span></span>  
  
 <span data-ttu-id="bcf50-111">下面的示例将 `dynamic` 类型的变量与 `object` 类型的变量进行对比。</span><span class="sxs-lookup"><span data-stu-id="bcf50-111">The following example contrasts a variable of type `dynamic` to a variable of type `object`.</span></span> <span data-ttu-id="bcf50-112">若要在编译时验证每个变量的类型，请将鼠标指针放在 `WriteLine` 语句中的 `dyn` 或 `obj` 上。</span><span class="sxs-lookup"><span data-stu-id="bcf50-112">To verify the type of each variable at compile time, place the mouse pointer over `dyn` or `obj` in the `WriteLine` statements.</span></span> <span data-ttu-id="bcf50-113">IntelliSense 对 `dyn` 显示“dynamic”，对 `obj` 显示“object”。</span><span class="sxs-lookup"><span data-stu-id="bcf50-113">IntelliSense shows **dynamic** for `dyn` and **object** for `obj`.</span></span>  
  
 <span data-ttu-id="bcf50-114">[!code-cs[csrefKeywordsTypes#21](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="bcf50-114">[!code-cs[csrefKeywordsTypes#21](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_1.cs)]</span></span>  
  
 <span data-ttu-id="bcf50-115">`WriteLine` 语句显示 `dyn` 和 `obj` 的运行时类型。</span><span class="sxs-lookup"><span data-stu-id="bcf50-115">The `WriteLine` statements display the run-time types of `dyn` and `obj`.</span></span> <span data-ttu-id="bcf50-116">此时，两者的类型均为整数。</span><span class="sxs-lookup"><span data-stu-id="bcf50-116">At that point, both have the same type, integer.</span></span> <span data-ttu-id="bcf50-117">将生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="bcf50-117">The following output is produced:</span></span>  
  
 `System.Int32`  
  
 `System.Int32`  
  
 <span data-ttu-id="bcf50-118">若要查看编译时 `dyn` 与 `obj` 之间的区别，请在前面示例的声明和 `WriteLine` 语句之间添加下列两行。</span><span class="sxs-lookup"><span data-stu-id="bcf50-118">To see the difference between `dyn` and `obj` at compile time, add the following two lines between the declarations and the `WriteLine` statements in the previous example.</span></span>  
  
```csharp  
dyn = dyn + 3;  
obj = obj + 3;  
```  
  
 <span data-ttu-id="bcf50-119">尝试在表达式 `obj + 3` 中添加整数和对象时，将报告编译器错误。</span><span class="sxs-lookup"><span data-stu-id="bcf50-119">A compiler error is reported for the attempted addition of an integer and an object in expression `obj + 3`.</span></span> <span data-ttu-id="bcf50-120">但是，对于 `dyn + 3`，不会报告任何错误。</span><span class="sxs-lookup"><span data-stu-id="bcf50-120">However, no error is reported for `dyn + 3`.</span></span> <span data-ttu-id="bcf50-121">在编译时不会检查包含 `dyn` 的表达式，原因是 `dyn` 的类型为 `dynamic`。</span><span class="sxs-lookup"><span data-stu-id="bcf50-121">The expression that contains `dyn` is not checked at compile time because the type of `dyn` is `dynamic`.</span></span>  
  
## <a name="context"></a><span data-ttu-id="bcf50-122">上下文</span><span class="sxs-lookup"><span data-stu-id="bcf50-122">Context</span></span>  
 <span data-ttu-id="bcf50-123">`dynamic` 关键字可以直接出现，也可以作为构造类型的组件在下列情况中出现：</span><span class="sxs-lookup"><span data-stu-id="bcf50-123">The `dynamic` keyword can appear directly or as a component of a constructed type in the following situations:</span></span>  
  
-   <span data-ttu-id="bcf50-124">在声明中，作为属性、字段、索引器、参数、返回值、本地变量或类型约束的类型。</span><span class="sxs-lookup"><span data-stu-id="bcf50-124">In declarations, as the type of a property, field, indexer, parameter, return value, local variable, or type constraint.</span></span> <span data-ttu-id="bcf50-125">下面的类定义在多个不同的声明中使用 `dynamic`。</span><span class="sxs-lookup"><span data-stu-id="bcf50-125">The following class definition uses `dynamic` in several different declarations.</span></span>  
  
     <span data-ttu-id="bcf50-126">[!code-cs[csrefKeywordsTypes#22](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="bcf50-126">[!code-cs[csrefKeywordsTypes#22](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_2.cs)]</span></span>  
  
-   <span data-ttu-id="bcf50-127">在显式类型转换中，作为转换的目标类型。</span><span class="sxs-lookup"><span data-stu-id="bcf50-127">In explicit type conversions, as the target type of a conversion.</span></span>  
  
     <span data-ttu-id="bcf50-128">[!code-cs[csrefKeywordsTypes#23](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="bcf50-128">[!code-cs[csrefKeywordsTypes#23](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_3.cs)]</span></span>  
  
-   <span data-ttu-id="bcf50-129">在以下任何情况下：类型用作值（如 `is` 运算符或 `as` 运算符右侧），或者用作构造类型中 `typeof` 的参数。</span><span class="sxs-lookup"><span data-stu-id="bcf50-129">In any context where types serve as values, such as on the right side of an `is` operator or an `as` operator, or as the argument to `typeof` as part of a constructed type.</span></span> <span data-ttu-id="bcf50-130">例如，可以在下列表达式中使用 `dynamic`。</span><span class="sxs-lookup"><span data-stu-id="bcf50-130">For example, `dynamic` can be used in the following expressions.</span></span>  
  
     <span data-ttu-id="bcf50-131">[!code-cs[csrefKeywordsTypes#24](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="bcf50-131">[!code-cs[csrefKeywordsTypes#24](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_4.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="bcf50-132">示例</span><span class="sxs-lookup"><span data-stu-id="bcf50-132">Example</span></span>  
 <span data-ttu-id="bcf50-133">下面的示例在多个声明中使用 `dynamic`。</span><span class="sxs-lookup"><span data-stu-id="bcf50-133">The following example uses `dynamic` in several declarations.</span></span> <span data-ttu-id="bcf50-134">`Main` 方法也将编译时类型检查与运行时类型检查进行了对比。</span><span class="sxs-lookup"><span data-stu-id="bcf50-134">The `Main` method also contrasts compile-time type checking with run-time type checking.</span></span>  
  
 <span data-ttu-id="bcf50-135">[!code-cs[csrefKeywordsTypes#25](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="bcf50-135">[!code-cs[csrefKeywordsTypes#25](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_5.cs)]</span></span>  
  
 <span data-ttu-id="bcf50-136">有关详细信息和示例，请参阅[使用类型 dynamic](../../../csharp/programming-guide/types/using-type-dynamic.md)。</span><span class="sxs-lookup"><span data-stu-id="bcf50-136">For more information and examples, see [Using Type dynamic](../../../csharp/programming-guide/types/using-type-dynamic.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcf50-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bcf50-137">See Also</span></span>  
 <span data-ttu-id="bcf50-138"><xref:System.Dynamic.ExpandoObject?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="bcf50-138"><xref:System.Dynamic.ExpandoObject?displayProperty=fullName></span></span>   
 <span data-ttu-id="bcf50-139"><xref:System.Dynamic.DynamicObject?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="bcf50-139"><xref:System.Dynamic.DynamicObject?displayProperty=fullName></span></span>   
 <span data-ttu-id="bcf50-140">[使用类型 dynamic](../../../csharp/programming-guide/types/using-type-dynamic.md) </span><span class="sxs-lookup"><span data-stu-id="bcf50-140">[Using Type dynamic](../../../csharp/programming-guide/types/using-type-dynamic.md) </span></span>  
 <span data-ttu-id="bcf50-141">[对象](../../../csharp/language-reference/keywords/object.md) </span><span class="sxs-lookup"><span data-stu-id="bcf50-141">[object](../../../csharp/language-reference/keywords/object.md) </span></span>  
 <span data-ttu-id="bcf50-142">[is](../../../csharp/language-reference/keywords/is.md) </span><span class="sxs-lookup"><span data-stu-id="bcf50-142">[is](../../../csharp/language-reference/keywords/is.md) </span></span>  
 <span data-ttu-id="bcf50-143">[as](../../../csharp/language-reference/keywords/as.md) </span><span class="sxs-lookup"><span data-stu-id="bcf50-143">[as](../../../csharp/language-reference/keywords/as.md) </span></span>  
 <span data-ttu-id="bcf50-144">[typeof](../../../csharp/language-reference/keywords/typeof.md) </span><span class="sxs-lookup"><span data-stu-id="bcf50-144">[typeof](../../../csharp/language-reference/keywords/typeof.md) </span></span>  
 <span data-ttu-id="bcf50-145">[如何：使用 as 和 is 运算符安全地进行强制转换](../../../csharp/programming-guide/types/how-to-safely-cast-by-using-as-and-is-operators.md) </span><span class="sxs-lookup"><span data-stu-id="bcf50-145">[How to: Safely Cast by Using as and is Operators](../../../csharp/programming-guide/types/how-to-safely-cast-by-using-as-and-is-operators.md) </span></span>  
 [<span data-ttu-id="bcf50-146">演练：创建和使用动态对象</span><span class="sxs-lookup"><span data-stu-id="bcf50-146">Walkthrough: Creating and Using Dynamic Objects</span></span>](../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)

