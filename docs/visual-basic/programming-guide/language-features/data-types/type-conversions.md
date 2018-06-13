---
title: Visual Basic 中的类型转换
ms.date: 07/20/2015
helpviewer_keywords:
- conversions [Visual Basic], type
- data types [Visual Basic], changing
- variables [Visual Basic], changing data type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- changing data types [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: 1cdacd21-ba31-4b62-b5be-395e41eeaa17
ms.openlocfilehash: 7f1a571cda4f68222c5c03c3a8fe31c29eafd8c0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647173"
---
# <a name="type-conversions-in-visual-basic"></a><span data-ttu-id="6f851-102">Visual Basic 中的类型转换</span><span class="sxs-lookup"><span data-stu-id="6f851-102">Type Conversions in Visual Basic</span></span>
<span data-ttu-id="6f851-103">值从一种数据类型更改为另一种类型的过程称为*转换*。</span><span class="sxs-lookup"><span data-stu-id="6f851-103">The process of changing a value from one data type to another type is called *conversion*.</span></span> <span data-ttu-id="6f851-104">转换都是*扩大*或*收缩*，取决于涉及的类型的数据容量。</span><span class="sxs-lookup"><span data-stu-id="6f851-104">Conversions are either *widening* or *narrowing*, depending on the data capacities of the types involved.</span></span> <span data-ttu-id="6f851-105">它们也是*隐式*或*显式*，具体的源代码中的语法取决于。</span><span class="sxs-lookup"><span data-stu-id="6f851-105">They are also *implicit* or *explicit*, depending on the syntax in the source code.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6f851-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="6f851-106">In This Section</span></span>  
 [<span data-ttu-id="6f851-107">扩大转换和收缩转换</span><span class="sxs-lookup"><span data-stu-id="6f851-107">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 <span data-ttu-id="6f851-108">说明来目标类型是否能容纳数据分类的转换。</span><span class="sxs-lookup"><span data-stu-id="6f851-108">Explains conversions classified by whether the destination type can hold the data.</span></span>  
  
 [<span data-ttu-id="6f851-109">隐式转换和显式转换</span><span class="sxs-lookup"><span data-stu-id="6f851-109">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 <span data-ttu-id="6f851-110">讨论来是否 Visual Basic 执行它们自动分类的转换。</span><span class="sxs-lookup"><span data-stu-id="6f851-110">Discusses conversions classified by whether Visual Basic performs them automatically.</span></span>  
  
 [<span data-ttu-id="6f851-111">字符串和其他类型之间的转换</span><span class="sxs-lookup"><span data-stu-id="6f851-111">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)  
 <span data-ttu-id="6f851-112">演示字符串和数字之间进行转换`Boolean`，或日期/时间值。</span><span class="sxs-lookup"><span data-stu-id="6f851-112">Illustrates converting between strings and numeric, `Boolean`, or date/time values.</span></span>  
  
 [<span data-ttu-id="6f851-113">如何： 将对象转换为在 Visual Basic 中的另一种类型</span><span class="sxs-lookup"><span data-stu-id="6f851-113">How to: Convert an Object to Another Type in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)  
 <span data-ttu-id="6f851-114">演示如何将转换`Object`变量为任何其他数据类型。</span><span class="sxs-lookup"><span data-stu-id="6f851-114">Shows how to convert an `Object` variable to any other data type.</span></span>  
  
 [<span data-ttu-id="6f851-115">数组转换</span><span class="sxs-lookup"><span data-stu-id="6f851-115">Array Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)  
 <span data-ttu-id="6f851-116">指导您完成不同的数据类型的数组之间进行转换的过程。</span><span class="sxs-lookup"><span data-stu-id="6f851-116">Steps you through the process of converting between arrays of different data types.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="6f851-117">相关章节</span><span class="sxs-lookup"><span data-stu-id="6f851-117">Related Sections</span></span>  
 [<span data-ttu-id="6f851-118">数据类型</span><span class="sxs-lookup"><span data-stu-id="6f851-118">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 <span data-ttu-id="6f851-119">介绍 Visual Basic 数据类型并说明如何使用它们。</span><span class="sxs-lookup"><span data-stu-id="6f851-119">Introduces the Visual Basic data types and describes how to use them.</span></span>  
  
 [<span data-ttu-id="6f851-120">数据类型</span><span class="sxs-lookup"><span data-stu-id="6f851-120">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 <span data-ttu-id="6f851-121">列出提供的 Visual Basic 的基本数据类型。</span><span class="sxs-lookup"><span data-stu-id="6f851-121">Lists the elementary data types supplied by Visual Basic.</span></span>  
  
 [<span data-ttu-id="6f851-122">数据类型疑难解答</span><span class="sxs-lookup"><span data-stu-id="6f851-122">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 <span data-ttu-id="6f851-123">讨论使用数据类型时，会产生一些常见问题的方法。</span><span class="sxs-lookup"><span data-stu-id="6f851-123">Discusses some common problems that can arise when working with data types.</span></span>
