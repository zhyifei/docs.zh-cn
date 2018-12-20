---
title: 参数设计
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines [.NET Framework], parameters
- members [.NET Framework], parameters
- names [.NET Framework], parameters
- parameters, design guidelines
- reserved parameters
ms.assetid: 3f33bf46-4a7b-43b3-bb78-1ffebe0dcfa6
author: KrzysztofCwalina
ms.openlocfilehash: a639e1389d0771dfcb5635b7d78982150b684fd3
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53150802"
---
# <a name="parameter-design"></a><span data-ttu-id="0c23f-102">参数设计</span><span class="sxs-lookup"><span data-stu-id="0c23f-102">Parameter Design</span></span>
<span data-ttu-id="0c23f-103">本部分提供了有关参数设计的广泛准则，包括用于检查参数的准则。</span><span class="sxs-lookup"><span data-stu-id="0c23f-103">This section provides broad guidelines on parameter design, including sections with guidelines for checking arguments.</span></span> <span data-ttu-id="0c23f-104">此外，还应参考[命名参数](../../../docs/standard/design-guidelines/naming-parameters.md)中介绍的准则。</span><span class="sxs-lookup"><span data-stu-id="0c23f-104">In addition, you should refer to the guidelines described in [Naming Parameters](../../../docs/standard/design-guidelines/naming-parameters.md).</span></span>  
  
 <span data-ttu-id="0c23f-105">**✓ 务必**使用可提供成员所需功能的最少的派生参数类型。</span><span class="sxs-lookup"><span data-stu-id="0c23f-105">**✓ DO** use the least derived parameter type that provides the functionality required by the member.</span></span>  
  
 <span data-ttu-id="0c23f-106">例如，假设想要设计一个枚举集合并将每个项输出到控制台的的方法。</span><span class="sxs-lookup"><span data-stu-id="0c23f-106">For example, suppose you want to design a method that enumerates a collection and prints each item to the console.</span></span> <span data-ttu-id="0c23f-107">此类方法应使用 <xref:System.Collections.IEnumerable> 作为参数，而不应使用 <xref:System.Collections.ArrayList> 或 <xref:System.Collections.IList>。</span><span class="sxs-lookup"><span data-stu-id="0c23f-107">Such a method should take <xref:System.Collections.IEnumerable> as the parameter, not <xref:System.Collections.ArrayList> or <xref:System.Collections.IList>, for example.</span></span>  
  
 <span data-ttu-id="0c23f-108">**X 切忌**使用保留参数。</span><span class="sxs-lookup"><span data-stu-id="0c23f-108">**X DO NOT** use reserved parameters.</span></span>  
  
 <span data-ttu-id="0c23f-109">如果在将来的某个版本中需要对成员有更多输入，则可以添加新的重载。</span><span class="sxs-lookup"><span data-stu-id="0c23f-109">If more input to a member is needed in some future version, a new overload can be added.</span></span>  
  
 <span data-ttu-id="0c23f-110">**X 切忌**使用将指针、指针数组或多维数组作为参数的公开方法。</span><span class="sxs-lookup"><span data-stu-id="0c23f-110">**X DO NOT** have publicly exposed methods that take pointers, arrays of pointers, or multidimensional arrays as parameters.</span></span>  
  
 <span data-ttu-id="0c23f-111">指针和多维数组相对难以正确使用。</span><span class="sxs-lookup"><span data-stu-id="0c23f-111">Pointers and multidimensional arrays are relatively difficult to use properly.</span></span> <span data-ttu-id="0c23f-112">几乎在所有情况下，都可以重新设计 API 以避免将这些类型作为参数。</span><span class="sxs-lookup"><span data-stu-id="0c23f-112">In almost all cases, APIs can be redesigned to avoid taking these types as parameters.</span></span>  
  
 <span data-ttu-id="0c23f-113">**✓ 务必**把所有 `out` 参数放置在所有传值和 `ref` 参数（不包括参数数组）之后，即使它会导致重载之间参数排序的不一致（请参阅[成员重载](../../../docs/standard/design-guidelines/member-overloading.md)）。</span><span class="sxs-lookup"><span data-stu-id="0c23f-113">**✓ DO** place all `out` parameters following all of the by-value and `ref` parameters (excluding parameter arrays), even if it results in an inconsistency in parameter ordering between overloads (see [Member Overloading](../../../docs/standard/design-guidelines/member-overloading.md)).</span></span>  
  
 <span data-ttu-id="0c23f-114">可以将 `out` 参数看作是额外的返回值，并且可以将它们分组在一起，使方法签名更易于理解。</span><span class="sxs-lookup"><span data-stu-id="0c23f-114">The `out` parameters can be seen as extra return values, and grouping them together makes the method signature easier to understand.</span></span>  
  
 <span data-ttu-id="0c23f-115">**✓ 务必**在重写成员或实现接口成员时，在命名参数上保持一致。</span><span class="sxs-lookup"><span data-stu-id="0c23f-115">**✓ DO** be consistent in naming parameters when overriding members or implementing interface members.</span></span>  
  
 <span data-ttu-id="0c23f-116">这更好地传达了方法之间的关系。</span><span class="sxs-lookup"><span data-stu-id="0c23f-116">This better communicates the relationship between the methods.</span></span>  
  
### <a name="choosing-between-enum-and-boolean-parameters"></a><span data-ttu-id="0c23f-117">在枚举和布尔形参之间进行选择</span><span class="sxs-lookup"><span data-stu-id="0c23f-117">Choosing Between Enum and Boolean Parameters</span></span>  
 <span data-ttu-id="0c23f-118">**✓ 务必**使用枚举，如果成员有两个或多个布尔参数的话。</span><span class="sxs-lookup"><span data-stu-id="0c23f-118">**✓ DO** use enums if a member would otherwise have two or more Boolean parameters.</span></span>  
  
 <span data-ttu-id="0c23f-119">**X 切忌**使用布尔值，除非绝对确定永远不需要两个以上的值。</span><span class="sxs-lookup"><span data-stu-id="0c23f-119">**X DO NOT** use Booleans unless you are absolutely sure there will never be a need for more than two values.</span></span>  
  
 <span data-ttu-id="0c23f-120">枚举为你将来添加值提供了一些空间，但应该注意在枚举中添加值的所有影响，这些内容在[枚举设计](../../../docs/standard/design-guidelines/enum.md)中进行了描述。</span><span class="sxs-lookup"><span data-stu-id="0c23f-120">Enums give you some room for future addition of values, but you should be aware of all the implications of adding values to enums, which are described in [Enum Design](../../../docs/standard/design-guidelines/enum.md).</span></span>  
  
 <span data-ttu-id="0c23f-121">**✓ 考虑**使用布尔值作为构造函数参数，这些参数是真正的双状态值，仅用于初始化布尔属性。</span><span class="sxs-lookup"><span data-stu-id="0c23f-121">**✓ CONSIDER** using Booleans for constructor parameters that are truly two-state values and are simply used to initialize Boolean properties.</span></span>  
  
### <a name="validating-arguments"></a><span data-ttu-id="0c23f-122">验证实参</span><span class="sxs-lookup"><span data-stu-id="0c23f-122">Validating Arguments</span></span>  
 <span data-ttu-id="0c23f-123">**✓ 务必**验证传递到公共、受保护或显式实现的成员的实参。</span><span class="sxs-lookup"><span data-stu-id="0c23f-123">**✓ DO** validate arguments passed to public, protected, or explicitly implemented members.</span></span> <span data-ttu-id="0c23f-124">如果验证失败，将引发 <xref:System.ArgumentException?displayProperty=nameWithType> 或其一个子类。</span><span class="sxs-lookup"><span data-stu-id="0c23f-124">Throw <xref:System.ArgumentException?displayProperty=nameWithType>, or one of its subclasses, if the validation fails.</span></span>  
  
 <span data-ttu-id="0c23f-125">请注意，实际验证不一定必须在公共成员或受保护成员本身中进行。</span><span class="sxs-lookup"><span data-stu-id="0c23f-125">Note that the actual validation does not necessarily have to happen in the public or protected member itself.</span></span> <span data-ttu-id="0c23f-126">它可能发生在某些私有或内部例程的较低级别。</span><span class="sxs-lookup"><span data-stu-id="0c23f-126">It could happen at a lower level in some private or internal routine.</span></span> <span data-ttu-id="0c23f-127">重点是暴露给最终用户的整个上层区域会检查参数。</span><span class="sxs-lookup"><span data-stu-id="0c23f-127">The main point is that the entire surface area that is exposed to the end users checks the arguments.</span></span>  
  
 <span data-ttu-id="0c23f-128">**✓ 务必**引发 <xref:System.ArgumentNullException>，如果传递 null 实参且该成员不支持 null 实参。</span><span class="sxs-lookup"><span data-stu-id="0c23f-128">**✓ DO** throw <xref:System.ArgumentNullException> if a null argument is passed and the member does not support null arguments.</span></span>  
  
 <span data-ttu-id="0c23f-129">**✓ 务必**验证 enum 形参。</span><span class="sxs-lookup"><span data-stu-id="0c23f-129">**✓ DO** validate enum parameters.</span></span>  
  
 <span data-ttu-id="0c23f-130">不要假设枚举实参将在枚举定义的范围内。</span><span class="sxs-lookup"><span data-stu-id="0c23f-130">Do not assume enum arguments will be in the range defined by the enum.</span></span> <span data-ttu-id="0c23f-131">CLR 允许将任何整数值转换为枚举值，即使该值未在枚举中定义。</span><span class="sxs-lookup"><span data-stu-id="0c23f-131">The CLR allows casting any integer value into an enum value even if the value is not defined in the enum.</span></span>  
  
 <span data-ttu-id="0c23f-132">**X 切忌**将 <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> 用于枚举范围检查。</span><span class="sxs-lookup"><span data-stu-id="0c23f-132">**X DO NOT** use <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> for enum range checks.</span></span>  
  
 <span data-ttu-id="0c23f-133">**✓ 务必**注意，可变实参在验证后可能已更改。</span><span class="sxs-lookup"><span data-stu-id="0c23f-133">**✓ DO** be aware that mutable arguments might have changed after they were validated.</span></span>  
  
 <span data-ttu-id="0c23f-134">如果该成员对安全性敏感，则建议生成一个副本，然后验证并处理该实参。</span><span class="sxs-lookup"><span data-stu-id="0c23f-134">If the member is security sensitive, you are encouraged to make a copy and then validate and process the argument.</span></span>  
  
### <a name="parameter-passing"></a><span data-ttu-id="0c23f-135">参数传递</span><span class="sxs-lookup"><span data-stu-id="0c23f-135">Parameter Passing</span></span>  
 <span data-ttu-id="0c23f-136">从框架设计者的角度来看，有三组主要形参：传值形参、`ref` 形参和 `out` 形参。</span><span class="sxs-lookup"><span data-stu-id="0c23f-136">From the perspective of a framework designer, there are three main groups of parameters: by-value parameters, `ref` parameters, and `out` parameters.</span></span>  
  
 <span data-ttu-id="0c23f-137">当实参通过传值形参传递时，该成员将接收传入的实际实参的副本。</span><span class="sxs-lookup"><span data-stu-id="0c23f-137">When an argument is passed through a by-value parameter, the member receives a copy of the actual argument passed in.</span></span> <span data-ttu-id="0c23f-138">如果实参是值类型，则将实参的副本放在栈上。</span><span class="sxs-lookup"><span data-stu-id="0c23f-138">If the argument is a value type, a copy of the argument is put on the stack.</span></span> <span data-ttu-id="0c23f-139">如果实参是引用类型，则将引用的副本放在栈上。</span><span class="sxs-lookup"><span data-stu-id="0c23f-139">If the argument is a reference type, a copy of the reference is put on the stack.</span></span> <span data-ttu-id="0c23f-140">最常用的 CLR 语言，如 C#，VB.NET 和 C++，默认按值传递形参。</span><span class="sxs-lookup"><span data-stu-id="0c23f-140">Most popular CLR languages, such as C#, VB.NET, and C++, default to passing parameters by value.</span></span>  
  
 <span data-ttu-id="0c23f-141">当实参通过 `ref` 形参传递时，成员接收对传入的实际实参的引用。</span><span class="sxs-lookup"><span data-stu-id="0c23f-141">When an argument is passed through a `ref` parameter, the member receives a reference to the actual argument passed in.</span></span> <span data-ttu-id="0c23f-142">如果实参是值类型，则将实参的引用放在栈上。</span><span class="sxs-lookup"><span data-stu-id="0c23f-142">If the argument is a value type, a reference to the argument is put on the stack.</span></span> <span data-ttu-id="0c23f-143">如果实参是引用类型，则将引用的引用放在栈上。</span><span class="sxs-lookup"><span data-stu-id="0c23f-143">If the argument is a reference type, a reference to the reference is put on the stack.</span></span> <span data-ttu-id="0c23f-144">`Ref` 形参可用于允许成员修改调用方传递的实参。</span><span class="sxs-lookup"><span data-stu-id="0c23f-144">`Ref` parameters can be used to allow the member to modify arguments passed by the caller.</span></span>  
  
 <span data-ttu-id="0c23f-145">`Out`形参类似于`ref`形参，但存在一些细微差异。</span><span class="sxs-lookup"><span data-stu-id="0c23f-145">`Out` parameters are similar to `ref` parameters, with some small differences.</span></span> <span data-ttu-id="0c23f-146">该形参最初被视为未分配，并且在为其分配某个值之前无法在成员体内中读取。</span><span class="sxs-lookup"><span data-stu-id="0c23f-146">The parameter is initially considered unassigned and cannot be read in the member body before it is assigned some value.</span></span> <span data-ttu-id="0c23f-147">此外，必须在成员返回之前为形参指定一些值。</span><span class="sxs-lookup"><span data-stu-id="0c23f-147">Also, the parameter has to be assigned some value before the member returns.</span></span>  
  
 <span data-ttu-id="0c23f-148">**X 避免**使用 `out` 或 `ref` 形参。</span><span class="sxs-lookup"><span data-stu-id="0c23f-148">**X AVOID** using `out` or `ref` parameters.</span></span>  
  
 <span data-ttu-id="0c23f-149">使用 `out` 或 `ref` 形参需要一些经验，包括使用指针，理解值类型和引用类型的不同，以及处理具有多个返回值的方法。</span><span class="sxs-lookup"><span data-stu-id="0c23f-149">Using `out` or `ref` parameters requires experience with pointers, understanding how value types and reference types differ, and handling methods with multiple return values.</span></span> <span data-ttu-id="0c23f-150">另外，`out` 和 `ref` 形参之间的区别并不广为人知。</span><span class="sxs-lookup"><span data-stu-id="0c23f-150">Also, the difference between `out` and `ref` parameters is not widely understood.</span></span> <span data-ttu-id="0c23f-151">为一般用户设计的框架架构师不应期望用户熟练掌握使用 `out` 或 `ref` 形参。</span><span class="sxs-lookup"><span data-stu-id="0c23f-151">Framework architects designing for a general audience should not expect users to master working with `out` or `ref` parameters.</span></span>  
  
 <span data-ttu-id="0c23f-152">**X 切忌**通过引用传递引用类型。</span><span class="sxs-lookup"><span data-stu-id="0c23f-152">**X DO NOT** pass reference types by reference.</span></span>  
  
 <span data-ttu-id="0c23f-153">该规则有一些有限的例外情况，例如可用于交换引用的方法。</span><span class="sxs-lookup"><span data-stu-id="0c23f-153">There are some limited exceptions to the rule, such as a method that can be used to swap references.</span></span>  
  
### <a name="members-with-variable-number-of-parameters"></a><span data-ttu-id="0c23f-154">具有可变形参数量的成员</span><span class="sxs-lookup"><span data-stu-id="0c23f-154">Members with Variable Number of Parameters</span></span>  
 <span data-ttu-id="0c23f-155">可以通过提供数组形参来表示使用可变数量实参的成员。</span><span class="sxs-lookup"><span data-stu-id="0c23f-155">Members that can take a variable number of arguments are expressed by providing an array parameter.</span></span> <span data-ttu-id="0c23f-156">例如，<xref:System.String> 提供了以下方法：</span><span class="sxs-lookup"><span data-stu-id="0c23f-156">For example, <xref:System.String> provides the following method:</span></span>  
  
```  
public class String {  
    public static string Format(string format, object[] parameters);  
}  
```  
  
 <span data-ttu-id="0c23f-157">然后，用户可以调用<xref:System.String.Format%2A?displayProperty=nameWithType>方法，按如下所示：</span><span class="sxs-lookup"><span data-stu-id="0c23f-157">A user can then call the <xref:System.String.Format%2A?displayProperty=nameWithType> method, as follows:</span></span>  
  
 `String.Format("File {0} not found in {1}",new object[]{filename,directory});`  
  
 <span data-ttu-id="0c23f-158">将 C# params 关键字添加到数组形参会将形参更改为所谓的 params 数组形参，并提供了创建临时数组的快捷方式。</span><span class="sxs-lookup"><span data-stu-id="0c23f-158">Adding the C# params keyword to an array parameter changes the parameter to a so-called params array parameter and provides a shortcut to creating a temporary array.</span></span>  
  
```  
public class String {  
    public static string Format(string format, params object[] parameters);  
}  
```  
  
 <span data-ttu-id="0c23f-159">执行此操作允许用户通过直接在实参列表中传递数组元素来调用方法。</span><span class="sxs-lookup"><span data-stu-id="0c23f-159">Doing this allows the user to call the method by passing the array elements directly in the argument list.</span></span>  
  
 `String.Format("File {0} not found in {1}",filename,directory);`  
  
 <span data-ttu-id="0c23f-160">请注意，params 关键字只能添加到形参列表中的最后一个形参。</span><span class="sxs-lookup"><span data-stu-id="0c23f-160">Note that the params keyword can be added only to the last parameter in the parameter list.</span></span>  
  
 <span data-ttu-id="0c23f-161">**✓ 考虑**如果希望最终用户传递具有少量元素的数组，则将 params 关键字添加到数组形参中。</span><span class="sxs-lookup"><span data-stu-id="0c23f-161">**✓ CONSIDER** adding the params keyword to array parameters if you expect the end users to pass arrays with a small number of elements.</span></span> <span data-ttu-id="0c23f-162">如果期望在常见场景中传递大量元素，则用户可能无论如何也不会以内联方式传递这些元素，因此 params 关键字不是必需的。</span><span class="sxs-lookup"><span data-stu-id="0c23f-162">If it’s expected that lots of elements will be passed in common scenarios, users will probably not pass these elements inline anyway, and so the params keyword is not necessary.</span></span>  
  
 <span data-ttu-id="0c23f-163">**X 避免**使用 params 数组，如果调用方几乎总是将输入放在数组中。</span><span class="sxs-lookup"><span data-stu-id="0c23f-163">**X AVOID** using params arrays if the caller would almost always have the input already in an array.</span></span>  
  
 <span data-ttu-id="0c23f-164">例如，具有字节数组形参的成员几乎不会通过传递单个字节来调用。</span><span class="sxs-lookup"><span data-stu-id="0c23f-164">For example, members with byte array parameters would almost never be called by passing individual bytes.</span></span> <span data-ttu-id="0c23f-165">因此，.NET Framework 中的字节数组形参不使用 params 关键字。</span><span class="sxs-lookup"><span data-stu-id="0c23f-165">For this reason, byte array parameters in the .NET Framework do not use the params keyword.</span></span>  
  
 <span data-ttu-id="0c23f-166">**X 切忌**使用 params 数组，如果采用 params 数组形参的成员修改了数组。</span><span class="sxs-lookup"><span data-stu-id="0c23f-166">**X DO NOT** use params arrays if the array is modified by the member taking the params array parameter.</span></span>  
  
 <span data-ttu-id="0c23f-167">由于许多编译器将成员的实参转换为调用站点的临时数组，因此该数组可能是临时对象，所以对数组的任何修改都将丢失。</span><span class="sxs-lookup"><span data-stu-id="0c23f-167">Because of the fact that many compilers turn the arguments to the member into a temporary array at the call site, the array might be a temporary object, and therefore any modifications to the array will be lost.</span></span>  
  
 <span data-ttu-id="0c23f-168">**✓ 考虑**在简单的重载中使用 params 关键字，即使更复杂的重载不能使用它。</span><span class="sxs-lookup"><span data-stu-id="0c23f-168">**✓ CONSIDER** using the params keyword in a simple overload, even if a more complex overload could not use it.</span></span>  
  
 <span data-ttu-id="0c23f-169">问问自己用户是否会重视在一个重载中使用 params 数组，即使它不在所有重载中。</span><span class="sxs-lookup"><span data-stu-id="0c23f-169">Ask yourself if users would value having the params array in one overload even if it wasn’t in all overloads.</span></span>  
  
 <span data-ttu-id="0c23f-170">**✓ 务必**尝试对形参进行排序，以使其可以使用 params 关键字。</span><span class="sxs-lookup"><span data-stu-id="0c23f-170">**✓ DO** try to order parameters to make it possible to use the params keyword.</span></span>  
  
 <span data-ttu-id="0c23f-171">**✓ 考虑**在性能极其敏感的 API 中为具有少量实参的调用提供特殊的重载和代码路径。</span><span class="sxs-lookup"><span data-stu-id="0c23f-171">**✓ CONSIDER** providing special overloads and code paths for calls with a small number of arguments in extremely performance-sensitive APIs.</span></span>  
  
 <span data-ttu-id="0c23f-172">这样在使用少量实参调用 API 时可以避免创建数组对象。</span><span class="sxs-lookup"><span data-stu-id="0c23f-172">This makes it possible to avoid creating array objects when the API is called with a small number of arguments.</span></span> <span data-ttu-id="0c23f-173">通过采用数组形参的单数形式，并添加数字后缀来形成形参的名称。</span><span class="sxs-lookup"><span data-stu-id="0c23f-173">Form the names of the parameters by taking a singular form of the array parameter and adding a numeric suffix.</span></span>  
  
 <span data-ttu-id="0c23f-174">应该只在对整个代码路径执行特例时才这样做，而不仅仅是创建一个数组并调用更通用的方法。</span><span class="sxs-lookup"><span data-stu-id="0c23f-174">You should only do this if you are going to special-case the entire code path, not just create an array and call the more general method.</span></span>  
  
 <span data-ttu-id="0c23f-175">**✓ 务必**注意，null 可以作为 params 数组实参传递。</span><span class="sxs-lookup"><span data-stu-id="0c23f-175">**✓ DO** be aware that null could be passed as a params array argument.</span></span>  
  
 <span data-ttu-id="0c23f-176">应该在处理之前验证数组是否为 null。</span><span class="sxs-lookup"><span data-stu-id="0c23f-176">You should validate that the array is not null before processing.</span></span>  
  
 <span data-ttu-id="0c23f-177">**X 切忌**使用 `varargs` 方法，也称为省略号。</span><span class="sxs-lookup"><span data-stu-id="0c23f-177">**X DO NOT** use the `varargs` methods, otherwise known as the ellipsis.</span></span>  
  
 <span data-ttu-id="0c23f-178">某些 CLR 语言，如 C++ ，支持传递变量形参列表的替代约定，称为 `varargs` 方法。</span><span class="sxs-lookup"><span data-stu-id="0c23f-178">Some CLR languages, such as C++, support an alternative convention for passing variable parameter lists called `varargs` methods.</span></span> <span data-ttu-id="0c23f-179">该约定不应在框架中使用，因为它不符合CLS。</span><span class="sxs-lookup"><span data-stu-id="0c23f-179">The convention should not be used in frameworks, because it is not CLS compliant.</span></span>  
  
### <a name="pointer-parameters"></a><span data-ttu-id="0c23f-180">指针参数</span><span class="sxs-lookup"><span data-stu-id="0c23f-180">Pointer Parameters</span></span>  
 <span data-ttu-id="0c23f-181">通常，指针不应出现在设计良好的托管代码框架的公共上层区域中。</span><span class="sxs-lookup"><span data-stu-id="0c23f-181">In general, pointers should not appear in the public surface area of a well-designed managed code framework.</span></span> <span data-ttu-id="0c23f-182">大多数情况下，指针应该被封装。</span><span class="sxs-lookup"><span data-stu-id="0c23f-182">Most of the time, pointers should be encapsulated.</span></span> <span data-ttu-id="0c23f-183">但是，在某些情况下，出于互操作性原因需要指针，在这种情况下适合使用指针。</span><span class="sxs-lookup"><span data-stu-id="0c23f-183">However, in some cases pointers are required for interoperability reasons, and using pointers in such cases is appropriate.</span></span>  
  
 <span data-ttu-id="0c23f-184">**✓ 务必**为所有采用指针实参的成员提供替代方法，因为指针不符合 CLS。</span><span class="sxs-lookup"><span data-stu-id="0c23f-184">**✓ DO** provide an alternative for any member that takes a pointer argument, because pointers are not CLS-compliant.</span></span>  
  
 <span data-ttu-id="0c23f-185">**X 避免**对指针实参进行高开销的实参检查。</span><span class="sxs-lookup"><span data-stu-id="0c23f-185">**X AVOID** doing expensive argument checking of pointer arguments.</span></span>  
  
 <span data-ttu-id="0c23f-186">**✓ 务必**在设计带指针的成员时，遵循常见的指针相关约定。</span><span class="sxs-lookup"><span data-stu-id="0c23f-186">**✓ DO** follow common pointer-related conventions when designing members with pointers.</span></span>  
  
 <span data-ttu-id="0c23f-187">例如，不需要传递起始索引，因为可以使用简单的指针算法来完成相同的结果。</span><span class="sxs-lookup"><span data-stu-id="0c23f-187">For example, there is no need to pass the start index, because simple pointer arithmetic can be used to accomplish the same result.</span></span>  
  
 <span data-ttu-id="0c23f-188">*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="0c23f-188">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="0c23f-189">*通过从 Pearson Education，Inc.的权限重新打印[Framework 设计准则：约定、 语法和模式的可重用.NET 库，第 2 版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)Krzysztof Cwalina 和 Brad Abrams，作为 Microsoft Windows 开发系列的一部分发布 2008 年 10 月 22 日由 Addison-wesley 专业人员。*</span><span class="sxs-lookup"><span data-stu-id="0c23f-189">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c23f-190">请参阅</span><span class="sxs-lookup"><span data-stu-id="0c23f-190">See also</span></span>

- [<span data-ttu-id="0c23f-191">成员设计准则</span><span class="sxs-lookup"><span data-stu-id="0c23f-191">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
- [<span data-ttu-id="0c23f-192">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="0c23f-192">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
