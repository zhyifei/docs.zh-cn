---
title: "结构 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- structures [Visual Basic]
- user-defined data types [Visual Basic], structures
- user-defined types [Visual Basic], about user-defined types
- data types [Visual Basic], user-defined
- user-defined data types [Visual Basic], about user-defined data types
- types [Visual Basic], user-defined
ms.assetid: 55e86462-5e99-4d33-8018-6d097ca491b2
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: de99d67ee31d8fb8e92e0a351142b30f622bf5f0
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="structures-visual-basic"></a><span data-ttu-id="f8c4f-102">结构 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f8c4f-102">Structures (Visual Basic)</span></span>
<span data-ttu-id="f8c4f-103">A*结构*是用户定义支持的类型 (UDT) 的早期版本的泛化[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f8c4f-103">A *structure* is a generalization of the user-defined type (UDT) supported by previous versions of [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span> <span data-ttu-id="f8c4f-104">字段中，除了结构可以公开属性、 方法和事件。</span><span class="sxs-lookup"><span data-stu-id="f8c4f-104">In addition to fields, structures can expose properties, methods, and events.</span></span> <span data-ttu-id="f8c4f-105">结构可以实现一个或多个接口，而您可以声明的每个字段的单独的访问级别。</span><span class="sxs-lookup"><span data-stu-id="f8c4f-105">A structure can implement one or more interfaces, and you can declare individual access levels for each field.</span></span>  
  
 <span data-ttu-id="f8c4f-106">你可以组合来创建结构的不同类型的数据项。</span><span class="sxs-lookup"><span data-stu-id="f8c4f-106">You can combine data items of different types to create a structure.</span></span> <span data-ttu-id="f8c4f-107">一个结构将相关联，这是一个或多个*元素*和与结构本身。</span><span class="sxs-lookup"><span data-stu-id="f8c4f-107">A structure associates one or more *elements* with each other and with the structure itself.</span></span> <span data-ttu-id="f8c4f-108">当你声明一个结构时，它将成为*复合数据类型*，你可以声明该类型的变量。</span><span class="sxs-lookup"><span data-stu-id="f8c4f-108">When you declare a structure, it becomes a *composite data type*, and you can declare variables of that type.</span></span>  
  
 <span data-ttu-id="f8c4f-109">当你想单个变量来保存多个相关的信息片段时，结构很有用。</span><span class="sxs-lookup"><span data-stu-id="f8c4f-109">Structures are useful when you want a single variable to hold several related pieces of information.</span></span> <span data-ttu-id="f8c4f-110">例如，你可能想要将员工的名称、 电话分机和薪金放在一起。</span><span class="sxs-lookup"><span data-stu-id="f8c4f-110">For example, you might want to keep an employee's name, telephone extension, and salary together.</span></span> <span data-ttu-id="f8c4f-111">你可以使用多个变量进行此信息，或无法定义结构并将其用于单个雇员变量。</span><span class="sxs-lookup"><span data-stu-id="f8c4f-111">You could use several variables for this information, or you could define a structure and use it for a single employee variable.</span></span> <span data-ttu-id="f8c4f-112">当有许多员工，因此的变量的多个实例时，会了然-结构的优点。</span><span class="sxs-lookup"><span data-stu-id="f8c4f-112">The advantage of the structure becomes apparent when you have many employees and therefore many instances of the variable.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f8c4f-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="f8c4f-113">In This Section</span></span>  
 [<span data-ttu-id="f8c4f-114">如何：声明结构</span><span class="sxs-lookup"><span data-stu-id="f8c4f-114">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 <span data-ttu-id="f8c4f-115">演示如何声明一个结构和它的元素。</span><span class="sxs-lookup"><span data-stu-id="f8c4f-115">Shows how to declare a structure and its elements.</span></span>  
  
 [<span data-ttu-id="f8c4f-116">结构变量</span><span class="sxs-lookup"><span data-stu-id="f8c4f-116">Structure Variables</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structure-variables.md)  
 <span data-ttu-id="f8c4f-117">涉及将一个结构分配给变量并访问其元素。</span><span class="sxs-lookup"><span data-stu-id="f8c4f-117">Covers assigning a structure to a variable and accessing its elements.</span></span>  
  
 [<span data-ttu-id="f8c4f-118">结构和其他编程元素</span><span class="sxs-lookup"><span data-stu-id="f8c4f-118">Structures and Other Programming Elements</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)  
 <span data-ttu-id="f8c4f-119">总结了结构如何与数组、 对象、 过程和相互交互。</span><span class="sxs-lookup"><span data-stu-id="f8c4f-119">Summarizes how structures interact with arrays, objects, procedures, and each other.</span></span>  
  
 [<span data-ttu-id="f8c4f-120">结构和类</span><span class="sxs-lookup"><span data-stu-id="f8c4f-120">Structures and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)  
 <span data-ttu-id="f8c4f-121">描述的相似之处和结构和类之间的差异。</span><span class="sxs-lookup"><span data-stu-id="f8c4f-121">Describes the similarities and differences between structures and classes.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f8c4f-122">相关章节</span><span class="sxs-lookup"><span data-stu-id="f8c4f-122">Related Sections</span></span>  
 [<span data-ttu-id="f8c4f-123">数据类型</span><span class="sxs-lookup"><span data-stu-id="f8c4f-123">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 <span data-ttu-id="f8c4f-124">引入了[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]数据类型，并说明如何使用它们。</span><span class="sxs-lookup"><span data-stu-id="f8c4f-124">Introduces the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] data types and describes how to use them.</span></span>  
  
 [<span data-ttu-id="f8c4f-125">数据类型</span><span class="sxs-lookup"><span data-stu-id="f8c4f-125">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 <span data-ttu-id="f8c4f-126">列出由提供的基本数据类型[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f8c4f-126">Lists the elementary data types supplied by [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>
