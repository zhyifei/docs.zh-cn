---
title: "Visual Basic 语言功能"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, elements of
- Visual Basic code
ms.assetid: b0b21730-298c-47e6-9a2f-cc81f628067b
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f7074206baa51259592cca3fdc224d99438791f9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="visual-basic-language-features"></a><span data-ttu-id="c3b88-102">Visual Basic 语言功能</span><span class="sxs-lookup"><span data-stu-id="c3b88-102">Visual Basic Language Features</span></span>
<span data-ttu-id="c3b88-103">下面各主题介绍并讨论了 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]（面向对象的编程语言）的基本组成部分。</span><span class="sxs-lookup"><span data-stu-id="c3b88-103">The following topics introduce and discuss the essential components of [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], an object-oriented programming language.</span></span> <span data-ttu-id="c3b88-104">使用窗体和控件创建应用程序的用户界面后，需要编写代码来定义应用程序的行为。</span><span class="sxs-lookup"><span data-stu-id="c3b88-104">After creating the user interface for your application using forms and controls, you need to write the code that defines the application's behavior.</span></span> <span data-ttu-id="c3b88-105">与所有新式编程语言一样，[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 支持许多常见的编程构造和语言元素。</span><span class="sxs-lookup"><span data-stu-id="c3b88-105">As with any modern programming language, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] supports a number of common programming constructs and language elements.</span></span>  
  
 <span data-ttu-id="c3b88-106">如果你已使用其他语言进行过编程，可能会对此部分中介绍的大部分资料感到熟悉。</span><span class="sxs-lookup"><span data-stu-id="c3b88-106">If you have programmed in other languages, much of the material covered in this section might seem familiar.</span></span> <span data-ttu-id="c3b88-107">虽然大多数构造与其他语言的构造类似，但 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 的事件驱动本质却造成了细微差异。</span><span class="sxs-lookup"><span data-stu-id="c3b88-107">While most of the constructs are similar to those in other languages, the event-driven nature of [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] introduces some subtle differences.</span></span>  
  
 <span data-ttu-id="c3b88-108">如果是刚开始接触编程，可通过此部分中的资料，了解用于编写代码的基本构建基块的入门知识。</span><span class="sxs-lookup"><span data-stu-id="c3b88-108">If you are new to programming, the material in this section serves as an introduction to the basic building blocks for writing code.</span></span> <span data-ttu-id="c3b88-109">掌握基础知识后，便能使用 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 创建强大的应用程序。</span><span class="sxs-lookup"><span data-stu-id="c3b88-109">Once you understand the basics, you can create powerful applications using [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c3b88-110">本节内容</span><span class="sxs-lookup"><span data-stu-id="c3b88-110">In This Section</span></span>  
 [<span data-ttu-id="c3b88-111">阵列</span><span class="sxs-lookup"><span data-stu-id="c3b88-111">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 <span data-ttu-id="c3b88-112">介绍了如何通过声明和使用包含多个相关值的数组，让代码变得更紧凑、更强大。</span><span class="sxs-lookup"><span data-stu-id="c3b88-112">Discusses making your code more compact and powerful by declaring and using arrays, which hold multiple related values.</span></span>  
  
 [<span data-ttu-id="c3b88-113">集合初始值设定项</span><span class="sxs-lookup"><span data-stu-id="c3b88-113">Collection Initializers</span></span>](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)  
 <span data-ttu-id="c3b88-114">介绍了集合初始值设定项。使用它，可以创建集合并在其中填充一组初始值。</span><span class="sxs-lookup"><span data-stu-id="c3b88-114">Describes collection initializers, which enable you to create a collection and populate it with an initial set of values.</span></span>  
  
 [<span data-ttu-id="c3b88-115">常量和枚举</span><span class="sxs-lookup"><span data-stu-id="c3b88-115">Constants and Enumerations</span></span>](../../../visual-basic/programming-guide/language-features/constants-enums/index.md)  
 <span data-ttu-id="c3b88-116">介绍了如何存储固定不变的值（包括各组相关常量值）以供重用。</span><span class="sxs-lookup"><span data-stu-id="c3b88-116">Discusses storing unchanging values for repeated use, including sets of related constant values.</span></span>  
  
 [<span data-ttu-id="c3b88-117">控制流</span><span class="sxs-lookup"><span data-stu-id="c3b88-117">Control Flow</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 <span data-ttu-id="c3b88-118">介绍了如何控制程序的执行流。</span><span class="sxs-lookup"><span data-stu-id="c3b88-118">Shows how to regulate the flow of your program's execution.</span></span>  
  
 [<span data-ttu-id="c3b88-119">数据类型</span><span class="sxs-lookup"><span data-stu-id="c3b88-119">Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 <span data-ttu-id="c3b88-120">介绍了编程元素可以保留的数据类型以及数据的存储方式。</span><span class="sxs-lookup"><span data-stu-id="c3b88-120">Describes what kinds of data a programming element can hold and how that data is stored.</span></span>  
  
 [<span data-ttu-id="c3b88-121">已声明的元素</span><span class="sxs-lookup"><span data-stu-id="c3b88-121">Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/index.md)  
 <span data-ttu-id="c3b88-122">介绍了可以声明的编程元素及其名称和特征，以及编译器如何解析对这些元素的引用。</span><span class="sxs-lookup"><span data-stu-id="c3b88-122">Covers programming elements you can declare, their names and characteristics, and how the compiler resolves references to them.</span></span>  
  
 [<span data-ttu-id="c3b88-123">委托</span><span class="sxs-lookup"><span data-stu-id="c3b88-123">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 <span data-ttu-id="c3b88-124">介绍了委托及其在 Visual Basic 中的使用方式。</span><span class="sxs-lookup"><span data-stu-id="c3b88-124">Provides an introduction to delegates and how they are used in Visual Basic.</span></span>  
  
 [<span data-ttu-id="c3b88-125">早期绑定和后期绑定</span><span class="sxs-lookup"><span data-stu-id="c3b88-125">Early and Late Binding</span></span>](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)  
 <span data-ttu-id="c3b88-126">介绍了在对象被分配给对象变量时编译器执行的绑定，以及早期绑定和晚期绑定对象的区别。</span><span class="sxs-lookup"><span data-stu-id="c3b88-126">Describes binding, which is performed by the compiler when an object is assigned to an object variable, and the differences between early-bound and late-bound objects.</span></span>  
  
 [<span data-ttu-id="c3b88-127">错误类型</span><span class="sxs-lookup"><span data-stu-id="c3b88-127">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)  
 <span data-ttu-id="c3b88-128">概述了语法错误、运行时错误和逻辑错误。</span><span class="sxs-lookup"><span data-stu-id="c3b88-128">Provides an overview of syntax errors, run-time errors, and logic errors.</span></span>  
  
 [<span data-ttu-id="c3b88-129">事件</span><span class="sxs-lookup"><span data-stu-id="c3b88-129">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)  
 <span data-ttu-id="c3b88-130">介绍了如何声明和使用事件。</span><span class="sxs-lookup"><span data-stu-id="c3b88-130">Shows how to declare and use events.</span></span>  
  
 [<span data-ttu-id="c3b88-131">接口</span><span class="sxs-lookup"><span data-stu-id="c3b88-131">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)  
 <span data-ttu-id="c3b88-132">介绍了什么是接口，以及如何在应用程序中使用接口。</span><span class="sxs-lookup"><span data-stu-id="c3b88-132">Describes what interfaces are and how you can use them in your applications.</span></span>  
  
 [<span data-ttu-id="c3b88-133">LINQ</span><span class="sxs-lookup"><span data-stu-id="c3b88-133">LINQ</span></span>](../../../visual-basic/programming-guide/language-features/linq/index.md)  
 <span data-ttu-id="c3b88-134">收录了主题链接，有助于你了解[!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] 功能和编程。</span><span class="sxs-lookup"><span data-stu-id="c3b88-134">Provides links to topics that introduce [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] features and programming.</span></span>  
  
 [<span data-ttu-id="c3b88-135">对象和类</span><span class="sxs-lookup"><span data-stu-id="c3b88-135">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 <span data-ttu-id="c3b88-136">概述了对象和类及其使用方式、相互之间的关系，以及它们公开的属性、方法和事件。</span><span class="sxs-lookup"><span data-stu-id="c3b88-136">Provides an overview of objects and classes, how they are used, their relationships to each other, and the properties, methods, and events they expose.</span></span>  
  
 [<span data-ttu-id="c3b88-137">运算符和表达式</span><span class="sxs-lookup"><span data-stu-id="c3b88-137">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 <span data-ttu-id="c3b88-138">介绍了可控制含值元素的代码元素、如何有效地使用这些元素，以及如何结合使用它们来生成新值。</span><span class="sxs-lookup"><span data-stu-id="c3b88-138">Describes the code elements that manipulate value-holding elements, how to use them efficiently, and how to combine them to yield new values.</span></span>  
  
 [<span data-ttu-id="c3b88-139">过程</span><span class="sxs-lookup"><span data-stu-id="c3b88-139">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 <span data-ttu-id="c3b88-140">介绍了 `Sub`、`Function`、`Property` 和 `Operator` 过程，以及递归和已重载过程等高级主题。</span><span class="sxs-lookup"><span data-stu-id="c3b88-140">Describes `Sub`, `Function`, `Property`, and `Operator` procedures, as well as advanced topics such as recursive and overloaded procedures.</span></span>  
  
 [<span data-ttu-id="c3b88-141">语句</span><span class="sxs-lookup"><span data-stu-id="c3b88-141">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)  
 <span data-ttu-id="c3b88-142">介绍了声明和可执行语句。</span><span class="sxs-lookup"><span data-stu-id="c3b88-142">Describes declaration and executable statements.</span></span>  
  
 [<span data-ttu-id="c3b88-143">字符串</span><span class="sxs-lookup"><span data-stu-id="c3b88-143">Strings</span></span>](../../../visual-basic/programming-guide/language-features/strings/index.md)  
 <span data-ttu-id="c3b88-144">收录了主题链接，有助于你了解如何在 Visual Basic 中使用字符串的基本概念。</span><span class="sxs-lookup"><span data-stu-id="c3b88-144">Provides links to topics that describe the basic concepts about using strings in Visual Basic.</span></span>  
  
 [<span data-ttu-id="c3b88-145">变量</span><span class="sxs-lookup"><span data-stu-id="c3b88-145">Variables</span></span>](../../../visual-basic/programming-guide/language-features/variables/index.md)  
 <span data-ttu-id="c3b88-146">介绍了变量以及如何在 Visual Basic 中使用变量。</span><span class="sxs-lookup"><span data-stu-id="c3b88-146">Introduces variables and describes how to use them in Visual Basic.</span></span>  
  
 [<span data-ttu-id="c3b88-147">XML</span><span class="sxs-lookup"><span data-stu-id="c3b88-147">XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/index.md)  
 <span data-ttu-id="c3b88-148">收录了主题链接，有助于你了解如何在 Visual Basic 中使用 XML。</span><span class="sxs-lookup"><span data-stu-id="c3b88-148">Provides links to topics that describe how to use XML in Visual Basic.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c3b88-149">相关章节</span><span class="sxs-lookup"><span data-stu-id="c3b88-149">Related Sections</span></span>  
 [<span data-ttu-id="c3b88-150">集合</span><span class="sxs-lookup"><span data-stu-id="c3b88-150">Collections</span></span>](http://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b)  
 <span data-ttu-id="c3b88-151">介绍了 .NET Framework 提供的一些类型集合。</span><span class="sxs-lookup"><span data-stu-id="c3b88-151">Describes some of the types of collections that are provided by the .NET Framework.</span></span> <span data-ttu-id="c3b88-152">展示了如何使用简单的集合和键/值对集合。</span><span class="sxs-lookup"><span data-stu-id="c3b88-152">Demonstrates how to use simple collections and collections of key/value pairs.</span></span>  
  
 [<span data-ttu-id="c3b88-153">Visual Basic 语言参考</span><span class="sxs-lookup"><span data-stu-id="c3b88-153">Visual Basic Language Reference</span></span>](../../../visual-basic/language-reference/index.md)  
 <span data-ttu-id="c3b88-154">收录了有关 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 编程的各方面参考信息。</span><span class="sxs-lookup"><span data-stu-id="c3b88-154">Provides reference information on various aspects of [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] programming.</span></span>
