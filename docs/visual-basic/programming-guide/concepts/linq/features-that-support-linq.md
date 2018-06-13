---
title: 支持 LINQ 的 Visual Basic 功能
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic, LINQ features
- LINQ [Visual Basic], features supporting LINQ
ms.assetid: c821bb50-b6f6-4cf9-8aba-2717e465bd3a
ms.openlocfilehash: db2eff2f7c19a3c510e7b212f5bb406d7a885439
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33643895"
---
# <a name="visual-basic-features-that-support-linq"></a><span data-ttu-id="00ea7-102">支持 LINQ 的 Visual Basic 功能</span><span class="sxs-lookup"><span data-stu-id="00ea7-102">Visual Basic Features That Support LINQ</span></span>
<span data-ttu-id="00ea7-103">名称[!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]指在 Visual Basic 支持查询语法和其他语言构造直接在语言中的技术。</span><span class="sxs-lookup"><span data-stu-id="00ea7-103">The name [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] refers to technology in Visual Basic that supports query syntax and other language constructs directly in the language.</span></span> <span data-ttu-id="00ea7-104">与[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]，则不需要了解对外部数据源执行查询的新语言。</span><span class="sxs-lookup"><span data-stu-id="00ea7-104">With [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], you do not have to learn a new language to query against an external data source.</span></span> <span data-ttu-id="00ea7-105">可以使用 Visual Basic 查询针对关系数据库、 XML 存储区或对象中的数据。</span><span class="sxs-lookup"><span data-stu-id="00ea7-105">You can query against data in relational databases, XML stores, or objects by using Visual Basic.</span></span> <span data-ttu-id="00ea7-106">查询功能语言编程到此集成使编译时检查语法错误和类型安全。</span><span class="sxs-lookup"><span data-stu-id="00ea7-106">This integration of query capabilities into the language enables compile-time checking for syntax errors and type safety.</span></span> <span data-ttu-id="00ea7-107">此集成还可确保你已经知道你需要知道要在 Visual Basic 中编写丰富、 不同的查询的大部分。</span><span class="sxs-lookup"><span data-stu-id="00ea7-107">This integration also ensures that you already know most of what you have to know to write rich, varied queries in Visual Basic.</span></span>  
  
 <span data-ttu-id="00ea7-108">以下各节描述了足够的详细信息，以便你开始读取的介绍性文档、 代码示例和示例应用程序中支持 LINQ 的语言构造。</span><span class="sxs-lookup"><span data-stu-id="00ea7-108">The following sections describe the language constructs that support LINQ in enough detail to enable you to get started in reading the introductory documentation, code examples, and sample applications.</span></span> <span data-ttu-id="00ea7-109">您也可以单击链接，以了解如何的语言功能结合使用才能启用语言集成查询的更详细的解释。</span><span class="sxs-lookup"><span data-stu-id="00ea7-109">You can also click the links to find more detailed explanations of how the language features come together to enable language-integrated query.</span></span> <span data-ttu-id="00ea7-110">启动的好时机是[演练： 在 Visual Basic 中编写查询](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)。</span><span class="sxs-lookup"><span data-stu-id="00ea7-110">A good place to start is [Walkthrough: Writing Queries in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md).</span></span>  
  
## <a name="query-expressions"></a><span data-ttu-id="00ea7-111">查询表达式</span><span class="sxs-lookup"><span data-stu-id="00ea7-111">Query Expressions</span></span>  
 <span data-ttu-id="00ea7-112">在 Visual Basic 中的查询表达式可以表示类似于 SQL 或 XQuery 的声明性语法。</span><span class="sxs-lookup"><span data-stu-id="00ea7-112">Query expressions in Visual Basic can be expressed in a declarative syntax similar to that of SQL or XQuery.</span></span> <span data-ttu-id="00ea7-113">在编译时，查询语法将转换为对标准查询运算符扩展方法的 LINQ 提供程序实现的方法调用。</span><span class="sxs-lookup"><span data-stu-id="00ea7-113">At compile time, query syntax is converted into method calls to a LINQ provider's implementation of the standard query operator extension methods.</span></span> <span data-ttu-id="00ea7-114">应用程序控件的标准查询运算符在作用域中通过指定适当的命名空间与`Imports`语句。</span><span class="sxs-lookup"><span data-stu-id="00ea7-114">Applications control which standard query operators are in scope by specifying the appropriate namespace with an `Imports` statement.</span></span> <span data-ttu-id="00ea7-115">Visual Basic 查询表达式的语法如下所示：</span><span class="sxs-lookup"><span data-stu-id="00ea7-115">Syntax for a Visual Basic query expression looks like this:</span></span>  
  
 [!code-vb[VbLINQVbFeatures#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_1.vb)]  
  
 <span data-ttu-id="00ea7-116">有关详细信息，请参阅[Visual Basic 中的 LINQ 简介](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)。</span><span class="sxs-lookup"><span data-stu-id="00ea7-116">For more information, see [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md).</span></span>  
  
## <a name="implicitly-typed-variables"></a><span data-ttu-id="00ea7-117">隐式类型化的变量</span><span class="sxs-lookup"><span data-stu-id="00ea7-117">Implicitly Typed Variables</span></span>  
 <span data-ttu-id="00ea7-118">而不是显式指定类型声明和初始化变量时，你可以启用编译器推导出，分配类型。</span><span class="sxs-lookup"><span data-stu-id="00ea7-118">Instead of explicitly specifying a type when you declare and initialize a variable, you can enable the compiler to infer and assign the type.</span></span> <span data-ttu-id="00ea7-119">这称为*局部类型推理*。</span><span class="sxs-lookup"><span data-stu-id="00ea7-119">This is referred to as *local type inference*.</span></span>  
  
 <span data-ttu-id="00ea7-120">变量的类型推断强类型，就像你显式指定其类型的变量一样。</span><span class="sxs-lookup"><span data-stu-id="00ea7-120">Variables whose types are inferred are strongly typed, just like variables whose type you specify explicitly.</span></span> <span data-ttu-id="00ea7-121">局部类型推理仅适用于你正在定义方法主体内的本地变量。</span><span class="sxs-lookup"><span data-stu-id="00ea7-121">Local type inference works only when you are defining a local variable inside a method body.</span></span> <span data-ttu-id="00ea7-122">有关详细信息，请参阅[Option Infer 语句](../../../../visual-basic/language-reference/statements/option-infer-statement.md)和[本地类型推理](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)。</span><span class="sxs-lookup"><span data-stu-id="00ea7-122">For more information, see [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md) and [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>  
  
 <span data-ttu-id="00ea7-123">下面的示例阐释了局部类型推理。</span><span class="sxs-lookup"><span data-stu-id="00ea7-123">The following example illustrates local type inference.</span></span> <span data-ttu-id="00ea7-124">若要使用此示例，必须设置`Option Infer`到`On`。</span><span class="sxs-lookup"><span data-stu-id="00ea7-124">To use this example, you must set `Option Infer` to `On`.</span></span>  
  
 [!code-vb[VbLINQVbFeatures#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_2.vb)]  
  
 <span data-ttu-id="00ea7-125">局部类型推理还使可以创建匿名类型，也不能在本部分稍后介绍 LINQ 查询所必需的。</span><span class="sxs-lookup"><span data-stu-id="00ea7-125">Local type inference also makes it possible to create anonymous types, which are described later in this section and are necessary for LINQ queries.</span></span>  
  
 <span data-ttu-id="00ea7-126">在以下 LINQ 示例中，会发生类型推理如果`Option Infer`是`On`或`Off`。</span><span class="sxs-lookup"><span data-stu-id="00ea7-126">In the following LINQ example, type inference occurs if `Option Infer` is either `On` or `Off`.</span></span> <span data-ttu-id="00ea7-127">如果，则会发生编译时错误`Option Infer`是`Off`和`Option Strict`是`On`。</span><span class="sxs-lookup"><span data-stu-id="00ea7-127">A compile-time error occurs if `Option Infer` is `Off` and `Option Strict` is `On`.</span></span>  
  
 [!code-vb[VbLINQVbFeatures#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_3.vb)]  
  
## <a name="object-initializers"></a><span data-ttu-id="00ea7-128">对象初始值设定项</span><span class="sxs-lookup"><span data-stu-id="00ea7-128">Object Initializers</span></span>  
 <span data-ttu-id="00ea7-129">当您必须创建一个匿名类型来保存查询的结果时，将在查询表达式中使用对象初始值设定项。</span><span class="sxs-lookup"><span data-stu-id="00ea7-129">Object initializers are used in query expressions when you have to create an anonymous type to hold the results of a query.</span></span> <span data-ttu-id="00ea7-130">它们还可以用于初始化命名外部的类型的查询的对象。</span><span class="sxs-lookup"><span data-stu-id="00ea7-130">They also can be used to initialize objects of named types outside of queries.</span></span> <span data-ttu-id="00ea7-131">通过使用对象初始值设定项，可以无需显式调用构造函数初始化单个行中的对象。</span><span class="sxs-lookup"><span data-stu-id="00ea7-131">By using an object initializer, you can initialize an object in a single line without explicitly calling a constructor.</span></span> <span data-ttu-id="00ea7-132">假设你有一个名为类`Customer`该类具有公共`Name`和`Phone`属性，以及其他属性，可以按照此方式使用对象初始值设定项：</span><span class="sxs-lookup"><span data-stu-id="00ea7-132">Assuming that you have a class named `Customer` that has public `Name` and `Phone` properties, along with other properties, an object initializer can be used in this manner:</span></span>  
  
 [!code-vb[VbLINQVbFeatures#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_4.vb)]  
  
 <span data-ttu-id="00ea7-133">有关详细信息，请参阅[对象初始值设定项： 命名类型和匿名类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)。</span><span class="sxs-lookup"><span data-stu-id="00ea7-133">For more information, see [Object Initializers: Named and Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md).</span></span>  
  
## <a name="anonymous-types"></a><span data-ttu-id="00ea7-134">匿名类型</span><span class="sxs-lookup"><span data-stu-id="00ea7-134">Anonymous Types</span></span>  
 <span data-ttu-id="00ea7-135">匿名类型提供一种简便方式暂时到你想要在查询结果中包含的元素进行分组的一组属性。</span><span class="sxs-lookup"><span data-stu-id="00ea7-135">Anonymous types provide a convenient way to temporarily group a set of properties into an element that you want to include in a query result.</span></span> <span data-ttu-id="00ea7-136">这使你可以在查询中，按任何顺序中，选择可用字段的任意组合，但不定义元素的已命名的数据类型。</span><span class="sxs-lookup"><span data-stu-id="00ea7-136">This enables you to choose any combination of available fields in the query, in any order, without defining a named data type for the element.</span></span>  
  
 <span data-ttu-id="00ea7-137">*匿名类型*由编译器动态构造。</span><span class="sxs-lookup"><span data-stu-id="00ea7-137">An *anonymous type* is constructed dynamically by the compiler.</span></span> <span data-ttu-id="00ea7-138">类型的名称分配由编译器，并且它可能会更改与每个新的编译。</span><span class="sxs-lookup"><span data-stu-id="00ea7-138">The name of the type is assigned by the compiler, and it might change with each new compilation.</span></span> <span data-ttu-id="00ea7-139">因此，不能直接使用的名称。</span><span class="sxs-lookup"><span data-stu-id="00ea7-139">Therefore, the name cannot be used directly.</span></span> <span data-ttu-id="00ea7-140">按以下方式初始化匿名类型：</span><span class="sxs-lookup"><span data-stu-id="00ea7-140">Anonymous types are initialized in the following way:</span></span>  
  
 [!code-vb[VbLINQVbFeatures#5](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_5.vb)]  
  
 <span data-ttu-id="00ea7-141">有关详细信息，请参阅[匿名类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)。</span><span class="sxs-lookup"><span data-stu-id="00ea7-141">For more information, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
## <a name="extension-methods"></a><span data-ttu-id="00ea7-142">扩展方法</span><span class="sxs-lookup"><span data-stu-id="00ea7-142">Extension Methods</span></span>  
 <span data-ttu-id="00ea7-143">扩展方法，可以将方法添加到的数据类型或从定义之外的接口。</span><span class="sxs-lookup"><span data-stu-id="00ea7-143">Extension methods enable you to add methods to a data type or interface from outside the definition.</span></span> <span data-ttu-id="00ea7-144">此功能使您能够，实际上，将新方法添加到现有类型而实际修改该类型。</span><span class="sxs-lookup"><span data-stu-id="00ea7-144">This feature enables you to, in effect, add new methods to an existing type without actually modifying the type.</span></span> <span data-ttu-id="00ea7-145">标准查询运算符本身就是扩展方法，它们提供一组[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]查询实现任何类型的功能<xref:System.Collections.Generic.IEnumerable%601>。</span><span class="sxs-lookup"><span data-stu-id="00ea7-145">The standard query operators are themselves a set of extension methods that provide [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query functionality for any type that implements <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="00ea7-146">到其他扩展<xref:System.Collections.Generic.IEnumerable%601>包括<xref:System.Linq.Enumerable.Count%2A>， <xref:System.Linq.Enumerable.Union%2A>，和<xref:System.Linq.Enumerable.Intersect%2A>。</span><span class="sxs-lookup"><span data-stu-id="00ea7-146">Other extensions to <xref:System.Collections.Generic.IEnumerable%601> include <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Union%2A>, and <xref:System.Linq.Enumerable.Intersect%2A>.</span></span>  
  
 <span data-ttu-id="00ea7-147">下面的扩展方法将添加到打印方法<xref:System.String>类。</span><span class="sxs-lookup"><span data-stu-id="00ea7-147">The following extension method adds a print method to the <xref:System.String> class.</span></span>  
  
 [!code-vb[VbLINQVbFeatures#6](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_6.vb)]  
  
 <span data-ttu-id="00ea7-148">默认情况下，调用类似于普通的实例方法的<xref:System.String>:</span><span class="sxs-lookup"><span data-stu-id="00ea7-148">The method is called like an ordinary instance method of <xref:System.String>:</span></span>  
  
 [!code-vb[VbLINQVbFeatures#7](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_7.vb)]  
  
 <span data-ttu-id="00ea7-149">有关详细信息，请参阅[扩展方法](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)。</span><span class="sxs-lookup"><span data-stu-id="00ea7-149">For more information, see [Extension Methods](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md).</span></span>  
  
## <a name="lambda-expressions"></a><span data-ttu-id="00ea7-150">Lambda 表达式</span><span class="sxs-lookup"><span data-stu-id="00ea7-150">Lambda Expressions</span></span>  
 <span data-ttu-id="00ea7-151">Lambda 表达式是没有名称，用于计算并返回单个值的函数。</span><span class="sxs-lookup"><span data-stu-id="00ea7-151">A lambda expression is a function without a name that calculates and returns a single value.</span></span> <span data-ttu-id="00ea7-152">不同于命名的函数，可以定义并在同一时间执行 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="00ea7-152">Unlike named functions, a lambda expression can be defined and executed at the same time.</span></span> <span data-ttu-id="00ea7-153">下面的示例显示 4。</span><span class="sxs-lookup"><span data-stu-id="00ea7-153">The following example displays 4.</span></span>  
  
 [!code-vb[VbLINQVbFeatures#8](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_8.vb)]  
  
 <span data-ttu-id="00ea7-154">你可以将 lambda 表达式定义分配给变量的名称，然后使用名称调用该函数。</span><span class="sxs-lookup"><span data-stu-id="00ea7-154">You can assign the lambda expression definition to a variable name and then use the name to call the function.</span></span> <span data-ttu-id="00ea7-155">下面的示例还显示 4。</span><span class="sxs-lookup"><span data-stu-id="00ea7-155">The following example also displays 4.</span></span>  
  
 [!code-vb[VbLINQVbFeatures#12](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_9.vb)]  
  
 <span data-ttu-id="00ea7-156">在[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]，lambda 表达式生成许多标准查询运算符。</span><span class="sxs-lookup"><span data-stu-id="00ea7-156">In [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], lambda expressions underlie many of the standard query operators.</span></span> <span data-ttu-id="00ea7-157">编译器创建 lambda 表达式捕获的计算，如基本查询方法中定义`Where`， `Select`， `Order By`， `Take While`，和其他人。</span><span class="sxs-lookup"><span data-stu-id="00ea7-157">The compiler creates lambda expressions to capture the calculations that are defined in fundamental query methods such as `Where`, `Select`, `Order By`, `Take While`, and others.</span></span>  
  
 <span data-ttu-id="00ea7-158">例如，下面的代码定义学生列表中返回所有高年级学生的查询。</span><span class="sxs-lookup"><span data-stu-id="00ea7-158">For example, the following code defines a query that returns all senior students from a list of students.</span></span>  
  
 [!code-vb[VbLINQVbFeatures#9](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_10.vb)]  
  
 <span data-ttu-id="00ea7-159">查询定义编译为类似于下面的示例使用两个 lambda 表达式来指定的自变量的代码`Where`和`Select`。</span><span class="sxs-lookup"><span data-stu-id="00ea7-159">The query definition is compiled into code that is similar to the following example, which uses two lambda expressions to specify the arguments for `Where` and `Select`.</span></span>  
  
 [!code-vb[VbLINQVbFeatures#10](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_11.vb)]  
  
 <span data-ttu-id="00ea7-160">可以使用运行任一版本`For Each`循环：</span><span class="sxs-lookup"><span data-stu-id="00ea7-160">Either version can be run by using a `For Each` loop:</span></span>  
  
 [!code-vb[VbLINQVbFeatures#11](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_12.vb)]  
  
 <span data-ttu-id="00ea7-161">有关详细信息，请参阅 [Lambda 表达式](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="00ea7-161">For more information, see [Lambda Expressions](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00ea7-162">请参阅</span><span class="sxs-lookup"><span data-stu-id="00ea7-162">See Also</span></span>  
 [<span data-ttu-id="00ea7-163">语言集成查询 (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="00ea7-163">Language-Integrated Query (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/index.md)  
 [<span data-ttu-id="00ea7-164">Visual Basic 中的 LINQ 入门</span><span class="sxs-lookup"><span data-stu-id="00ea7-164">Getting Started with LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)  
 [<span data-ttu-id="00ea7-165">LINQ 和字符串 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="00ea7-165">LINQ and Strings (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)  
 [<span data-ttu-id="00ea7-166">Option Infer 语句</span><span class="sxs-lookup"><span data-stu-id="00ea7-166">Option Infer Statement</span></span>](../../../../visual-basic/language-reference/statements/option-infer-statement.md)  
 [<span data-ttu-id="00ea7-167">Option Strict 语句</span><span class="sxs-lookup"><span data-stu-id="00ea7-167">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
