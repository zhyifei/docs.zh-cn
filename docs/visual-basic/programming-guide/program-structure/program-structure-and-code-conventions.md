---
title: 程序结构和代码约定 (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- coding conventions
- Visual Basic code, coding conventions
- coding conventions [Visual Basic], Visual Basic
- programs [Visual Basic], structure
- program structure [Visual Basic]
- naming conventions [Visual Basic], Visual Basic
- best practices [Visual Basic], coding conventions
- conventions [Visual Basic], Visual Basic coding
- Visual Basic code
- programming [Visual Basic], Visual Basic coding conventions
ms.assetid: dd9be76f-6944-4e78-ad72-0b6084a3fc13
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9980a815d83b21214f1be441d641c3da38c1b541
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="program-structure-and-code-conventions-visual-basic"></a><span data-ttu-id="5936b-102">程序结构和代码约定 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5936b-102">Program Structure and Code Conventions (Visual Basic)</span></span>
<span data-ttu-id="5936b-103">本部分介绍了典型的 Visual Basic 程序结构，提供一个简单的 Visual Basic 程序，"Hello，World"，并讨论了 Visual Basic 代码约定。</span><span class="sxs-lookup"><span data-stu-id="5936b-103">This section introduces the typical Visual Basic program structure, provides a simple Visual Basic program, "Hello, World", and discusses Visual Basic code conventions.</span></span> <span data-ttu-id="5936b-104">代码约定是针对不是程序的逻辑，而是其物理结构和外观的建议值。</span><span class="sxs-lookup"><span data-stu-id="5936b-104">Code conventions are suggestions that focus not on a program's logic but on its physical structure and appearance.</span></span> <span data-ttu-id="5936b-105">以下它们使得你的代码易于阅读、 理解和维护。</span><span class="sxs-lookup"><span data-stu-id="5936b-105">Following them makes your code easier to read, understand, and maintain.</span></span> <span data-ttu-id="5936b-106">代码约定，可以包括的其他：</span><span class="sxs-lookup"><span data-stu-id="5936b-106">Code conventions can include, among others:</span></span>  
  
-   <span data-ttu-id="5936b-107">标记和注释代码的标准化的格式。</span><span class="sxs-lookup"><span data-stu-id="5936b-107">Standardized formats for labeling and commenting code.</span></span>  
  
-   <span data-ttu-id="5936b-108">间距、 格式和缩进代码的准则。</span><span class="sxs-lookup"><span data-stu-id="5936b-108">Guidelines for spacing, formatting, and indenting code.</span></span>  
  
-   <span data-ttu-id="5936b-109">对象、 变量和过程的命名约定。</span><span class="sxs-lookup"><span data-stu-id="5936b-109">Naming conventions for objects, variables, and procedures.</span></span>  
  
 <span data-ttu-id="5936b-110">以下主题提供一系列编程原则对于 Visual Basic 的程序，以及好的用法的示例。</span><span class="sxs-lookup"><span data-stu-id="5936b-110">The following topics present a set of programming guidelines for Visual Basic programs, along with examples of good usage.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5936b-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="5936b-111">In This Section</span></span>  
 [<span data-ttu-id="5936b-112">Visual Basic 程序的结构</span><span class="sxs-lookup"><span data-stu-id="5936b-112">Structure of a Visual Basic Program</span></span>](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)  
 <span data-ttu-id="5936b-113">概述构成 Visual Basic 程序的元素。</span><span class="sxs-lookup"><span data-stu-id="5936b-113">Provides an overview of the elements that make up a Visual Basic program.</span></span>  
  
 [<span data-ttu-id="5936b-114">Visual Basic 中的 main 过程</span><span class="sxs-lookup"><span data-stu-id="5936b-114">Main Procedure in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/main-procedure.md)  
 <span data-ttu-id="5936b-115">讨论作为起始点和总体控制你的应用程序的过程。</span><span class="sxs-lookup"><span data-stu-id="5936b-115">Discusses the procedure that serves as the starting point and overall control for your application.</span></span>  
  
 [<span data-ttu-id="5936b-116">引用和 Imports 语句</span><span class="sxs-lookup"><span data-stu-id="5936b-116">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)  
 <span data-ttu-id="5936b-117">讨论如何引用其他程序集中的对象。</span><span class="sxs-lookup"><span data-stu-id="5936b-117">Discusses how to reference objects in other assemblies.</span></span>  
  
 [<span data-ttu-id="5936b-118">在 Visual Basic 中的命名空间</span><span class="sxs-lookup"><span data-stu-id="5936b-118">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 <span data-ttu-id="5936b-119">描述如何命名空间组织程序集内的对象。</span><span class="sxs-lookup"><span data-stu-id="5936b-119">Describes how namespaces organize objects within assemblies.</span></span>  
  
 [<span data-ttu-id="5936b-120">Visual Basic 命名约定</span><span class="sxs-lookup"><span data-stu-id="5936b-120">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 <span data-ttu-id="5936b-121">包括命名过程、 常量、 变量、 自变量和对象的一般准则。</span><span class="sxs-lookup"><span data-stu-id="5936b-121">Includes general guidelines for naming procedures, constants, variables, arguments, and objects.</span></span>  
  
 [<span data-ttu-id="5936b-122">Visual Basic 编码约定</span><span class="sxs-lookup"><span data-stu-id="5936b-122">Visual Basic Coding Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/coding-conventions.md)  
 <span data-ttu-id="5936b-123">查看在开发中本文档的示例中使用的准则。</span><span class="sxs-lookup"><span data-stu-id="5936b-123">Reviews the guidelines used in developing the samples in this documentation.</span></span>  
  
 [<span data-ttu-id="5936b-124">条件编译</span><span class="sxs-lookup"><span data-stu-id="5936b-124">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 <span data-ttu-id="5936b-125">描述如何将定向编译器忽略其他时有选择地编译的代码的特定块。</span><span class="sxs-lookup"><span data-stu-id="5936b-125">Describes how to compile particular blocks of code selectively while directing the compiler to ignore others.</span></span>  
  
 [<span data-ttu-id="5936b-126">如何：在代码中拆分和合并语句</span><span class="sxs-lookup"><span data-stu-id="5936b-126">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)  
 <span data-ttu-id="5936b-127">演示如何将划分为多行的长语句和合并在一个行上的短语句。</span><span class="sxs-lookup"><span data-stu-id="5936b-127">Shows how to divide long statements into multiple lines and combine short statements on one line.</span></span>  
  
 [<span data-ttu-id="5936b-128">如何：折叠和隐藏代码节</span><span class="sxs-lookup"><span data-stu-id="5936b-128">How to: Collapse and Hide Sections of Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)  
 <span data-ttu-id="5936b-129">演示如何折叠并隐藏 Visual Basic 中的代码段代码编辑器。</span><span class="sxs-lookup"><span data-stu-id="5936b-129">Shows how to collapse and hide sections of code in the Visual Basic code editor.</span></span>  
  
 [<span data-ttu-id="5936b-130">如何：标记语句</span><span class="sxs-lookup"><span data-stu-id="5936b-130">How to: Label Statements</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)  
 <span data-ttu-id="5936b-131">演示如何将标记的一行代码来确定它适用于使用与语句如`On Error Goto`。</span><span class="sxs-lookup"><span data-stu-id="5936b-131">Shows how to mark a line of code to identify it for use with statements such as `On Error Goto`.</span></span>  
  
 [<span data-ttu-id="5936b-132">代码中的特殊字符</span><span class="sxs-lookup"><span data-stu-id="5936b-132">Special Characters in Code</span></span>](../../../visual-basic/programming-guide/program-structure/special-characters-in-code.md)  
 <span data-ttu-id="5936b-133">演示如何以及在何处若要使用非数字和非字母字符。</span><span class="sxs-lookup"><span data-stu-id="5936b-133">Shows how and where to use non-numeric and non-alphabetic characters.</span></span>  
  
 [<span data-ttu-id="5936b-134">代码中的注释</span><span class="sxs-lookup"><span data-stu-id="5936b-134">Comments in Code</span></span>](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)  
 <span data-ttu-id="5936b-135">讨论如何将描述性注释添加到你的代码。</span><span class="sxs-lookup"><span data-stu-id="5936b-135">Discusses how to add descriptive comments to your code.</span></span>  
  
 [<span data-ttu-id="5936b-136">代码中用作元素名称的关键字</span><span class="sxs-lookup"><span data-stu-id="5936b-136">Keywords as Element Names in Code</span></span>](../../../visual-basic/programming-guide/program-structure/keywords-as-element-names-in-code.md)  
 <span data-ttu-id="5936b-137">介绍如何使用方括号 (`[]`) 来分隔也是 Visual Basic 关键字的变量名。</span><span class="sxs-lookup"><span data-stu-id="5936b-137">Describes how to use brackets (`[]`) to delimit variable names that are also Visual Basic keywords.</span></span>  
  
 [<span data-ttu-id="5936b-138">Me、My、MyBase 和 MyClass</span><span class="sxs-lookup"><span data-stu-id="5936b-138">Me, My, MyBase, and MyClass</span></span>](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 <span data-ttu-id="5936b-139">描述各种方式引用的 Visual Basic 程序元素。</span><span class="sxs-lookup"><span data-stu-id="5936b-139">Describes various ways to refer to elements of a Visual Basic program.</span></span>  
  
 [<span data-ttu-id="5936b-140">Visual Basic 限制</span><span class="sxs-lookup"><span data-stu-id="5936b-140">Visual Basic Limitations</span></span>](../../../visual-basic/programming-guide/program-structure/limitations.md)  
 <span data-ttu-id="5936b-141">讨论在 Visual Basic 中的已知编码限制删除。</span><span class="sxs-lookup"><span data-stu-id="5936b-141">Discusses the removal of known coding limits within Visual Basic.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="5936b-142">相关章节</span><span class="sxs-lookup"><span data-stu-id="5936b-142">Related Sections</span></span>  
 [<span data-ttu-id="5936b-143">版式和代码约定</span><span class="sxs-lookup"><span data-stu-id="5936b-143">Typographic and Code Conventions</span></span>](../../../visual-basic/language-reference/typographic-and-code-conventions.md)  
 <span data-ttu-id="5936b-144">适用于 Visual Basic，提供了标准编码约定。</span><span class="sxs-lookup"><span data-stu-id="5936b-144">Provides standard coding conventions for Visual Basic.</span></span>  
  
 [<span data-ttu-id="5936b-145">编写代码</span><span class="sxs-lookup"><span data-stu-id="5936b-145">Writing Code</span></span>](/visualstudio/ide/writing-code-in-the-code-and-text-editor)  
 <span data-ttu-id="5936b-146">描述使你更轻松地编写和管理你的代码的功能。</span><span class="sxs-lookup"><span data-stu-id="5936b-146">Describes features that make it easier for you to write and manage your code.</span></span>
