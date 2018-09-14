---
title: Visual Basic 中的泛型类型 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- generic interfaces
- data type arguments [Visual Basic], defining
- generic delegates
- arguments [Visual Basic], data types
- Of keyword [Visual Basic], using
- delegates, generic
- constraints, Visual Basic generic types
- generic parameters
- data type parameters
- procedures [Visual Basic], generic
- generic procedures
- data types [Visual Basic], generic
- data types [Visual Basic], as parameters
- generics [Visual Basic], generic types
- data types [Visual Basic], as arguments
- generic classes [Visual Basic], Visual Basic
- parameters [Visual Basic], type
- type arguments
- interfaces [Visual Basic], generic
- generics [Visual Basic]
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- generic structures [Visual Basic]
- generic classes [Visual Basic]
- type parameters
- data type arguments
- structures [Visual Basic], generic
- parameters [Visual Basic], data type
- collections, generic
- classes [Visual Basic], generic
- data type parameters [Visual Basic], defining
- type arguments [Visual Basic], defining
- arguments [Visual Basic], type
ms.assetid: 89f771d9-ecbb-4737-88b8-116b63c6cf4d
ms.openlocfilehash: 3a419fb38d3b97b08c8aaa094265d8b426429ae4
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2018
ms.locfileid: "45591823"
---
# <a name="generic-types-in-visual-basic-visual-basic"></a><span data-ttu-id="09f9f-102">Visual Basic 中的泛型类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="09f9f-102">Generic Types in Visual Basic (Visual Basic)</span></span>
<span data-ttu-id="09f9f-103">*泛型类型* 是可适应对多种数据类型执行相同功能的单个编程元素。</span><span class="sxs-lookup"><span data-stu-id="09f9f-103">A *generic type* is a single programming element that adapts to perform the same functionality for a variety of data types.</span></span> <span data-ttu-id="09f9f-104">定义泛型类或过程时，无需为可能需要对其执行该功能的每个数据类型定义单独版本。</span><span class="sxs-lookup"><span data-stu-id="09f9f-104">When you define a generic class or procedure, you do not have to define a separate version for each data type for which you might want to perform that functionality.</span></span>  
  
 <span data-ttu-id="09f9f-105">就好比是带有可拆卸刀头的螺丝刀。</span><span class="sxs-lookup"><span data-stu-id="09f9f-105">An analogy is a screwdriver set with removable heads.</span></span> <span data-ttu-id="09f9f-106">你检查需要拧动的螺丝，然后选择适合该螺丝的刀头（一字、十字、星形）。</span><span class="sxs-lookup"><span data-stu-id="09f9f-106">You inspect the screw you need to turn and select the correct head for that screw (slotted, crossed, starred).</span></span> <span data-ttu-id="09f9f-107">将正确的刀头插入到螺丝刀柄上后，你就可以使用螺丝刀执行完全相同的功能，即拧螺丝。</span><span class="sxs-lookup"><span data-stu-id="09f9f-107">Once you insert the correct head in the screwdriver handle, you perform the exact same function with the screwdriver, namely turning the screw.</span></span>  
  
 <span data-ttu-id="09f9f-108">![作为通用工具的螺丝刀的示意图](../../../../visual-basic/programming-guide/language-features/data-types/media/genericscrewdriver.gif "GenericScrewDriver")</span><span class="sxs-lookup"><span data-stu-id="09f9f-108">![Diagram of a screwdriver set as a generic tool](../../../../visual-basic/programming-guide/language-features/data-types/media/genericscrewdriver.gif "GenericScrewDriver")</span></span>  
<span data-ttu-id="09f9f-109">作为通用工具的螺丝刀</span><span class="sxs-lookup"><span data-stu-id="09f9f-109">Screwdriver set as a generic tool</span></span>  
  
 <span data-ttu-id="09f9f-110">定义泛型类型时，即使用一个或多个数据类型将其参数化。</span><span class="sxs-lookup"><span data-stu-id="09f9f-110">When you define a generic type, you parameterize it with one or more data types.</span></span> <span data-ttu-id="09f9f-111">这样可允许使用代码定制数据类型以满足其要求。</span><span class="sxs-lookup"><span data-stu-id="09f9f-111">This allows the using code to tailor the data types to its requirements.</span></span> <span data-ttu-id="09f9f-112">代码可以通过泛型元素声明若干个不同的编程元素，每个元素可使用一组不同的数据类型。</span><span class="sxs-lookup"><span data-stu-id="09f9f-112">Your code can declare several different programming elements from the generic element, each one acting on a different set of data types.</span></span> <span data-ttu-id="09f9f-113">但是，无论声明的元素使用哪些数据类型，它们均执行相同的逻辑。</span><span class="sxs-lookup"><span data-stu-id="09f9f-113">But the declared elements all perform the identical logic, no matter what data types they are using.</span></span>  
  
 <span data-ttu-id="09f9f-114">例如，你可能想创建并使用一个处理特定数据类型（例如 `String`）的队列类。</span><span class="sxs-lookup"><span data-stu-id="09f9f-114">For example, you might want to create and use a queue class that operates on a specific data type such as `String`.</span></span> <span data-ttu-id="09f9f-115">您可以声明这样的类从<xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType>，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="09f9f-115">You can declare such a class from <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType>, as the following example shows.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#1](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-types_1.vb)]  
  
 <span data-ttu-id="09f9f-116">现在，可以使用 `stringQ` 来专门处理 `String` 值。</span><span class="sxs-lookup"><span data-stu-id="09f9f-116">You can now use `stringQ` to work exclusively with `String` values.</span></span> <span data-ttu-id="09f9f-117">由于 `stringQ` 专用于 `String` 而未针对 `Object` 值进行泛型化，因此，不会有晚期绑定或类型转换。</span><span class="sxs-lookup"><span data-stu-id="09f9f-117">Because `stringQ` is specific for `String` instead of being generalized for `Object` values, you do not have late binding or type conversion.</span></span> <span data-ttu-id="09f9f-118">从而节省了执行时间并减少了运行时错误。</span><span class="sxs-lookup"><span data-stu-id="09f9f-118">This saves execution time and reduces run-time errors.</span></span>  
  
 <span data-ttu-id="09f9f-119">有关使用泛型类型的更多信息，请参阅 [How to: Use a Generic Class](../../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)。</span><span class="sxs-lookup"><span data-stu-id="09f9f-119">For more information on using a generic type, see [How to: Use a Generic Class](../../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md).</span></span>  
  
## <a name="example-of-a-generic-class"></a><span data-ttu-id="09f9f-120">泛型类的示例。</span><span class="sxs-lookup"><span data-stu-id="09f9f-120">Example of a Generic Class</span></span>  
 <span data-ttu-id="09f9f-121">下面的示例演示了泛型类的主干定义。</span><span class="sxs-lookup"><span data-stu-id="09f9f-121">The following example shows a skeleton definition of a generic class.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#2](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-types_2.vb)]  
  
 <span data-ttu-id="09f9f-122">在上面的主干中， `t` 是一个 *类型形参*，即你在声明此类时提供的数据类型的占位符。</span><span class="sxs-lookup"><span data-stu-id="09f9f-122">In the preceding skeleton, `t` is a *type parameter*, that is, a placeholder for a data type that you supply when you declare the class.</span></span> <span data-ttu-id="09f9f-123">在代码中的其他地方，可以通过为 `classHolder` 提供不同的数据类型来声明不同版本的 `t`</span><span class="sxs-lookup"><span data-stu-id="09f9f-123">Elsewhere in your code, you can declare various versions of `classHolder` by supplying various data types for `t`.</span></span> <span data-ttu-id="09f9f-124">下面的示例演示了两个此类声明。</span><span class="sxs-lookup"><span data-stu-id="09f9f-124">The following example shows two such declarations.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#3](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-types_3.vb)]  
  
 <span data-ttu-id="09f9f-125">上面的语句声明了 *构造类*，在这些类中，特定的类型替换了类型形参。</span><span class="sxs-lookup"><span data-stu-id="09f9f-125">The preceding statements declare *constructed classes*, in which a specific type replaces the type parameter.</span></span> <span data-ttu-id="09f9f-126">此类替换会在构造类中的代码内进行传播。</span><span class="sxs-lookup"><span data-stu-id="09f9f-126">This replacement is propagated throughout the code within the constructed class.</span></span> <span data-ttu-id="09f9f-127">下面的示例显示了 `processNewItem` 过程在 `integerClass`中的外观。</span><span class="sxs-lookup"><span data-stu-id="09f9f-127">The following example shows what the `processNewItem` procedure looks like in `integerClass`.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#4](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-types_4.vb)]  
  
 <span data-ttu-id="09f9f-128">有关更完整的示例，请参阅[如何： 对不同数据类型定义类，可以提供相同的功能](../../../../visual-basic/programming-guide/language-features/data-types/how-to-define-a-class-that-can-provide-identical-functionality.md)。</span><span class="sxs-lookup"><span data-stu-id="09f9f-128">For a more complete example, see [How to: Define a Class That Can Provide Identical Functionality on Different Data Types](../../../../visual-basic/programming-guide/language-features/data-types/how-to-define-a-class-that-can-provide-identical-functionality.md).</span></span>  
  
## <a name="eligible-programming-elements"></a><span data-ttu-id="09f9f-129">合格的编程元素</span><span class="sxs-lookup"><span data-stu-id="09f9f-129">Eligible Programming Elements</span></span>  
 <span data-ttu-id="09f9f-130">你可以定义并使用泛型类、结构、接口、过程和委托。</span><span class="sxs-lookup"><span data-stu-id="09f9f-130">You can define and use generic classes, structures, interfaces, procedures, and delegates.</span></span> <span data-ttu-id="09f9f-131">请注意， [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 定义了几个代表常用泛型元素的泛型类、结构和接口。</span><span class="sxs-lookup"><span data-stu-id="09f9f-131">Note that the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] defines several generic classes, structures, and interfaces that represent commonly used generic elements.</span></span> <span data-ttu-id="09f9f-132"><xref:System.Collections.Generic?displayProperty=nameWithType>命名空间提供字典、 列表、 队列和堆栈。</span><span class="sxs-lookup"><span data-stu-id="09f9f-132">The <xref:System.Collections.Generic?displayProperty=nameWithType> namespace provides dictionaries, lists, queues, and stacks.</span></span> <span data-ttu-id="09f9f-133">在定义您自己的泛型元素之前, 查看它是否已推出<xref:System.Collections.Generic?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="09f9f-133">Before defining your own generic element, see if it is already available in <xref:System.Collections.Generic?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="09f9f-134">过程不是类型，但可以定义并使用泛型过程。</span><span class="sxs-lookup"><span data-stu-id="09f9f-134">Procedures are not types, but you can define and use generic procedures.</span></span> <span data-ttu-id="09f9f-135">请参阅 [Generic Procedures in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="09f9f-135">See [Generic Procedures in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md).</span></span>  
  
## <a name="advantages-of-generic-types"></a><span data-ttu-id="09f9f-136">泛型类型的优点</span><span class="sxs-lookup"><span data-stu-id="09f9f-136">Advantages of Generic Types</span></span>  
 <span data-ttu-id="09f9f-137">泛型类型用作声明几个不同编程元素的基础，而每个元素均处理特定的数据类型。</span><span class="sxs-lookup"><span data-stu-id="09f9f-137">A generic type serves as a basis for declaring several different programming elements, each of which operates on a specific data type.</span></span> <span data-ttu-id="09f9f-138">泛型类型的替代项有：</span><span class="sxs-lookup"><span data-stu-id="09f9f-138">The alternatives to a generic type are:</span></span>  
  
1.  <span data-ttu-id="09f9f-139">对 `Object` 数据类型进行处理的单一类型。</span><span class="sxs-lookup"><span data-stu-id="09f9f-139">A single type operating on the `Object` data type.</span></span>  
  
2.  <span data-ttu-id="09f9f-140">一组 *特定于类型* 的类型版本，每个版本单独进行编码并处理一种特定的数据类型（如 `String`、 `Integer`）或用户定义的类型（如 `customer`）。</span><span class="sxs-lookup"><span data-stu-id="09f9f-140">A set of *type-specific* versions of the type, each version individually coded and operating on one specific data type such as `String`, `Integer`, or a user-defined type such as `customer`.</span></span>  
  
 <span data-ttu-id="09f9f-141">与上述替代项相比，泛型类型具有以下优点：</span><span class="sxs-lookup"><span data-stu-id="09f9f-141">A generic type has the following advantages over these alternatives:</span></span>  
  
-   <span data-ttu-id="09f9f-142">**类型安全。**</span><span class="sxs-lookup"><span data-stu-id="09f9f-142">**Type Safety.**</span></span> <span data-ttu-id="09f9f-143">泛型类型强制实施编译时类型检查。</span><span class="sxs-lookup"><span data-stu-id="09f9f-143">Generic types enforce compile-time type checking.</span></span> <span data-ttu-id="09f9f-144">而基于 `Object` 的类型可接受任何数据类型，因此，你必须编写代码以检查是否可接受某种输入数据类型。</span><span class="sxs-lookup"><span data-stu-id="09f9f-144">Types based on `Object` accept any data type, and you must write code to check whether an input data type is acceptable.</span></span> <span data-ttu-id="09f9f-145">通过泛型类型，编译器可以在运行时之前捕获类型的不匹配。</span><span class="sxs-lookup"><span data-stu-id="09f9f-145">With generic types, the compiler can catch type mismatches before run time.</span></span>  
  
-   <span data-ttu-id="09f9f-146">**性能。**</span><span class="sxs-lookup"><span data-stu-id="09f9f-146">**Performance.**</span></span> <span data-ttu-id="09f9f-147">泛型类型无需对数据进行 *装箱* 和 *取消装箱* 操作，原因是每种泛型类型均专用于一种数据类型。</span><span class="sxs-lookup"><span data-stu-id="09f9f-147">Generic types do not have to *box* and *unbox* data, because each one is specialized for one data type.</span></span> <span data-ttu-id="09f9f-148">而基于 `Object` 的操作必须将输入数据类型进行装箱，以将它们转换为 `Object` ，而且还将对预定输出的数据进行取消装箱操作。</span><span class="sxs-lookup"><span data-stu-id="09f9f-148">Operations based on `Object` must box input data types to convert them to `Object` and unbox data destined for output.</span></span> <span data-ttu-id="09f9f-149">装箱和取消装箱操作会降低性能。</span><span class="sxs-lookup"><span data-stu-id="09f9f-149">Boxing and unboxing reduce performance.</span></span>  
  
     <span data-ttu-id="09f9f-150">此外，还要对基于 `Object` 的类型进行晚期绑定，这意味着需要编写额外的代码才能在运行时访问它们的成员。</span><span class="sxs-lookup"><span data-stu-id="09f9f-150">Types based on `Object` are also late-bound, which means that accessing their members requires extra code at run time.</span></span> <span data-ttu-id="09f9f-151">这同样会降低性能。</span><span class="sxs-lookup"><span data-stu-id="09f9f-151">This also reduces performance.</span></span>  
  
-   <span data-ttu-id="09f9f-152">**代码合并。**</span><span class="sxs-lookup"><span data-stu-id="09f9f-152">**Code Consolidation.**</span></span> <span data-ttu-id="09f9f-153">只能对泛型类型中的代码定义一次。</span><span class="sxs-lookup"><span data-stu-id="09f9f-153">The code in a generic type has to be defined only once.</span></span> <span data-ttu-id="09f9f-154">而一组特定于类型的类型版本必须在每个版本中复制相同的代码，唯一的不同就是该版本的特定数据类型。</span><span class="sxs-lookup"><span data-stu-id="09f9f-154">A set of type-specific versions of a type must replicate the same code in each version, with the only difference being the specific data type for that version.</span></span> <span data-ttu-id="09f9f-155">利用泛型类型，特定于类型的版本全都利用原始的泛型类型生成。</span><span class="sxs-lookup"><span data-stu-id="09f9f-155">With generic types, the type-specific versions are all generated from the original generic type.</span></span>  
  
-   <span data-ttu-id="09f9f-156">**代码重用。**</span><span class="sxs-lookup"><span data-stu-id="09f9f-156">**Code Reuse.**</span></span> <span data-ttu-id="09f9f-157">对于不依赖特定数据类型的泛型代码，可以利用不同的数据类型重用它。</span><span class="sxs-lookup"><span data-stu-id="09f9f-157">Code that does not depend on a particular data type can be reused with various data types if it is generic.</span></span> <span data-ttu-id="09f9f-158">你可以经常重用此类代码（甚至利用最初未预料到的数据类型来重用它）。</span><span class="sxs-lookup"><span data-stu-id="09f9f-158">You can often reuse it even with a data type that you did not originally predict.</span></span>  
  
-   <span data-ttu-id="09f9f-159">**IDE 支持。**</span><span class="sxs-lookup"><span data-stu-id="09f9f-159">**IDE Support.**</span></span> <span data-ttu-id="09f9f-160">在使用通过泛型类型声明的构造类型时，集成开发环境 (IDE) 可以在你开发代码时给予更多的支持。</span><span class="sxs-lookup"><span data-stu-id="09f9f-160">When you use a constructed type declared from a generic type, the integrated development environment (IDE) can give you more support while you are developing your code.</span></span> <span data-ttu-id="09f9f-161">例如，IntelliSense 可以显示适用于构造函数或方法的某个参数的特定于类型的选项。</span><span class="sxs-lookup"><span data-stu-id="09f9f-161">For example, IntelliSense can show you the type-specific options for an argument to a constructor or method.</span></span>  
  
-   <span data-ttu-id="09f9f-162">**泛型算法。**</span><span class="sxs-lookup"><span data-stu-id="09f9f-162">**Generic Algorithms.**</span></span> <span data-ttu-id="09f9f-163">独立于类型的抽象算法非常适用于泛型类型。</span><span class="sxs-lookup"><span data-stu-id="09f9f-163">Abstract algorithms that are type-independent are good candidates for generic types.</span></span> <span data-ttu-id="09f9f-164">例如，可以将使用 <xref:System.IComparable> 接口对项进行排序的泛型过程用于可实现 <xref:System.IComparable>的任何数据类型。</span><span class="sxs-lookup"><span data-stu-id="09f9f-164">For example, a generic procedure that sorts items using the <xref:System.IComparable> interface can be used with any data type that implements <xref:System.IComparable>.</span></span>  
  
## <a name="constraints"></a><span data-ttu-id="09f9f-165">约束</span><span class="sxs-lookup"><span data-stu-id="09f9f-165">Constraints</span></span>  
 <span data-ttu-id="09f9f-166">虽然泛型类型定义中的代码应尽可能独立于类型，但你可能需要要求向泛型类型提供任何数据类型的某项功能。</span><span class="sxs-lookup"><span data-stu-id="09f9f-166">Although the code in a generic type definition should be as type-independent as possible, you might need to require a certain capability of any data type supplied to your generic type.</span></span> <span data-ttu-id="09f9f-167">例如，如果出于排序或对照的目的而想比较两个项，则它们的数据类型必须实现 <xref:System.IComparable> 接口。</span><span class="sxs-lookup"><span data-stu-id="09f9f-167">For example, if you want to compare two items for the purpose of sorting or collating, their data type must implement the <xref:System.IComparable> interface.</span></span> <span data-ttu-id="09f9f-168">可通过向类型形参添加 *约束* 来强制实施此要求。</span><span class="sxs-lookup"><span data-stu-id="09f9f-168">You can enforce this requirement by adding a *constraint* to the type parameter.</span></span>  
  
### <a name="example-of-a-constraint"></a><span data-ttu-id="09f9f-169">约束的示例</span><span class="sxs-lookup"><span data-stu-id="09f9f-169">Example of a Constraint</span></span>  
 <span data-ttu-id="09f9f-170">下面的示例演示了带有约束（要求类型实参实现 <xref:System.IComparable>）的类的主干定义。</span><span class="sxs-lookup"><span data-stu-id="09f9f-170">The following example shows a skeleton definition of a class with a constraint that requires the type argument to implement <xref:System.IComparable>.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#5](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-types_5.vb)]  
  
 <span data-ttu-id="09f9f-171">如果后续代码尝试从提供未实现 `itemManager` 的类型的 <xref:System.IComparable>中构造一个类，则编译器会提示错误。</span><span class="sxs-lookup"><span data-stu-id="09f9f-171">If subsequent code attempts to construct a class from `itemManager` supplying a type that does not implement <xref:System.IComparable>, the compiler signals an error.</span></span>  
  
### <a name="types-of-constraints"></a><span data-ttu-id="09f9f-172">约束的类型</span><span class="sxs-lookup"><span data-stu-id="09f9f-172">Types of Constraints</span></span>  
 <span data-ttu-id="09f9f-173">约束可以按任意组合指定下列要求：</span><span class="sxs-lookup"><span data-stu-id="09f9f-173">Your constraint can specify the following requirements in any combination:</span></span>  
  
-   <span data-ttu-id="09f9f-174">该类型实参必须实现一个或多个接口</span><span class="sxs-lookup"><span data-stu-id="09f9f-174">The type argument must implement one or more interfaces</span></span>  
  
-   <span data-ttu-id="09f9f-175">类型实参至多只能是一个类的类型，或至多只能从一个类继承</span><span class="sxs-lookup"><span data-stu-id="09f9f-175">The type argument must be of the type of, or inherit from, at most one class</span></span>  
  
-   <span data-ttu-id="09f9f-176">对于通过类型实参创建对象的代码，类型实参必须公开一个可供其访问的无参数构造函数</span><span class="sxs-lookup"><span data-stu-id="09f9f-176">The type argument must expose a parameterless constructor accessible to the code that creates objects from it</span></span>  
  
-   <span data-ttu-id="09f9f-177">类型实参必须是 *引用类型*或 *值类型*</span><span class="sxs-lookup"><span data-stu-id="09f9f-177">The type argument must be a *reference type*, or it must be a *value type*</span></span>  
  
 <span data-ttu-id="09f9f-178">如果需要强制实施多个要求，则可以使用以逗号分隔的 *约束列表* （括在大括号 (`{ }`) 内）。</span><span class="sxs-lookup"><span data-stu-id="09f9f-178">If you need to impose more than one requirement, you use a comma-separated *constraint list* inside braces (`{ }`).</span></span> <span data-ttu-id="09f9f-179">若要要求可访问的构造函数，则包含[New 运算符](../../../../visual-basic/language-reference/operators/new-operator.md)列表中的关键字。</span><span class="sxs-lookup"><span data-stu-id="09f9f-179">To require an accessible constructor, you include the [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) keyword in the list.</span></span> <span data-ttu-id="09f9f-180">若需要引用类型，请加入 `Class` 关键字；若需要值类型，请加入 `Structure` 关键字。</span><span class="sxs-lookup"><span data-stu-id="09f9f-180">To require a reference type, you include the `Class` keyword; to require a value type, you include the `Structure` keyword.</span></span>  
  
 <span data-ttu-id="09f9f-181">有关约束的详细信息，请参阅 [Type List](../../../../visual-basic/language-reference/statements/type-list.md)。</span><span class="sxs-lookup"><span data-stu-id="09f9f-181">For more information on constraints, see [Type List](../../../../visual-basic/language-reference/statements/type-list.md).</span></span>  
  
### <a name="example-of-multiple-constraints"></a><span data-ttu-id="09f9f-182">多个约束的示例</span><span class="sxs-lookup"><span data-stu-id="09f9f-182">Example of Multiple Constraints</span></span>  
 <span data-ttu-id="09f9f-183">下面的示例演示了带有类型形参约束列表的泛型类的主干定义。</span><span class="sxs-lookup"><span data-stu-id="09f9f-183">The following example shows a skeleton definition of a generic class with a constraint list on the type parameter.</span></span> <span data-ttu-id="09f9f-184">在创建此类的实例的代码中，类型实参必须实现 <xref:System.IComparable> 和 <xref:System.IDisposable> 接口，必须是引用类型，并且必须公开一个可访问的无参数构造函数。</span><span class="sxs-lookup"><span data-stu-id="09f9f-184">In the code that creates an instance of this class, the type argument must implement both the <xref:System.IComparable> and <xref:System.IDisposable> interfaces, be a reference type, and expose an accessible parameterless constructor.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#6](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-types_6.vb)]  
  
## <a name="important-terms"></a><span data-ttu-id="09f9f-185">重要术语</span><span class="sxs-lookup"><span data-stu-id="09f9f-185">Important Terms</span></span>  
 <span data-ttu-id="09f9f-186">泛型类型引入并使用了以下术语：</span><span class="sxs-lookup"><span data-stu-id="09f9f-186">Generic types introduce and use the following terms:</span></span>  
  
-   <span data-ttu-id="09f9f-187">*泛型类型*。</span><span class="sxs-lookup"><span data-stu-id="09f9f-187">*Generic Type*.</span></span> <span data-ttu-id="09f9f-188">类、结构、接口、过程或委托的定义，在声明它们时要为它们提供至少一种数据类型。</span><span class="sxs-lookup"><span data-stu-id="09f9f-188">A definition of a class, structure, interface, procedure, or delegate for which you supply at least one data type when you declare it.</span></span>  
  
-   <span data-ttu-id="09f9f-189">*类型形参*。</span><span class="sxs-lookup"><span data-stu-id="09f9f-189">*Type Parameter*.</span></span> <span data-ttu-id="09f9f-190">在泛型类型定义中，你在声明数据类型时为其提供的占位符。</span><span class="sxs-lookup"><span data-stu-id="09f9f-190">In a generic type definition, a placeholder for a data type you supply when you declare the type.</span></span>  
  
-   <span data-ttu-id="09f9f-191">*类型实参*。</span><span class="sxs-lookup"><span data-stu-id="09f9f-191">*Type Argument*.</span></span> <span data-ttu-id="09f9f-192">一种特定的数据类型，用于在你通过泛型类型声明构造类型时替换类型形参。</span><span class="sxs-lookup"><span data-stu-id="09f9f-192">A specific data type that replaces a type parameter when you declare a constructed type from a generic type.</span></span>  
  
-   <span data-ttu-id="09f9f-193">*约束*。</span><span class="sxs-lookup"><span data-stu-id="09f9f-193">*Constraint*.</span></span> <span data-ttu-id="09f9f-194">关于类型形参的条件，用于限制可以为类型形参提供的类型实参。</span><span class="sxs-lookup"><span data-stu-id="09f9f-194">A condition on a type parameter that restricts the type argument you can supply for it.</span></span> <span data-ttu-id="09f9f-195">约束可以要求类型实参必须实现特定接口，必须是特定的类或继承自特定的类，必须具有可访问的无参数构造函数，或者必须是引用类型或值类型。</span><span class="sxs-lookup"><span data-stu-id="09f9f-195">A constraint can require that the type argument must implement a particular interface, be or inherit from a particular class, have an accessible parameterless constructor, or be a reference type or a value type.</span></span> <span data-ttu-id="09f9f-196">你可以组合这些约束，但至多只能指定一个类。</span><span class="sxs-lookup"><span data-stu-id="09f9f-196">You can combine these constraints, but you can specify at most one class.</span></span>  
  
-   <span data-ttu-id="09f9f-197">*构造类型*。</span><span class="sxs-lookup"><span data-stu-id="09f9f-197">*Constructed Type*.</span></span> <span data-ttu-id="09f9f-198">通过为泛型类型的类型形参提供类型实参，从泛型类型声明的类、结构、接口、过程或委托。</span><span class="sxs-lookup"><span data-stu-id="09f9f-198">A class, structure, interface, procedure, or delegate declared from a generic type by supplying type arguments for its type parameters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09f9f-199">请参阅</span><span class="sxs-lookup"><span data-stu-id="09f9f-199">See also</span></span>

- [<span data-ttu-id="09f9f-200">数据类型</span><span class="sxs-lookup"><span data-stu-id="09f9f-200">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
- [<span data-ttu-id="09f9f-201">类型字符</span><span class="sxs-lookup"><span data-stu-id="09f9f-201">Type Characters</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)  
- [<span data-ttu-id="09f9f-202">值类型和引用类型</span><span class="sxs-lookup"><span data-stu-id="09f9f-202">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
- [<span data-ttu-id="09f9f-203">在 Visual Basic 中的类型转换</span><span class="sxs-lookup"><span data-stu-id="09f9f-203">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
- [<span data-ttu-id="09f9f-204">数据类型疑难解答</span><span class="sxs-lookup"><span data-stu-id="09f9f-204">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
- [<span data-ttu-id="09f9f-205">数据类型</span><span class="sxs-lookup"><span data-stu-id="09f9f-205">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)  
- [<span data-ttu-id="09f9f-206">Of</span><span class="sxs-lookup"><span data-stu-id="09f9f-206">Of</span></span>](../../../../visual-basic/language-reference/statements/of-clause.md)  
- [<span data-ttu-id="09f9f-207">As</span><span class="sxs-lookup"><span data-stu-id="09f9f-207">As</span></span>](../../../../visual-basic/language-reference/statements/as-clause.md)  
- [<span data-ttu-id="09f9f-208">Object 数据类型</span><span class="sxs-lookup"><span data-stu-id="09f9f-208">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)  
- [<span data-ttu-id="09f9f-209">协变和逆变</span><span class="sxs-lookup"><span data-stu-id="09f9f-209">Covariance and Contravariance</span></span>](../../concepts/covariance-contravariance/index.md)  
- [<span data-ttu-id="09f9f-210">迭代器</span><span class="sxs-lookup"><span data-stu-id="09f9f-210">Iterators</span></span>](../../../../visual-basic/programming-guide/concepts/iterators.md)
