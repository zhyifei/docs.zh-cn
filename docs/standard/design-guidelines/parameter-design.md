---
title: 参数设计
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines [.NET Framework], parameters
- members [.NET Framework], parameters
- names [.NET Framework], parameters
- parameters, design guidelines
- reserved parameters
ms.assetid: 3f33bf46-4a7b-43b3-bb78-1ffebe0dcfa6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ea5311de8cef266af23b259d943568bfa95eaf72
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2018
ms.locfileid: "44275543"
---
# <a name="parameter-design"></a><span data-ttu-id="c8d8f-102">参数设计</span><span class="sxs-lookup"><span data-stu-id="c8d8f-102">Parameter Design</span></span>
<span data-ttu-id="c8d8f-103">本部分提供全面的指南参数的设计方案，包括用于检查参数的指导原则的部分。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-103">This section provides broad guidelines on parameter design, including sections with guidelines for checking arguments.</span></span> <span data-ttu-id="c8d8f-104">此外，应参考中所述的准则[命名参数](../../../docs/standard/design-guidelines/naming-parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-104">In addition, you should refer to the guidelines described in [Naming Parameters](../../../docs/standard/design-guidelines/naming-parameters.md).</span></span>  
  
 <span data-ttu-id="c8d8f-105">**✓ DO** 使用至少派生的参数提供的类型的成员所需的功能。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-105">**✓ DO** use the least derived parameter type that provides the functionality required by the member.</span></span>  
  
 <span data-ttu-id="c8d8f-106">例如，假设你想要设计枚举集合，并输出到控制台的每个项的方法。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-106">For example, suppose you want to design a method that enumerates a collection and prints each item to the console.</span></span> <span data-ttu-id="c8d8f-107">此类方法应采取<xref:System.Collections.IEnumerable>作为参数，不<xref:System.Collections.ArrayList>或<xref:System.Collections.IList>，例如。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-107">Such a method should take <xref:System.Collections.IEnumerable> as the parameter, not <xref:System.Collections.ArrayList> or <xref:System.Collections.IList>, for example.</span></span>  
  
 <span data-ttu-id="c8d8f-108">**X DO NOT** 使用保留的参数。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-108">**X DO NOT** use reserved parameters.</span></span>  
  
 <span data-ttu-id="c8d8f-109">如果某些未来版本中需要更多输入到成员，则可以添加新的重载。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-109">If more input to a member is needed in some future version, a new overload can be added.</span></span>  
  
 <span data-ttu-id="c8d8f-110">**X DO NOT** 具有公共公开指针、 数组的指针或作为参数的多维数组的方法。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-110">**X DO NOT** have publicly exposed methods that take pointers, arrays of pointers, or multidimensional arrays as parameters.</span></span>  
  
 <span data-ttu-id="c8d8f-111">指针和多维数组是相对较难正确使用。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-111">Pointers and multidimensional arrays are relatively difficult to use properly.</span></span> <span data-ttu-id="c8d8f-112">在几乎所有情况下，可以重新设计的 Api 来避免这些类型作为参数。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-112">In almost all cases, APIs can be redesigned to avoid taking these types as parameters.</span></span>  
  
 <span data-ttu-id="c8d8f-113">**✓ DO** 放置所有`out`后所有按值的参数和`ref`参数 （不包括参数数组），即使它会导致重载之间进行排序的参数中的不一致 (请参阅[成员重载](../../../docs/standard/design-guidelines/member-overloading.md))。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-113">**✓ DO** place all `out` parameters following all of the by-value and `ref` parameters (excluding parameter arrays), even if it results in an inconsistency in parameter ordering between overloads (see [Member Overloading](../../../docs/standard/design-guidelines/member-overloading.md)).</span></span>  
  
 <span data-ttu-id="c8d8f-114">`out`参数可将其视为额外返回的值，并将它们组合在一起使方法签名易于理解。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-114">The `out` parameters can be seen as extra return values, and grouping them together makes the method signature easier to understand.</span></span>  
  
 <span data-ttu-id="c8d8f-115">**✓ DO** 时重写成员命名参数或实现接口成员中保持一致。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-115">**✓ DO** be consistent in naming parameters when overriding members or implementing interface members.</span></span>  
  
 <span data-ttu-id="c8d8f-116">这更好地进行通信的方法之间的关系。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-116">This better communicates the relationship between the methods.</span></span>  
  
### <a name="choosing-between-enum-and-boolean-parameters"></a><span data-ttu-id="c8d8f-117">枚举和布尔参数之间进行选择</span><span class="sxs-lookup"><span data-stu-id="c8d8f-117">Choosing Between Enum and Boolean Parameters</span></span>  
 <span data-ttu-id="c8d8f-118">**✓ DO** 如果成员本来两个或多个布尔参数，请使用枚举。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-118">**✓ DO** use enums if a member would otherwise have two or more Boolean parameters.</span></span>  
  
 <span data-ttu-id="c8d8f-119">**X DO NOT** 如果你不完全确定永远不会将两个以上值需要使用布尔值。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-119">**X DO NOT** use Booleans unless you are absolutely sure there will never be a need for more than two values.</span></span>  
  
 <span data-ttu-id="c8d8f-120">枚举为您提供一些空间以便将来添加值，但您应注意将值添加到枚举器中所述的所有隐患[枚举设计](../../../docs/standard/design-guidelines/enum.md)。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-120">Enums give you some room for future addition of values, but you should be aware of all the implications of adding values to enums, which are described in [Enum Design](../../../docs/standard/design-guidelines/enum.md).</span></span>  
  
 <span data-ttu-id="c8d8f-121">**✓ CONSIDER** 布尔值用于构造函数参数是真正的两个状态的值，只需用来初始化布尔属性。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-121">**✓ CONSIDER** using Booleans for constructor parameters that are truly two-state values and are simply used to initialize Boolean properties.</span></span>  
  
### <a name="validating-arguments"></a><span data-ttu-id="c8d8f-122">验证自变量</span><span class="sxs-lookup"><span data-stu-id="c8d8f-122">Validating Arguments</span></span>  
 <span data-ttu-id="c8d8f-123">**✓ DO** 验证自变量传递到公共、 受保护，或显式实现的成员。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-123">**✓ DO** validate arguments passed to public, protected, or explicitly implemented members.</span></span> <span data-ttu-id="c8d8f-124">引发<xref:System.ArgumentException?displayProperty=nameWithType>，或一个子类，如果验证失败。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-124">Throw <xref:System.ArgumentException?displayProperty=nameWithType>, or one of its subclasses, if the validation fails.</span></span>  
  
 <span data-ttu-id="c8d8f-125">请注意，实际的验证不一定发生这种情况中的公共或受保护成员本身。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-125">Note that the actual validation does not necessarily have to happen in the public or protected member itself.</span></span> <span data-ttu-id="c8d8f-126">它可能在某些私有或内部的例程中较低级别。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-126">It could happen at a lower level in some private or internal routine.</span></span> <span data-ttu-id="c8d8f-127">要点是，向最终用户公开的整个图面区域会检查自变量。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-127">The main point is that the entire surface area that is exposed to the end users checks the arguments.</span></span>  
  
 <span data-ttu-id="c8d8f-128">**✓ DO** 引发<xref:System.ArgumentNullException>如果传递 null 自变量，并将该成员不支持 null 参数。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-128">**✓ DO** throw <xref:System.ArgumentNullException> if a null argument is passed and the member does not support null arguments.</span></span>  
  
 <span data-ttu-id="c8d8f-129">**✓ DO** 验证 enum 参数。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-129">**✓ DO** validate enum parameters.</span></span>  
  
 <span data-ttu-id="c8d8f-130">不要假定枚举自变量将在枚举定义的范围内。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-130">Do not assume enum arguments will be in the range defined by the enum.</span></span> <span data-ttu-id="c8d8f-131">CLR 允许任何整数值转换为枚举值，即使在枚举中未定义值。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-131">The CLR allows casting any integer value into an enum value even if the value is not defined in the enum.</span></span>  
  
 <span data-ttu-id="c8d8f-132">**X DO NOT** 使用<xref:System.Enum.IsDefined%2A?displayProperty=nameWithType>枚举范围检查。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-132">**X DO NOT** use <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> for enum range checks.</span></span>  
  
 <span data-ttu-id="c8d8f-133">**✓ DO** 请注意，在经过验证后，可能已更改可变自变量。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-133">**✓ DO** be aware that mutable arguments might have changed after they were validated.</span></span>  
  
 <span data-ttu-id="c8d8f-134">如果该成员是敏感的安全，建议您的生成副本和验证并处理自变量。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-134">If the member is security sensitive, you are encouraged to make a copy and then validate and process the argument.</span></span>  
  
### <a name="parameter-passing"></a><span data-ttu-id="c8d8f-135">参数传递</span><span class="sxs-lookup"><span data-stu-id="c8d8f-135">Parameter Passing</span></span>  
 <span data-ttu-id="c8d8f-136">从框架设计器的角度来看，有三个主要组的参数： 按值参数，`ref`参数，和`out`参数。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-136">From the perspective of a framework designer, there are three main groups of parameters: by-value parameters, `ref` parameters, and `out` parameters.</span></span>  
  
 <span data-ttu-id="c8d8f-137">当自变量传递通过按值参数时，成员都会中传递的实际自变量的副本。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-137">When an argument is passed through a by-value parameter, the member receives a copy of the actual argument passed in.</span></span> <span data-ttu-id="c8d8f-138">如果参数为值类型，自变量的副本放在堆栈上。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-138">If the argument is a value type, a copy of the argument is put on the stack.</span></span> <span data-ttu-id="c8d8f-139">如果参数为引用类型，引用的副本放在堆栈上。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-139">If the argument is a reference type, a copy of the reference is put on the stack.</span></span> <span data-ttu-id="c8d8f-140">最常用的 CLR 语言，如 C#、 VB.NET 和 c + +，默认为按值传递参数。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-140">Most popular CLR languages, such as C#, VB.NET, and C++, default to passing parameters by value.</span></span>  
  
 <span data-ttu-id="c8d8f-141">当自变量传递通过`ref`参数，该成员接收到传入的实际参数的引用。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-141">When an argument is passed through a `ref` parameter, the member receives a reference to the actual argument passed in.</span></span> <span data-ttu-id="c8d8f-142">如果参数为值类型，对自变量的引用放在堆栈上。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-142">If the argument is a value type, a reference to the argument is put on the stack.</span></span> <span data-ttu-id="c8d8f-143">如果参数为引用类型，对引用的引用放在堆栈上。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-143">If the argument is a reference type, a reference to the reference is put on the stack.</span></span> <span data-ttu-id="c8d8f-144">`Ref` 可以使用参数，以便成员可以修改由调用方传递的参数。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-144">`Ref` parameters can be used to allow the member to modify arguments passed by the caller.</span></span>  
  
 <span data-ttu-id="c8d8f-145">`Out` 参数是类似于`ref`参数，但存在一些小差异。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-145">`Out` parameters are similar to `ref` parameters, with some small differences.</span></span> <span data-ttu-id="c8d8f-146">参数最初被认为是未分配，分配一些值之前无法在成员正文中读取。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-146">The parameter is initially considered unassigned and cannot be read in the member body before it is assigned some value.</span></span> <span data-ttu-id="c8d8f-147">此外，该参数具有值分配给某些成员返回之前。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-147">Also, the parameter has to be assigned some value before the member returns.</span></span>  
  
 <span data-ttu-id="c8d8f-148">**X AVOID** 使用`out`或`ref`参数。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-148">**X AVOID** using `out` or `ref` parameters.</span></span>  
  
 <span data-ttu-id="c8d8f-149">使用`out`或`ref`参数需要体验提供了指导，了解值类型和引用类型的不同之处，以及能处理具有多个返回值的方法。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-149">Using `out` or `ref` parameters requires experience with pointers, understanding how value types and reference types differ, and handling methods with multiple return values.</span></span> <span data-ttu-id="c8d8f-150">此外，之间的差异`out`和`ref`参数没有得到广泛了解。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-150">Also, the difference between `out` and `ref` parameters is not widely understood.</span></span> <span data-ttu-id="c8d8f-151">为一般用户设计的框架架构师不应指望用户掌握了`out`或`ref`参数。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-151">Framework architects designing for a general audience should not expect users to master working with `out` or `ref` parameters.</span></span>  
  
 <span data-ttu-id="c8d8f-152">**X DO NOT** 通过引用传递引用类型。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-152">**X DO NOT** pass reference types by reference.</span></span>  
  
 <span data-ttu-id="c8d8f-153">有一些有限的例外规则，例如可用于交换的引用的方法。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-153">There are some limited exceptions to the rule, such as a method that can be used to swap references.</span></span>  
  
### <a name="members-with-variable-number-of-parameters"></a><span data-ttu-id="c8d8f-154">具有可变数量的参数的成员</span><span class="sxs-lookup"><span data-stu-id="c8d8f-154">Members with Variable Number of Parameters</span></span>  
 <span data-ttu-id="c8d8f-155">通过提供的数组参数表示可以采用可变数量的参数的成员。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-155">Members that can take a variable number of arguments are expressed by providing an array parameter.</span></span> <span data-ttu-id="c8d8f-156">例如，<xref:System.String>提供了以下方法：</span><span class="sxs-lookup"><span data-stu-id="c8d8f-156">For example, <xref:System.String> provides the following method:</span></span>  
  
```  
public class String {  
    public static string Format(string format, object[] parameters);  
}  
```  
  
 <span data-ttu-id="c8d8f-157">然后，用户可以调用<xref:System.String.Format%2A?displayProperty=nameWithType>方法，按如下所示：</span><span class="sxs-lookup"><span data-stu-id="c8d8f-157">A user can then call the <xref:System.String.Format%2A?displayProperty=nameWithType> method, as follows:</span></span>  
  
 `String.Format("File {0} not found in {1}",new object[]{filename,directory});`  
  
 <span data-ttu-id="c8d8f-158">将 C# params 关键字添加到的数组参数更改为所谓的 params 数组参数的参数，并提供了创建临时数组的快捷方式。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-158">Adding the C# params keyword to an array parameter changes the parameter to a so-called params array parameter and provides a shortcut to creating a temporary array.</span></span>  
  
```  
public class String {  
    public static string Format(string format, params object[] parameters);  
}  
```  
  
 <span data-ttu-id="c8d8f-159">执行此操作允许用户通过将数组元素传递自变量列表中直接调用的方法。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-159">Doing this allows the user to call the method by passing the array elements directly in the argument list.</span></span>  
  
 `String.Format("File {0} not found in {1}",filename,directory);`  
  
 <span data-ttu-id="c8d8f-160">请注意 params 关键字，可以添加仅对在参数列表中的最后一个参数。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-160">Note that the params keyword can be added only to the last parameter in the parameter list.</span></span>  
  
 <span data-ttu-id="c8d8f-161">**✓ CONSIDER** 将 params 关键字添加到数组参数中，如果希望最终用户能够将较少的元素的数组传递。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-161">**✓ CONSIDER** adding the params keyword to array parameters if you expect the end users to pass arrays with a small number of elements.</span></span> <span data-ttu-id="c8d8f-162">如果希望，大量元素将传递在常见方案，用户可能不会传递这些元素内联不管怎样，并因此 params 关键字不必要。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-162">If it’s expected that lots of elements will be passed in common scenarios, users will probably not pass these elements inline anyway, and so the params keyword is not necessary.</span></span>  
  
 <span data-ttu-id="c8d8f-163">**X AVOID** 使用 params 数组，如果调用方将几乎始终输入已具有数组中。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-163">**X AVOID** using params arrays if the caller would almost always have the input already in an array.</span></span>  
  
 <span data-ttu-id="c8d8f-164">例如，几乎不会将单个字节表示通过调用通过字节数组参数的成员。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-164">For example, members with byte array parameters would almost never be called by passing individual bytes.</span></span> <span data-ttu-id="c8d8f-165">出于此原因，.NET Framework 中的字节数组参数不使用 params 关键字。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-165">For this reason, byte array parameters in the .NET Framework do not use the params keyword.</span></span>  
  
 <span data-ttu-id="c8d8f-166">**X DO NOT** 使用 params 数组，如果采用 params 数组参数的成员来修改数组。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-166">**X DO NOT** use params arrays if the array is modified by the member taking the params array parameter.</span></span>  
  
 <span data-ttu-id="c8d8f-167">原因在于，许多编译器将对成员实参转换到调用站点上的临时数组，该数组可能为临时对象，并因此对数组进行任何修改都将丢失。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-167">Because of the fact that many compilers turn the arguments to the member into a temporary array at the call site, the array might be a temporary object, and therefore any modifications to the array will be lost.</span></span>  
  
 <span data-ttu-id="c8d8f-168">**✓ CONSIDER** 使用在简单的重载中，params 关键字，即使更复杂的重载不能使用它。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-168">**✓ CONSIDER** using the params keyword in a simple overload, even if a more complex overload could not use it.</span></span>  
  
 <span data-ttu-id="c8d8f-169">问问自己，是否用户将具有参数数组中某一重载，即使它不是在所有重载值。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-169">Ask yourself if users would value having the params array in one overload even if it wasn’t in all overloads.</span></span>  
  
 <span data-ttu-id="c8d8f-170">**✓ DO** 尝试顺序参数，以使其可以使用 params 关键字。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-170">**✓ DO** try to order parameters to make it possible to use the params keyword.</span></span>  
  
 <span data-ttu-id="c8d8f-171">**✓ CONSIDER** 使用少量的极性能敏感的 Api 中的自变量调用提供特殊的重载和代码路径。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-171">**✓ CONSIDER** providing special overloads and code paths for calls with a small number of arguments in extremely performance-sensitive APIs.</span></span>  
  
 <span data-ttu-id="c8d8f-172">这样可以避免使用少量的参数调用 API 时创建的数组对象。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-172">This makes it possible to avoid creating array objects when the API is called with a small number of arguments.</span></span> <span data-ttu-id="c8d8f-173">通过采用数组参数的单数形式，并添加数字后缀构成的参数的名称。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-173">Form the names of the parameters by taking a singular form of the array parameter and adding a numeric suffix.</span></span>  
  
 <span data-ttu-id="c8d8f-174">只有如果您将特殊处理的完整的代码路径，而不仅仅是创建一个数组，并调用更多常规方法的保护时，才应该这样做。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-174">You should only do this if you are going to special-case the entire code path, not just create an array and call the more general method.</span></span>  
  
 <span data-ttu-id="c8d8f-175">**✓ DO** 请注意该 null 可以作为参数数组自变量传递。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-175">**✓ DO** be aware that null could be passed as a params array argument.</span></span>  
  
 <span data-ttu-id="c8d8f-176">您应验证数组不处理前为 null。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-176">You should validate that the array is not null before processing.</span></span>  
  
 <span data-ttu-id="c8d8f-177">**X DO NOT** 使用`varargs`方法，也称为旁边的省略号。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-177">**X DO NOT** use the `varargs` methods, otherwise known as the ellipsis.</span></span>  
  
 <span data-ttu-id="c8d8f-178">某些 CLR 语言，例如，c + +，支持替代约定，以便传递变量参数列表调用`varargs`方法。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-178">Some CLR languages, such as C++, support an alternative convention for passing variable parameter lists called `varargs` methods.</span></span> <span data-ttu-id="c8d8f-179">约定不应在框架中，因为它不符合 CLS。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-179">The convention should not be used in frameworks, because it is not CLS compliant.</span></span>  
  
### <a name="pointer-parameters"></a><span data-ttu-id="c8d8f-180">指针参数</span><span class="sxs-lookup"><span data-stu-id="c8d8f-180">Pointer Parameters</span></span>  
 <span data-ttu-id="c8d8f-181">一般情况下，指针不应出现在一个设计良好的托管的代码框架的公共图面区域。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-181">In general, pointers should not appear in the public surface area of a well-designed managed code framework.</span></span> <span data-ttu-id="c8d8f-182">大多数情况下，应封装的指针。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-182">Most of the time, pointers should be encapsulated.</span></span> <span data-ttu-id="c8d8f-183">但是，在某些情况下指针所需的互操作性方面的考虑，并且在这种情况下使用指针适合。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-183">However, in some cases pointers are required for interoperability reasons, and using pointers in such cases is appropriate.</span></span>  
  
 <span data-ttu-id="c8d8f-184">**✓ DO** 为采用指针自变量，任何成员提供一种替代方法，因为不符合 cls 的指针。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-184">**✓ DO** provide an alternative for any member that takes a pointer argument, because pointers are not CLS-compliant.</span></span>  
  
 <span data-ttu-id="c8d8f-185">**X AVOID** 执行检查的指针自变量的高开销的参数。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-185">**X AVOID** doing expensive argument checking of pointer arguments.</span></span>  
  
 <span data-ttu-id="c8d8f-186">**✓ DO** 设计具有使用指针的成员时遵循指针相关的常见约定。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-186">**✓ DO** follow common pointer-related conventions when designing members with pointers.</span></span>  
  
 <span data-ttu-id="c8d8f-187">例如，没有必要将传递的起始索引，因为简单指针算法可用于实现相同的结果。</span><span class="sxs-lookup"><span data-stu-id="c8d8f-187">For example, there is no need to pass the start index, because simple pointer arithmetic can be used to accomplish the same result.</span></span>  
  
 <span data-ttu-id="c8d8f-188">*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="c8d8f-188">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="c8d8f-189">*经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*</span><span class="sxs-lookup"><span data-stu-id="c8d8f-189">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8d8f-190">请参阅</span><span class="sxs-lookup"><span data-stu-id="c8d8f-190">See also</span></span>

- [<span data-ttu-id="c8d8f-191">成员设计准则</span><span class="sxs-lookup"><span data-stu-id="c8d8f-191">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
- [<span data-ttu-id="c8d8f-192">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="c8d8f-192">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
