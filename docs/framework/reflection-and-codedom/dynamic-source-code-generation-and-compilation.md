---
title: "动态源代码生成和编译"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Code Document Object Model
- System.CodeDom namespace
- language-independent source code modeling
- CodeDOM
- multiple languages supported by CodeDOM
- source code in multiple languages
- languages, multiple language support by CodeDOM
ms.assetid: d077a3e8-bd81-4bdf-b6a3-323857ea30fb
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 535a60aa1a174319a4db3403a64c3998784bbb58
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="dynamic-source-code-generation-and-compilation"></a><span data-ttu-id="87b22-102">动态源代码生成和编译</span><span class="sxs-lookup"><span data-stu-id="87b22-102">Dynamic Source Code Generation and Compilation</span></span>
<span data-ttu-id="87b22-103">.NET Framework 包括一个名为代码文档对象模型 (CodeDOM) 的机制。通过该机制，发出源代码的程序开发者可基于一种表示要呈现的代码的单一模型，在运行时以多种编程语言生成源代码。</span><span class="sxs-lookup"><span data-stu-id="87b22-103">The .NET Framework includes a mechanism called the Code Document Object Model (CodeDOM) that enables developers of programs that emit source code to generate source code in multiple programming languages at run time, based on a single model that represents the code to render.</span></span>  
  
 <span data-ttu-id="87b22-104">为表示源代码，CodeDOM 元素相互链接，构成一个名为 CodeDOM 图的数据结构。该数据结构对某些源代码的结构建模。</span><span class="sxs-lookup"><span data-stu-id="87b22-104">To represent source code, CodeDOM elements are linked to each other to form a data structure known as a CodeDOM graph, which models the structure of some source code.</span></span>  
  
 <span data-ttu-id="87b22-105">`System.CodeDom` 命名空间定义某些类型，这些类型可以表示源代码的逻辑结构，且不依赖特定编程语言。</span><span class="sxs-lookup"><span data-stu-id="87b22-105">The `System.CodeDom` namespace defines types that can represent the logical structure of source code, independent of a specific programming language.</span></span> <span data-ttu-id="87b22-106">`System.CodeDom.Compiler` 命名空间定义某些类型，用于从 CodeDOM 图中生成源代码，并管理使用支持语言的源代码的编译工作。</span><span class="sxs-lookup"><span data-stu-id="87b22-106">The `System.CodeDom.Compiler` namespace defines types for generating source code from CodeDOM graphs and managing the compilation of source code in supported languages.</span></span> <span data-ttu-id="87b22-107">编译器供应商或开发人员可以扩展支持语言。</span><span class="sxs-lookup"><span data-stu-id="87b22-107">Compiler vendors or developers can extend the set of supported languages.</span></span>  
  
 <span data-ttu-id="87b22-108">当程序需要为多种语言的程序模型或为某个不确定的目标语言生成源代码时，不依赖语言的源代码建模非常有用。</span><span class="sxs-lookup"><span data-stu-id="87b22-108">Language-independent source code modeling can be valuable when a program needs to generate source code for a program model in multiple languages or for an uncertain target language.</span></span> <span data-ttu-id="87b22-109">例如，某些设计器使用 CodeDOM 作为语言抽象接口生成使用正确编程语言的源代码，前提是 CodeDOM 支持该语言。</span><span class="sxs-lookup"><span data-stu-id="87b22-109">For example, some designers use the CodeDOM as a language abstraction interface to produce source code in the correct programming language, if CodeDOM support for the language is available.</span></span>  
  
 <span data-ttu-id="87b22-110">.NET Framework 包括适用于 <xref:Microsoft.CSharp.CSharpCodeProvider>、<xref:Microsoft.JScript.JScriptCodeProvider> 和 <xref:Microsoft.VisualBasic.VBCodeProvider> 的代码生成器和代码编译器。</span><span class="sxs-lookup"><span data-stu-id="87b22-110">The .NET Framework includes code generators and code compilers for <xref:Microsoft.CSharp.CSharpCodeProvider>, <xref:Microsoft.JScript.JScriptCodeProvider>, and <xref:Microsoft.VisualBasic.VBCodeProvider>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="87b22-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="87b22-111">In This Section</span></span>  
 [<span data-ttu-id="87b22-112">使用 CodeDOM</span><span class="sxs-lookup"><span data-stu-id="87b22-112">Using the CodeDOM</span></span>](../../../docs/framework/reflection-and-codedom/using-the-codedom.md)  
 <span data-ttu-id="87b22-113">介绍 CodeDOM 的常见用途，并演示如何使用 CodeDOM 构建一个简单的对象图。</span><span class="sxs-lookup"><span data-stu-id="87b22-113">Describes common uses, and demonstrates building a simple object graph using the CodeDOM.</span></span>  
  
 [<span data-ttu-id="87b22-114">从 CodeDOM 图中生成源代码并编译程序</span><span class="sxs-lookup"><span data-stu-id="87b22-114">Generating Source Code and Compiling a Program from a CodeDOM Graph</span></span>](../../../docs/framework/reflection-and-codedom/generating-and-compiling-source-code-from-a-codedom-graph.md)  
 <span data-ttu-id="87b22-115">介绍如何使用 `System.CodeDom.Compiler` 命名空间中定义的类，通过外部编译器生成源代码并编译生成的代码。</span><span class="sxs-lookup"><span data-stu-id="87b22-115">Describes how to generate source code and compile the generated code with an external compiler using classes defined in the `System.CodeDom.Compiler` namespace.</span></span>  
  
 [<span data-ttu-id="87b22-116">如何：使用 CodeDOM 创建 XML 文档文件</span><span class="sxs-lookup"><span data-stu-id="87b22-116">How to: Create an XML Documentation File Using CodeDOM</span></span>](../../../docs/framework/reflection-and-codedom/how-to-create-an-xml-documentation-file-using-codedom.md)  
 <span data-ttu-id="87b22-117">介绍如何使用 CodeDOM 生成带有 XML 文档注释的代码，以及如何编译生成的代码以使其创建 XML 文档输出。</span><span class="sxs-lookup"><span data-stu-id="87b22-117">Describes how to use CodeDOM to generate code with XML documentation comments, and compile the generated code so that it creates the XML documentation output.</span></span>  
  
 [<span data-ttu-id="87b22-118">如何：使用 CodeDOM 创建类</span><span class="sxs-lookup"><span data-stu-id="87b22-118">How to: Create a Class Using CodeDOM</span></span>](../../../docs/framework/reflection-and-codedom/how-to-create-a-class-using-codedom.md)  
 <span data-ttu-id="87b22-119">介绍如何使用 CodeDOM 生成包含字段、属性、方法、构造函数和入口点的类。</span><span class="sxs-lookup"><span data-stu-id="87b22-119">Describes how to use CodeDOM to generate a class containing fields, properties, a method, a constructor, and an entry point.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="87b22-120">参考</span><span class="sxs-lookup"><span data-stu-id="87b22-120">Reference</span></span>  
 <xref:System.CodeDom>  
 <span data-ttu-id="87b22-121">定义采用面向公共语言运行时的编程语言表示代码元素的元素。</span><span class="sxs-lookup"><span data-stu-id="87b22-121">Defines elements that represent code elements in programming languages that target the common language runtime.</span></span>  
  
 <xref:System.CodeDom.Compiler>  
 <span data-ttu-id="87b22-122">定义用于在运行时生成和编译代码的接口。</span><span class="sxs-lookup"><span data-stu-id="87b22-122">Defines interfaces for generating and compiling code at run time.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="87b22-123">相关章节</span><span class="sxs-lookup"><span data-stu-id="87b22-123">Related Sections</span></span>  
 [<span data-ttu-id="87b22-124">CodeDOM 快速参考</span><span class="sxs-lookup"><span data-stu-id="87b22-124">CodeDOM Quick Reference</span></span>](http://msdn.microsoft.com/library/c77b8bfd-0a32-4e36-b59a-4f687f32c524)  
 <span data-ttu-id="87b22-125">为开发人员提供了一种方法，使其可以快速查找表示源代码元素的 CodeDOM 元素。</span><span class="sxs-lookup"><span data-stu-id="87b22-125">Provides a quick way for developers to find the CodeDOM elements that represent source code elements.</span></span>
