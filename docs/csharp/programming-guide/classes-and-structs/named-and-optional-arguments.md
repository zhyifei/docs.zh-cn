---
title: 命名参数和可选参数 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- namedParameter_CSharpKeyword
- cs_namedParameter
helpviewer_keywords:
- parameters [C#], named
- named arguments [C#]
- arguments [C#], named
- optional arguments [C#]
- arguments [C#], optional
- parameters [C#], optional
- named and optional arguments [C#]
ms.assetid: 839c960c-c2dc-4d05-af4d-ca5428e54008
ms.openlocfilehash: df590cf9d18b6de81caccfb77e544451da9ee0df
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2018
ms.locfileid: "53244903"
---
# <a name="named-and-optional-arguments-c-programming-guide"></a><span data-ttu-id="0ea7f-102">命名实参和可选实参（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="0ea7f-102">Named and Optional Arguments (C# Programming Guide)</span></span>
[!INCLUDE[csharp_dev10_long](~/includes/csharp-dev10-long-md.md)] <span data-ttu-id="0ea7f-103">介绍命名实参和可选实参。</span><span class="sxs-lookup"><span data-stu-id="0ea7f-103">introduces named and optional arguments.</span></span> <span data-ttu-id="0ea7f-104">通过*命名实参*，你可以为特定形参指定实参，方法是将实参与该形参的名称关联，而不是与形参在形参列表中的位置关联。</span><span class="sxs-lookup"><span data-stu-id="0ea7f-104">*Named arguments* enable you to specify an argument for a particular parameter by associating the argument with the parameter's name rather than with the parameter's position in the parameter list.</span></span> <span data-ttu-id="0ea7f-105">通过*可选参数*，你可以为某些形参省略实参。</span><span class="sxs-lookup"><span data-stu-id="0ea7f-105">*Optional arguments* enable you to omit arguments for some parameters.</span></span> <span data-ttu-id="0ea7f-106">这两种技术都可与方法、索引器、构造函数和委托一起使用。</span><span class="sxs-lookup"><span data-stu-id="0ea7f-106">Both techniques can be used with methods, indexers, constructors, and delegates.</span></span>  
  
 <span data-ttu-id="0ea7f-107">使用命名参数和可选参数时，将按实参出现在实参列表（而不是形参列表）中的顺序计算这些实参。</span><span class="sxs-lookup"><span data-stu-id="0ea7f-107">When you use named and optional arguments, the arguments are evaluated in the order in which they appear in the argument list, not the parameter list.</span></span>  
  
 <span data-ttu-id="0ea7f-108">命名形参和可选形参一起使用时，你可以只为可选形参列表中的少数形参提供实参。</span><span class="sxs-lookup"><span data-stu-id="0ea7f-108">Named and optional parameters, when used together, enable you to supply arguments for only a few parameters from a list of optional parameters.</span></span> <span data-ttu-id="0ea7f-109">此功能极大地方便了对 COM 接口（例如 Microsoft Office 自动化 API）的调用。</span><span class="sxs-lookup"><span data-stu-id="0ea7f-109">This capability greatly facilitates calls to COM interfaces such as the Microsoft Office Automation APIs.</span></span>  
  
## <a name="named-arguments"></a><span data-ttu-id="0ea7f-110">命名实参</span><span class="sxs-lookup"><span data-stu-id="0ea7f-110">Named Arguments</span></span>  
 <span data-ttu-id="0ea7f-111">有了命名实参，你将不再需要记住或查找形参在所调用方法的形参列表中的顺序。</span><span class="sxs-lookup"><span data-stu-id="0ea7f-111">Named arguments free you from the need to remember or to look up the order of parameters in the parameter lists of called methods.</span></span> <span data-ttu-id="0ea7f-112">每个实参的形参都可按形参名称进行指定。</span><span class="sxs-lookup"><span data-stu-id="0ea7f-112">The parameter for each argument can be specified by parameter name.</span></span> <span data-ttu-id="0ea7f-113">例如，通过以函数定义的顺序按位置发送实参，可以采用标准方式调用打印订单详细信息（例如卖家姓名、订单号和产品名称）的函数。</span><span class="sxs-lookup"><span data-stu-id="0ea7f-113">For example, a function that prints order details (such as, seller name, order number & product name) can be called in the standard way by sending arguments by position, in the order defined by the function.</span></span>
  
 `PrintOrderDetails("Gift Shop", 31, "Red Mug");`
  
 <span data-ttu-id="0ea7f-114">如果不记得形参的顺序，但却知道其名称，则可以按任意顺序发送实参。</span><span class="sxs-lookup"><span data-stu-id="0ea7f-114">If you do not remember the order of the parameters but know their names, you can send the arguments in any order.</span></span>  
  
 `PrintOrderDetails(orderNum: 31, productName: "Red Mug", sellerName: "Gift Shop");`
  
 `PrintOrderDetails(productName: "Red Mug", sellerName: "Gift Shop", orderNum: 31);`
  
 <span data-ttu-id="0ea7f-115">命名实参还可以标识每个实参所表示的含义，从而改进代码的可读性。</span><span class="sxs-lookup"><span data-stu-id="0ea7f-115">Named arguments also improve the readability of your code by identifying what each argument represents.</span></span> <span data-ttu-id="0ea7f-116">在下面的示例方法中，`sellerName` 不得为 NULL 或空白符。</span><span class="sxs-lookup"><span data-stu-id="0ea7f-116">In the example method below, the `sellerName` cannot be null or white space.</span></span> <span data-ttu-id="0ea7f-117">由于 `sellerName` 和 `productName` 都是字符串类型，所以使用命名实参而不是按位置发送实参是有意义的，可以区分这两种类型并减少代码阅读者的困惑。</span><span class="sxs-lookup"><span data-stu-id="0ea7f-117">As both `sellerName` and `productName` are string types, instead of sending arguments by position, it makes sense to use named arguments to disambiguate the two and reduce confusion for anyone reading the code.</span></span>
  
 <span data-ttu-id="0ea7f-118">当命名实参与位置实参一起使用时，只要</span><span class="sxs-lookup"><span data-stu-id="0ea7f-118">Named arguments, when used with positional arguments, are valid as long as</span></span> 

- <span data-ttu-id="0ea7f-119">没有后接任何位置实参或</span><span class="sxs-lookup"><span data-stu-id="0ea7f-119">they're not followed by any positional arguments, or</span></span>

 `PrintOrderDetails("Gift Shop", 31, productName: "Red Mug");`

- <span data-ttu-id="0ea7f-120">以 C# 7.2 开头，则它们就有效并用在正确位置。</span><span class="sxs-lookup"><span data-stu-id="0ea7f-120">_starting with C# 7.2_, they're used in the correct position.</span></span> <span data-ttu-id="0ea7f-121">在以下示例中，形参 `orderNum` 位于正确的位置，但未显式命名。</span><span class="sxs-lookup"><span data-stu-id="0ea7f-121">In the example below, the parameter `orderNum` is in the correct position but isn't explicitly named.</span></span>

 `PrintOrderDetails(sellerName: "Gift Shop", 31, productName: "Red Mug");`
  
 <span data-ttu-id="0ea7f-122">但是，如果其后接位置实参，则无序命名实参无效。</span><span class="sxs-lookup"><span data-stu-id="0ea7f-122">However, out-of-order named arguments are invalid if they're followed by positional arguments.</span></span>

 ```csharp
 // This generates CS1738: Named argument specifications must appear after all fixed arguments have been specified.
 PrintOrderDetails(productName: "Red Mug", 31, "Gift Shop");
 ```
  
## <a name="example"></a><span data-ttu-id="0ea7f-123">示例</span><span class="sxs-lookup"><span data-stu-id="0ea7f-123">Example</span></span>  
 <span data-ttu-id="0ea7f-124">以下代码执行本节以及某些其他节中的示例。</span><span class="sxs-lookup"><span data-stu-id="0ea7f-124">The following code implements the examples from this section along with some additional ones.</span></span>  
  
 [!code-csharp[csProgGuideNamedAndOptional#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_1.cs)]  
  
## <a name="optional-arguments"></a><span data-ttu-id="0ea7f-125">可选实参</span><span class="sxs-lookup"><span data-stu-id="0ea7f-125">Optional Arguments</span></span>  
 <span data-ttu-id="0ea7f-126">方法、构造函数、索引器或委托的定义可以指定其形参为必需还是可选。</span><span class="sxs-lookup"><span data-stu-id="0ea7f-126">The definition of a method, constructor, indexer, or delegate can specify that its parameters are required or that they are optional.</span></span> <span data-ttu-id="0ea7f-127">任何调用都必须为所有必需的形参提供实参，但可以为可选的形参省略实参。</span><span class="sxs-lookup"><span data-stu-id="0ea7f-127">Any call must provide arguments for all required parameters, but can omit arguments for optional parameters.</span></span>  
  
 <span data-ttu-id="0ea7f-128">每个可选形参都有一个默认值作为其定义的一部分。</span><span class="sxs-lookup"><span data-stu-id="0ea7f-128">Each optional parameter has a default value as part of its definition.</span></span> <span data-ttu-id="0ea7f-129">如果没有为该形参发送实参，则使用默认值。</span><span class="sxs-lookup"><span data-stu-id="0ea7f-129">If no argument is sent for that parameter, the default value is used.</span></span> <span data-ttu-id="0ea7f-130">默认值必须是以下类型的表达式之一：</span><span class="sxs-lookup"><span data-stu-id="0ea7f-130">A default value must be one of the following types of expressions:</span></span>  
  
-   <span data-ttu-id="0ea7f-131">常量表达式；</span><span class="sxs-lookup"><span data-stu-id="0ea7f-131">a constant expression;</span></span>  
  
-   <span data-ttu-id="0ea7f-132">`new ValType()` 形式的表达式，其中 `ValType` 是值类型，例如 [enum](../../../csharp/language-reference/keywords/enum.md) 或 [struct](../../../csharp/programming-guide/classes-and-structs/structs.md)；</span><span class="sxs-lookup"><span data-stu-id="0ea7f-132">an expression of the form `new ValType()`, where `ValType` is a value type, such as an [enum](../../../csharp/language-reference/keywords/enum.md) or a [struct](../../../csharp/programming-guide/classes-and-structs/structs.md);</span></span>  
  
-   <span data-ttu-id="0ea7f-133">[default(ValType)](../../../csharp/programming-guide/statements-expressions-operators/default-value-expressions.md) 形式的表达式，其中 `ValType` 是值类型。</span><span class="sxs-lookup"><span data-stu-id="0ea7f-133">an expression of the form [default(ValType)](../../../csharp/programming-guide/statements-expressions-operators/default-value-expressions.md),  where `ValType` is a value type.</span></span>  
  
 <span data-ttu-id="0ea7f-134">可选参数定义于参数列表的末尾和必需参数之后。</span><span class="sxs-lookup"><span data-stu-id="0ea7f-134">Optional parameters are defined at the end of the parameter list, after any required parameters.</span></span> <span data-ttu-id="0ea7f-135">如果调用方为一系列可选形参中的任意一个形参提供了实参，则它必须为前面的所有可选形参提供实参。</span><span class="sxs-lookup"><span data-stu-id="0ea7f-135">If the caller provides an argument for any one of a succession of optional parameters, it must provide arguments for all preceding optional parameters.</span></span> <span data-ttu-id="0ea7f-136">实参列表中不支持使用逗号分隔的间隔。</span><span class="sxs-lookup"><span data-stu-id="0ea7f-136">Comma-separated gaps in the argument list are not supported.</span></span> <span data-ttu-id="0ea7f-137">例如，在以下代码中，使用一个必选形参和两个可选形参定义实例方法 `ExampleMethod`。</span><span class="sxs-lookup"><span data-stu-id="0ea7f-137">For example, in the following code, instance method `ExampleMethod` is defined with one required and two optional parameters.</span></span>  
  
 [!code-csharp[csProgGuideNamedAndOptional#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_2.cs)]  
  
 <span data-ttu-id="0ea7f-138">下面对 `ExampleMethod` 的调用会导致编译器错误，原因是为第三个形参而不是为第二个形参提供了实参。</span><span class="sxs-lookup"><span data-stu-id="0ea7f-138">The following call to `ExampleMethod` causes a compiler error, because an argument is provided for the third parameter but not for the second.</span></span>  
  
 `//anExample.ExampleMethod(3, ,4);`  
  
 <span data-ttu-id="0ea7f-139">但是，如果知道第三个形参的名称，则可以使用命名实参来完成此任务。</span><span class="sxs-lookup"><span data-stu-id="0ea7f-139">However, if you know the name of the third parameter, you can use a named argument to accomplish the task.</span></span>  
  
 `anExample.ExampleMethod(3, optionalint: 4);`  
  
 <span data-ttu-id="0ea7f-140">IntelliSense 使用括号表示可选形参，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="0ea7f-140">IntelliSense uses brackets to indicate optional parameters, as shown in the following illustration.</span></span>  
  
 <span data-ttu-id="0ea7f-141">![ExampleMethod 方法的 IntelliSense 快速信息。](../../../csharp/programming-guide/classes-and-structs/media/optional_parameters.png "Optional_Parameters")</span><span class="sxs-lookup"><span data-stu-id="0ea7f-141">![IntelliSense Quick Info for method ExampleMethod.](../../../csharp/programming-guide/classes-and-structs/media/optional_parameters.png "Optional_Parameters")</span></span>  
<span data-ttu-id="0ea7f-142">ExampleMethod 中的可选形参</span><span class="sxs-lookup"><span data-stu-id="0ea7f-142">Optional parameters in ExampleMethod</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0ea7f-143">此外，还可通过使用 .NET <xref:System.Runtime.InteropServices.OptionalAttribute> 类声明可选参数。</span><span class="sxs-lookup"><span data-stu-id="0ea7f-143">You can also declare optional parameters by using the .NET <xref:System.Runtime.InteropServices.OptionalAttribute> class.</span></span> <span data-ttu-id="0ea7f-144">`OptionalAttribute` 形参不需要默认值。</span><span class="sxs-lookup"><span data-stu-id="0ea7f-144">`OptionalAttribute` parameters do not require a default value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0ea7f-145">示例</span><span class="sxs-lookup"><span data-stu-id="0ea7f-145">Example</span></span>  
 <span data-ttu-id="0ea7f-146">在以下示例中，`ExampleClass` 的构造函数具有一个可选形参。</span><span class="sxs-lookup"><span data-stu-id="0ea7f-146">In the following example, the constructor for `ExampleClass` has one parameter, which is optional.</span></span> <span data-ttu-id="0ea7f-147">实例方法 `ExampleMethod` 具有一个必选形参（`required`）和两个可选形参（`optionalstr` 和 `optionalint`）。</span><span class="sxs-lookup"><span data-stu-id="0ea7f-147">Instance method `ExampleMethod` has one required parameter, `required`, and two optional parameters, `optionalstr` and `optionalint`.</span></span> <span data-ttu-id="0ea7f-148">`Main` 中的代码演示了可用于调用构造函数和方法的不同方式。</span><span class="sxs-lookup"><span data-stu-id="0ea7f-148">The code in `Main` shows the different ways in which the constructor and method can be invoked.</span></span>  
  
 [!code-csharp[csProgGuideNamedAndOptional#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_3.cs)]  
  
## <a name="com-interfaces"></a><span data-ttu-id="0ea7f-149">COM 接口</span><span class="sxs-lookup"><span data-stu-id="0ea7f-149">COM Interfaces</span></span>  
 <span data-ttu-id="0ea7f-150">命名实参和可选实参，以及对动态对象的支持和其他增强功能大大提高了与 COM API（例如 Office Automation API）的互操作性。</span><span class="sxs-lookup"><span data-stu-id="0ea7f-150">Named and optional arguments, along with support for dynamic objects and other enhancements, greatly improve interoperability with COM APIs, such as Office Automation APIs.</span></span>  
  
 <span data-ttu-id="0ea7f-151">例如，Microsoft Office Excel 的 <xref:Microsoft.Office.Interop.Excel.Range> 接口中的 <xref:Microsoft.Office.Interop.Excel.Range.AutoFormat%2A> 方法有七个可选形参。</span><span class="sxs-lookup"><span data-stu-id="0ea7f-151">For example, the <xref:Microsoft.Office.Interop.Excel.Range.AutoFormat%2A> method in the Microsoft Office Excel <xref:Microsoft.Office.Interop.Excel.Range> interface has seven parameters, all of which are optional.</span></span> <span data-ttu-id="0ea7f-152">这些形参如下图所示。</span><span class="sxs-lookup"><span data-stu-id="0ea7f-152">These parameters are shown in the following illustration.</span></span>  
  
 <span data-ttu-id="0ea7f-153">![AutoFormat 方法的 IntelliSense 快速信息。](../../../csharp/programming-guide/classes-and-structs/media/autoformat_parameters.png "AutoFormat_Parameters")</span><span class="sxs-lookup"><span data-stu-id="0ea7f-153">![IntelliSense Quick Info for the AutoFormat method.](../../../csharp/programming-guide/classes-and-structs/media/autoformat_parameters.png "AutoFormat_Parameters")</span></span>  
<span data-ttu-id="0ea7f-154">AutoFormat 形参</span><span class="sxs-lookup"><span data-stu-id="0ea7f-154">AutoFormat parameters</span></span>  
  
 <span data-ttu-id="0ea7f-155">在 C# 3.0 以及早期版本中，每个形参都需要一个实参，如下例所示。</span><span class="sxs-lookup"><span data-stu-id="0ea7f-155">In C# 3.0 and earlier versions, an argument is required for each parameter, as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideNamedAndOptional#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_4.cs)]  
  
 <span data-ttu-id="0ea7f-156">但是，可以通过使用 C# 4.0 中引入的命名实参和可选实参来大大简化对 `AutoFormat` 的调用。</span><span class="sxs-lookup"><span data-stu-id="0ea7f-156">However, you can greatly simplify the call to `AutoFormat` by using named and optional arguments, introduced in C# 4.0.</span></span> <span data-ttu-id="0ea7f-157">如果不希望更改形参的默认值，则可以通过使用命名实参和可选实参来为可选形参省略实参。</span><span class="sxs-lookup"><span data-stu-id="0ea7f-157">Named and optional arguments enable you to omit the argument for an optional parameter if you do not want to change the parameter's default value.</span></span> <span data-ttu-id="0ea7f-158">在下面的调用中，仅为 7 个形参中的其中一个指定了值。</span><span class="sxs-lookup"><span data-stu-id="0ea7f-158">In the following call, a value is specified for only one of the seven parameters.</span></span>  
  
 [!code-csharp[csProgGuideNamedAndOptional#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_5.cs)]  
  
 <span data-ttu-id="0ea7f-159">有关详细信息和示例，请参阅[操作说明：在 Office 编程中使用命名参数和可选参数](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md)和[操作说明：使用 Visual C# 功能访问 Office 互操作对象](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md)。</span><span class="sxs-lookup"><span data-stu-id="0ea7f-159">For more information and examples, see [How to: Use Named and Optional Arguments in Office Programming](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md) and [How to: Access Office Interop Objects by Using Visual C# Features](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md).</span></span>  
  
## <a name="overload-resolution"></a><span data-ttu-id="0ea7f-160">重载决策</span><span class="sxs-lookup"><span data-stu-id="0ea7f-160">Overload Resolution</span></span>  
 <span data-ttu-id="0ea7f-161">使用命名实参和可选实参将在以下方面对重载决策产生影响：</span><span class="sxs-lookup"><span data-stu-id="0ea7f-161">Use of named and optional arguments affects overload resolution in the following ways:</span></span>  
  
-   <span data-ttu-id="0ea7f-162">如果方法、索引器或构造函数的每个参数是可选的，或按名称或位置对应于调用语句中的单个自变量，且该自变量可转换为参数的类型，则方法、索引器或构造函数为执行的候选项。</span><span class="sxs-lookup"><span data-stu-id="0ea7f-162">A method, indexer, or constructor is a candidate for execution if each of its parameters either is optional or corresponds, by name or by position, to a single argument in the calling statement, and that argument can be converted to the type of the parameter.</span></span>  
  
-   <span data-ttu-id="0ea7f-163">如果找到多个候选项，则会将用于首选转换的重载决策规则应用于显式指定的自变量。</span><span class="sxs-lookup"><span data-stu-id="0ea7f-163">If more than one candidate is found, overload resolution rules for preferred conversions are applied to the arguments that are explicitly specified.</span></span> <span data-ttu-id="0ea7f-164">将忽略可选形参已省略的实参。</span><span class="sxs-lookup"><span data-stu-id="0ea7f-164">Omitted arguments for optional parameters are ignored.</span></span>  
  
-   <span data-ttu-id="0ea7f-165">如果两个候选项不相上下，则会将没有可选形参的候选项作为首选项，对于这些可选形参，已在调用中为其省略了实参。</span><span class="sxs-lookup"><span data-stu-id="0ea7f-165">If two candidates are judged to be equally good, preference goes to a candidate that does not have optional parameters for which arguments were omitted in the call.</span></span> <span data-ttu-id="0ea7f-166">这是重载决策中的常规引用的结果，该引用用于参数较少的候选项。</span><span class="sxs-lookup"><span data-stu-id="0ea7f-166">This is a consequence of a general preference in overload resolution for candidates that have fewer parameters.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="0ea7f-167">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="0ea7f-167">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0ea7f-168">请参阅</span><span class="sxs-lookup"><span data-stu-id="0ea7f-168">See Also</span></span>

- [<span data-ttu-id="0ea7f-169">如何：在 Office 编程中使用命名参数和可选参数</span><span class="sxs-lookup"><span data-stu-id="0ea7f-169">How to: Use Named and Optional Arguments in Office Programming</span></span>](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md)  
- [<span data-ttu-id="0ea7f-170">使用类型 dynamic</span><span class="sxs-lookup"><span data-stu-id="0ea7f-170">Using Type dynamic</span></span>](../../../csharp/programming-guide/types/using-type-dynamic.md)  
- [<span data-ttu-id="0ea7f-171">使用构造函数</span><span class="sxs-lookup"><span data-stu-id="0ea7f-171">Using Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/using-constructors.md)  
- [<span data-ttu-id="0ea7f-172">使用索引器</span><span class="sxs-lookup"><span data-stu-id="0ea7f-172">Using Indexers</span></span>](../../../csharp/programming-guide/indexers/using-indexers.md)
