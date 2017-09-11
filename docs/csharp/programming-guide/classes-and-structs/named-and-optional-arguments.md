---
title: "命名实参和可选实参（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- namedParameter_CSharpKeyword
- cs_namedParameter
dev_langs:
- CSharp
helpviewer_keywords:
- parameters [C#], named
- named arguments [C#]
- arguments [C#], named
- optional arguments [C#]
- arguments [C#], optional
- parameters [C#], optional
- named and optional arguments [C#]
ms.assetid: 839c960c-c2dc-4d05-af4d-ca5428e54008
caps.latest.revision: 43
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
ms.sourcegitcommit: 1e548df4de2c07934313311a7ffcfae82be76000
ms.openlocfilehash: a7f05e3e0b19bf6457989f8db2b46741cf6b28c1
ms.contentlocale: zh-cn
ms.lasthandoff: 08/29/2017

---
# <a name="named-and-optional-arguments-c-programming-guide"></a><span data-ttu-id="5d188-102">命名实参和可选实参（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="5d188-102">Named and Optional Arguments (C# Programming Guide)</span></span>
[!INCLUDE[csharp_dev10_long](~/includes/csharp-dev10-long-md.md)]<span data-ttu-id="5d188-103"> 介绍命名实参和可选实参。</span><span class="sxs-lookup"><span data-stu-id="5d188-103"> introduces named and optional arguments.</span></span> <span data-ttu-id="5d188-104">通过*命名实参*，你可以为特定形参指定实参，方法是将实参与该形参的名称关联，而不是与形参在形参列表中的位置关联。</span><span class="sxs-lookup"><span data-stu-id="5d188-104">*Named arguments* enable you to specify an argument for a particular parameter by associating the argument with the parameter's name rather than with the parameter's position in the parameter list.</span></span> <span data-ttu-id="5d188-105">通过*可选参数*，你可以为某些形参省略实参。</span><span class="sxs-lookup"><span data-stu-id="5d188-105">*Optional arguments* enable you to omit arguments for some parameters.</span></span> <span data-ttu-id="5d188-106">这两种技术都可与方法、索引器、构造函数和委托一起使用。</span><span class="sxs-lookup"><span data-stu-id="5d188-106">Both techniques can be used with methods, indexers, constructors, and delegates.</span></span>  
  
 <span data-ttu-id="5d188-107">使用命名参数和可选参数时，将按实参出现在实参列表（而不是形参列表）中的顺序计算这些实参。</span><span class="sxs-lookup"><span data-stu-id="5d188-107">When you use named and optional arguments, the arguments are evaluated in the order in which they appear in the argument list, not the parameter list.</span></span>  
  
 <span data-ttu-id="5d188-108">命名形参和可选形参一起使用时，你可以只为可选形参列表中的少数形参提供实参。</span><span class="sxs-lookup"><span data-stu-id="5d188-108">Named and optional parameters, when used together, enable you to supply arguments for only a few parameters from a list of optional parameters.</span></span> <span data-ttu-id="5d188-109">此功能极大地方便了对 COM 接口（例如 Microsoft Office 自动化 API）的调用。</span><span class="sxs-lookup"><span data-stu-id="5d188-109">This capability greatly facilitates calls to COM interfaces such as the Microsoft Office Automation APIs.</span></span>  
  
## <a name="named-arguments"></a><span data-ttu-id="5d188-110">命名实参</span><span class="sxs-lookup"><span data-stu-id="5d188-110">Named Arguments</span></span>  
 <span data-ttu-id="5d188-111">有了命名实参，你将不再需要记住或查找形参在所调用方法的形参列表中的顺序。</span><span class="sxs-lookup"><span data-stu-id="5d188-111">Named arguments free you from the need to remember or to look up the order of parameters in the parameter lists of called methods.</span></span> <span data-ttu-id="5d188-112">每个实参的形参都可按形参名称进行指定。</span><span class="sxs-lookup"><span data-stu-id="5d188-112">The parameter for each argument can be specified by parameter name.</span></span> <span data-ttu-id="5d188-113">例如，可以采用标准方式调用计算体重指数 (BMI) 的函数，方法是按照该函数定义的顺序按位置发送体重和身高的实参。</span><span class="sxs-lookup"><span data-stu-id="5d188-113">For example, a function that calculates body mass index (BMI) can be called in the standard way by sending arguments for weight and height by position, in the order defined by the function.</span></span>  
  
 `CalculateBMI(123, 64);`  
  
 <span data-ttu-id="5d188-114">如果不记得形参的顺序，但却知道其名称，则可以按任意顺序（体重优先或身高优先）发送实参。</span><span class="sxs-lookup"><span data-stu-id="5d188-114">If you do not remember the order of the parameters but you do know their names, you can send the arguments in either order, weight first or height first.</span></span>  
  
 `CalculateBMI(weight: 123, height: 64);`  
  
 `CalculateBMI(height: 64, weight: 123);`  
  
 <span data-ttu-id="5d188-115">命名实参还可以标识每个实参所表示的含义，从而改进代码的可读性。</span><span class="sxs-lookup"><span data-stu-id="5d188-115">Named arguments also improve the readability of your code by identifying what each argument represents.</span></span>  
  
 <span data-ttu-id="5d188-116">命名实参可以放在位置实参后面，如此处所示。</span><span class="sxs-lookup"><span data-stu-id="5d188-116">A named argument can follow positional arguments, as shown here.</span></span>  
  
 `CalculateBMI(123, height: 64);`  
  
 <span data-ttu-id="5d188-117">但是，位置自变量不能位于命名的自变量之后。</span><span class="sxs-lookup"><span data-stu-id="5d188-117">However, a positional argument cannot follow a named argument.</span></span> <span data-ttu-id="5d188-118">下面的语句会导致编译器错误。</span><span class="sxs-lookup"><span data-stu-id="5d188-118">The following statement causes a compiler error.</span></span>  
  
 `//CalculateBMI(weight: 123, 64);`  
  
## <a name="example"></a><span data-ttu-id="5d188-119">示例</span><span class="sxs-lookup"><span data-stu-id="5d188-119">Example</span></span>  
 <span data-ttu-id="5d188-120">以下代码执行本节中的示例。</span><span class="sxs-lookup"><span data-stu-id="5d188-120">The following code implements the examples from this section.</span></span>  
  
 <span data-ttu-id="5d188-121">[!code-cs[csProgGuideNamedAndOptional#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="5d188-121">[!code-cs[csProgGuideNamedAndOptional#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_1.cs)]</span></span>  
  
## <a name="optional-arguments"></a><span data-ttu-id="5d188-122">可选实参</span><span class="sxs-lookup"><span data-stu-id="5d188-122">Optional Arguments</span></span>  
 <span data-ttu-id="5d188-123">方法、构造函数、索引器或委托的定义可以指定其形参为必需还是可选。</span><span class="sxs-lookup"><span data-stu-id="5d188-123">The definition of a method, constructor, indexer, or delegate can specify that its parameters are required or that they are optional.</span></span> <span data-ttu-id="5d188-124">任何调用都必须为所有必需的形参提供实参，但可以为可选的形参省略实参。</span><span class="sxs-lookup"><span data-stu-id="5d188-124">Any call must provide arguments for all required parameters, but can omit arguments for optional parameters.</span></span>  
  
 <span data-ttu-id="5d188-125">每个可选形参都有一个默认值作为其定义的一部分。</span><span class="sxs-lookup"><span data-stu-id="5d188-125">Each optional parameter has a default value as part of its definition.</span></span> <span data-ttu-id="5d188-126">如果没有为该形参发送实参，则使用默认值。</span><span class="sxs-lookup"><span data-stu-id="5d188-126">If no argument is sent for that parameter, the default value is used.</span></span> <span data-ttu-id="5d188-127">默认值必须是以下类型的表达式之一：</span><span class="sxs-lookup"><span data-stu-id="5d188-127">A default value must be one of the following types of expressions:</span></span>  
  
-   <span data-ttu-id="5d188-128">常量表达式；</span><span class="sxs-lookup"><span data-stu-id="5d188-128">a constant expression;</span></span>  
  
-   <span data-ttu-id="5d188-129">`new ValType()` 形式的表达式，其中 `ValType` 是值类型，例如 [enum](../../../csharp/language-reference/keywords/enum.md) 或 [struct](../../../csharp/programming-guide/classes-and-structs/structs.md)；</span><span class="sxs-lookup"><span data-stu-id="5d188-129">an expression of the form `new ValType()`, where `ValType` is a value type, such as an [enum](../../../csharp/language-reference/keywords/enum.md) or a [struct](../../../csharp/programming-guide/classes-and-structs/structs.md);</span></span>  
  
-   <span data-ttu-id="5d188-130">[default(ValType)](../../../csharp/programming-guide/statements-expressions-operators/default-value-expressions.md) 形式的表达式，其中 `ValType` 是值类型。</span><span class="sxs-lookup"><span data-stu-id="5d188-130">an expression of the form [default(ValType)](../../../csharp/programming-guide/statements-expressions-operators/default-value-expressions.md),  where `ValType` is a value type.</span></span>  
  
 <span data-ttu-id="5d188-131">可选参数定义于参数列表的末尾和必需参数之后。</span><span class="sxs-lookup"><span data-stu-id="5d188-131">Optional parameters are defined at the end of the parameter list, after any required parameters.</span></span> <span data-ttu-id="5d188-132">如果调用方为一系列可选形参中的任意一个形参提供了实参，则它必须为前面的所有可选形参提供实参。</span><span class="sxs-lookup"><span data-stu-id="5d188-132">If the caller provides an argument for any one of a succession of optional parameters, it must provide arguments for all preceding optional parameters.</span></span> <span data-ttu-id="5d188-133">实参列表中不支持使用逗号分隔的间隔。</span><span class="sxs-lookup"><span data-stu-id="5d188-133">Comma-separated gaps in the argument list are not supported.</span></span> <span data-ttu-id="5d188-134">例如，在以下代码中，使用一个必选形参和两个可选形参定义实例方法 `ExampleMethod`。</span><span class="sxs-lookup"><span data-stu-id="5d188-134">For example, in the following code, instance method `ExampleMethod` is defined with one required and two optional parameters.</span></span>  
  
 <span data-ttu-id="5d188-135">[!code-cs[csProgGuideNamedAndOptional#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="5d188-135">[!code-cs[csProgGuideNamedAndOptional#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_2.cs)]</span></span>  
  
 <span data-ttu-id="5d188-136">下面对 `ExampleMethod` 的调用会导致编译器错误，原因是为第三个形参而不是为第二个形参提供了实参。</span><span class="sxs-lookup"><span data-stu-id="5d188-136">The following call to `ExampleMethod` causes a compiler error, because an argument is provided for the third parameter but not for the second.</span></span>  
  
 `//anExample.ExampleMethod(3, ,4);`  
  
 <span data-ttu-id="5d188-137">但是，如果知道第三个形参的名称，则可以使用命名实参来完成此任务。</span><span class="sxs-lookup"><span data-stu-id="5d188-137">However, if you know the name of the third parameter, you can use a named argument to accomplish the task.</span></span>  
  
 `anExample.ExampleMethod(3, optionalint: 4);`  
  
 <span data-ttu-id="5d188-138">IntelliSense 使用括号表示可选形参，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="5d188-138">IntelliSense uses brackets to indicate optional parameters, as shown in the following illustration.</span></span>  
  
 <span data-ttu-id="5d188-139">![ExampleMethod 方法的 IntelliSense 快速信息。](../../../csharp/programming-guide/classes-and-structs/media/optional_parameters.png "Optional_Parameters")</span><span class="sxs-lookup"><span data-stu-id="5d188-139">![IntelliSense Quick Info for method ExampleMethod.](../../../csharp/programming-guide/classes-and-structs/media/optional_parameters.png "Optional_Parameters")</span></span>  
<span data-ttu-id="5d188-140">ExampleMethod 中的可选形参</span><span class="sxs-lookup"><span data-stu-id="5d188-140">Optional parameters in ExampleMethod</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5d188-141">此外，还可通过使用 .NET <xref:System.Runtime.InteropServices.OptionalAttribute> 类声明可选参数。</span><span class="sxs-lookup"><span data-stu-id="5d188-141">You can also declare optional parameters by using the .NET <xref:System.Runtime.InteropServices.OptionalAttribute> class.</span></span> <span data-ttu-id="5d188-142">`OptionalAttribute` 形参不需要默认值。</span><span class="sxs-lookup"><span data-stu-id="5d188-142">`OptionalAttribute` parameters do not require a default value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d188-143">示例</span><span class="sxs-lookup"><span data-stu-id="5d188-143">Example</span></span>  
 <span data-ttu-id="5d188-144">在以下示例中，`ExampleClass` 的构造函数具有一个可选形参。</span><span class="sxs-lookup"><span data-stu-id="5d188-144">In the following example, the constructor for `ExampleClass` has one parameter, which is optional.</span></span> <span data-ttu-id="5d188-145">实例方法 `ExampleMethod` 具有一个必选形参（`required`）和两个可选形参（`optionalstr` 和 `optionalint`）。</span><span class="sxs-lookup"><span data-stu-id="5d188-145">Instance method `ExampleMethod` has one required parameter, `required`, and two optional parameters, `optionalstr` and `optionalint`.</span></span> <span data-ttu-id="5d188-146">`Main` 中的代码演示了可用于调用构造函数和方法的不同方式。</span><span class="sxs-lookup"><span data-stu-id="5d188-146">The code in `Main` shows the different ways in which the constructor and method can be invoked.</span></span>  
  
 <span data-ttu-id="5d188-147">[!code-cs[csProgGuideNamedAndOptional#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="5d188-147">[!code-cs[csProgGuideNamedAndOptional#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_3.cs)]</span></span>  
  
## <a name="com-interfaces"></a><span data-ttu-id="5d188-148">COM 接口</span><span class="sxs-lookup"><span data-stu-id="5d188-148">COM Interfaces</span></span>  
 <span data-ttu-id="5d188-149">命名实参和可选实参，以及对动态对象的支持和其他增强功能大大提高了与 COM API（例如 Office Automation API）的互操作性。</span><span class="sxs-lookup"><span data-stu-id="5d188-149">Named and optional arguments, along with support for dynamic objects and other enhancements, greatly improve interoperability with COM APIs, such as Office Automation APIs.</span></span>  
  
 <span data-ttu-id="5d188-150">例如，Microsoft Office Excel 的 [Range](http://go.microsoft.com/fwlink/?LinkId=148196) 接口中的 [AutoFormat](http://go.microsoft.com/fwlink/?LinkId=148201) 方法具有 7 个可选形参。</span><span class="sxs-lookup"><span data-stu-id="5d188-150">For example, the [AutoFormat](http://go.microsoft.com/fwlink/?LinkId=148201) method in the Microsoft Office Excel [Range](http://go.microsoft.com/fwlink/?LinkId=148196) interface has seven parameters, all of which are optional.</span></span> <span data-ttu-id="5d188-151">这些形参如下图所示。</span><span class="sxs-lookup"><span data-stu-id="5d188-151">These parameters are shown in the following illustration.</span></span>  
  
 <span data-ttu-id="5d188-152">![AutoFormat 方法的 IntelliSense 快速信息。](../../../csharp/programming-guide/classes-and-structs/media/autoformat_parameters.png "AutoFormat_Parameters")</span><span class="sxs-lookup"><span data-stu-id="5d188-152">![IntelliSense Quick Info for the AutoFormat method.](../../../csharp/programming-guide/classes-and-structs/media/autoformat_parameters.png "AutoFormat_Parameters")</span></span>  
<span data-ttu-id="5d188-153">AutoFormat 形参</span><span class="sxs-lookup"><span data-stu-id="5d188-153">AutoFormat parameters</span></span>  
  
 <span data-ttu-id="5d188-154">在 C# 3.0 以及早期版本中，每个形参都需要一个实参，如下例所示。</span><span class="sxs-lookup"><span data-stu-id="5d188-154">In C# 3.0 and earlier versions, an argument is required for each parameter, as shown in the following example.</span></span>  
  
 <span data-ttu-id="5d188-155">[!code-cs[csProgGuideNamedAndOptional#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="5d188-155">[!code-cs[csProgGuideNamedAndOptional#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_4.cs)]</span></span>  
  
 <span data-ttu-id="5d188-156">但是，可以通过使用 C# 4.0 中引入的命名实参和可选实参来大大简化对 `AutoFormat` 的调用。</span><span class="sxs-lookup"><span data-stu-id="5d188-156">However, you can greatly simplify the call to `AutoFormat` by using named and optional arguments, introduced in C# 4.0.</span></span> <span data-ttu-id="5d188-157">如果不希望更改形参的默认值，则可以通过使用命名实参和可选实参来为可选形参省略实参。</span><span class="sxs-lookup"><span data-stu-id="5d188-157">Named and optional arguments enable you to omit the argument for an optional parameter if you do not want to change the parameter's default value.</span></span> <span data-ttu-id="5d188-158">在下面的调用中，仅为 7 个形参中的其中一个指定了值。</span><span class="sxs-lookup"><span data-stu-id="5d188-158">In the following call, a value is specified for only one of the seven parameters.</span></span>  
  
 <span data-ttu-id="5d188-159">[!code-cs[csProgGuideNamedAndOptional#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="5d188-159">[!code-cs[csProgGuideNamedAndOptional#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_5.cs)]</span></span>  
  
 <span data-ttu-id="5d188-160">有关详细信息和示例，请参阅[如何：在 Office 编程中使用命名实参和可选实参](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md)和[如何：使用 Visual C# 功能访问 Office 互操作性对象](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md)。</span><span class="sxs-lookup"><span data-stu-id="5d188-160">For more information and examples, see [How to: Use Named and Optional Arguments in Office Programming](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md) and [How to: Access Office Interop Objects by Using Visual C# Features](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md).</span></span>  
  
## <a name="overload-resolution"></a><span data-ttu-id="5d188-161">重载决策</span><span class="sxs-lookup"><span data-stu-id="5d188-161">Overload Resolution</span></span>  
 <span data-ttu-id="5d188-162">使用命名实参和可选实参将在以下方面对重载决策产生影响：</span><span class="sxs-lookup"><span data-stu-id="5d188-162">Use of named and optional arguments affects overload resolution in the following ways:</span></span>  
  
-   <span data-ttu-id="5d188-163">如果方法、索引器或构造函数的每个参数是可选的，或按名称或位置对应于调用语句中的单个自变量，且该自变量可转换为参数的类型，则方法、索引器或构造函数为执行的候选项。</span><span class="sxs-lookup"><span data-stu-id="5d188-163">A method, indexer, or constructor is a candidate for execution if each of its parameters either is optional or corresponds, by name or by position, to a single argument in the calling statement, and that argument can be converted to the type of the parameter.</span></span>  
  
-   <span data-ttu-id="5d188-164">如果找到多个候选项，则会将用于首选转换的重载决策规则应用于显式指定的自变量。</span><span class="sxs-lookup"><span data-stu-id="5d188-164">If more than one candidate is found, overload resolution rules for preferred conversions are applied to the arguments that are explicitly specified.</span></span> <span data-ttu-id="5d188-165">将忽略可选形参已省略的实参。</span><span class="sxs-lookup"><span data-stu-id="5d188-165">Omitted arguments for optional parameters are ignored.</span></span>  
  
-   <span data-ttu-id="5d188-166">如果两个候选项不相上下，则会将没有可选形参的候选项作为首选项，对于这些可选形参，已在调用中为其省略了实参。</span><span class="sxs-lookup"><span data-stu-id="5d188-166">If two candidates are judged to be equally good, preference goes to a candidate that does not have optional parameters for which arguments were omitted in the call.</span></span> <span data-ttu-id="5d188-167">这是重载决策中的常规引用的结果，该引用用于参数较少的候选项。</span><span class="sxs-lookup"><span data-stu-id="5d188-167">This is a consequence of a general preference in overload resolution for candidates that have fewer parameters.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="5d188-168">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="5d188-168">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5d188-169">请参阅</span><span class="sxs-lookup"><span data-stu-id="5d188-169">See Also</span></span>  
 <span data-ttu-id="5d188-170">[如何：在 Office 编程中使用命名实参和可选实参](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md) </span><span class="sxs-lookup"><span data-stu-id="5d188-170">[How to: Use Named and Optional Arguments in Office Programming](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md) </span></span>  
 <span data-ttu-id="5d188-171">[使用类型 dynamic](../../../csharp/programming-guide/types/using-type-dynamic.md) </span><span class="sxs-lookup"><span data-stu-id="5d188-171">[Using Type dynamic](../../../csharp/programming-guide/types/using-type-dynamic.md) </span></span>  
 <span data-ttu-id="5d188-172">[使用构造函数](../../../csharp/programming-guide/classes-and-structs/using-constructors.md) </span><span class="sxs-lookup"><span data-stu-id="5d188-172">[Using Constructors](../../../csharp/programming-guide/classes-and-structs/using-constructors.md) </span></span>  
 [<span data-ttu-id="5d188-173">使用索引器</span><span class="sxs-lookup"><span data-stu-id="5d188-173">Using Indexers</span></span>](../../../csharp/programming-guide/indexers/using-indexers.md)

