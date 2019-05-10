---
title: 程序结构和代码约定 (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: 9dbe8fe977b2aa11573ab7a1ac1d79be0b5204af
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64624335"
---
# <a name="program-structure-and-code-conventions-visual-basic"></a><span data-ttu-id="c890a-102">程序结构和代码约定 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c890a-102">Program Structure and Code Conventions (Visual Basic)</span></span>
<span data-ttu-id="c890a-103">本节介绍典型的 Visual Basic 程序结构，提供了一个简单的 Visual Basic 程序，"Hello，World"并且讨论了 Visual Basic 代码约定。</span><span class="sxs-lookup"><span data-stu-id="c890a-103">This section introduces the typical Visual Basic program structure, provides a simple Visual Basic program, "Hello, World", and discusses Visual Basic code conventions.</span></span> <span data-ttu-id="c890a-104">代码约定是针对不是程序的逻辑，而是其物理结构和外观的建议。</span><span class="sxs-lookup"><span data-stu-id="c890a-104">Code conventions are suggestions that focus not on a program's logic but on its physical structure and appearance.</span></span> <span data-ttu-id="c890a-105">遵循它们使您的代码易于阅读、 理解和维护。</span><span class="sxs-lookup"><span data-stu-id="c890a-105">Following them makes your code easier to read, understand, and maintain.</span></span> <span data-ttu-id="c890a-106">代码约定可以包含其他项中：</span><span class="sxs-lookup"><span data-stu-id="c890a-106">Code conventions can include, among others:</span></span>  
  
- <span data-ttu-id="c890a-107">标记和注释代码的标准化的格式。</span><span class="sxs-lookup"><span data-stu-id="c890a-107">Standardized formats for labeling and commenting code.</span></span>  
  
- <span data-ttu-id="c890a-108">间距、 格式和缩进代码的指南。</span><span class="sxs-lookup"><span data-stu-id="c890a-108">Guidelines for spacing, formatting, and indenting code.</span></span>  
  
- <span data-ttu-id="c890a-109">对象、 变量和过程的命名约定。</span><span class="sxs-lookup"><span data-stu-id="c890a-109">Naming conventions for objects, variables, and procedures.</span></span>  
  
 <span data-ttu-id="c890a-110">下列主题显示了一系列编程准则以及的好的用法示例的 Visual Basic 程序。</span><span class="sxs-lookup"><span data-stu-id="c890a-110">The following topics present a set of programming guidelines for Visual Basic programs, along with examples of good usage.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c890a-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="c890a-111">In This Section</span></span>  
 [<span data-ttu-id="c890a-112">Visual Basic 程序的结构</span><span class="sxs-lookup"><span data-stu-id="c890a-112">Structure of a Visual Basic Program</span></span>](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)  
 <span data-ttu-id="c890a-113">概述组成 Visual Basic 程序的元素。</span><span class="sxs-lookup"><span data-stu-id="c890a-113">Provides an overview of the elements that make up a Visual Basic program.</span></span>  
  
 [<span data-ttu-id="c890a-114">在 Visual Basic 中的主要过程</span><span class="sxs-lookup"><span data-stu-id="c890a-114">Main Procedure in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/main-procedure.md)  
 <span data-ttu-id="c890a-115">讨论作为起始点和应用程序的总体控制的过程。</span><span class="sxs-lookup"><span data-stu-id="c890a-115">Discusses the procedure that serves as the starting point and overall control for your application.</span></span>  
  
 [<span data-ttu-id="c890a-116">引用和 Imports 语句</span><span class="sxs-lookup"><span data-stu-id="c890a-116">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)  
 <span data-ttu-id="c890a-117">讨论如何引用其他程序集中的对象。</span><span class="sxs-lookup"><span data-stu-id="c890a-117">Discusses how to reference objects in other assemblies.</span></span>  
  
 [<span data-ttu-id="c890a-118">在 Visual Basic 中的命名空间</span><span class="sxs-lookup"><span data-stu-id="c890a-118">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 <span data-ttu-id="c890a-119">介绍如何命名空间组织程序集内的对象。</span><span class="sxs-lookup"><span data-stu-id="c890a-119">Describes how namespaces organize objects within assemblies.</span></span>  
  
 [<span data-ttu-id="c890a-120">Visual Basic 命名约定</span><span class="sxs-lookup"><span data-stu-id="c890a-120">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 <span data-ttu-id="c890a-121">包括命名过程、 常量、 变量、 参数以及对象的一般指导原则。</span><span class="sxs-lookup"><span data-stu-id="c890a-121">Includes general guidelines for naming procedures, constants, variables, arguments, and objects.</span></span>  
  
 [<span data-ttu-id="c890a-122">Visual Basic 编码约定</span><span class="sxs-lookup"><span data-stu-id="c890a-122">Visual Basic Coding Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/coding-conventions.md)  
 <span data-ttu-id="c890a-123">回顾在开发此文档中的示例使用的准则。</span><span class="sxs-lookup"><span data-stu-id="c890a-123">Reviews the guidelines used in developing the samples in this documentation.</span></span>  
  
 [<span data-ttu-id="c890a-124">条件编译</span><span class="sxs-lookup"><span data-stu-id="c890a-124">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 <span data-ttu-id="c890a-125">描述如何同时控制编译器忽略其他有选择性地编译特定代码块。</span><span class="sxs-lookup"><span data-stu-id="c890a-125">Describes how to compile particular blocks of code selectively while directing the compiler to ignore others.</span></span>  
  
 [<span data-ttu-id="c890a-126">如何：在代码中拆分和合并语句</span><span class="sxs-lookup"><span data-stu-id="c890a-126">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)  
 <span data-ttu-id="c890a-127">演示如何将长语句分成多行并将在同一行的短语句合并。</span><span class="sxs-lookup"><span data-stu-id="c890a-127">Shows how to divide long statements into multiple lines and combine short statements on one line.</span></span>  
  
 [<span data-ttu-id="c890a-128">如何：折叠和隐藏代码节</span><span class="sxs-lookup"><span data-stu-id="c890a-128">How to: Collapse and Hide Sections of Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)  
 <span data-ttu-id="c890a-129">演示如何折叠和隐藏代码在 Visual Basic 中的部分代码编辑器。</span><span class="sxs-lookup"><span data-stu-id="c890a-129">Shows how to collapse and hide sections of code in the Visual Basic code editor.</span></span>  
  
 [<span data-ttu-id="c890a-130">如何：标记语句</span><span class="sxs-lookup"><span data-stu-id="c890a-130">How to: Label Statements</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)  
 <span data-ttu-id="c890a-131">演示如何将标记的一行代码以将其标识用于与语句如`On Error Goto`。</span><span class="sxs-lookup"><span data-stu-id="c890a-131">Shows how to mark a line of code to identify it for use with statements such as `On Error Goto`.</span></span>  
  
 [<span data-ttu-id="c890a-132">代码中的特殊字符</span><span class="sxs-lookup"><span data-stu-id="c890a-132">Special Characters in Code</span></span>](../../../visual-basic/programming-guide/program-structure/special-characters-in-code.md)  
 <span data-ttu-id="c890a-133">演示如何以及在何处使用非数字和非字母字符。</span><span class="sxs-lookup"><span data-stu-id="c890a-133">Shows how and where to use non-numeric and non-alphabetic characters.</span></span>  
  
 [<span data-ttu-id="c890a-134">代码中的注释</span><span class="sxs-lookup"><span data-stu-id="c890a-134">Comments in Code</span></span>](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)  
 <span data-ttu-id="c890a-135">讨论如何将描述性注释添加到你的代码。</span><span class="sxs-lookup"><span data-stu-id="c890a-135">Discusses how to add descriptive comments to your code.</span></span>  
  
 [<span data-ttu-id="c890a-136">代码中用作元素名称的关键字</span><span class="sxs-lookup"><span data-stu-id="c890a-136">Keywords as Element Names in Code</span></span>](../../../visual-basic/programming-guide/program-structure/keywords-as-element-names-in-code.md)  
 <span data-ttu-id="c890a-137">介绍如何使用方括号 (`[]`) 来分隔也是 Visual Basic 关键字的变量名称。</span><span class="sxs-lookup"><span data-stu-id="c890a-137">Describes how to use brackets (`[]`) to delimit variable names that are also Visual Basic keywords.</span></span>  
  
 [<span data-ttu-id="c890a-138">Me、My、MyBase 和 MyClass</span><span class="sxs-lookup"><span data-stu-id="c890a-138">Me, My, MyBase, and MyClass</span></span>](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 <span data-ttu-id="c890a-139">介绍了各种方法来指代 Visual Basic 程序中的元素。</span><span class="sxs-lookup"><span data-stu-id="c890a-139">Describes various ways to refer to elements of a Visual Basic program.</span></span>  
  
 [<span data-ttu-id="c890a-140">Visual Basic 限制</span><span class="sxs-lookup"><span data-stu-id="c890a-140">Visual Basic Limitations</span></span>](../../../visual-basic/programming-guide/program-structure/limitations.md)  
 <span data-ttu-id="c890a-141">讨论 Visual Basic 中已知的编码限制删除。</span><span class="sxs-lookup"><span data-stu-id="c890a-141">Discusses the removal of known coding limits within Visual Basic.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c890a-142">相关章节</span><span class="sxs-lookup"><span data-stu-id="c890a-142">Related Sections</span></span>  
 [<span data-ttu-id="c890a-143">版式和代码约定</span><span class="sxs-lookup"><span data-stu-id="c890a-143">Typographic and Code Conventions</span></span>](../../../visual-basic/language-reference/typographic-and-code-conventions.md)  
 <span data-ttu-id="c890a-144">对于 Visual Basic 提供标准编码约定。</span><span class="sxs-lookup"><span data-stu-id="c890a-144">Provides standard coding conventions for Visual Basic.</span></span>  
  
 [<span data-ttu-id="c890a-145">编写代码</span><span class="sxs-lookup"><span data-stu-id="c890a-145">Writing Code</span></span>](/visualstudio/ide/writing-code-in-the-code-and-text-editor)  
 <span data-ttu-id="c890a-146">介绍了功能，使你更轻松地编写和管理你的代码。</span><span class="sxs-lookup"><span data-stu-id="c890a-146">Describes features that make it easier for you to write and manage your code.</span></span>
