---
title: 支持 LINQ 的 Visual Basic 功能
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic, LINQ features
- LINQ [Visual Basic], features supporting LINQ
ms.assetid: c821bb50-b6f6-4cf9-8aba-2717e465bd3a
ms.openlocfilehash: e76fcb891e0b258d261208f7cb9173c49899ba11
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56974258"
---
# <a name="visual-basic-features-that-support-linq"></a><span data-ttu-id="a1909-102">支持 LINQ 的 Visual Basic 功能</span><span class="sxs-lookup"><span data-stu-id="a1909-102">Visual Basic Features That Support LINQ</span></span>
<span data-ttu-id="a1909-103">名称[!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]指的是在 Visual Basic 支持查询语法和其他语言构造大大降低直接在语言中的技术。</span><span class="sxs-lookup"><span data-stu-id="a1909-103">The name [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] refers to technology in Visual Basic that supports query syntax and other language constructs directly in the language.</span></span> <span data-ttu-id="a1909-104">使用[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]，无需学习新语言对外部数据源的查询。</span><span class="sxs-lookup"><span data-stu-id="a1909-104">With [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], you do not have to learn a new language to query against an external data source.</span></span> <span data-ttu-id="a1909-105">可以通过使用 Visual Basic 针对关系数据库、 XML 存储或对象中的数据进行查询。</span><span class="sxs-lookup"><span data-stu-id="a1909-105">You can query against data in relational databases, XML stores, or objects by using Visual Basic.</span></span> <span data-ttu-id="a1909-106">此集成的语言的查询功能，编译时检查语法错误和类型安全。</span><span class="sxs-lookup"><span data-stu-id="a1909-106">This integration of query capabilities into the language enables compile-time checking for syntax errors and type safety.</span></span> <span data-ttu-id="a1909-107">这种集成还可确保您已知道大多数您需要了解在 Visual Basic 中编写丰富而各不相同的查询。</span><span class="sxs-lookup"><span data-stu-id="a1909-107">This integration also ensures that you already know most of what you have to know to write rich, varied queries in Visual Basic.</span></span>  
  
 <span data-ttu-id="a1909-108">以下部分介绍在足够的详细信息，以便可以开始阅读介绍性文档、 代码示例和示例应用程序中支持 LINQ 的语言构造。</span><span class="sxs-lookup"><span data-stu-id="a1909-108">The following sections describe the language constructs that support LINQ in enough detail to enable you to get started in reading the introductory documentation, code examples, and sample applications.</span></span> <span data-ttu-id="a1909-109">您还可以单击链接，以了解如何语言功能组合在一起以实现语言集成查询的更详细的解释。</span><span class="sxs-lookup"><span data-stu-id="a1909-109">You can also click the links to find more detailed explanations of how the language features come together to enable language-integrated query.</span></span> <span data-ttu-id="a1909-110">启动的好时机是[演练：在 Visual Basic 中编写查询](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)。</span><span class="sxs-lookup"><span data-stu-id="a1909-110">A good place to start is [Walkthrough: Writing Queries in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md).</span></span>  
  
## <a name="query-expressions"></a><span data-ttu-id="a1909-111">查询表达式</span><span class="sxs-lookup"><span data-stu-id="a1909-111">Query Expressions</span></span>  
 <span data-ttu-id="a1909-112">在 Visual Basic 中的查询表达式可以用类似于 SQL 或 XQuery 的声明性语法来表示。</span><span class="sxs-lookup"><span data-stu-id="a1909-112">Query expressions in Visual Basic can be expressed in a declarative syntax similar to that of SQL or XQuery.</span></span> <span data-ttu-id="a1909-113">在编译时，查询语法转换为对标准查询运算符扩展方法的 LINQ 提供程序实现的方法调用。</span><span class="sxs-lookup"><span data-stu-id="a1909-113">At compile time, query syntax is converted into method calls to a LINQ provider's implementation of the standard query operator extension methods.</span></span> <span data-ttu-id="a1909-114">应用程序控制的标准查询运算符是在范围内通过指定适当的命名空间与`Imports`语句。</span><span class="sxs-lookup"><span data-stu-id="a1909-114">Applications control which standard query operators are in scope by specifying the appropriate namespace with an `Imports` statement.</span></span> <span data-ttu-id="a1909-115">Visual Basic 查询表达式的语法如下所示：</span><span class="sxs-lookup"><span data-stu-id="a1909-115">Syntax for a Visual Basic query expression looks like this:</span></span>  
  
 [!code-vb[VbLINQVbFeatures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#1)]  
  
 <span data-ttu-id="a1909-116">有关详细信息，请参阅[Visual Basic 中的 LINQ 简介](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)。</span><span class="sxs-lookup"><span data-stu-id="a1909-116">For more information, see [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md).</span></span>  
  
## <a name="implicitly-typed-variables"></a><span data-ttu-id="a1909-117">隐式类型化的变量</span><span class="sxs-lookup"><span data-stu-id="a1909-117">Implicitly Typed Variables</span></span>  
 <span data-ttu-id="a1909-118">而不是显式指定类型声明和初始化一个变量时，可以使编译器能够推断和分配类型。</span><span class="sxs-lookup"><span data-stu-id="a1909-118">Instead of explicitly specifying a type when you declare and initialize a variable, you can enable the compiler to infer and assign the type.</span></span> <span data-ttu-id="a1909-119">这被称为*局部类型推理*。</span><span class="sxs-lookup"><span data-stu-id="a1909-119">This is referred to as *local type inference*.</span></span>  
  
 <span data-ttu-id="a1909-120">变量推断其类型强类型，就像您显式指定其类型的变量一样。</span><span class="sxs-lookup"><span data-stu-id="a1909-120">Variables whose types are inferred are strongly typed, just like variables whose type you specify explicitly.</span></span> <span data-ttu-id="a1909-121">局部类型推理仅适用于定义方法体内局部变量。</span><span class="sxs-lookup"><span data-stu-id="a1909-121">Local type inference works only when you are defining a local variable inside a method body.</span></span> <span data-ttu-id="a1909-122">有关详细信息，请参阅[Option Infer 语句](../../../../visual-basic/language-reference/statements/option-infer-statement.md)并[本地类型推断](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)。</span><span class="sxs-lookup"><span data-stu-id="a1909-122">For more information, see [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md) and [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>  
  
 <span data-ttu-id="a1909-123">下面的示例说明了局部类型推理。</span><span class="sxs-lookup"><span data-stu-id="a1909-123">The following example illustrates local type inference.</span></span> <span data-ttu-id="a1909-124">若要使用此示例中，必须设置`Option Infer`到`On`。</span><span class="sxs-lookup"><span data-stu-id="a1909-124">To use this example, you must set `Option Infer` to `On`.</span></span>  
  
 [!code-vb[VbLINQVbFeatures#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#2)]  
  
 <span data-ttu-id="a1909-125">局部类型推理还，可以创建匿名类型，也不能在本部分稍后介绍 LINQ 查询所必需的。</span><span class="sxs-lookup"><span data-stu-id="a1909-125">Local type inference also makes it possible to create anonymous types, which are described later in this section and are necessary for LINQ queries.</span></span>  
  
 <span data-ttu-id="a1909-126">在下面的 LINQ 示例中，类型推理发生如果`Option Infer`可以是`On`或`Off`。</span><span class="sxs-lookup"><span data-stu-id="a1909-126">In the following LINQ example, type inference occurs if `Option Infer` is either `On` or `Off`.</span></span> <span data-ttu-id="a1909-127">如果会发生编译时错误`Option Infer`是`Off`并`Option Strict`是`On`。</span><span class="sxs-lookup"><span data-stu-id="a1909-127">A compile-time error occurs if `Option Infer` is `Off` and `Option Strict` is `On`.</span></span>  
  
 [!code-vb[VbLINQVbFeatures#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#3)]  
  
## <a name="object-initializers"></a><span data-ttu-id="a1909-128">对象初始值设定项</span><span class="sxs-lookup"><span data-stu-id="a1909-128">Object Initializers</span></span>  
 <span data-ttu-id="a1909-129">您必须创建匿名类型来存储查询的结果时，将在查询表达式中使用对象初始值设定项。</span><span class="sxs-lookup"><span data-stu-id="a1909-129">Object initializers are used in query expressions when you have to create an anonymous type to hold the results of a query.</span></span> <span data-ttu-id="a1909-130">它们还可用于初始化外部查询的命名类型的对象。</span><span class="sxs-lookup"><span data-stu-id="a1909-130">They also can be used to initialize objects of named types outside of queries.</span></span> <span data-ttu-id="a1909-131">通过使用对象初始值设定项，可以无需显式调用构造函数初始化单个行中的对象。</span><span class="sxs-lookup"><span data-stu-id="a1909-131">By using an object initializer, you can initialize an object in a single line without explicitly calling a constructor.</span></span> <span data-ttu-id="a1909-132">假设你有一个名为类`Customer`具有公共`Name`和`Phone`属性，以及其他属性，可以以这种方式使用对象初始值设定项：</span><span class="sxs-lookup"><span data-stu-id="a1909-132">Assuming that you have a class named `Customer` that has public `Name` and `Phone` properties, along with other properties, an object initializer can be used in this manner:</span></span>  
  
 [!code-vb[VbLINQVbFeatures#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#4)]  
  
 <span data-ttu-id="a1909-133">有关详细信息，请参阅[对象初始值设定项：命名和匿名类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)。</span><span class="sxs-lookup"><span data-stu-id="a1909-133">For more information, see [Object Initializers: Named and Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md).</span></span>  
  
## <a name="anonymous-types"></a><span data-ttu-id="a1909-134">匿名类型</span><span class="sxs-lookup"><span data-stu-id="a1909-134">Anonymous Types</span></span>  
 <span data-ttu-id="a1909-135">匿名类型提供的一组属性临时分组你想要在查询结果中包含的元素的简便方法。</span><span class="sxs-lookup"><span data-stu-id="a1909-135">Anonymous types provide a convenient way to temporarily group a set of properties into an element that you want to include in a query result.</span></span> <span data-ttu-id="a1909-136">这使您可以在查询中，按任意顺序中，选择可用字段的任意组合，而无需定义元素的已命名的数据类型。</span><span class="sxs-lookup"><span data-stu-id="a1909-136">This enables you to choose any combination of available fields in the query, in any order, without defining a named data type for the element.</span></span>  
  
 <span data-ttu-id="a1909-137">*匿名类型*编译器动态构造。</span><span class="sxs-lookup"><span data-stu-id="a1909-137">An *anonymous type* is constructed dynamically by the compiler.</span></span> <span data-ttu-id="a1909-138">类型的名称分配由编译器，并且它可能会更改与每个新的编译。</span><span class="sxs-lookup"><span data-stu-id="a1909-138">The name of the type is assigned by the compiler, and it might change with each new compilation.</span></span> <span data-ttu-id="a1909-139">因此，不能直接使用该名称。</span><span class="sxs-lookup"><span data-stu-id="a1909-139">Therefore, the name cannot be used directly.</span></span> <span data-ttu-id="a1909-140">按以下方式初始化匿名类型：</span><span class="sxs-lookup"><span data-stu-id="a1909-140">Anonymous types are initialized in the following way:</span></span>  
  
 [!code-vb[VbLINQVbFeatures#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#5)]  
  
 <span data-ttu-id="a1909-141">有关详细信息，请参阅[匿名类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)。</span><span class="sxs-lookup"><span data-stu-id="a1909-141">For more information, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
## <a name="extension-methods"></a><span data-ttu-id="a1909-142">扩展方法</span><span class="sxs-lookup"><span data-stu-id="a1909-142">Extension Methods</span></span>  
 <span data-ttu-id="a1909-143">扩展方法，可将方法添加到数据类型或接口定义之外的位置。</span><span class="sxs-lookup"><span data-stu-id="a1909-143">Extension methods enable you to add methods to a data type or interface from outside the definition.</span></span> <span data-ttu-id="a1909-144">此功能可以以，实际上，向现有类型添加新方法，而无需实际修改类型。</span><span class="sxs-lookup"><span data-stu-id="a1909-144">This feature enables you to, in effect, add new methods to an existing type without actually modifying the type.</span></span> <span data-ttu-id="a1909-145">标准查询运算符本身就是一组提供的扩展方法[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]查询功能实现的任何类型<xref:System.Collections.Generic.IEnumerable%601>。</span><span class="sxs-lookup"><span data-stu-id="a1909-145">The standard query operators are themselves a set of extension methods that provide [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query functionality for any type that implements <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="a1909-146">其他扩展<xref:System.Collections.Generic.IEnumerable%601>包括<xref:System.Linq.Enumerable.Count%2A>， <xref:System.Linq.Enumerable.Union%2A>，和<xref:System.Linq.Enumerable.Intersect%2A>。</span><span class="sxs-lookup"><span data-stu-id="a1909-146">Other extensions to <xref:System.Collections.Generic.IEnumerable%601> include <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Union%2A>, and <xref:System.Linq.Enumerable.Intersect%2A>.</span></span>  
  
 <span data-ttu-id="a1909-147">以下扩展方法将添加到了 print 方法<xref:System.String>类。</span><span class="sxs-lookup"><span data-stu-id="a1909-147">The following extension method adds a print method to the <xref:System.String> class.</span></span>  
  
 [!code-vb[VbLINQVbFeatures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#6)]  
  
 <span data-ttu-id="a1909-148">类似于普通实例方法的调用的方法<xref:System.String>:</span><span class="sxs-lookup"><span data-stu-id="a1909-148">The method is called like an ordinary instance method of <xref:System.String>:</span></span>  
  
 [!code-vb[VbLINQVbFeatures#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#7)]  
  
 <span data-ttu-id="a1909-149">有关详细信息，请参阅[扩展方法](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)。</span><span class="sxs-lookup"><span data-stu-id="a1909-149">For more information, see [Extension Methods](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md).</span></span>  
  
## <a name="lambda-expressions"></a><span data-ttu-id="a1909-150">Lambda 表达式</span><span class="sxs-lookup"><span data-stu-id="a1909-150">Lambda Expressions</span></span>  
 <span data-ttu-id="a1909-151">Lambda 表达式是没有名称，用于计算并返回单个值的函数。</span><span class="sxs-lookup"><span data-stu-id="a1909-151">A lambda expression is a function without a name that calculates and returns a single value.</span></span> <span data-ttu-id="a1909-152">命名与函数不同，可以定义并在同一时间执行 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="a1909-152">Unlike named functions, a lambda expression can be defined and executed at the same time.</span></span> <span data-ttu-id="a1909-153">以下示例显示 4。</span><span class="sxs-lookup"><span data-stu-id="a1909-153">The following example displays 4.</span></span>  
  
 [!code-vb[VbLINQVbFeatures#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#8)]  
  
 <span data-ttu-id="a1909-154">您可以将 lambda 表达式定义分配给变量的名称，然后使用名称来调用该函数。</span><span class="sxs-lookup"><span data-stu-id="a1909-154">You can assign the lambda expression definition to a variable name and then use the name to call the function.</span></span> <span data-ttu-id="a1909-155">下面的示例还显示 4。</span><span class="sxs-lookup"><span data-stu-id="a1909-155">The following example also displays 4.</span></span>  
  
 [!code-vb[VbLINQVbFeatures#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#12)]  
  
 <span data-ttu-id="a1909-156">在[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]，lambda 表达式基础许多标准查询运算符。</span><span class="sxs-lookup"><span data-stu-id="a1909-156">In [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], lambda expressions underlie many of the standard query operators.</span></span> <span data-ttu-id="a1909-157">编译器会创建 lambda 表达式，以捕获等基本查询方法中定义的计算`Where`， `Select`， `Order By`， `Take While`，等等。</span><span class="sxs-lookup"><span data-stu-id="a1909-157">The compiler creates lambda expressions to capture the calculations that are defined in fundamental query methods such as `Where`, `Select`, `Order By`, `Take While`, and others.</span></span>  
  
 <span data-ttu-id="a1909-158">例如，以下代码定义学生列表中返回所有高年级学生的查询。</span><span class="sxs-lookup"><span data-stu-id="a1909-158">For example, the following code defines a query that returns all senior students from a list of students.</span></span>  
  
 [!code-vb[VbLINQVbFeatures#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#9)]  
  
 <span data-ttu-id="a1909-159">查询定义编译为类似于下面的示例使用两个 lambda 表达式来指定的参数的代码`Where`和`Select`。</span><span class="sxs-lookup"><span data-stu-id="a1909-159">The query definition is compiled into code that is similar to the following example, which uses two lambda expressions to specify the arguments for `Where` and `Select`.</span></span>  
  
 [!code-vb[VbLINQVbFeatures#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#10)]  
  
 <span data-ttu-id="a1909-160">可以使用运行任一版本`For Each`循环：</span><span class="sxs-lookup"><span data-stu-id="a1909-160">Either version can be run by using a `For Each` loop:</span></span>  
  
 [!code-vb[VbLINQVbFeatures#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#11)]  
  
 <span data-ttu-id="a1909-161">有关详细信息，请参阅 [Lambda 表达式](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="a1909-161">For more information, see [Lambda Expressions](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1909-162">请参阅</span><span class="sxs-lookup"><span data-stu-id="a1909-162">See also</span></span>
- [<span data-ttu-id="a1909-163">语言集成查询 (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a1909-163">Language-Integrated Query (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="a1909-164">Visual Basic 中的 LINQ 入门</span><span class="sxs-lookup"><span data-stu-id="a1909-164">Getting Started with LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [<span data-ttu-id="a1909-165">LINQ 和字符串 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a1909-165">LINQ and Strings (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)
- [<span data-ttu-id="a1909-166">Option Infer 语句</span><span class="sxs-lookup"><span data-stu-id="a1909-166">Option Infer Statement</span></span>](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [<span data-ttu-id="a1909-167">Option Strict 语句</span><span class="sxs-lookup"><span data-stu-id="a1909-167">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
