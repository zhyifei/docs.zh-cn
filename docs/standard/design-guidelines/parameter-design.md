---
title: "参数设计"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- member design guidelines [.NET Framework], parameters
- members [.NET Framework], parameters
- names [.NET Framework], parameters
- parameters, design guidelines
- reserved parameters
ms.assetid: 3f33bf46-4a7b-43b3-bb78-1ffebe0dcfa6
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7d49c4263517830f46b1416684c7d9b874cda4db
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="parameter-design"></a><span data-ttu-id="fca9e-102">参数设计</span><span class="sxs-lookup"><span data-stu-id="fca9e-102">Parameter Design</span></span>
<span data-ttu-id="fca9e-103">本部分参数的设计方案，包括有关检查的自变量的指南的各节提供全面的指南。</span><span class="sxs-lookup"><span data-stu-id="fca9e-103">This section provides broad guidelines on parameter design, including sections with guidelines for checking arguments.</span></span> <span data-ttu-id="fca9e-104">此外，你应参考中所述的指导原则[命名参数](../../../docs/standard/design-guidelines/naming-parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="fca9e-104">In addition, you should refer to the guidelines described in [Naming Parameters](../../../docs/standard/design-guidelines/naming-parameters.md).</span></span>  
  
 <span data-ttu-id="fca9e-105">**✓ 执行**使用至少派生的参数提供的类型的成员所需的功能。</span><span class="sxs-lookup"><span data-stu-id="fca9e-105">**✓ DO** use the least derived parameter type that provides the functionality required by the member.</span></span>  
  
 <span data-ttu-id="fca9e-106">例如，假设你想要设计枚举集合，并输出到控制台的每个项的方法。</span><span class="sxs-lookup"><span data-stu-id="fca9e-106">For example, suppose you want to design a method that enumerates a collection and prints each item to the console.</span></span> <span data-ttu-id="fca9e-107">此类方法应接受<xref:System.Collections.IEnumerable>作为参数，不<xref:System.Collections.ArrayList>或<xref:System.Collections.IList>，例如。</span><span class="sxs-lookup"><span data-stu-id="fca9e-107">Such a method should take <xref:System.Collections.IEnumerable> as the parameter, not <xref:System.Collections.ArrayList> or <xref:System.Collections.IList>, for example.</span></span>  
  
 <span data-ttu-id="fca9e-108">**X 不**使用保留的参数。</span><span class="sxs-lookup"><span data-stu-id="fca9e-108">**X DO NOT** use reserved parameters.</span></span>  
  
 <span data-ttu-id="fca9e-109">如果在将来某个版本中需要更多输入到成员，则可以添加的新重载。</span><span class="sxs-lookup"><span data-stu-id="fca9e-109">If more input to a member is needed in some future version, a new overload can be added.</span></span>  
  
 <span data-ttu-id="fca9e-110">**X 不**具有公共公开指针、 数组的指针或作为参数的多维数组的方法。</span><span class="sxs-lookup"><span data-stu-id="fca9e-110">**X DO NOT** have publicly exposed methods that take pointers, arrays of pointers, or multidimensional arrays as parameters.</span></span>  
  
 <span data-ttu-id="fca9e-111">指针和多维数组是相对较难正确使用。</span><span class="sxs-lookup"><span data-stu-id="fca9e-111">Pointers and multidimensional arrays are relatively difficult to use properly.</span></span> <span data-ttu-id="fca9e-112">在几乎所有情况下，可以避免这些类型作为参数而重新设计 Api。</span><span class="sxs-lookup"><span data-stu-id="fca9e-112">In almost all cases, APIs can be redesigned to avoid taking these types as parameters.</span></span>  
  
 <span data-ttu-id="fca9e-113">**✓ 执行**放置所有`out`后所有按值的参数和`ref`参数 （不包括参数数组），即使它会导致重载之间进行排序的参数中的不一致 (请参阅[成员重载](../../../docs/standard/design-guidelines/member-overloading.md))。</span><span class="sxs-lookup"><span data-stu-id="fca9e-113">**✓ DO** place all `out` parameters following all of the by-value and `ref` parameters (excluding parameter arrays), even if it results in an inconsistency in parameter ordering between overloads (see [Member Overloading](../../../docs/standard/design-guidelines/member-overloading.md)).</span></span>  
  
 <span data-ttu-id="fca9e-114">`out`参数可以被视为额外返回值，并对其进行分组在一起使方法签名易于理解。</span><span class="sxs-lookup"><span data-stu-id="fca9e-114">The `out` parameters can be seen as extra return values, and grouping them together makes the method signature easier to understand.</span></span>  
  
 <span data-ttu-id="fca9e-115">**✓ 执行**时重写成员命名参数或实现接口成员中保持一致。</span><span class="sxs-lookup"><span data-stu-id="fca9e-115">**✓ DO** be consistent in naming parameters when overriding members or implementing interface members.</span></span>  
  
 <span data-ttu-id="fca9e-116">这更好地进行通信的方法之间的关系。</span><span class="sxs-lookup"><span data-stu-id="fca9e-116">This better communicates the relationship between the methods.</span></span>  
  
### <a name="choosing-between-enum-and-boolean-parameters"></a><span data-ttu-id="fca9e-117">枚举和布尔参数之间进行选择</span><span class="sxs-lookup"><span data-stu-id="fca9e-117">Choosing Between Enum and Boolean Parameters</span></span>  
 <span data-ttu-id="fca9e-118">**✓ 执行**如果成员本来两个或多个布尔参数，请使用枚举。</span><span class="sxs-lookup"><span data-stu-id="fca9e-118">**✓ DO** use enums if a member would otherwise have two or more Boolean parameters.</span></span>  
  
 <span data-ttu-id="fca9e-119">**X 不**如果你不完全确定永远不会将两个以上值需要使用布尔值。</span><span class="sxs-lookup"><span data-stu-id="fca9e-119">**X DO NOT** use Booleans unless you are absolutely sure there will never be a need for more than two values.</span></span>  
  
 <span data-ttu-id="fca9e-120">枚举为你提供了一些空间来将来添加的值，但你应注意到的将值添加到枚举中所述的所有影响[枚举设计](../../../docs/standard/design-guidelines/enum.md)。</span><span class="sxs-lookup"><span data-stu-id="fca9e-120">Enums give you some room for future addition of values, but you should be aware of all the implications of adding values to enums, which are described in [Enum Design](../../../docs/standard/design-guidelines/enum.md).</span></span>  
  
 <span data-ttu-id="fca9e-121">**请考虑 ✓**布尔值用于构造函数参数是真正的两个状态的值，只需用来初始化布尔属性。</span><span class="sxs-lookup"><span data-stu-id="fca9e-121">**✓ CONSIDER** using Booleans for constructor parameters that are truly two-state values and are simply used to initialize Boolean properties.</span></span>  
  
### <a name="validating-arguments"></a><span data-ttu-id="fca9e-122">验证自变量</span><span class="sxs-lookup"><span data-stu-id="fca9e-122">Validating Arguments</span></span>  
 <span data-ttu-id="fca9e-123">**✓ 执行**验证自变量传递到公共、 受保护，或显式实现的成员。</span><span class="sxs-lookup"><span data-stu-id="fca9e-123">**✓ DO** validate arguments passed to public, protected, or explicitly implemented members.</span></span> <span data-ttu-id="fca9e-124">引发<xref:System.ArgumentException?displayProperty=nameWithType>，或它的某个子类，如果验证失败。</span><span class="sxs-lookup"><span data-stu-id="fca9e-124">Throw <xref:System.ArgumentException?displayProperty=nameWithType>, or one of its subclasses, if the validation fails.</span></span>  
  
 <span data-ttu-id="fca9e-125">请注意，实际验证不一定有发生在公共或受保护成员本身中。</span><span class="sxs-lookup"><span data-stu-id="fca9e-125">Note that the actual validation does not necessarily have to happen in the public or protected member itself.</span></span> <span data-ttu-id="fca9e-126">也有可能发生在某些私有或内部的例程中较低级别。</span><span class="sxs-lookup"><span data-stu-id="fca9e-126">It could happen at a lower level in some private or internal routine.</span></span> <span data-ttu-id="fca9e-127">主要目的是向最终用户公开的整个图面区域检查自变量。</span><span class="sxs-lookup"><span data-stu-id="fca9e-127">The main point is that the entire surface area that is exposed to the end users checks the arguments.</span></span>  
  
 <span data-ttu-id="fca9e-128">**✓ 执行**引发<xref:System.ArgumentNullException>如果传递 null 自变量，并将该成员不支持 null 参数。</span><span class="sxs-lookup"><span data-stu-id="fca9e-128">**✓ DO** throw <xref:System.ArgumentNullException> if a null argument is passed and the member does not support null arguments.</span></span>  
  
 <span data-ttu-id="fca9e-129">**✓ 执行**验证 enum 参数。</span><span class="sxs-lookup"><span data-stu-id="fca9e-129">**✓ DO** validate enum parameters.</span></span>  
  
 <span data-ttu-id="fca9e-130">不要假定枚举自变量将通过枚举定义的范围内。</span><span class="sxs-lookup"><span data-stu-id="fca9e-130">Do not assume enum arguments will be in the range defined by the enum.</span></span> <span data-ttu-id="fca9e-131">CLR 允许任何整数值转换为枚举值，即使值未定义的枚举中。</span><span class="sxs-lookup"><span data-stu-id="fca9e-131">The CLR allows casting any integer value into an enum value even if the value is not defined in the enum.</span></span>  
  
 <span data-ttu-id="fca9e-132">**X 不**使用<xref:System.Enum.IsDefined%2A?displayProperty=nameWithType>枚举范围检查。</span><span class="sxs-lookup"><span data-stu-id="fca9e-132">**X DO NOT** use <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> for enum range checks.</span></span>  
  
 <span data-ttu-id="fca9e-133">**✓ 执行**请注意，在经过验证后，可能已更改可变自变量。</span><span class="sxs-lookup"><span data-stu-id="fca9e-133">**✓ DO** be aware that mutable arguments might have changed after they were validated.</span></span>  
  
 <span data-ttu-id="fca9e-134">如果该成员是敏感的安全，建议您的制作的副本然后验证并处理自变量。</span><span class="sxs-lookup"><span data-stu-id="fca9e-134">If the member is security sensitive, you are encouraged to make a copy and then validate and process the argument.</span></span>  
  
### <a name="parameter-passing"></a><span data-ttu-id="fca9e-135">参数传递</span><span class="sxs-lookup"><span data-stu-id="fca9e-135">Parameter Passing</span></span>  
 <span data-ttu-id="fca9e-136">从框架设计器的角度来看，有三个主要组的参数： 按值参数，`ref`参数，和`out`参数。</span><span class="sxs-lookup"><span data-stu-id="fca9e-136">From the perspective of a framework designer, there are three main groups of parameters: by-value parameters, `ref` parameters, and `out` parameters.</span></span>  
  
 <span data-ttu-id="fca9e-137">当通过按值参数传递的参数，则成员会收到一份中传递的实际自变量。</span><span class="sxs-lookup"><span data-stu-id="fca9e-137">When an argument is passed through a by-value parameter, the member receives a copy of the actual argument passed in.</span></span> <span data-ttu-id="fca9e-138">如果参数为值类型，自变量的副本将放在堆栈上。</span><span class="sxs-lookup"><span data-stu-id="fca9e-138">If the argument is a value type, a copy of the argument is put on the stack.</span></span> <span data-ttu-id="fca9e-139">如果参数为引用类型，引用的副本将放在堆栈上。</span><span class="sxs-lookup"><span data-stu-id="fca9e-139">If the argument is a reference type, a copy of the reference is put on the stack.</span></span> <span data-ttu-id="fca9e-140">最常用的 CLR 语言，例如 C#、 VB.NET 和 c + +，默认为按值传递参数。</span><span class="sxs-lookup"><span data-stu-id="fca9e-140">Most popular CLR languages, such as C#, VB.NET, and C++, default to passing parameters by value.</span></span>  
  
 <span data-ttu-id="fca9e-141">当自变量传递通过`ref`参数，该成员会接收对中传递的实际自变量的引用。</span><span class="sxs-lookup"><span data-stu-id="fca9e-141">When an argument is passed through a `ref` parameter, the member receives a reference to the actual argument passed in.</span></span> <span data-ttu-id="fca9e-142">如果参数为值类型，对自变量的引用将存储在堆栈上。</span><span class="sxs-lookup"><span data-stu-id="fca9e-142">If the argument is a value type, a reference to the argument is put on the stack.</span></span> <span data-ttu-id="fca9e-143">如果参数为引用类型，对引用的引用将存储在堆栈上。</span><span class="sxs-lookup"><span data-stu-id="fca9e-143">If the argument is a reference type, a reference to the reference is put on the stack.</span></span> <span data-ttu-id="fca9e-144">`Ref`参数可以用于允许要修改由调用方传递自变量的成员。</span><span class="sxs-lookup"><span data-stu-id="fca9e-144">`Ref` parameters can be used to allow the member to modify arguments passed by the caller.</span></span>  
  
 <span data-ttu-id="fca9e-145">`Out`参数是类似于`ref`参数，其中有一些小的差异。</span><span class="sxs-lookup"><span data-stu-id="fca9e-145">`Out` parameters are similar to `ref` parameters, with some small differences.</span></span> <span data-ttu-id="fca9e-146">参数最初被认为是未分配的它还未分配的一些值无法读取成员正文中。</span><span class="sxs-lookup"><span data-stu-id="fca9e-146">The parameter is initially considered unassigned and cannot be read in the member body before it is assigned some value.</span></span> <span data-ttu-id="fca9e-147">此外，该参数必须之前的成员返回分配的一些值。</span><span class="sxs-lookup"><span data-stu-id="fca9e-147">Also, the parameter has to be assigned some value before the member returns.</span></span>  
  
 <span data-ttu-id="fca9e-148">**请避免 x**使用`out`或`ref`参数。</span><span class="sxs-lookup"><span data-stu-id="fca9e-148">**X AVOID** using `out` or `ref` parameters.</span></span>  
  
 <span data-ttu-id="fca9e-149">使用`out`或`ref`参数要求具有使用指针，了解值类型和引用类型的不同之处，以及能处理具有多个返回值的方法的经验。</span><span class="sxs-lookup"><span data-stu-id="fca9e-149">Using `out` or `ref` parameters requires experience with pointers, understanding how value types and reference types differ, and handling methods with multiple return values.</span></span> <span data-ttu-id="fca9e-150">此外，之间的差异`out`和`ref`参数没有得到广泛了解。</span><span class="sxs-lookup"><span data-stu-id="fca9e-150">Also, the difference between `out` and `ref` parameters is not widely understood.</span></span> <span data-ttu-id="fca9e-151">Framework 架构师设计为一般不应指望用户能熟练运用`out`或`ref`参数。</span><span class="sxs-lookup"><span data-stu-id="fca9e-151">Framework architects designing for a general audience should not expect users to master working with `out` or `ref` parameters.</span></span>  
  
 <span data-ttu-id="fca9e-152">**X 不**通过引用传递引用类型。</span><span class="sxs-lookup"><span data-stu-id="fca9e-152">**X DO NOT** pass reference types by reference.</span></span>  
  
 <span data-ttu-id="fca9e-153">有一些有限的例外规则，如用于交换引用的方法。</span><span class="sxs-lookup"><span data-stu-id="fca9e-153">There are some limited exceptions to the rule, such as a method that can be used to swap references.</span></span>  
  
### <a name="members-with-variable-number-of-parameters"></a><span data-ttu-id="fca9e-154">具有可变数量的参数的成员</span><span class="sxs-lookup"><span data-stu-id="fca9e-154">Members with Variable Number of Parameters</span></span>  
 <span data-ttu-id="fca9e-155">可以采用数量可变的自变量的成员所用提供的数组参数。</span><span class="sxs-lookup"><span data-stu-id="fca9e-155">Members that can take a variable number of arguments are expressed by providing an array parameter.</span></span> <span data-ttu-id="fca9e-156">例如，<xref:System.String>提供以下方法：</span><span class="sxs-lookup"><span data-stu-id="fca9e-156">For example, <xref:System.String> provides the following method:</span></span>  
  
```  
public class String {  
    public static string Format(string format, object[] parameters);  
}  
```  
  
 <span data-ttu-id="fca9e-157">然后，用户可以调用<xref:System.String.Format%2A?displayProperty=nameWithType>方法，如下所示：</span><span class="sxs-lookup"><span data-stu-id="fca9e-157">A user can then call the <xref:System.String.Format%2A?displayProperty=nameWithType> method, as follows:</span></span>  
  
 `String.Format("File {0} not found in {1}",new object[]{filename,directory});`  
  
 <span data-ttu-id="fca9e-158">将 C# params 关键字添加到的数组参数更改为所谓的参数数组参数的参数，并提供创建临时数组的快捷方式。</span><span class="sxs-lookup"><span data-stu-id="fca9e-158">Adding the C# params keyword to an array parameter changes the parameter to a so-called params array parameter and provides a shortcut to creating a temporary array.</span></span>  
  
```  
public class String {  
    public static string Format(string format, params object[] parameters);  
}  
```  
  
 <span data-ttu-id="fca9e-159">执行此操作允许用户通过将数组元素传递自变量列表中的直接调用该方法。</span><span class="sxs-lookup"><span data-stu-id="fca9e-159">Doing this allows the user to call the method by passing the array elements directly in the argument list.</span></span>  
  
 `String.Format("File {0} not found in {1}",filename,directory);`  
  
 <span data-ttu-id="fca9e-160">请注意，可以仅对在参数列表中的最后一个参数添加 params 关键字。</span><span class="sxs-lookup"><span data-stu-id="fca9e-160">Note that the params keyword can be added only to the last parameter in the parameter list.</span></span>  
  
 <span data-ttu-id="fca9e-161">**请考虑 ✓**将 params 关键字添加到数组参数中，如果希望最终用户能够将较少的元素的数组传递。</span><span class="sxs-lookup"><span data-stu-id="fca9e-161">**✓ CONSIDER** adding the params keyword to array parameters if you expect the end users to pass arrays with a small number of elements.</span></span> <span data-ttu-id="fca9e-162">如果预期，大量元素将传递在常见方案，用户可能不会传递这些元素内联，并因此 params 关键字是不必要。</span><span class="sxs-lookup"><span data-stu-id="fca9e-162">If it’s expected that lots of elements will be passed in common scenarios, users will probably not pass these elements inline anyway, and so the params keyword is not necessary.</span></span>  
  
 <span data-ttu-id="fca9e-163">**请避免 x**使用 params 数组，如果调用方将几乎始终输入已具有数组中。</span><span class="sxs-lookup"><span data-stu-id="fca9e-163">**X AVOID** using params arrays if the caller would almost always have the input already in an array.</span></span>  
  
 <span data-ttu-id="fca9e-164">例如，将几乎从未调用具有字节数组参数的成员，通过传递单个字节。</span><span class="sxs-lookup"><span data-stu-id="fca9e-164">For example, members with byte array parameters would almost never be called by passing individual bytes.</span></span> <span data-ttu-id="fca9e-165">出于此原因，.NET Framework 中的字节数组参数不使用 params 关键字。</span><span class="sxs-lookup"><span data-stu-id="fca9e-165">For this reason, byte array parameters in the .NET Framework do not use the params keyword.</span></span>  
  
 <span data-ttu-id="fca9e-166">**X 不**使用 params 数组，如果采用 params 数组参数的成员来修改数组。</span><span class="sxs-lookup"><span data-stu-id="fca9e-166">**X DO NOT** use params arrays if the array is modified by the member taking the params array parameter.</span></span>  
  
 <span data-ttu-id="fca9e-167">原因在于，许多编译器将该成员的自变量转换为调用站点的临时数组，数组可能是临时对象，并因此对数组进行任何修改都将丢失。</span><span class="sxs-lookup"><span data-stu-id="fca9e-167">Because of the fact that many compilers turn the arguments to the member into a temporary array at the call site, the array might be a temporary object, and therefore any modifications to the array will be lost.</span></span>  
  
 <span data-ttu-id="fca9e-168">**请考虑 ✓**使用在简单的重载中，params 关键字，即使更复杂的重载不能使用它。</span><span class="sxs-lookup"><span data-stu-id="fca9e-168">**✓ CONSIDER** using the params keyword in a simple overload, even if a more complex overload could not use it.</span></span>  
  
 <span data-ttu-id="fca9e-169">问问自己，是否用户将采用一个重载的参数数组，即使它不是所有重载中的值。</span><span class="sxs-lookup"><span data-stu-id="fca9e-169">Ask yourself if users would value having the params array in one overload even if it wasn’t in all overloads.</span></span>  
  
 <span data-ttu-id="fca9e-170">**✓ 执行**尝试顺序参数，以使其可以使用 params 关键字。</span><span class="sxs-lookup"><span data-stu-id="fca9e-170">**✓ DO** try to order parameters to make it possible to use the params keyword.</span></span>  
  
 <span data-ttu-id="fca9e-171">**请考虑 ✓**使用少量的极性能敏感的 Api 中的自变量调用提供特殊的重载和代码路径。</span><span class="sxs-lookup"><span data-stu-id="fca9e-171">**✓ CONSIDER** providing special overloads and code paths for calls with a small number of arguments in extremely performance-sensitive APIs.</span></span>  
  
 <span data-ttu-id="fca9e-172">这使得可能以避免使用少量的自变量调用 API 时创建数组对象。</span><span class="sxs-lookup"><span data-stu-id="fca9e-172">This makes it possible to avoid creating array objects when the API is called with a small number of arguments.</span></span> <span data-ttu-id="fca9e-173">通过采用数组参数的单数形式，并添加数字后缀而形成的参数的名称。</span><span class="sxs-lookup"><span data-stu-id="fca9e-173">Form the names of the parameters by taking a singular form of the array parameter and adding a numeric suffix.</span></span>  
  
 <span data-ttu-id="fca9e-174">只有如果你要到特殊的用例的整个代码路径，而不仅仅是创建一个数组，然后调用更多常规方法的保护时，才应这样做。</span><span class="sxs-lookup"><span data-stu-id="fca9e-174">You should only do this if you are going to special-case the entire code path, not just create an array and call the more general method.</span></span>  
  
 <span data-ttu-id="fca9e-175">**✓ 执行**请注意该 null 可以作为参数数组自变量传递。</span><span class="sxs-lookup"><span data-stu-id="fca9e-175">**✓ DO** be aware that null could be passed as a params array argument.</span></span>  
  
 <span data-ttu-id="fca9e-176">你应验证数组不在处理之前为 null。</span><span class="sxs-lookup"><span data-stu-id="fca9e-176">You should validate that the array is not null before processing.</span></span>  
  
 <span data-ttu-id="fca9e-177">**X 不**使用`varargs`方法，也称为旁边的省略号。</span><span class="sxs-lookup"><span data-stu-id="fca9e-177">**X DO NOT** use the `varargs` methods, otherwise known as the ellipsis.</span></span>  
  
 <span data-ttu-id="fca9e-178">某些 CLR 语言，如 c + +，支持备用约定传递变量参数列表调用`varargs`方法。</span><span class="sxs-lookup"><span data-stu-id="fca9e-178">Some CLR languages, such as C++, support an alternative convention for passing variable parameter lists called `varargs` methods.</span></span> <span data-ttu-id="fca9e-179">应在框架，使用约定，因为它不符合 CLS。</span><span class="sxs-lookup"><span data-stu-id="fca9e-179">The convention should not be used in frameworks, because it is not CLS compliant.</span></span>  
  
### <a name="pointer-parameters"></a><span data-ttu-id="fca9e-180">指针参数</span><span class="sxs-lookup"><span data-stu-id="fca9e-180">Pointer Parameters</span></span>  
 <span data-ttu-id="fca9e-181">一般情况下，指针不应出现在设计良好的托管的代码 framework 的公共外围应用。</span><span class="sxs-lookup"><span data-stu-id="fca9e-181">In general, pointers should not appear in the public surface area of a well-designed managed code framework.</span></span> <span data-ttu-id="fca9e-182">大多数情况下，应封装指针。</span><span class="sxs-lookup"><span data-stu-id="fca9e-182">Most of the time, pointers should be encapsulated.</span></span> <span data-ttu-id="fca9e-183">但是，在某些情况下指针所需的互操作性原因，并且在这种情况下使用指针适合。</span><span class="sxs-lookup"><span data-stu-id="fca9e-183">However, in some cases pointers are required for interoperability reasons, and using pointers in such cases is appropriate.</span></span>  
  
 <span data-ttu-id="fca9e-184">**✓ 执行**为采用指针自变量，任何成员提供一种替代方法，因为不符合 cls 的指针。</span><span class="sxs-lookup"><span data-stu-id="fca9e-184">**✓ DO** provide an alternative for any member that takes a pointer argument, because pointers are not CLS-compliant.</span></span>  
  
 <span data-ttu-id="fca9e-185">**请避免 x**执行检查的指针自变量的高开销的参数。</span><span class="sxs-lookup"><span data-stu-id="fca9e-185">**X AVOID** doing expensive argument checking of pointer arguments.</span></span>  
  
 <span data-ttu-id="fca9e-186">**✓ 执行**设计具有使用指针的成员时遵循指针相关的常见约定。</span><span class="sxs-lookup"><span data-stu-id="fca9e-186">**✓ DO** follow common pointer-related conventions when designing members with pointers.</span></span>  
  
 <span data-ttu-id="fca9e-187">例如，没有无需传递的起始索引，因为可以使用简单指针算法来达到相同的结果。</span><span class="sxs-lookup"><span data-stu-id="fca9e-187">For example, there is no need to pass the start index, because simple pointer arithmetic can be used to accomplish the same result.</span></span>  
  
 <span data-ttu-id="fca9e-188">*部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="fca9e-188">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="fca9e-189">*通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*</span><span class="sxs-lookup"><span data-stu-id="fca9e-189">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fca9e-190">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fca9e-190">See Also</span></span>  
 [<span data-ttu-id="fca9e-191">成员设计准则</span><span class="sxs-lookup"><span data-stu-id="fca9e-191">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
 [<span data-ttu-id="fca9e-192">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="fca9e-192">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
