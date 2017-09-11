---
title: "结构 (Visual Basic) |Microsoft 文档"
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
- structures
- user-defined data types, structures
- user-defined types, about user-defined types
- data types [Visual Basic], user-defined
- user-defined data types, about user-defined data types
- types [Visual Basic], user-defined
ms.assetid: 55e86462-5e99-4d33-8018-6d097ca491b2
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: d1ba8671af9ff6d50499149fce6d55b3db78ffe0
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="structures-visual-basic"></a><span data-ttu-id="d0c16-102">结构 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d0c16-102">Structures (Visual Basic)</span></span>
<span data-ttu-id="d0c16-103">一个*结构*是用户定义类型 (UDT 的早期版本支持) 的归纳[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d0c16-103">A *structure* is a generalization of the user-defined type (UDT) supported by previous versions of [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span> <span data-ttu-id="d0c16-104">除字段外，结构可以公开属性、 方法和事件。</span><span class="sxs-lookup"><span data-stu-id="d0c16-104">In addition to fields, structures can expose properties, methods, and events.</span></span> <span data-ttu-id="d0c16-105">一种结构可以实现一个或多个接口，而您可以声明为每个字段的单独的访问级别。</span><span class="sxs-lookup"><span data-stu-id="d0c16-105">A structure can implement one or more interfaces, and you can declare individual access levels for each field.</span></span>  
  
 <span data-ttu-id="d0c16-106">您可以组合创建一个结构的不同类型的数据项。</span><span class="sxs-lookup"><span data-stu-id="d0c16-106">You can combine data items of different types to create a structure.</span></span> <span data-ttu-id="d0c16-107">一种结构将相关联，这是一个或多个*元素*和与结构本身。</span><span class="sxs-lookup"><span data-stu-id="d0c16-107">A structure associates one or more *elements* with each other and with the structure itself.</span></span> <span data-ttu-id="d0c16-108">当您声明一个结构时，它将成为*复合数据类型*，而您可以声明该类型的变量。</span><span class="sxs-lookup"><span data-stu-id="d0c16-108">When you declare a structure, it becomes a *composite data type*, and you can declare variables of that type.</span></span>  
  
 <span data-ttu-id="d0c16-109">当您希望一个一个变量来保存多个相关的信息片段时，结构十分有用。</span><span class="sxs-lookup"><span data-stu-id="d0c16-109">Structures are useful when you want a single variable to hold several related pieces of information.</span></span> <span data-ttu-id="d0c16-110">例如，您可能想要将某一员工名称、 电话分机和薪金放在一起。</span><span class="sxs-lookup"><span data-stu-id="d0c16-110">For example, you might want to keep an employee's name, telephone extension, and salary together.</span></span> <span data-ttu-id="d0c16-111">可以使用几个变量获得此信息，或者可以定义一种结构并将其用于单个雇员变量。</span><span class="sxs-lookup"><span data-stu-id="d0c16-111">You could use several variables for this information, or you could define a structure and use it for a single employee variable.</span></span> <span data-ttu-id="d0c16-112">当有许多员工，因此多个实例的变量时，该结构的优点越明显。</span><span class="sxs-lookup"><span data-stu-id="d0c16-112">The advantage of the structure becomes apparent when you have many employees and therefore many instances of the variable.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d0c16-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="d0c16-113">In This Section</span></span>  
 [<span data-ttu-id="d0c16-114">如何：声明结构</span><span class="sxs-lookup"><span data-stu-id="d0c16-114">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 <span data-ttu-id="d0c16-115">演示如何声明一个结构和它的元素。</span><span class="sxs-lookup"><span data-stu-id="d0c16-115">Shows how to declare a structure and its elements.</span></span>  
  
 [<span data-ttu-id="d0c16-116">结构变量</span><span class="sxs-lookup"><span data-stu-id="d0c16-116">Structure Variables</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structure-variables.md)  
 <span data-ttu-id="d0c16-117">涉及将结构指派给一个变量并访问其元素。</span><span class="sxs-lookup"><span data-stu-id="d0c16-117">Covers assigning a structure to a variable and accessing its elements.</span></span>  
  
 [<span data-ttu-id="d0c16-118">结构和其他编程元素</span><span class="sxs-lookup"><span data-stu-id="d0c16-118">Structures and Other Programming Elements</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)  
 <span data-ttu-id="d0c16-119">总结了结构如何与数组、 对象、 过程和彼此进行交互。</span><span class="sxs-lookup"><span data-stu-id="d0c16-119">Summarizes how structures interact with arrays, objects, procedures, and each other.</span></span>  
  
 [<span data-ttu-id="d0c16-120">结构和类</span><span class="sxs-lookup"><span data-stu-id="d0c16-120">Structures and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)  
 <span data-ttu-id="d0c16-121">介绍的相似之处和结构和类之间的差异。</span><span class="sxs-lookup"><span data-stu-id="d0c16-121">Describes the similarities and differences between structures and classes.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d0c16-122">相关章节</span><span class="sxs-lookup"><span data-stu-id="d0c16-122">Related Sections</span></span>  
 [<span data-ttu-id="d0c16-123">数据类型</span><span class="sxs-lookup"><span data-stu-id="d0c16-123">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 <span data-ttu-id="d0c16-124">引入了[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]数据类型并说明如何使用它们。</span><span class="sxs-lookup"><span data-stu-id="d0c16-124">Introduces the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] data types and describes how to use them.</span></span>  
  
 [<span data-ttu-id="d0c16-125">数据类型</span><span class="sxs-lookup"><span data-stu-id="d0c16-125">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 <span data-ttu-id="d0c16-126">列出了由提供的基本数据类型[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d0c16-126">Lists the elementary data types supplied by [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>
