---
title: "程序结构和代码约定 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
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
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b38ba9623a20dcd1be4bc96f4aff1eb646b0a053
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="program-structure-and-code-conventions-visual-basic"></a><span data-ttu-id="4dcb7-102">程序结构和代码约定 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4dcb7-102">Program Structure and Code Conventions (Visual Basic)</span></span>
<span data-ttu-id="4dcb7-103">本部分介绍典型[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]程序结构中，提供一个简单的[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]程序，"Hello，World"，并讨论了[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]代码约定。</span><span class="sxs-lookup"><span data-stu-id="4dcb7-103">This section introduces the typical [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] program structure, provides a simple [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] program, "Hello, World", and discusses [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] code conventions.</span></span> <span data-ttu-id="4dcb7-104">代码约定是针对不是程序的逻辑，而是其物理结构和外观的建议值。</span><span class="sxs-lookup"><span data-stu-id="4dcb7-104">Code conventions are suggestions that focus not on a program's logic but on its physical structure and appearance.</span></span> <span data-ttu-id="4dcb7-105">以下它们使得你的代码易于阅读、 理解和维护。</span><span class="sxs-lookup"><span data-stu-id="4dcb7-105">Following them makes your code easier to read, understand, and maintain.</span></span> <span data-ttu-id="4dcb7-106">代码约定，可以包括的其他：</span><span class="sxs-lookup"><span data-stu-id="4dcb7-106">Code conventions can include, among others:</span></span>  
  
-   <span data-ttu-id="4dcb7-107">标记和注释代码的标准化的格式。</span><span class="sxs-lookup"><span data-stu-id="4dcb7-107">Standardized formats for labeling and commenting code.</span></span>  
  
-   <span data-ttu-id="4dcb7-108">间距、 格式和缩进代码的准则。</span><span class="sxs-lookup"><span data-stu-id="4dcb7-108">Guidelines for spacing, formatting, and indenting code.</span></span>  
  
-   <span data-ttu-id="4dcb7-109">对象、 变量和过程的命名约定。</span><span class="sxs-lookup"><span data-stu-id="4dcb7-109">Naming conventions for objects, variables, and procedures.</span></span>  
  
 <span data-ttu-id="4dcb7-110">以下主题提供一套编程准则[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]程序，以及好的用法的示例。</span><span class="sxs-lookup"><span data-stu-id="4dcb7-110">The following topics present a set of programming guidelines for [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] programs, along with examples of good usage.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4dcb7-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="4dcb7-111">In This Section</span></span>  
 [<span data-ttu-id="4dcb7-112">Visual Basic 程序的结构</span><span class="sxs-lookup"><span data-stu-id="4dcb7-112">Structure of a Visual Basic Program</span></span>](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)  
 <span data-ttu-id="4dcb7-113">提供的构成的元素概述[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]程序。</span><span class="sxs-lookup"><span data-stu-id="4dcb7-113">Provides an overview of the elements that make up a [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] program.</span></span>  
  
 [<span data-ttu-id="4dcb7-114">Visual Basic 中的 main 过程</span><span class="sxs-lookup"><span data-stu-id="4dcb7-114">Main Procedure in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/main-procedure.md)  
 <span data-ttu-id="4dcb7-115">讨论作为起始点和总体控制你的应用程序的过程。</span><span class="sxs-lookup"><span data-stu-id="4dcb7-115">Discusses the procedure that serves as the starting point and overall control for your application.</span></span>  
  
 [<span data-ttu-id="4dcb7-116">引用和 Imports 语句</span><span class="sxs-lookup"><span data-stu-id="4dcb7-116">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)  
 <span data-ttu-id="4dcb7-117">讨论如何引用其他程序集中的对象。</span><span class="sxs-lookup"><span data-stu-id="4dcb7-117">Discusses how to reference objects in other assemblies.</span></span>  
  
 [<span data-ttu-id="4dcb7-118">在 Visual Basic 中的命名空间</span><span class="sxs-lookup"><span data-stu-id="4dcb7-118">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 <span data-ttu-id="4dcb7-119">描述如何命名空间组织程序集内的对象。</span><span class="sxs-lookup"><span data-stu-id="4dcb7-119">Describes how namespaces organize objects within assemblies.</span></span>  
  
 [<span data-ttu-id="4dcb7-120">Visual Basic 命名约定</span><span class="sxs-lookup"><span data-stu-id="4dcb7-120">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 <span data-ttu-id="4dcb7-121">包括命名过程、 常量、 变量、 自变量和对象的一般准则。</span><span class="sxs-lookup"><span data-stu-id="4dcb7-121">Includes general guidelines for naming procedures, constants, variables, arguments, and objects.</span></span>  
  
 [<span data-ttu-id="4dcb7-122">Visual Basic 编码约定</span><span class="sxs-lookup"><span data-stu-id="4dcb7-122">Visual Basic Coding Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/coding-conventions.md)  
 <span data-ttu-id="4dcb7-123">查看在开发中本文档的示例中使用的准则。</span><span class="sxs-lookup"><span data-stu-id="4dcb7-123">Reviews the guidelines used in developing the samples in this documentation.</span></span>  
  
 [<span data-ttu-id="4dcb7-124">条件编译</span><span class="sxs-lookup"><span data-stu-id="4dcb7-124">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 <span data-ttu-id="4dcb7-125">描述如何将定向编译器忽略其他时有选择地编译的代码的特定块。</span><span class="sxs-lookup"><span data-stu-id="4dcb7-125">Describes how to compile particular blocks of code selectively while directing the compiler to ignore others.</span></span>  
  
 [<span data-ttu-id="4dcb7-126">如何：在代码中拆分和合并语句</span><span class="sxs-lookup"><span data-stu-id="4dcb7-126">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)  
 <span data-ttu-id="4dcb7-127">演示如何将划分为多行的长语句和合并在一个行上的短语句。</span><span class="sxs-lookup"><span data-stu-id="4dcb7-127">Shows how to divide long statements into multiple lines and combine short statements on one line.</span></span>  
  
 [<span data-ttu-id="4dcb7-128">如何：折叠和隐藏代码节</span><span class="sxs-lookup"><span data-stu-id="4dcb7-128">How to: Collapse and Hide Sections of Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)  
 <span data-ttu-id="4dcb7-129">演示如何以折叠和隐藏中的代码段[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]代码编辑器。</span><span class="sxs-lookup"><span data-stu-id="4dcb7-129">Shows how to collapse and hide sections of code in the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] code editor.</span></span>  
  
 [<span data-ttu-id="4dcb7-130">如何：标记语句</span><span class="sxs-lookup"><span data-stu-id="4dcb7-130">How to: Label Statements</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)  
 <span data-ttu-id="4dcb7-131">演示如何将标记的一行代码来确定它适用于使用与语句如`On Error Goto`。</span><span class="sxs-lookup"><span data-stu-id="4dcb7-131">Shows how to mark a line of code to identify it for use with statements such as `On Error Goto`.</span></span>  
  
 [<span data-ttu-id="4dcb7-132">代码中的特殊字符</span><span class="sxs-lookup"><span data-stu-id="4dcb7-132">Special Characters in Code</span></span>](../../../visual-basic/programming-guide/program-structure/special-characters-in-code.md)  
 <span data-ttu-id="4dcb7-133">演示如何以及在何处若要使用非数字和非字母字符。</span><span class="sxs-lookup"><span data-stu-id="4dcb7-133">Shows how and where to use non-numeric and non-alphabetic characters.</span></span>  
  
 [<span data-ttu-id="4dcb7-134">代码中的注释</span><span class="sxs-lookup"><span data-stu-id="4dcb7-134">Comments in Code</span></span>](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)  
 <span data-ttu-id="4dcb7-135">讨论如何将描述性注释添加到你的代码。</span><span class="sxs-lookup"><span data-stu-id="4dcb7-135">Discusses how to add descriptive comments to your code.</span></span>  
  
 [<span data-ttu-id="4dcb7-136">代码中用作元素名称的关键字</span><span class="sxs-lookup"><span data-stu-id="4dcb7-136">Keywords as Element Names in Code</span></span>](../../../visual-basic/programming-guide/program-structure/keywords-as-element-names-in-code.md)  
 <span data-ttu-id="4dcb7-137">介绍如何使用方括号 (`[]`) 来分隔变量名也存在[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]关键字。</span><span class="sxs-lookup"><span data-stu-id="4dcb7-137">Describes how to use brackets (`[]`) to delimit variable names that are also [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] keywords.</span></span>  
  
 [<span data-ttu-id="4dcb7-138">Me、My、MyBase 和 MyClass</span><span class="sxs-lookup"><span data-stu-id="4dcb7-138">Me, My, MyBase, and MyClass</span></span>](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 <span data-ttu-id="4dcb7-139">描述各种方式引用的元素[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]程序。</span><span class="sxs-lookup"><span data-stu-id="4dcb7-139">Describes various ways to refer to elements of a [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] program.</span></span>  
  
 [<span data-ttu-id="4dcb7-140">Visual Basic 限制</span><span class="sxs-lookup"><span data-stu-id="4dcb7-140">Visual Basic Limitations</span></span>](../../../visual-basic/programming-guide/program-structure/limitations.md)  
 <span data-ttu-id="4dcb7-141">讨论中的已知编码限制删除[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4dcb7-141">Discusses the removal of known coding limits within [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="4dcb7-142">相关章节</span><span class="sxs-lookup"><span data-stu-id="4dcb7-142">Related Sections</span></span>  
 [<span data-ttu-id="4dcb7-143">版式和代码约定</span><span class="sxs-lookup"><span data-stu-id="4dcb7-143">Typographic and Code Conventions</span></span>](../../../visual-basic/language-reference/typographic-and-code-conventions.md)  
 <span data-ttu-id="4dcb7-144">提供标准编码约定[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4dcb7-144">Provides standard coding conventions for [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
 [<span data-ttu-id="4dcb7-145">编写代码</span><span class="sxs-lookup"><span data-stu-id="4dcb7-145">Writing Code</span></span>](/visualstudio/ide/writing-code-in-the-code-and-text-editor)  
 <span data-ttu-id="4dcb7-146">描述使你更轻松地编写和管理你的代码的功能。</span><span class="sxs-lookup"><span data-stu-id="4dcb7-146">Describes features that make it easier for you to write and manage your code.</span></span>
