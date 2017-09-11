---
title: "在 Visual Basic 中的类型转换 |Microsoft 文档"
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
- conversions, type
- data types [Visual Basic], changing
- variables [Visual Basic], changing data type
- type conversion
- conversions, data type
- changing data types
- data type conversion
ms.assetid: 1cdacd21-ba31-4b62-b5be-395e41eeaa17
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
ms.openlocfilehash: 61606572dd1f10dc5df4ed4baec02f230a23c8d6
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="type-conversions-in-visual-basic"></a><span data-ttu-id="e54f3-102">Visual Basic 中的类型转换</span><span class="sxs-lookup"><span data-stu-id="e54f3-102">Type Conversions in Visual Basic</span></span>
<span data-ttu-id="e54f3-103">将值从一种数据类型更改为另一种类型的过程被称为*转换*。</span><span class="sxs-lookup"><span data-stu-id="e54f3-103">The process of changing a value from one data type to another type is called *conversion*.</span></span> <span data-ttu-id="e54f3-104">转换都是*扩大*或*收缩*，取决于所涉及的类型的数据容量。</span><span class="sxs-lookup"><span data-stu-id="e54f3-104">Conversions are either *widening* or *narrowing*, depending on the data capacities of the types involved.</span></span> <span data-ttu-id="e54f3-105">它们也是*隐式*或*显式*，取决于在源代码中的语法。</span><span class="sxs-lookup"><span data-stu-id="e54f3-105">They are also *implicit* or *explicit*, depending on the syntax in the source code.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e54f3-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="e54f3-106">In This Section</span></span>  
 [<span data-ttu-id="e54f3-107">扩大转换和收缩转换</span><span class="sxs-lookup"><span data-stu-id="e54f3-107">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 <span data-ttu-id="e54f3-108">介绍了由目标类型是否可以容纳的数据进行分类的转换。</span><span class="sxs-lookup"><span data-stu-id="e54f3-108">Explains conversions classified by whether the destination type can hold the data.</span></span>  
  
 [<span data-ttu-id="e54f3-109">隐式转换和显式转换</span><span class="sxs-lookup"><span data-stu-id="e54f3-109">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 <span data-ttu-id="e54f3-110">讨论由是否进行分类的转换[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]将它们自动执行。</span><span class="sxs-lookup"><span data-stu-id="e54f3-110">Discusses conversions classified by whether [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] performs them automatically.</span></span>  
  
 [<span data-ttu-id="e54f3-111">字符串和其他类型之间的转换</span><span class="sxs-lookup"><span data-stu-id="e54f3-111">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)  
 <span data-ttu-id="e54f3-112">说明了字符串和数字之间进行转换`Boolean`，或日期/时间值。</span><span class="sxs-lookup"><span data-stu-id="e54f3-112">Illustrates converting between strings and numeric, `Boolean`, or date/time values.</span></span>  
  
 [<span data-ttu-id="e54f3-113">如何︰ 将对象转换为另一种类型在 Visual Basic 中</span><span class="sxs-lookup"><span data-stu-id="e54f3-113">How to: Convert an Object to Another Type in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)  
 <span data-ttu-id="e54f3-114">演示如何将转换`Object`变量与任何其他数据类型。</span><span class="sxs-lookup"><span data-stu-id="e54f3-114">Shows how to convert an `Object` variable to any other data type.</span></span>  
  
 [<span data-ttu-id="e54f3-115">数组转换</span><span class="sxs-lookup"><span data-stu-id="e54f3-115">Array Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)  
 <span data-ttu-id="e54f3-116">逐步说明不同的数据类型的数组之间进行转换的过程。</span><span class="sxs-lookup"><span data-stu-id="e54f3-116">Steps you through the process of converting between arrays of different data types.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e54f3-117">相关章节</span><span class="sxs-lookup"><span data-stu-id="e54f3-117">Related Sections</span></span>  
 [<span data-ttu-id="e54f3-118">数据类型</span><span class="sxs-lookup"><span data-stu-id="e54f3-118">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 <span data-ttu-id="e54f3-119">引入了[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]数据类型并说明如何使用它们。</span><span class="sxs-lookup"><span data-stu-id="e54f3-119">Introduces the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] data types and describes how to use them.</span></span>  
  
 [<span data-ttu-id="e54f3-120">数据类型</span><span class="sxs-lookup"><span data-stu-id="e54f3-120">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 <span data-ttu-id="e54f3-121">列出了由提供的基本数据类型[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e54f3-121">Lists the elementary data types supplied by [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
 [<span data-ttu-id="e54f3-122">数据类型疑难解答</span><span class="sxs-lookup"><span data-stu-id="e54f3-122">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 <span data-ttu-id="e54f3-123">讨论在使用数据类型时可能会出现一些常见问题。</span><span class="sxs-lookup"><span data-stu-id="e54f3-123">Discusses some common problems that can arise when working with data types.</span></span>
