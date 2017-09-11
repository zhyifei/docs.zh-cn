---
title: "程序结构和代码约定 (Visual Basic 中) |Microsoft 文档"
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
- coding conventions
- Visual Basic code, coding conventions
- coding conventions, Visual Basic
- programs, structure
- program structure
- naming conventions, Visual Basic
- best practices, coding conventions
- conventions, Visual Basic coding
- Visual Basic code
- programming, Visual Basic coding conventions
ms.assetid: dd9be76f-6944-4e78-ad72-0b6084a3fc13
caps.latest.revision: 21
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
ms.openlocfilehash: c3a091d64b3c55ad3f1291a635fd499da2dacdc8
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="program-structure-and-code-conventions-visual-basic"></a><span data-ttu-id="bfaee-102">程序结构和代码约定 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bfaee-102">Program Structure and Code Conventions (Visual Basic)</span></span>
<span data-ttu-id="bfaee-103">本部分介绍的典型[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]程序结构中，提供了一个简单[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]程序，"Hello，World"，并讨论了[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]代码约定。</span><span class="sxs-lookup"><span data-stu-id="bfaee-103">This section introduces the typical [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] program structure, provides a simple [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] program, "Hello, World", and discusses [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] code conventions.</span></span> <span data-ttu-id="bfaee-104">代码约定是针对不是程序的逻辑，而是其物理结构和外观的建议值。</span><span class="sxs-lookup"><span data-stu-id="bfaee-104">Code conventions are suggestions that focus not on a program's logic but on its physical structure and appearance.</span></span> <span data-ttu-id="bfaee-105">按照它们使您的代码易于阅读、 理解和维护。</span><span class="sxs-lookup"><span data-stu-id="bfaee-105">Following them makes your code easier to read, understand, and maintain.</span></span> <span data-ttu-id="bfaee-106">其他项中，代码约定，可以包括︰</span><span class="sxs-lookup"><span data-stu-id="bfaee-106">Code conventions can include, among others:</span></span>  
  
-   <span data-ttu-id="bfaee-107">添加标记和注释的代码的标准化的格式。</span><span class="sxs-lookup"><span data-stu-id="bfaee-107">Standardized formats for labeling and commenting code.</span></span>  
  
-   <span data-ttu-id="bfaee-108">间距、 格式和缩进代码的指南。</span><span class="sxs-lookup"><span data-stu-id="bfaee-108">Guidelines for spacing, formatting, and indenting code.</span></span>  
  
-   <span data-ttu-id="bfaee-109">对象、 变量和过程的命名约定。</span><span class="sxs-lookup"><span data-stu-id="bfaee-109">Naming conventions for objects, variables, and procedures.</span></span>  
  
 <span data-ttu-id="bfaee-110">下列主题显示了一组编程指导方针[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]计划，以及一些很好的用法示例。</span><span class="sxs-lookup"><span data-stu-id="bfaee-110">The following topics present a set of programming guidelines for [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] programs, along with examples of good usage.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bfaee-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="bfaee-111">In This Section</span></span>  
 [<span data-ttu-id="bfaee-112">Visual Basic 程序的结构</span><span class="sxs-lookup"><span data-stu-id="bfaee-112">Structure of a Visual Basic Program</span></span>](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)  
 <span data-ttu-id="bfaee-113">提供构成元素的概述[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]程序。</span><span class="sxs-lookup"><span data-stu-id="bfaee-113">Provides an overview of the elements that make up a [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] program.</span></span>  
  
 [<span data-ttu-id="bfaee-114">在 Visual Basic 中的 main 过程</span><span class="sxs-lookup"><span data-stu-id="bfaee-114">Main Procedure in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/main-procedure.md)  
 <span data-ttu-id="bfaee-115">讨论的过程作为起始点，以及对您的应用程序总体控制。</span><span class="sxs-lookup"><span data-stu-id="bfaee-115">Discusses the procedure that serves as the starting point and overall control for your application.</span></span>  
  
 [<span data-ttu-id="bfaee-116">引用和 Imports 语句</span><span class="sxs-lookup"><span data-stu-id="bfaee-116">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)  
 <span data-ttu-id="bfaee-117">讨论如何引用其他程序集中的对象。</span><span class="sxs-lookup"><span data-stu-id="bfaee-117">Discusses how to reference objects in other assemblies.</span></span>  
  
 [<span data-ttu-id="bfaee-118">在 Visual Basic 中的命名空间</span><span class="sxs-lookup"><span data-stu-id="bfaee-118">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 <span data-ttu-id="bfaee-119">描述如何命名空间组织内的程序集的对象。</span><span class="sxs-lookup"><span data-stu-id="bfaee-119">Describes how namespaces organize objects within assemblies.</span></span>  
  
 [<span data-ttu-id="bfaee-120">Visual Basic 命名约定</span><span class="sxs-lookup"><span data-stu-id="bfaee-120">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 <span data-ttu-id="bfaee-121">包括命名过程、 常量、 变量、 参数和对象的一般准则。</span><span class="sxs-lookup"><span data-stu-id="bfaee-121">Includes general guidelines for naming procedures, constants, variables, arguments, and objects.</span></span>  
  
 [<span data-ttu-id="bfaee-122">Visual Basic 编码约定</span><span class="sxs-lookup"><span data-stu-id="bfaee-122">Visual Basic Coding Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/coding-conventions.md)  
 <span data-ttu-id="bfaee-123">查看在开发本文档中的示例使用的准则。</span><span class="sxs-lookup"><span data-stu-id="bfaee-123">Reviews the guidelines used in developing the samples in this documentation.</span></span>  
  
 [<span data-ttu-id="bfaee-124">条件编译</span><span class="sxs-lookup"><span data-stu-id="bfaee-124">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 <span data-ttu-id="bfaee-125">描述如何同时控制编译器忽略其他有选择性地编译的代码的特定块。</span><span class="sxs-lookup"><span data-stu-id="bfaee-125">Describes how to compile particular blocks of code selectively while directing the compiler to ignore others.</span></span>  
  
 [<span data-ttu-id="bfaee-126">如何：在代码中拆分和合并语句</span><span class="sxs-lookup"><span data-stu-id="bfaee-126">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)  
 <span data-ttu-id="bfaee-127">演示如何将划分为多行的长语句和合并内容位于一行的短语句。</span><span class="sxs-lookup"><span data-stu-id="bfaee-127">Shows how to divide long statements into multiple lines and combine short statements on one line.</span></span>  
  
 [<span data-ttu-id="bfaee-128">如何：折叠和隐藏代码节</span><span class="sxs-lookup"><span data-stu-id="bfaee-128">How to: Collapse and Hide Sections of Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)  
 <span data-ttu-id="bfaee-129">演示如何以折叠和隐藏代码节[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]代码编辑器中。</span><span class="sxs-lookup"><span data-stu-id="bfaee-129">Shows how to collapse and hide sections of code in the [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] code editor.</span></span>  
  
 [<span data-ttu-id="bfaee-130">如何：标记语句</span><span class="sxs-lookup"><span data-stu-id="bfaee-130">How to: Label Statements</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)  
 <span data-ttu-id="bfaee-131">演示如何将标记的一行代码以将其标识用于使用语句如`On Error Goto`。</span><span class="sxs-lookup"><span data-stu-id="bfaee-131">Shows how to mark a line of code to identify it for use with statements such as `On Error Goto`.</span></span>  
  
 [<span data-ttu-id="bfaee-132">代码中的特殊字符</span><span class="sxs-lookup"><span data-stu-id="bfaee-132">Special Characters in Code</span></span>](../../../visual-basic/programming-guide/program-structure/special-characters-in-code.md)  
 <span data-ttu-id="bfaee-133">演示如何以及在何处使用非数字和非字母字符。</span><span class="sxs-lookup"><span data-stu-id="bfaee-133">Shows how and where to use non-numeric and non-alphabetic characters.</span></span>  
  
 [<span data-ttu-id="bfaee-134">代码中的注释</span><span class="sxs-lookup"><span data-stu-id="bfaee-134">Comments in Code</span></span>](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)  
 <span data-ttu-id="bfaee-135">讨论如何向代码中添加说明性注释。</span><span class="sxs-lookup"><span data-stu-id="bfaee-135">Discusses how to add descriptive comments to your code.</span></span>  
  
 [<span data-ttu-id="bfaee-136">代码中用作元素名称的关键字</span><span class="sxs-lookup"><span data-stu-id="bfaee-136">Keywords as Element Names in Code</span></span>](../../../visual-basic/programming-guide/program-structure/keywords-as-element-names-in-code.md)  
 <span data-ttu-id="bfaee-137">介绍如何使用方括号 (`[]`) 来分隔还有的变量名[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]关键字。</span><span class="sxs-lookup"><span data-stu-id="bfaee-137">Describes how to use brackets (`[]`) to delimit variable names that are also [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] keywords.</span></span>  
  
 [<span data-ttu-id="bfaee-138">Me、My、MyBase 和 MyClass</span><span class="sxs-lookup"><span data-stu-id="bfaee-138">Me, My, MyBase, and MyClass</span></span>](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 <span data-ttu-id="bfaee-139">介绍各种方式引用的元素[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]程序。</span><span class="sxs-lookup"><span data-stu-id="bfaee-139">Describes various ways to refer to elements of a [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] program.</span></span>  
  
 [<span data-ttu-id="bfaee-140">Visual Basic 限制</span><span class="sxs-lookup"><span data-stu-id="bfaee-140">Visual Basic Limitations</span></span>](../../../visual-basic/programming-guide/program-structure/limitations.md)  
 <span data-ttu-id="bfaee-141">讨论中已知的编码限制删除[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bfaee-141">Discusses the removal of known coding limits within [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="bfaee-142">相关章节</span><span class="sxs-lookup"><span data-stu-id="bfaee-142">Related Sections</span></span>  
 [<span data-ttu-id="bfaee-143">版式和代码约定</span><span class="sxs-lookup"><span data-stu-id="bfaee-143">Typographic and Code Conventions</span></span>](../../../visual-basic/language-reference/typographic-and-code-conventions.md)  
 <span data-ttu-id="bfaee-144">提供了有关标准编码约定[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bfaee-144">Provides standard coding conventions for [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
 [<span data-ttu-id="bfaee-145">编写代码</span><span class="sxs-lookup"><span data-stu-id="bfaee-145">Writing Code</span></span>](https://docs.microsoft.com/visualstudio/ide/writing-code-in-the-code-and-text-editor)  
 <span data-ttu-id="bfaee-146">介绍使您更轻松地编写和管理您的代码的功能。</span><span class="sxs-lookup"><span data-stu-id="bfaee-146">Describes features that make it easier for you to write and manage your code.</span></span>
