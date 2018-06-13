---
title: 使用 .NET Compiler Platform SDK 语义模型
description: 此概述介绍了用于理解和操作代码的语义节点的类型。
ms.date: 10/15/2017
ms.custom: mvc
ms.openlocfilehash: cf34e2ab9688325f58cb54755db4142a883fca77
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33357483"
---
# <a name="work-with-semantics"></a><span data-ttu-id="7a692-103">使用语义</span><span class="sxs-lookup"><span data-stu-id="7a692-103">Work with semantics</span></span>

<span data-ttu-id="7a692-104">[语法树](work-with-syntax.md)表示源代码的词法和语法结构。</span><span class="sxs-lookup"><span data-stu-id="7a692-104">[Syntax trees](work-with-syntax.md) represent the lexical and syntactic structure of source code.</span></span> <span data-ttu-id="7a692-105">尽管此信息已足以描述源中的所有声明和逻辑，但不足以识别正在引用的内容。</span><span class="sxs-lookup"><span data-stu-id="7a692-105">Although this information alone is enough to describe all the declarations and logic in the source, it is not enough information to identify what is being referenced.</span></span> <span data-ttu-id="7a692-106">一个名称可能表示：</span><span class="sxs-lookup"><span data-stu-id="7a692-106">A name may represent:</span></span>

- <span data-ttu-id="7a692-107">一种类型</span><span class="sxs-lookup"><span data-stu-id="7a692-107">a type</span></span>
- <span data-ttu-id="7a692-108">一个字段</span><span class="sxs-lookup"><span data-stu-id="7a692-108">a field</span></span>
- <span data-ttu-id="7a692-109">一种方法</span><span class="sxs-lookup"><span data-stu-id="7a692-109">a method</span></span>
- <span data-ttu-id="7a692-110">一个局部变量</span><span class="sxs-lookup"><span data-stu-id="7a692-110">a local variable</span></span>

<span data-ttu-id="7a692-111">尽管以上每一项都各不相同，但要确定标识符实际上引用哪一项，通常需要深入了解语言规则。</span><span class="sxs-lookup"><span data-stu-id="7a692-111">Although each of these is uniquely different, determining which one an identifier actually refers to often requires a deep understanding of the language rules.</span></span> 

<span data-ttu-id="7a692-112">源代码中还表示了程序元素，并且程序也可引用以前编译的库，这些库打包在程序集文件中。</span><span class="sxs-lookup"><span data-stu-id="7a692-112">There are program elements represented in source code, and programs can also refer to previously compiled libraries, packaged in assembly files.</span></span> <span data-ttu-id="7a692-113">尽管没有任何可用于程序集的源代码（因此没有任何可用于程序集的语法节点或语法树），程序仍可引用其中的元素。</span><span class="sxs-lookup"><span data-stu-id="7a692-113">Although no source code, and therefore no syntax nodes or trees, are available for assemblies, programs can still refer to elements inside them.</span></span>

<span data-ttu-id="7a692-114">对于这些任务，需要语义模型。</span><span class="sxs-lookup"><span data-stu-id="7a692-114">For those tasks, you need the **Semantic model**.</span></span>

<span data-ttu-id="7a692-115">除了源代码的语法模型外，语义模型还封装了语言规则，提供了一种将标识符与正在引用的正确程序元素正确匹配的简单办法。</span><span class="sxs-lookup"><span data-stu-id="7a692-115">In addition to a syntactic model of the source code, a semantic model encapsulates the language rules, giving you an easy way to correctly match identifiers with the correct program element being referenced.</span></span>

## <a name="compilation"></a><span data-ttu-id="7a692-116">编译</span><span class="sxs-lookup"><span data-stu-id="7a692-116">Compilation</span></span>

<span data-ttu-id="7a692-117">编译是编译 C# 或 Visual Basic 程序所需的所有内容的表示形式，其中包括所有程序集引用、编译器选项和源文件。</span><span class="sxs-lookup"><span data-stu-id="7a692-117">A compilation is a representation of everything needed to compile a C# or Visual Basic program, which includes all the assembly references, compiler options, and source files.</span></span> 

<span data-ttu-id="7a692-118">由于所有这些信息都存储在一个位置，因此可以更详细地描述源代码中包含的元素。</span><span class="sxs-lookup"><span data-stu-id="7a692-118">Because all this information is in one place, the elements contained in the source code can be described in more detail.</span></span> <span data-ttu-id="7a692-119">编译以符号的形式表示每个声明的类型、成员或变量。</span><span class="sxs-lookup"><span data-stu-id="7a692-119">The compilation represents each declared type, member, or variable as a symbol.</span></span> <span data-ttu-id="7a692-120">编译包含多种方法，可帮助查找和关联在源代码中声明的符号或作为元数据从程序集中导出的符号。</span><span class="sxs-lookup"><span data-stu-id="7a692-120">The compilation contains a variety of methods that help you find and relate the symbols that have either been declared in the source code or imported as metadata from an assembly.</span></span>

<span data-ttu-id="7a692-121">与语法树类似，编译是不可变的。</span><span class="sxs-lookup"><span data-stu-id="7a692-121">Similar to syntax trees, compilations are immutable.</span></span> <span data-ttu-id="7a692-122">创建编译后，创建者或可能与之共享该编译的任何其他用户均不可进行更改。</span><span class="sxs-lookup"><span data-stu-id="7a692-122">After you create a compilation, it cannot be changed by you or anyone else you might be sharing it with.</span></span> <span data-ttu-id="7a692-123">但是，可以从现有编译创建新编译，指定进行的更改。</span><span class="sxs-lookup"><span data-stu-id="7a692-123">However, you can create a new compilation from an existing compilation, specifying a change as you do so.</span></span> <span data-ttu-id="7a692-124">例如，可以创建与现有编译各方面均相同、但可能包含其他源文件或程序集引用的编译。</span><span class="sxs-lookup"><span data-stu-id="7a692-124">For example, you might create a compilation that is the same in every way as an existing compilation, except it may include an additional source file or assembly reference.</span></span>

## <a name="symbols"></a><span data-ttu-id="7a692-125">符号</span><span class="sxs-lookup"><span data-stu-id="7a692-125">Symbols</span></span>

<span data-ttu-id="7a692-126">符号表示源代码声明的不同元素，或作为元数据从程序集中导出。</span><span class="sxs-lookup"><span data-stu-id="7a692-126">A symbol represents a distinct element declared by the source code or imported from an assembly as metadata.</span></span> <span data-ttu-id="7a692-127">每个命名空间、类型、方法、属性、字段、事件、参数或局部变量都由符号表示。</span><span class="sxs-lookup"><span data-stu-id="7a692-127">Every namespace, type, method, property, field, event, parameter, or local variable is represented by a symbol.</span></span> 

<span data-ttu-id="7a692-128"><xref:Microsoft.CodeAnalysis.Compilation> 类型的各种方法和属性可帮助查找符号。</span><span class="sxs-lookup"><span data-stu-id="7a692-128">A variety of methods and properties on the <xref:Microsoft.CodeAnalysis.Compilation> type help you find symbols.</span></span> <span data-ttu-id="7a692-129">例如，可以通过声明的类型的通用元数据名称来查找该类型的符号。</span><span class="sxs-lookup"><span data-stu-id="7a692-129">For example, you can find a symbol for a declared type by its common metadata name.</span></span> <span data-ttu-id="7a692-130">还可以访问整个符号表，该表是以全局命名空间为根的符号树。</span><span class="sxs-lookup"><span data-stu-id="7a692-130">You can also access the entire symbol table as a tree of symbols rooted by the global namespace.</span></span>

<span data-ttu-id="7a692-131">符号还包含编译器根据源或元数据（如其他引用的符号）确定的其他信息。</span><span class="sxs-lookup"><span data-stu-id="7a692-131">Symbols also contain additional information that the compiler determines from the source or metadata, such as other referenced symbols.</span></span> <span data-ttu-id="7a692-132">每种类型的符号都由派生自 <xref:Microsoft.CodeAnalysis.ISymbol> 的单独接口表示，每种符号都有其自己的方法和属性，详细说明了编译器收集的信息。</span><span class="sxs-lookup"><span data-stu-id="7a692-132">Each kind of symbol is represented by a separate interface derived from <xref:Microsoft.CodeAnalysis.ISymbol>, each with its own methods and properties detailing the information the compiler has gathered.</span></span> <span data-ttu-id="7a692-133">其中许多属性直接引用了其他符号。</span><span class="sxs-lookup"><span data-stu-id="7a692-133">Many of these properties directly reference other symbols.</span></span> <span data-ttu-id="7a692-134">例如，可通过 <xref:Microsoft.CodeAnalysis.IMethodSymbol.ReturnType?displayProperty=nameWithType> 属性得知方法声明引用的实际类型符号。</span><span class="sxs-lookup"><span data-stu-id="7a692-134">For example, the <xref:Microsoft.CodeAnalysis.IMethodSymbol.ReturnType?displayProperty=nameWithType> property tells you the actual type symbol that the method declaration references.</span></span>

<span data-ttu-id="7a692-135">符号提供了源代码与元数据之间命名空间、类型和成员的共同表示形式。</span><span class="sxs-lookup"><span data-stu-id="7a692-135">Symbols present a common representation of namespaces, types, and members, between source code and metadata.</span></span> <span data-ttu-id="7a692-136">例如，在源代码中声明的方法以及从元数据导入的方法均由具有相同属性的 <xref:Microsoft.CodeAnalysis.IMethodSymbol> 表示。</span><span class="sxs-lookup"><span data-stu-id="7a692-136">For example, a method that was declared in source code and a method that was imported from metadata are both represented by an <xref:Microsoft.CodeAnalysis.IMethodSymbol> with the same properties.</span></span>

<span data-ttu-id="7a692-137">符号在概念上类似于 <xref:System.Reflection> API 表示的 CLR 类型系统，但前者更丰富，因为它们不仅仅可以对类型建模。</span><span class="sxs-lookup"><span data-stu-id="7a692-137">Symbols are similar in concept to the CLR type system as represented by the <xref:System.Reflection> API, yet they are richer in that they model more than just types.</span></span> <span data-ttu-id="7a692-138">命名空间、局部变量和标签都是符号。</span><span class="sxs-lookup"><span data-stu-id="7a692-138">Namespaces, local variables, and labels are all symbols.</span></span> <span data-ttu-id="7a692-139">此外，符号是语言概念，而不是 CLR 概念的表示形式。</span><span class="sxs-lookup"><span data-stu-id="7a692-139">In addition, symbols are a representation of language concepts, not CLR concepts.</span></span> <span data-ttu-id="7a692-140">存在很多重叠，但也有许多有意义的区别。</span><span class="sxs-lookup"><span data-stu-id="7a692-140">There is a lot of overlap, but there are many meaningful distinctions as well.</span></span> <span data-ttu-id="7a692-141">例如，在 C# 或 Visual Basic 中，迭代器方法是单个符号。</span><span class="sxs-lookup"><span data-stu-id="7a692-141">For instance, an iterator method in C# or Visual Basic is a single symbol.</span></span> <span data-ttu-id="7a692-142">但是，当迭代器方法转换为 CLR 元数据时，它是一种类型和多个方法。</span><span class="sxs-lookup"><span data-stu-id="7a692-142">However, when the iterator method is translated to CLR metadata, it is a type and multiple methods.</span></span>

## <a name="semantic-model"></a><span data-ttu-id="7a692-143">语义模型</span><span class="sxs-lookup"><span data-stu-id="7a692-143">Semantic model</span></span>

<span data-ttu-id="7a692-144">语义模型表示单个源文件的所有语义信息。</span><span class="sxs-lookup"><span data-stu-id="7a692-144">A semantic model represents all the semantic information for a single source file.</span></span> <span data-ttu-id="7a692-145">可使用语义模型发现以下内容：</span><span class="sxs-lookup"><span data-stu-id="7a692-145">You can use it to discover the following:</span></span> 

* <span data-ttu-id="7a692-146">在源中特定位置引用的符号。</span><span class="sxs-lookup"><span data-stu-id="7a692-146">The symbols referenced at a specific location in source.</span></span>
* <span data-ttu-id="7a692-147">任何表达式的结果类型。</span><span class="sxs-lookup"><span data-stu-id="7a692-147">The resultant type of any expression.</span></span>
* <span data-ttu-id="7a692-148">所有诊断（错误和警告）。</span><span class="sxs-lookup"><span data-stu-id="7a692-148">All diagnostics, which are errors and warnings.</span></span>
* <span data-ttu-id="7a692-149">变量流入和流出源区域的方式。</span><span class="sxs-lookup"><span data-stu-id="7a692-149">How variables flow in and out of regions of source.</span></span>
* <span data-ttu-id="7a692-150">更多推理问题的答案。</span><span class="sxs-lookup"><span data-stu-id="7a692-150">The answers to more speculative questions.</span></span>
