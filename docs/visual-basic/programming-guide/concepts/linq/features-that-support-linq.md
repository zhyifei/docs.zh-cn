---
title: "支持 LINQ 的 Visual Basic 功能 |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic, LINQ features
- LINQ [Visual Basic], features supporting LINQ
ms.assetid: c821bb50-b6f6-4cf9-8aba-2717e465bd3a
caps.latest.revision: 51
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
ms.openlocfilehash: 728018de7e38374875b15a809e5659003519d60f
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="visual-basic-features-that-support-linq"></a><span data-ttu-id="56489-102">支持 LINQ 的 Visual Basic 功能</span><span class="sxs-lookup"><span data-stu-id="56489-102">Visual Basic Features That Support LINQ</span></span>
<span data-ttu-id="56489-103">名称[!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)]是指在 Visual Basic 中支持查询语法和其他语言构造直接在语言中的技术。</span><span class="sxs-lookup"><span data-stu-id="56489-103">The name [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] refers to technology in Visual Basic that supports query syntax and other language constructs directly in the language.</span></span> <span data-ttu-id="56489-104">与[!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]，无需学习新语言对外部数据源执行查询。</span><span class="sxs-lookup"><span data-stu-id="56489-104">With [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)], you do not have to learn a new language to query against an external data source.</span></span> <span data-ttu-id="56489-105">可以通过使用 Visual Basic 查询针对关系数据库、 XML 存储或对象中的数据。</span><span class="sxs-lookup"><span data-stu-id="56489-105">You can query against data in relational databases, XML stores, or objects by using Visual Basic.</span></span> <span data-ttu-id="56489-106">此集成到该语言的查询功能使编译时检查有语法错误和类型安全。</span><span class="sxs-lookup"><span data-stu-id="56489-106">This integration of query capabilities into the language enables compile-time checking for syntax errors and type safety.</span></span> <span data-ttu-id="56489-107">这一集成还可确保您已经知道您需要了解在 Visual Basic 中编写丰富的、 不同的查询的大部分。</span><span class="sxs-lookup"><span data-stu-id="56489-107">This integration also ensures that you already know most of what you have to know to write rich, varied queries in Visual Basic.</span></span>  
  
 <span data-ttu-id="56489-108">以下各节描述了足够的详细信息，以使您能够开始阅读介绍性文档、 代码示例和示例应用程序中支持 LINQ 的语言构造。</span><span class="sxs-lookup"><span data-stu-id="56489-108">The following sections describe the language constructs that support LINQ in enough detail to enable you to get started in reading the introductory documentation, code examples, and sample applications.</span></span> <span data-ttu-id="56489-109">您还可以单击链接，以了解如何语言功能组合在一起以启用对语言集成查询的更详细的解释。</span><span class="sxs-lookup"><span data-stu-id="56489-109">You can also click the links to find more detailed explanations of how the language features come together to enable language-integrated query.</span></span> <span data-ttu-id="56489-110">是一个好启动[演练︰ 在 Visual Basic 中编写查询](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)。</span><span class="sxs-lookup"><span data-stu-id="56489-110">A good place to start is [Walkthrough: Writing Queries in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md).</span></span>  
  
## <a name="query-expressions"></a><span data-ttu-id="56489-111">查询表达式</span><span class="sxs-lookup"><span data-stu-id="56489-111">Query Expressions</span></span>  
 <span data-ttu-id="56489-112">在 Visual Basic 中的查询表达式可以用类似于 SQL 或 XQuery 的声明性语法来表示。</span><span class="sxs-lookup"><span data-stu-id="56489-112">Query expressions in Visual Basic can be expressed in a declarative syntax similar to that of SQL or XQuery.</span></span> <span data-ttu-id="56489-113">在编译时，查询语法转换为对标准查询运算符扩展方法的 LINQ 提供程序实现的方法调用。</span><span class="sxs-lookup"><span data-stu-id="56489-113">At compile time, query syntax is converted into method calls to a LINQ provider's implementation of the standard query operator extension methods.</span></span> <span data-ttu-id="56489-114">应用程序来控制它们在作用域内是通过指定具有适当的命名空间的标准查询运算符`Imports`语句。</span><span class="sxs-lookup"><span data-stu-id="56489-114">Applications control which standard query operators are in scope by specifying the appropriate namespace with an `Imports` statement.</span></span> <span data-ttu-id="56489-115">Visual Basic 查询表达式的语法如下所示︰</span><span class="sxs-lookup"><span data-stu-id="56489-115">Syntax for a Visual Basic query expression looks like this:</span></span>  
  
 <span data-ttu-id="56489-116">[!code-vb[VbLINQVbFeatures #&1;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="56489-116">[!code-vb[VbLINQVbFeatures#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_1.vb)]</span></span>  
  
 <span data-ttu-id="56489-117">有关详细信息，请参阅[在 Visual Basic 中的 LINQ 简介](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)。</span><span class="sxs-lookup"><span data-stu-id="56489-117">For more information, see [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md).</span></span>  
  
## <a name="implicitly-typed-variables"></a><span data-ttu-id="56489-118">隐式类型化的变量</span><span class="sxs-lookup"><span data-stu-id="56489-118">Implicitly Typed Variables</span></span>  
 <span data-ttu-id="56489-119">而不是在显式指定类型声明和初始化变量时，可以使编译器能够推断并分配类型。</span><span class="sxs-lookup"><span data-stu-id="56489-119">Instead of explicitly specifying a type when you declare and initialize a variable, you can enable the compiler to infer and assign the type.</span></span> <span data-ttu-id="56489-120">这被称为*局部类型推理*。</span><span class="sxs-lookup"><span data-stu-id="56489-120">This is referred to as *local type inference*.</span></span>  
  
 <span data-ttu-id="56489-121">变量推断其类型强类型，就像您显式指定其类型的变量一样。</span><span class="sxs-lookup"><span data-stu-id="56489-121">Variables whose types are inferred are strongly typed, just like variables whose type you specify explicitly.</span></span> <span data-ttu-id="56489-122">局部类型推理仅用于定义在方法体内的本地变量。</span><span class="sxs-lookup"><span data-stu-id="56489-122">Local type inference works only when you are defining a local variable inside a method body.</span></span> <span data-ttu-id="56489-123">有关详细信息，请参阅[Option Infer 语句](../../../../visual-basic/language-reference/statements/option-infer-statement.md)和[本地类型推理](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)。</span><span class="sxs-lookup"><span data-stu-id="56489-123">For more information, see [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md) and [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>  
  
 <span data-ttu-id="56489-124">下面的示例说明了局部类型推理。</span><span class="sxs-lookup"><span data-stu-id="56489-124">The following example illustrates local type inference.</span></span> <span data-ttu-id="56489-125">若要使用此示例，必须设置`Option Infer`到`On`。</span><span class="sxs-lookup"><span data-stu-id="56489-125">To use this example, you must set `Option Infer` to `On`.</span></span>  
  
 <span data-ttu-id="56489-126">[!code-vb[VbLINQVbFeatures #&2;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="56489-126">[!code-vb[VbLINQVbFeatures#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_2.vb)]</span></span>  
  
 <span data-ttu-id="56489-127">局部类型推理还使可以创建匿名类型，也不能在本部分稍后介绍 LINQ 查询所必需的。</span><span class="sxs-lookup"><span data-stu-id="56489-127">Local type inference also makes it possible to create anonymous types, which are described later in this section and are necessary for LINQ queries.</span></span>  
  
 <span data-ttu-id="56489-128">在下面的 LINQ 示例中，会发生类型推理如果`Option Infer`是`On`或`Off`。</span><span class="sxs-lookup"><span data-stu-id="56489-128">In the following LINQ example, type inference occurs if `Option Infer` is either `On` or `Off`.</span></span> <span data-ttu-id="56489-129">如果发生编译时错误`Option Infer`是`Off`和`Option Strict`是`On`。</span><span class="sxs-lookup"><span data-stu-id="56489-129">A compile-time error occurs if `Option Infer` is `Off` and `Option Strict` is `On`.</span></span>  
  
 <span data-ttu-id="56489-130">[!code-vb[VbLINQVbFeatures #&3;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="56489-130">[!code-vb[VbLINQVbFeatures#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_3.vb)]</span></span>  
  
## <a name="object-initializers"></a><span data-ttu-id="56489-131">对象初始值设定项</span><span class="sxs-lookup"><span data-stu-id="56489-131">Object Initializers</span></span>  
 <span data-ttu-id="56489-132">当您必须创建一个匿名类型来保存查询的结果时，将在查询表达式中使用对象初始值设定项。</span><span class="sxs-lookup"><span data-stu-id="56489-132">Object initializers are used in query expressions when you have to create an anonymous type to hold the results of a query.</span></span> <span data-ttu-id="56489-133">它们还可用于初始化外部查询的命名类型的对象。</span><span class="sxs-lookup"><span data-stu-id="56489-133">They also can be used to initialize objects of named types outside of queries.</span></span> <span data-ttu-id="56489-134">通过使用对象初始值设定项，可以无需显式调用构造函数初始化单个行中的对象。</span><span class="sxs-lookup"><span data-stu-id="56489-134">By using an object initializer, you can initialize an object in a single line without explicitly calling a constructor.</span></span> <span data-ttu-id="56489-135">假设有一个名为类`Customer`该类具有公共`Name`和`Phone`属性，以及其他属性，可以按照此方式使用对象初始值设定项︰</span><span class="sxs-lookup"><span data-stu-id="56489-135">Assuming that you have a class named `Customer` that has public `Name` and `Phone` properties, along with other properties, an object initializer can be used in this manner:</span></span>  
  
 <span data-ttu-id="56489-136">[!code-vb[VbLINQVbFeatures #&4;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="56489-136">[!code-vb[VbLINQVbFeatures#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_4.vb)]</span></span>  
  
 <span data-ttu-id="56489-137">有关详细信息，请参阅[对象初始值设定项︰ 命名类型和匿名类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)。</span><span class="sxs-lookup"><span data-stu-id="56489-137">For more information, see [Object Initializers: Named and Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md).</span></span>  
  
## <a name="anonymous-types"></a><span data-ttu-id="56489-138">匿名类型</span><span class="sxs-lookup"><span data-stu-id="56489-138">Anonymous Types</span></span>  
 <span data-ttu-id="56489-139">匿名类型提供了方便地暂时你想要在查询结果中包含的元素进行分组的一组属性。</span><span class="sxs-lookup"><span data-stu-id="56489-139">Anonymous types provide a convenient way to temporarily group a set of properties into an element that you want to include in a query result.</span></span> <span data-ttu-id="56489-140">这使您在查询中，按任意顺序选择可用的字段的任意组合，而不定义该元素的已命名的数据类型。</span><span class="sxs-lookup"><span data-stu-id="56489-140">This enables you to choose any combination of available fields in the query, in any order, without defining a named data type for the element.</span></span>  
  
 <span data-ttu-id="56489-141">*匿名类型*由编译器动态构造。</span><span class="sxs-lookup"><span data-stu-id="56489-141">An *anonymous type* is constructed dynamically by the compiler.</span></span> <span data-ttu-id="56489-142">由该编译器中，分配的类型的名称，它可能会更改与每个新的编译。</span><span class="sxs-lookup"><span data-stu-id="56489-142">The name of the type is assigned by the compiler, and it might change with each new compilation.</span></span> <span data-ttu-id="56489-143">因此，不能直接使用该名称。</span><span class="sxs-lookup"><span data-stu-id="56489-143">Therefore, the name cannot be used directly.</span></span> <span data-ttu-id="56489-144">按以下方式初始化匿名类型︰</span><span class="sxs-lookup"><span data-stu-id="56489-144">Anonymous types are initialized in the following way:</span></span>  
  
 <span data-ttu-id="56489-145">[!code-vb[VbLINQVbFeatures #&5;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="56489-145">[!code-vb[VbLINQVbFeatures#5](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_5.vb)]</span></span>  
  
 <span data-ttu-id="56489-146">有关详细信息，请参阅[匿名类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)。</span><span class="sxs-lookup"><span data-stu-id="56489-146">For more information, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
## <a name="extension-methods"></a><span data-ttu-id="56489-147">扩展方法</span><span class="sxs-lookup"><span data-stu-id="56489-147">Extension Methods</span></span>  
 <span data-ttu-id="56489-148">扩展方法，可以将方法添加到数据类型或接口的定义之外的位置。</span><span class="sxs-lookup"><span data-stu-id="56489-148">Extension methods enable you to add methods to a data type or interface from outside the definition.</span></span> <span data-ttu-id="56489-149">此功能使您能够，实际上，向现有类型添加新方法，而无需实际修改该类型。</span><span class="sxs-lookup"><span data-stu-id="56489-149">This feature enables you to, in effect, add new methods to an existing type without actually modifying the type.</span></span> <span data-ttu-id="56489-150">标准查询运算符本身就是扩展方法，它们提供了一组[!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]查询实现<xref:System.Collections.Generic.IEnumerable%601>。</xref:System.Collections.Generic.IEnumerable%601>的任何类型的功能</span><span class="sxs-lookup"><span data-stu-id="56489-150">The standard query operators are themselves a set of extension methods that provide [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] query functionality for any type that implements <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="56489-151">对其他扩展<xref:System.Collections.Generic.IEnumerable%601>包括<xref:System.Linq.Enumerable.Count%2A>， <xref:System.Linq.Enumerable.Union%2A>，和<xref:System.Linq.Enumerable.Intersect%2A>。</xref:System.Linq.Enumerable.Intersect%2A> </xref:System.Linq.Enumerable.Union%2A> </xref:System.Linq.Enumerable.Count%2A> </xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="56489-151">Other extensions to <xref:System.Collections.Generic.IEnumerable%601> include <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Union%2A>, and <xref:System.Linq.Enumerable.Intersect%2A>.</span></span>  
  
 <span data-ttu-id="56489-152">下面的扩展方法将 print 方法添加到<xref:System.String>类。</xref:System.String></span><span class="sxs-lookup"><span data-stu-id="56489-152">The following extension method adds a print method to the <xref:System.String> class.</span></span>  
  
 <span data-ttu-id="56489-153">[!code-vb[VbLINQVbFeatures #&6;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="56489-153">[!code-vb[VbLINQVbFeatures#6](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_6.vb)]</span></span>  
  
 <span data-ttu-id="56489-154">该方法的调用方式类似<xref:System.String>::</xref:System.String>的普通实例方法</span><span class="sxs-lookup"><span data-stu-id="56489-154">The method is called like an ordinary instance method of <xref:System.String>:</span></span>  
  
 <span data-ttu-id="56489-155">[!code-vb[VbLINQVbFeatures #&7;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="56489-155">[!code-vb[VbLINQVbFeatures#7](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_7.vb)]</span></span>  
  
 <span data-ttu-id="56489-156">有关详细信息，请参阅[扩展方法](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)。</span><span class="sxs-lookup"><span data-stu-id="56489-156">For more information, see [Extension Methods](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md).</span></span>  
  
## <a name="lambda-expressions"></a><span data-ttu-id="56489-157">Lambda 表达式</span><span class="sxs-lookup"><span data-stu-id="56489-157">Lambda Expressions</span></span>  
 <span data-ttu-id="56489-158">Lambda 表达式是函数，而不计算并返回单个值的名称。</span><span class="sxs-lookup"><span data-stu-id="56489-158">A lambda expression is a function without a name that calculates and returns a single value.</span></span> <span data-ttu-id="56489-159">命名与函数不同，可以定义并在同一时间执行 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="56489-159">Unlike named functions, a lambda expression can be defined and executed at the same time.</span></span> <span data-ttu-id="56489-160">下面的示例显示 4。</span><span class="sxs-lookup"><span data-stu-id="56489-160">The following example displays 4.</span></span>  
  
 <span data-ttu-id="56489-161">[!code-vb[VbLINQVbFeatures #&8;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_8.vb)]</span><span class="sxs-lookup"><span data-stu-id="56489-161">[!code-vb[VbLINQVbFeatures#8](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_8.vb)]</span></span>  
  
 <span data-ttu-id="56489-162">您可以将 lambda 表达式定义分配给变量的名称，然后使用名称才能调用该函数。</span><span class="sxs-lookup"><span data-stu-id="56489-162">You can assign the lambda expression definition to a variable name and then use the name to call the function.</span></span> <span data-ttu-id="56489-163">下面的示例还显示 4。</span><span class="sxs-lookup"><span data-stu-id="56489-163">The following example also displays 4.</span></span>  
  
 <span data-ttu-id="56489-164">[!code-vb[VbLINQVbFeatures #&12;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_9.vb)]</span><span class="sxs-lookup"><span data-stu-id="56489-164">[!code-vb[VbLINQVbFeatures#12](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_9.vb)]</span></span>  
  
 <span data-ttu-id="56489-165">在[!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]，lambda 表达式是许多标准查询运算符的基础。</span><span class="sxs-lookup"><span data-stu-id="56489-165">In [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)], lambda expressions underlie many of the standard query operators.</span></span> <span data-ttu-id="56489-166">编译器将创建 lambda 表达式，以捕获等基本查询方法中定义的计算`Where`， `Select`， `Order By`， `Take While`，和其他人。</span><span class="sxs-lookup"><span data-stu-id="56489-166">The compiler creates lambda expressions to capture the calculations that are defined in fundamental query methods such as `Where`, `Select`, `Order By`, `Take While`, and others.</span></span>  
  
 <span data-ttu-id="56489-167">例如，下面的代码定义一个查询，返回所有高级学员的学生列表中。</span><span class="sxs-lookup"><span data-stu-id="56489-167">For example, the following code defines a query that returns all senior students from a list of students.</span></span>  
  
 <span data-ttu-id="56489-168">[!code-vb[VbLINQVbFeatures #&9;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_10.vb)]</span><span class="sxs-lookup"><span data-stu-id="56489-168">[!code-vb[VbLINQVbFeatures#9](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_10.vb)]</span></span>  
  
 <span data-ttu-id="56489-169">查询定义编译为类似于下面的示例使用两个 lambda 表达式来指定的参数的代码`Where`和`Select`。</span><span class="sxs-lookup"><span data-stu-id="56489-169">The query definition is compiled into code that is similar to the following example, which uses two lambda expressions to specify the arguments for `Where` and `Select`.</span></span>  
  
 <span data-ttu-id="56489-170">[!code-vb[VbLINQVbFeatures #&10;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_11.vb)]</span><span class="sxs-lookup"><span data-stu-id="56489-170">[!code-vb[VbLINQVbFeatures#10](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_11.vb)]</span></span>  
  
 <span data-ttu-id="56489-171">可以使用运行任何一个版本`For Each`循环︰</span><span class="sxs-lookup"><span data-stu-id="56489-171">Either version can be run by using a `For Each` loop:</span></span>  
  
 <span data-ttu-id="56489-172">[!code-vb[VbLINQVbFeatures #&11;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_12.vb)]</span><span class="sxs-lookup"><span data-stu-id="56489-172">[!code-vb[VbLINQVbFeatures#11](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_12.vb)]</span></span>  
  
 <span data-ttu-id="56489-173">有关详细信息，请参阅[Lambda 表达式](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="56489-173">For more information, see [Lambda Expressions](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56489-174">另请参阅</span><span class="sxs-lookup"><span data-stu-id="56489-174">See Also</span></span>  
 <span data-ttu-id="56489-175">[语言集成查询 (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md) </span><span class="sxs-lookup"><span data-stu-id="56489-175">[Language-Integrated Query (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md) </span></span>  
<span data-ttu-id="56489-176"> [在 Visual Basic 中的 LINQ 入门](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md) </span><span class="sxs-lookup"><span data-stu-id="56489-176"> [Getting Started with LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md) </span></span>  
<span data-ttu-id="56489-177"> [LINQ 和字符串 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md) </span><span class="sxs-lookup"><span data-stu-id="56489-177"> [LINQ and Strings (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md) </span></span>  
<span data-ttu-id="56489-178"> [Option Infer 语句](../../../../visual-basic/language-reference/statements/option-infer-statement.md) </span><span class="sxs-lookup"><span data-stu-id="56489-178"> [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md) </span></span>  
<span data-ttu-id="56489-179"> [Option Strict 语句](../../../../visual-basic/language-reference/statements/option-strict-statement.md)</span><span class="sxs-lookup"><span data-stu-id="56489-179"> [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)</span></span>
