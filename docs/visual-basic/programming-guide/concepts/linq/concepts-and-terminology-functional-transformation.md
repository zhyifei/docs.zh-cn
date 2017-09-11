---
title: "概念和术语 （功能转换） (Visual Basic 中) |Microsoft 文档"
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
ms.assetid: 24fd244d-ebae-4721-8858-89bb544aea0b
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 9b07bfffbb4f5c9d833f821c9c548892aab0e606
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017


---
# <a name="concepts-and-terminology-functional-transformation-visual-basic"></a><span data-ttu-id="6351a-102">概念和术语 （功能转换） (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6351a-102">Concepts and Terminology (Functional Transformation) (Visual Basic)</span></span>
<span data-ttu-id="6351a-103">本主题介绍纯函数转换的概念和术语。</span><span class="sxs-lookup"><span data-stu-id="6351a-103">This topic introduces the concepts and terminology of pure functional transformations.</span></span> <span data-ttu-id="6351a-104">与更加传统的命令性编程方式相比，用来转换数据的函数转换方法所生成的代码往往编程速度更快、含义更明确、更易于调试和维护。</span><span class="sxs-lookup"><span data-stu-id="6351a-104">The functional transformation approach to transforming data yields code that is often quicker to program, more expressive, and easier to debug and maintain than more traditional, imperative programming.</span></span>  
  
 <span data-ttu-id="6351a-105">请注意，本节中的主题并不是要透彻解释函数编程。</span><span class="sxs-lookup"><span data-stu-id="6351a-105">Note that the topics in this section are not intended to fully explain functional programming.</span></span> <span data-ttu-id="6351a-106">这些主题只是介绍函数编程的一些功能，这些功能降低了将 XML 从一种形状转换为另一种形状的难度。</span><span class="sxs-lookup"><span data-stu-id="6351a-106">Instead, these topics identify some of the functional programming capabilities that make it easier to transform XML from one shape to another.</span></span>  
  
## <a name="what-is-pure-functional-transformation"></a><span data-ttu-id="6351a-107">什么是纯函数转换？</span><span class="sxs-lookup"><span data-stu-id="6351a-107">What Is Pure Functional Transformation?</span></span>  
 <span data-ttu-id="6351a-108">在*纯函数转换*，一组函数，称为*纯函数*，定义如何将一组结构化数据从其原始格式转换为另一种形式。</span><span class="sxs-lookup"><span data-stu-id="6351a-108">In *pure functional transformation*, a set of functions, called *pure functions*, define how to transform a set of structured data from its original form into another form.</span></span> <span data-ttu-id="6351a-109">"纯"一词表示的函数是*可组合*，这要求它们是︰</span><span class="sxs-lookup"><span data-stu-id="6351a-109">The word "pure" indicates that the functions are *composable*, which requires that they are:</span></span>  
  
-   <span data-ttu-id="6351a-110">*自包含*，以便它们可以自由排序和重新排列，而不牵连和与该程序的其余部分相互依赖关系。</span><span class="sxs-lookup"><span data-stu-id="6351a-110">*Self-contained*, so that they can be freely ordered and rearranged without entanglement or interdependencies with the rest of the program.</span></span> <span data-ttu-id="6351a-111">纯转换不了解其环境，对环境也没有任何影响。</span><span class="sxs-lookup"><span data-stu-id="6351a-111">Pure transformations have no knowledge of or effect upon their environment.</span></span> <span data-ttu-id="6351a-112">也就是说，用在转换中的函数没有*副作用*。</span><span class="sxs-lookup"><span data-stu-id="6351a-112">That is, the functions used in the transformation have no *side effects*.</span></span>  
  
-   <span data-ttu-id="6351a-113">*无状态*，因而对相同输入执行相同的函数或组特定的函数将始终产生相同的输出。</span><span class="sxs-lookup"><span data-stu-id="6351a-113">*Stateless*, so that executing the same function or specific set of functions on the same input will always result in the same output.</span></span> <span data-ttu-id="6351a-114">纯转换对于先前对它的使用没有记忆。</span><span class="sxs-lookup"><span data-stu-id="6351a-114">Pure transformations have no memory of their prior use.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6351a-115">在本教程的其余部分，术语“纯函数”用于概括表示编程方法，而不是具体的语言功能。</span><span class="sxs-lookup"><span data-stu-id="6351a-115">In the rest of this tutorial, the term "pure function" is used in a general sense to indicate a programming approach, and not a specific language feature.</span></span>  
>   
>  <span data-ttu-id="6351a-116">请注意，必须为在 Visual Basic 中的函数实现纯函数。</span><span class="sxs-lookup"><span data-stu-id="6351a-116">Note that pure functions must be implemented as functions in Visual Basic.</span></span>  
>   
>  <span data-ttu-id="6351a-117">此外，不要将纯函数与 C++ 中的纯虚方法混淆。</span><span class="sxs-lookup"><span data-stu-id="6351a-117">Also, you should not confuse pure functions with pure virtual methods in C++.</span></span> <span data-ttu-id="6351a-118">后者表示包含类是抽象的，并且不提供方法体。</span><span class="sxs-lookup"><span data-stu-id="6351a-118">The latter indicates that the containing class is abstract and that no method body is supplied.</span></span>  
  
### <a name="functional-programming"></a><span data-ttu-id="6351a-119">函数编程</span><span class="sxs-lookup"><span data-stu-id="6351a-119">Functional Programming</span></span>  
 <span data-ttu-id="6351a-120">*函数编程*是一种直接支持纯函数转换编程方法。</span><span class="sxs-lookup"><span data-stu-id="6351a-120">*Functional programming* is a programming approach that directly supports pure functional transformation.</span></span>  
  
 <span data-ttu-id="6351a-121">从历史上看，通用函数编程语言，如 ML、 方案、 Haskell 和 F # 中，已经浓厚的兴趣学术团体。</span><span class="sxs-lookup"><span data-stu-id="6351a-121">Historically, general-purpose functional programming languages, such as ML, Scheme, Haskell, and F#, have been primarily of interest to the academic community.</span></span> <span data-ttu-id="6351a-122">尽管它一直可以用来在 Visual Basic 中编写纯函数转换，但这样做的困难使之不具它对大多数程序员来说一个不错的选择。</span><span class="sxs-lookup"><span data-stu-id="6351a-122">Although it has always been possible to write pure functional transformations in Visual Basic, the difficulty of doing so has not made it an attractive option to most programmers.</span></span> <span data-ttu-id="6351a-123">有更高版本的 Visual Basic 中，但是，新语言构造如 lambda 表达式和类型推理降低了函数编程可以更简单、 提高工作效率。</span><span class="sxs-lookup"><span data-stu-id="6351a-123">With later versions of Visual Basic, however, new language constructs such as lambda expressions and type inference make it functional programming much easier and more productive.</span></span>  
  
 <span data-ttu-id="6351a-124">有关函数编程的详细信息，请参阅[功能性编程 vs。(Visual Basic 中) 的命令性编程](../../../../visual-basic/programming-guide/concepts/linq/functional-programming-vs-imperative-programming.md)。</span><span class="sxs-lookup"><span data-stu-id="6351a-124">For more information about functional programming, see [Functional Programming vs. Imperative Programming (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/functional-programming-vs-imperative-programming.md).</span></span>  
  
#### <a name="domain-specific-fp-languages"></a><span data-ttu-id="6351a-125">特定于域的 FP 语言</span><span class="sxs-lookup"><span data-stu-id="6351a-125">Domain-Specific FP Languages</span></span>  
 <span data-ttu-id="6351a-126">虽然通用函数编程语言并未得到广泛采用，但特定于域的函数编程语言却得到了较为成功的应用。</span><span class="sxs-lookup"><span data-stu-id="6351a-126">Although general functional programming languages have not been widely adopted, specific domain-specific functional programming languages have had better success.</span></span> <span data-ttu-id="6351a-127">例如，级联样式表 (CSS) 用于确定许多网页的外观，可扩展样式表转换语言 (XSLT) 样式表广泛应用于 XML 数据操作中。</span><span class="sxs-lookup"><span data-stu-id="6351a-127">For example, Cascading Style Sheets (CSS) are used to determine the look and feel of many Web pages, and Extensible Stylesheet Language Transformations (XSLT) style sheets are used extensively in XML data manipulation.</span></span> <span data-ttu-id="6351a-128">有关 XSLT 的详细信息，请参阅[XSLT 转换](http://msdn.microsoft.com/library/202f8820-224c-494f-b61e-cd127eac6e03)。</span><span class="sxs-lookup"><span data-stu-id="6351a-128">For more information about XSLT, see [XSLT Transformations](http://msdn.microsoft.com/library/202f8820-224c-494f-b61e-cd127eac6e03).</span></span>  
  
## <a name="terminology"></a><span data-ttu-id="6351a-129">术语</span><span class="sxs-lookup"><span data-stu-id="6351a-129">Terminology</span></span>  
 <span data-ttu-id="6351a-130">下表定义了一些与函数转换相关的术语。</span><span class="sxs-lookup"><span data-stu-id="6351a-130">The following table defines some terms related to functional transformations.</span></span>  
  
 <span data-ttu-id="6351a-131">高阶（第一类）函数</span><span class="sxs-lookup"><span data-stu-id="6351a-131">higher-order (first-class) function</span></span>  
 <span data-ttu-id="6351a-132">可作为编程对象的一种函数。</span><span class="sxs-lookup"><span data-stu-id="6351a-132">A function that can be treated as a programmatic object.</span></span> <span data-ttu-id="6351a-133">例如，高阶函数可以传递到其他函数或从其他函数返回。</span><span class="sxs-lookup"><span data-stu-id="6351a-133">For example, a higher-order function can be passed to or returned from other functions.</span></span> <span data-ttu-id="6351a-134">在 Visual Basic 中，委托和 lambda 表达式是支持高阶函数的语言功能。</span><span class="sxs-lookup"><span data-stu-id="6351a-134">In Visual Basic, delegates and lambda expressions are language features that support higher-order functions.</span></span> <span data-ttu-id="6351a-135">若要编写高阶函数，需要声明一个或多个自变量来接受委托，而在调用该函数时通常使用 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="6351a-135">To write a higher-order function, you declare one or more arguments to take delegates, and you often use lambda expressions when calling it.</span></span> <span data-ttu-id="6351a-136">许多标准查询运算符都属于高阶函数。</span><span class="sxs-lookup"><span data-stu-id="6351a-136">Many of the standard query operators are higher-order functions.</span></span>  
  
 <span data-ttu-id="6351a-137">有关详细信息，请参阅[标准查询运算符概述 (Visual Basic 中)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="6351a-137">For more information, see [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).</span></span>  
  
 <span data-ttu-id="6351a-138">lambda 表达式</span><span class="sxs-lookup"><span data-stu-id="6351a-138">lambda expression</span></span>  
 <span data-ttu-id="6351a-139">实质上是一个匿名的内联函数，可用在任何需要委托类型的地方。</span><span class="sxs-lookup"><span data-stu-id="6351a-139">Essentially, an inline anonymous function that can be used wherever a delegate type is expected.</span></span> <span data-ttu-id="6351a-140">这是对 lambda 表达式的一个简化的定义，但足以满足本教程的需要。</span><span class="sxs-lookup"><span data-stu-id="6351a-140">This is a simplified definition of lambda expressions, but it is adequate for the purposes of this tutorial.</span></span>  
  
 <span data-ttu-id="6351a-141">有关详细信息，请参阅[Lambda 表达式](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="6351a-141">For more information about, see [Lambda Expressions](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
 <span data-ttu-id="6351a-142">集合</span><span class="sxs-lookup"><span data-stu-id="6351a-142">collection</span></span>  
 <span data-ttu-id="6351a-143">结构化的一组数据，通常具有统一的类型。</span><span class="sxs-lookup"><span data-stu-id="6351a-143">A structured set of data, usually of a uniform type.</span></span> <span data-ttu-id="6351a-144">若要与 LINQ 兼容，集合必须实现<xref:System.Collections.IEnumerable>接口或<xref:System.Linq.IQueryable>接口 (或它们对应的泛型之一<xref:System.Collections.Generic.IEnumerator%601>或<xref:System.Linq.IQueryable%601>)。</xref:System.Linq.IQueryable%601> </xref:System.Collections.Generic.IEnumerator%601> </xref:System.Linq.IQueryable> </xref:System.Collections.IEnumerable></span><span class="sxs-lookup"><span data-stu-id="6351a-144">To be compatible with LINQ, a collection must implement the <xref:System.Collections.IEnumerable> interface or the <xref:System.Linq.IQueryable> interface (or one of their generic counterparts, <xref:System.Collections.Generic.IEnumerator%601> or <xref:System.Linq.IQueryable%601>).</span></span>  
  
 <span data-ttu-id="6351a-145">元组（匿名类型）</span><span class="sxs-lookup"><span data-stu-id="6351a-145">tuple (anonymous types)</span></span>  
 <span data-ttu-id="6351a-146">一个数学概念，元组是一个有限的对象序列，每个对象具有特定的类型。</span><span class="sxs-lookup"><span data-stu-id="6351a-146">A mathematical concept, a tuple is a finite sequence of objects, each of a specific type.</span></span> <span data-ttu-id="6351a-147">元组也称为有序列表。</span><span class="sxs-lookup"><span data-stu-id="6351a-147">A tuple is also known as an ordered list.</span></span> <span data-ttu-id="6351a-148">匿名类型是此概念的语言实现，支持在声明未命名类类型的同时实例化该类型的对象。</span><span class="sxs-lookup"><span data-stu-id="6351a-148">Anonymous types are a language implementation of this concept, which enable an unnamed class type to be declared and an object of that type to be instantiated at the same time.</span></span>  
  
 <span data-ttu-id="6351a-149">有关详细信息，请参阅[匿名类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)。</span><span class="sxs-lookup"><span data-stu-id="6351a-149">For more information, see  [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
 <span data-ttu-id="6351a-150">类型推理（隐式确定类型）</span><span class="sxs-lookup"><span data-stu-id="6351a-150">type inference (implicit typing)</span></span>  
 <span data-ttu-id="6351a-151">在没有显式类型声明的情况下编译器确定变量类型的能力。</span><span class="sxs-lookup"><span data-stu-id="6351a-151">The ability of a compiler to determine the type of a variable in the absence of an explicit type declaration.</span></span>  
  
 <span data-ttu-id="6351a-152">有关详细信息，请参阅[本地类型推理](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)。</span><span class="sxs-lookup"><span data-stu-id="6351a-152">For more information, see [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>  
  
 <span data-ttu-id="6351a-153">延迟执行和迟缓计算</span><span class="sxs-lookup"><span data-stu-id="6351a-153">deferred execution and lazy evaluation</span></span>  
 <span data-ttu-id="6351a-154">延迟表达式的计算，直到实际需要它的求解值。</span><span class="sxs-lookup"><span data-stu-id="6351a-154">The delaying of evaluation of an expression until its resolved value is actually required.</span></span> <span data-ttu-id="6351a-155">集合中支持延迟执行。</span><span class="sxs-lookup"><span data-stu-id="6351a-155">Deferred execution is supported in collections.</span></span>  
  
 <span data-ttu-id="6351a-156">有关详细信息，请参阅[基本查询操作 (Visual Basic 中)](../../../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md)和[延迟执行和迟缓计算 LINQ to XML (Visual Basic 中) 中](../../../../visual-basic/programming-guide/concepts/linq/deferred-execution-and-lazy-evaluation-in-linq-to-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="6351a-156">For more information, see [Basic Query Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md) and [Deferred Execution and Lazy Evaluation in LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/deferred-execution-and-lazy-evaluation-in-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="6351a-157">本节各处的代码示例中将使用这些语言功能。</span><span class="sxs-lookup"><span data-stu-id="6351a-157">These language features will be used in code samples throughout this section.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6351a-158">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6351a-158">See Also</span></span>  
 <span data-ttu-id="6351a-159">[介绍纯函数转换 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="6351a-159">[Introduction to Pure Functional Transformations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md) </span></span>  
<span data-ttu-id="6351a-160"> [函数编程与命令式编程 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/functional-programming-vs-imperative-programming.md)</span><span class="sxs-lookup"><span data-stu-id="6351a-160"> [Functional Programming vs. Imperative Programming (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/functional-programming-vs-imperative-programming.md)</span></span>
