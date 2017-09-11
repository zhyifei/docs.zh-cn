---
title: "在 Visual Basic (Visual Basic 中) 中的泛型类型 |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- generic interfaces
- data type arguments, defining
- generic delegates
- arguments [Visual Basic], data types
- Of keyword, using
- delegates, generic
- constraints, Visual Basic generic types
- generic parameters
- data type parameters
- procedures, generic
- generic procedures
- data types [Visual Basic], generic
- data types [Visual Basic], as parameters
- generics [Visual Basic], generic types
- data types [Visual Basic], as arguments
- generic classes, Visual Basic
- parameters, type
- type arguments
- interfaces, generic
- generics [Visual Basic]
- types [Visual Basic], generic
- parameters, generic
- generic structures
- generic classes
- type parameters
- data type arguments
- structures, generic
- parameters, data type
- collections, generic
- classes [Visual Basic], generic
- data type parameters, defining
- type arguments, defining
- arguments [Visual Basic], type
ms.assetid: 89f771d9-ecbb-4737-88b8-116b63c6cf4d
caps.latest.revision: 45
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 40b175655b2b2341fd15e763058a3dae1291f2c4
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="generic-types-in-visual-basic-visual-basic"></a><span data-ttu-id="ef487-102">Visual Basic 中的泛型类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ef487-102">Generic Types in Visual Basic (Visual Basic)</span></span>
<span data-ttu-id="ef487-103">*泛型类型* 是可适应对多种数据类型执行相同功能的单个编程元素。</span><span class="sxs-lookup"><span data-stu-id="ef487-103">A *generic type* is a single programming element that adapts to perform the same functionality for a variety of data types.</span></span> <span data-ttu-id="ef487-104">定义泛型类或过程时，无需为可能需要对其执行该功能的每个数据类型定义单独版本。</span><span class="sxs-lookup"><span data-stu-id="ef487-104">When you define a generic class or procedure, you do not have to define a separate version for each data type for which you might want to perform that functionality.</span></span>  
  
 <span data-ttu-id="ef487-105">就好比是带有可拆卸刀头的螺丝刀。</span><span class="sxs-lookup"><span data-stu-id="ef487-105">An analogy is a screwdriver set with removable heads.</span></span> <span data-ttu-id="ef487-106">你检查需要拧动的螺丝，然后选择适合该螺丝的刀头（一字、十字、星形）。</span><span class="sxs-lookup"><span data-stu-id="ef487-106">You inspect the screw you need to turn and select the correct head for that screw (slotted, crossed, starred).</span></span> <span data-ttu-id="ef487-107">将正确的刀头插入到螺丝刀柄上后，你就可以使用螺丝刀执行完全相同的功能，即拧螺丝。</span><span class="sxs-lookup"><span data-stu-id="ef487-107">Once you insert the correct head in the screwdriver handle, you perform the exact same function with the screwdriver, namely turning the screw.</span></span>  
  
 <span data-ttu-id="ef487-108">![作为通用工具的螺丝刀的示意图](../../../../visual-basic/programming-guide/language-features/data-types/media/genericscrewdriver.gif "GenericScrewDriver")</span><span class="sxs-lookup"><span data-stu-id="ef487-108">![Diagram of a screwdriver set as a generic tool](../../../../visual-basic/programming-guide/language-features/data-types/media/genericscrewdriver.gif "GenericScrewDriver")</span></span>  
<span data-ttu-id="ef487-109">作为通用工具的螺丝刀</span><span class="sxs-lookup"><span data-stu-id="ef487-109">Screwdriver set as a generic tool</span></span>  
  
 <span data-ttu-id="ef487-110">定义泛型类型时，即使用一个或多个数据类型将其参数化。</span><span class="sxs-lookup"><span data-stu-id="ef487-110">When you define a generic type, you parameterize it with one or more data types.</span></span> <span data-ttu-id="ef487-111">这样可允许使用代码定制数据类型以满足其要求。</span><span class="sxs-lookup"><span data-stu-id="ef487-111">This allows the using code to tailor the data types to its requirements.</span></span> <span data-ttu-id="ef487-112">代码可以通过泛型元素声明若干个不同的编程元素，每个元素可使用一组不同的数据类型。</span><span class="sxs-lookup"><span data-stu-id="ef487-112">Your code can declare several different programming elements from the generic element, each one acting on a different set of data types.</span></span> <span data-ttu-id="ef487-113">但是，无论声明的元素使用哪些数据类型，它们均执行相同的逻辑。</span><span class="sxs-lookup"><span data-stu-id="ef487-113">But the declared elements all perform the identical logic, no matter what data types they are using.</span></span>  
  
 <span data-ttu-id="ef487-114">例如，你可能想创建并使用一个处理特定数据类型（例如 `String`）的队列类。</span><span class="sxs-lookup"><span data-stu-id="ef487-114">For example, you might want to create and use a queue class that operates on a specific data type such as `String`.</span></span> <span data-ttu-id="ef487-115">您可以声明这样的类从<xref:System.Collections.Generic.Queue%601?displayProperty=fullName>，如下面的示例所示。</xref:System.Collections.Generic.Queue%601?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="ef487-115">You can declare such a class from <xref:System.Collections.Generic.Queue%601?displayProperty=fullName>, as the following example shows.</span></span>  
  
 <span data-ttu-id="ef487-116">[!code-vb[VbVbalrDataTypes #&1;](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-types_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="ef487-116">[!code-vb[VbVbalrDataTypes#1](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-types_1.vb)]</span></span>  
  
 <span data-ttu-id="ef487-117">现在，可以使用 `stringQ` 来专门处理 `String` 值。</span><span class="sxs-lookup"><span data-stu-id="ef487-117">You can now use `stringQ` to work exclusively with `String` values.</span></span> <span data-ttu-id="ef487-118">由于 `stringQ` 专用于 `String` 而未针对 `Object` 值进行泛型化，因此，不会有晚期绑定或类型转换。</span><span class="sxs-lookup"><span data-stu-id="ef487-118">Because `stringQ` is specific for `String` instead of being generalized for `Object` values, you do not have late binding or type conversion.</span></span> <span data-ttu-id="ef487-119">从而节省了执行时间并减少了运行时错误。</span><span class="sxs-lookup"><span data-stu-id="ef487-119">This saves execution time and reduces run-time errors.</span></span>  
  
 <span data-ttu-id="ef487-120">使用泛型类型的详细信息，请参阅[如何︰ 使用泛型类](../../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)。</span><span class="sxs-lookup"><span data-stu-id="ef487-120">For more information on using a generic type, see [How to: Use a Generic Class](../../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md).</span></span>  
  
## <a name="example-of-a-generic-class"></a><span data-ttu-id="ef487-121">泛型类的示例。</span><span class="sxs-lookup"><span data-stu-id="ef487-121">Example of a Generic Class</span></span>  
 <span data-ttu-id="ef487-122">下面的示例演示了泛型类的主干定义。</span><span class="sxs-lookup"><span data-stu-id="ef487-122">The following example shows a skeleton definition of a generic class.</span></span>  
  
 <span data-ttu-id="ef487-123">[!code-vb[VbVbalrDataTypes #&2;](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-types_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="ef487-123">[!code-vb[VbVbalrDataTypes#2](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-types_2.vb)]</span></span>  
  
 <span data-ttu-id="ef487-124">在上面的主干中， `t` 是一个 *类型形参*，即你在声明此类时提供的数据类型的占位符。</span><span class="sxs-lookup"><span data-stu-id="ef487-124">In the preceding skeleton, `t` is a *type parameter*, that is, a placeholder for a data type that you supply when you declare the class.</span></span> <span data-ttu-id="ef487-125">在代码中的其他地方，可以通过为 `classHolder` 提供不同的数据类型来声明不同版本的 `t`</span><span class="sxs-lookup"><span data-stu-id="ef487-125">Elsewhere in your code, you can declare various versions of `classHolder` by supplying various data types for `t`.</span></span> <span data-ttu-id="ef487-126">下面的示例演示了两个此类声明。</span><span class="sxs-lookup"><span data-stu-id="ef487-126">The following example shows two such declarations.</span></span>  
  
 <span data-ttu-id="ef487-127">[!code-vb[VbVbalrDataTypes #&3;](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-types_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="ef487-127">[!code-vb[VbVbalrDataTypes#3](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-types_3.vb)]</span></span>  
  
 <span data-ttu-id="ef487-128">上面的语句声明了 *构造类*，在这些类中，特定的类型替换了类型形参。</span><span class="sxs-lookup"><span data-stu-id="ef487-128">The preceding statements declare *constructed classes*, in which a specific type replaces the type parameter.</span></span> <span data-ttu-id="ef487-129">此类替换会在构造类中的代码内进行传播。</span><span class="sxs-lookup"><span data-stu-id="ef487-129">This replacement is propagated throughout the code within the constructed class.</span></span> <span data-ttu-id="ef487-130">下面的示例显示了 `processNewItem` 过程在 `integerClass`中的外观。</span><span class="sxs-lookup"><span data-stu-id="ef487-130">The following example shows what the `processNewItem` procedure looks like in `integerClass`.</span></span>  
  
 <span data-ttu-id="ef487-131">[!code-vb[VbVbalrDataTypes #&4;](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-types_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="ef487-131">[!code-vb[VbVbalrDataTypes#4](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-types_4.vb)]</span></span>  
  
 <span data-ttu-id="ef487-132">有关更完整的示例，请参阅[如何︰ 定义类，可以提供具有相同的功能对不同数据类型](../../../../visual-basic/programming-guide/language-features/data-types/how-to-define-a-class-that-can-provide-identical-functionality.md)。</span><span class="sxs-lookup"><span data-stu-id="ef487-132">For a more complete example, see [How to: Define a Class That Can Provide Identical Functionality on Different Data Types](../../../../visual-basic/programming-guide/language-features/data-types/how-to-define-a-class-that-can-provide-identical-functionality.md).</span></span>  
  
## <a name="eligible-programming-elements"></a><span data-ttu-id="ef487-133">合格的编程元素</span><span class="sxs-lookup"><span data-stu-id="ef487-133">Eligible Programming Elements</span></span>  
 <span data-ttu-id="ef487-134">你可以定义并使用泛型类、结构、接口、过程和委托。</span><span class="sxs-lookup"><span data-stu-id="ef487-134">You can define and use generic classes, structures, interfaces, procedures, and delegates.</span></span> <span data-ttu-id="ef487-135">请注意，[!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)]定义多个泛型类、 结构和接口，用于表示常用泛型元素。</span><span class="sxs-lookup"><span data-stu-id="ef487-135">Note that the [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] defines several generic classes, structures, and interfaces that represent commonly used generic elements.</span></span> <span data-ttu-id="ef487-136"><xref:System.Collections.Generic?displayProperty=fullName>命名空间提供词典、 列表、 队列和堆栈。</xref:System.Collections.Generic?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="ef487-136">The <xref:System.Collections.Generic?displayProperty=fullName> namespace provides dictionaries, lists, queues, and stacks.</span></span> <span data-ttu-id="ef487-137">在定义您自己的泛型元素之前, 查看它是否已可在<xref:System.Collections.Generic?displayProperty=fullName>。</xref:System.Collections.Generic?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="ef487-137">Before defining your own generic element, see if it is already available in <xref:System.Collections.Generic?displayProperty=fullName>.</span></span>  
  
 <span data-ttu-id="ef487-138">过程不是类型，但可以定义并使用泛型过程。</span><span class="sxs-lookup"><span data-stu-id="ef487-138">Procedures are not types, but you can define and use generic procedures.</span></span> <span data-ttu-id="ef487-139">请参阅[Visual Basic 中的泛型过程](../../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="ef487-139">See [Generic Procedures in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md).</span></span>  
  
## <a name="advantages-of-generic-types"></a><span data-ttu-id="ef487-140">泛型类型的优点</span><span class="sxs-lookup"><span data-stu-id="ef487-140">Advantages of Generic Types</span></span>  
 <span data-ttu-id="ef487-141">泛型类型用作声明几个不同编程元素的基础，而每个元素均处理特定的数据类型。</span><span class="sxs-lookup"><span data-stu-id="ef487-141">A generic type serves as a basis for declaring several different programming elements, each of which operates on a specific data type.</span></span> <span data-ttu-id="ef487-142">泛型类型的替代项有：</span><span class="sxs-lookup"><span data-stu-id="ef487-142">The alternatives to a generic type are:</span></span>  
  
1.  <span data-ttu-id="ef487-143">对 `Object` 数据类型进行处理的单一类型。</span><span class="sxs-lookup"><span data-stu-id="ef487-143">A single type operating on the `Object` data type.</span></span>  
  
2.  <span data-ttu-id="ef487-144">一组 *特定于类型* 的类型版本，每个版本单独进行编码并处理一种特定的数据类型（如 `String`、 `Integer`）或用户定义的类型（如 `customer`）。</span><span class="sxs-lookup"><span data-stu-id="ef487-144">A set of *type-specific* versions of the type, each version individually coded and operating on one specific data type such as `String`, `Integer`, or a user-defined type such as `customer`.</span></span>  
  
 <span data-ttu-id="ef487-145">与上述替代项相比，泛型类型具有以下优点：</span><span class="sxs-lookup"><span data-stu-id="ef487-145">A generic type has the following advantages over these alternatives:</span></span>  
  
-   <span data-ttu-id="ef487-146">**类型安全。**</span><span class="sxs-lookup"><span data-stu-id="ef487-146">**Type Safety.**</span></span> <span data-ttu-id="ef487-147">泛型类型强制实施编译时类型检查。</span><span class="sxs-lookup"><span data-stu-id="ef487-147">Generic types enforce compile-time type checking.</span></span> <span data-ttu-id="ef487-148">而基于 `Object` 的类型可接受任何数据类型，因此，你必须编写代码以检查是否可接受某种输入数据类型。</span><span class="sxs-lookup"><span data-stu-id="ef487-148">Types based on `Object` accept any data type, and you must write code to check whether an input data type is acceptable.</span></span> <span data-ttu-id="ef487-149">通过泛型类型，编译器可以在运行时之前捕获类型的不匹配。</span><span class="sxs-lookup"><span data-stu-id="ef487-149">With generic types, the compiler can catch type mismatches before run time.</span></span>  
  
-   <span data-ttu-id="ef487-150">**性能。**</span><span class="sxs-lookup"><span data-stu-id="ef487-150">**Performance.**</span></span> <span data-ttu-id="ef487-151">泛型类型无需对数据进行 *装箱* 和 *un装箱* 操作，原因是每种泛型类型均专用于一种数据类型。</span><span class="sxs-lookup"><span data-stu-id="ef487-151">Generic types do not have to *box* and *unbox* data, because each one is specialized for one data type.</span></span> <span data-ttu-id="ef487-152">而基于 `Object` 的操作必须将输入数据类型进行装箱，以将它们转换为 `Object` ，而且还将对预定输出的数据进行取消装箱操作。</span><span class="sxs-lookup"><span data-stu-id="ef487-152">Operations based on `Object` must box input data types to convert them to `Object` and unbox data destined for output.</span></span> <span data-ttu-id="ef487-153">装箱和取消装箱操作会降低性能。</span><span class="sxs-lookup"><span data-stu-id="ef487-153">Boxing and unboxing reduce performance.</span></span>  
  
     <span data-ttu-id="ef487-154">此外，还要对基于 `Object` 的类型进行晚期绑定，这意味着需要编写额外的代码才能在运行时访问它们的成员。</span><span class="sxs-lookup"><span data-stu-id="ef487-154">Types based on `Object` are also late-bound, which means that accessing their members requires extra code at run time.</span></span> <span data-ttu-id="ef487-155">这同样会降低性能。</span><span class="sxs-lookup"><span data-stu-id="ef487-155">This also reduces performance.</span></span>  
  
-   <span data-ttu-id="ef487-156">**代码合并。**</span><span class="sxs-lookup"><span data-stu-id="ef487-156">**Code Consolidation.**</span></span> <span data-ttu-id="ef487-157">只能对泛型类型中的代码定义一次。</span><span class="sxs-lookup"><span data-stu-id="ef487-157">The code in a generic type has to be defined only once.</span></span> <span data-ttu-id="ef487-158">而一组特定于类型的类型版本必须在每个版本中复制相同的代码，唯一的不同就是该版本的特定数据类型。</span><span class="sxs-lookup"><span data-stu-id="ef487-158">A set of type-specific versions of a type must replicate the same code in each version, with the only difference being the specific data type for that version.</span></span> <span data-ttu-id="ef487-159">利用泛型类型，特定于类型的版本全都利用原始的泛型类型生成。</span><span class="sxs-lookup"><span data-stu-id="ef487-159">With generic types, the type-specific versions are all generated from the original generic type.</span></span>  
  
-   <span data-ttu-id="ef487-160">**代码重用。**</span><span class="sxs-lookup"><span data-stu-id="ef487-160">**Code Reuse.**</span></span> <span data-ttu-id="ef487-161">对于不依赖特定数据类型的泛型代码，可以利用不同的数据类型重用它。</span><span class="sxs-lookup"><span data-stu-id="ef487-161">Code that does not depend on a particular data type can be reused with various data types if it is generic.</span></span> <span data-ttu-id="ef487-162">你可以经常重用此类代码（甚至利用最初未预料到的数据类型来重用它）。</span><span class="sxs-lookup"><span data-stu-id="ef487-162">You can often reuse it even with a data type that you did not originally predict.</span></span>  
  
-   <span data-ttu-id="ef487-163">**IDE 的支持。**</span><span class="sxs-lookup"><span data-stu-id="ef487-163">**IDE Support.**</span></span> <span data-ttu-id="ef487-164">在使用通过泛型类型声明的构造类型时，集成开发环境 (IDE) 可以在你开发代码时给予更多的支持。</span><span class="sxs-lookup"><span data-stu-id="ef487-164">When you use a constructed type declared from a generic type, the integrated development environment (IDE) can give you more support while you are developing your code.</span></span> <span data-ttu-id="ef487-165">例如，IntelliSense 可以显示适用于构造函数或方法的某个参数的特定于类型的选项。</span><span class="sxs-lookup"><span data-stu-id="ef487-165">For example, IntelliSense can show you the type-specific options for an argument to a constructor or method.</span></span>  
  
-   <span data-ttu-id="ef487-166">**泛型算法。**</span><span class="sxs-lookup"><span data-stu-id="ef487-166">**Generic Algorithms.**</span></span> <span data-ttu-id="ef487-167">独立于类型的抽象算法非常适用于泛型类型。</span><span class="sxs-lookup"><span data-stu-id="ef487-167">Abstract algorithms that are type-independent are good candidates for generic types.</span></span> <span data-ttu-id="ef487-168">例如，使用的<xref:System.IComparable>接口可以用于实现<xref:System.IComparable>。</xref:System.IComparable>任何数据类型</xref:System.IComparable>的项进行排序的泛型过程</span><span class="sxs-lookup"><span data-stu-id="ef487-168">For example, a generic procedure that sorts items using the <xref:System.IComparable> interface can be used with any data type that implements <xref:System.IComparable>.</span></span>  
  
## <a name="constraints"></a><span data-ttu-id="ef487-169">约束</span><span class="sxs-lookup"><span data-stu-id="ef487-169">Constraints</span></span>  
 <span data-ttu-id="ef487-170">虽然泛型类型定义中的代码应尽可能独立于类型，但你可能需要要求向泛型类型提供任何数据类型的某项功能。</span><span class="sxs-lookup"><span data-stu-id="ef487-170">Although the code in a generic type definition should be as type-independent as possible, you might need to require a certain capability of any data type supplied to your generic type.</span></span> <span data-ttu-id="ef487-171">例如，如果您想要比较两个项，以便在进行排序和排序规则，其数据类型必须实现<xref:System.IComparable>接口。</xref:System.IComparable></span><span class="sxs-lookup"><span data-stu-id="ef487-171">For example, if you want to compare two items for the purpose of sorting or collating, their data type must implement the <xref:System.IComparable> interface.</span></span> <span data-ttu-id="ef487-172">可通过向类型形参添加 *约束* 来强制实施此要求。</span><span class="sxs-lookup"><span data-stu-id="ef487-172">You can enforce this requirement by adding a *constraint* to the type parameter.</span></span>  
  
### <a name="example-of-a-constraint"></a><span data-ttu-id="ef487-173">约束的示例</span><span class="sxs-lookup"><span data-stu-id="ef487-173">Example of a Constraint</span></span>  
 <span data-ttu-id="ef487-174">下面的示例演示具有需要实现<xref:System.IComparable>。</xref:System.IComparable>让类型参数的约束的类的主干定义</span><span class="sxs-lookup"><span data-stu-id="ef487-174">The following example shows a skeleton definition of a class with a constraint that requires the type argument to implement <xref:System.IComparable>.</span></span>  
  
 <span data-ttu-id="ef487-175">[!code-vb[VbVbalrDataTypes #&5;](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-types_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="ef487-175">[!code-vb[VbVbalrDataTypes#5](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-types_5.vb)]</span></span>  
  
 <span data-ttu-id="ef487-176">如果后面的代码尝试构造一个类从`itemManager`提供了一个类型不实现<xref:System.IComparable>，编译器会引发错误。</xref:System.IComparable></span><span class="sxs-lookup"><span data-stu-id="ef487-176">If subsequent code attempts to construct a class from `itemManager` supplying a type that does not implement <xref:System.IComparable>, the compiler signals an error.</span></span>  
  
### <a name="types-of-constraints"></a><span data-ttu-id="ef487-177">约束的类型</span><span class="sxs-lookup"><span data-stu-id="ef487-177">Types of Constraints</span></span>  
 <span data-ttu-id="ef487-178">约束可以按任意组合指定下列要求：</span><span class="sxs-lookup"><span data-stu-id="ef487-178">Your constraint can specify the following requirements in any combination:</span></span>  
  
-   <span data-ttu-id="ef487-179">该类型实参必须实现一个或多个接口</span><span class="sxs-lookup"><span data-stu-id="ef487-179">The type argument must implement one or more interfaces</span></span>  
  
-   <span data-ttu-id="ef487-180">类型实参至多只能是一个类的类型，或至多只能从一个类继承</span><span class="sxs-lookup"><span data-stu-id="ef487-180">The type argument must be of the type of, or inherit from, at most one class</span></span>  
  
-   <span data-ttu-id="ef487-181">对于通过类型实参创建对象的代码，类型实参必须公开一个可供其访问的无参数构造函数</span><span class="sxs-lookup"><span data-stu-id="ef487-181">The type argument must expose a parameterless constructor accessible to the code that creates objects from it</span></span>  
  
-   <span data-ttu-id="ef487-182">类型实参必须是 *引用类型*或 *值类型*</span><span class="sxs-lookup"><span data-stu-id="ef487-182">The type argument must be a *reference type*, or it must be a *value type*</span></span>  
  
 <span data-ttu-id="ef487-183">如果需要强制实施多个要求，则可以使用以逗号分隔的 *约束列表* （括在大括号 (`{ }`) 内）。</span><span class="sxs-lookup"><span data-stu-id="ef487-183">If you need to impose more than one requirement, you use a comma-separated *constraint list* inside braces (`{ }`).</span></span> <span data-ttu-id="ef487-184">若要需要可访问构造函数，则包含[New 运算符](../../../../visual-basic/language-reference/operators/new-operator.md)列表中的关键字。</span><span class="sxs-lookup"><span data-stu-id="ef487-184">To require an accessible constructor, you include the [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) keyword in the list.</span></span> <span data-ttu-id="ef487-185">若需要引用类型，请加入 `Class` 关键字；若需要值类型，请加入 `Structure` 关键字。</span><span class="sxs-lookup"><span data-stu-id="ef487-185">To require a reference type, you include the `Class` keyword; to require a value type, you include the `Structure` keyword.</span></span>  
  
 <span data-ttu-id="ef487-186">有关约束的详细信息，请参阅[类型列表](../../../../visual-basic/language-reference/statements/type-list.md)。</span><span class="sxs-lookup"><span data-stu-id="ef487-186">For more information on constraints, see [Type List](../../../../visual-basic/language-reference/statements/type-list.md).</span></span>  
  
### <a name="example-of-multiple-constraints"></a><span data-ttu-id="ef487-187">多个约束的示例</span><span class="sxs-lookup"><span data-stu-id="ef487-187">Example of Multiple Constraints</span></span>  
 <span data-ttu-id="ef487-188">下面的示例演示了带有类型形参约束列表的泛型类的主干定义。</span><span class="sxs-lookup"><span data-stu-id="ef487-188">The following example shows a skeleton definition of a generic class with a constraint list on the type parameter.</span></span> <span data-ttu-id="ef487-189">在代码中创建此类的实例，类型参数必须同时实现<xref:System.IComparable>和<xref:System.IDisposable>接口，是引用类型，并公开访问的无参数构造函数。</xref:System.IDisposable> </xref:System.IComparable></span><span class="sxs-lookup"><span data-stu-id="ef487-189">In the code that creates an instance of this class, the type argument must implement both the <xref:System.IComparable> and <xref:System.IDisposable> interfaces, be a reference type, and expose an accessible parameterless constructor.</span></span>  
  
 <span data-ttu-id="ef487-190">[!code-vb[VbVbalrDataTypes #&6;](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-types_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="ef487-190">[!code-vb[VbVbalrDataTypes#6](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-types_6.vb)]</span></span>  
  
## <a name="important-terms"></a><span data-ttu-id="ef487-191">重要术语</span><span class="sxs-lookup"><span data-stu-id="ef487-191">Important Terms</span></span>  
 <span data-ttu-id="ef487-192">泛型类型引入并使用了以下术语：</span><span class="sxs-lookup"><span data-stu-id="ef487-192">Generic types introduce and use the following terms:</span></span>  
  
-   <span data-ttu-id="ef487-193">*泛型类型*。</span><span class="sxs-lookup"><span data-stu-id="ef487-193">*Generic Type*.</span></span> <span data-ttu-id="ef487-194">类、结构、接口、过程或委托的定义，在声明它们时要为它们提供至少一种数据类型。</span><span class="sxs-lookup"><span data-stu-id="ef487-194">A definition of a class, structure, interface, procedure, or delegate for which you supply at least one data type when you declare it.</span></span>  
  
-   <span data-ttu-id="ef487-195">*类型形参*。</span><span class="sxs-lookup"><span data-stu-id="ef487-195">*Type Parameter*.</span></span> <span data-ttu-id="ef487-196">在泛型类型定义中，你在声明数据类型时为其提供的占位符。</span><span class="sxs-lookup"><span data-stu-id="ef487-196">In a generic type definition, a placeholder for a data type you supply when you declare the type.</span></span>  
  
-   <span data-ttu-id="ef487-197">*类型实参*。</span><span class="sxs-lookup"><span data-stu-id="ef487-197">*Type Argument*.</span></span> <span data-ttu-id="ef487-198">一种特定的数据类型，用于在你通过泛型类型声明构造类型时替换类型形参。</span><span class="sxs-lookup"><span data-stu-id="ef487-198">A specific data type that replaces a type parameter when you declare a constructed type from a generic type.</span></span>  
  
-   <span data-ttu-id="ef487-199">*约束*。</span><span class="sxs-lookup"><span data-stu-id="ef487-199">*Constraint*.</span></span> <span data-ttu-id="ef487-200">关于类型形参的条件，用于限制可以为类型形参提供的类型实参。</span><span class="sxs-lookup"><span data-stu-id="ef487-200">A condition on a type parameter that restricts the type argument you can supply for it.</span></span> <span data-ttu-id="ef487-201">约束可以要求类型实参必须实现特定接口，必须是特定的类或继承自特定的类，必须具有可访问的无参数构造函数，或者必须是引用类型或值类型。</span><span class="sxs-lookup"><span data-stu-id="ef487-201">A constraint can require that the type argument must implement a particular interface, be or inherit from a particular class, have an accessible parameterless constructor, or be a reference type or a value type.</span></span> <span data-ttu-id="ef487-202">你可以组合这些约束，但至多只能指定一个类。</span><span class="sxs-lookup"><span data-stu-id="ef487-202">You can combine these constraints, but you can specify at most one class.</span></span>  
  
-   <span data-ttu-id="ef487-203">*构造类型*。</span><span class="sxs-lookup"><span data-stu-id="ef487-203">*Constructed Type*.</span></span> <span data-ttu-id="ef487-204">通过为泛型类型的类型形参提供类型实参，从泛型类型声明的类、结构、接口、过程或委托。</span><span class="sxs-lookup"><span data-stu-id="ef487-204">A class, structure, interface, procedure, or delegate declared from a generic type by supplying type arguments for its type parameters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef487-205">请参见</span><span class="sxs-lookup"><span data-stu-id="ef487-205">See Also</span></span>  
 <span data-ttu-id="ef487-206">[数据类型](../../../../visual-basic/programming-guide/language-features/data-types/index.md) </span><span class="sxs-lookup"><span data-stu-id="ef487-206">[Data Types](../../../../visual-basic/programming-guide/language-features/data-types/index.md) </span></span>  
<span data-ttu-id="ef487-207"> [类型字符](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md) </span><span class="sxs-lookup"><span data-stu-id="ef487-207"> [Type Characters](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md) </span></span>  
<span data-ttu-id="ef487-208"> [值类型和引用类型](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span><span class="sxs-lookup"><span data-stu-id="ef487-208"> [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span></span>  
<span data-ttu-id="ef487-209"> [在 Visual Basic 中的类型转换](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="ef487-209"> [Type Conversions in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span></span>  
<span data-ttu-id="ef487-210"> [数据类型疑难解答](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="ef487-210"> [Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span></span>  
<span data-ttu-id="ef487-211"> [数据类型](../../../../visual-basic/language-reference/data-types/data-type-summary.md) </span><span class="sxs-lookup"><span data-stu-id="ef487-211"> [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md) </span></span>  
<span data-ttu-id="ef487-212"> [Of](../../../../visual-basic/language-reference/statements/of-clause.md) </span><span class="sxs-lookup"><span data-stu-id="ef487-212"> [Of](../../../../visual-basic/language-reference/statements/of-clause.md) </span></span>  
<span data-ttu-id="ef487-213"> [作为](../../../../visual-basic/language-reference/statements/as-clause.md) </span><span class="sxs-lookup"><span data-stu-id="ef487-213"> [As](../../../../visual-basic/language-reference/statements/as-clause.md) </span></span>  
<span data-ttu-id="ef487-214"> [Object 数据类型](../../../../visual-basic/language-reference/data-types/object-data-type.md) </span><span class="sxs-lookup"><span data-stu-id="ef487-214"> [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) </span></span>  
<span data-ttu-id="ef487-215"> [协变和逆变](http://msdn.microsoft.com/library/a58cc086-276f-4f91-a366-85b7f95f38b8) </span><span class="sxs-lookup"><span data-stu-id="ef487-215"> [Covariance and Contravariance](http://msdn.microsoft.com/library/a58cc086-276f-4f91-a366-85b7f95f38b8) </span></span>  
<span data-ttu-id="ef487-216"> [迭代器](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)</span><span class="sxs-lookup"><span data-stu-id="ef487-216"> [Iterators](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)</span></span>
