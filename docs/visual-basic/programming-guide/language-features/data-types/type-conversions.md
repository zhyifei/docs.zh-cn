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
ms.openlocfilehash: 026b2a250abfac0782feb0946bc50a94f504f7ed
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2018
ms.locfileid: "42932281"
---
# <a name="type-conversions-in-visual-basic"></a><span data-ttu-id="e0b8e-102">Visual Basic 中的类型转换</span><span class="sxs-lookup"><span data-stu-id="e0b8e-102">Type Conversions in Visual Basic</span></span>
<span data-ttu-id="e0b8e-103">将值从一种数据类型更改为另一种类型的过程称为*转换*。</span><span class="sxs-lookup"><span data-stu-id="e0b8e-103">The process of changing a value from one data type to another type is called *conversion*.</span></span> <span data-ttu-id="e0b8e-104">转换为*扩大*或*收缩*，取决于所涉及的类型的数据容量。</span><span class="sxs-lookup"><span data-stu-id="e0b8e-104">Conversions are either *widening* or *narrowing*, depending on the data capacities of the types involved.</span></span> <span data-ttu-id="e0b8e-105">此外会缩短*隐式*或*显式*，取决于在源代码中的语法。</span><span class="sxs-lookup"><span data-stu-id="e0b8e-105">They are also *implicit* or *explicit*, depending on the syntax in the source code.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e0b8e-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="e0b8e-106">In This Section</span></span>  
 [<span data-ttu-id="e0b8e-107">扩大转换和收缩转换</span><span class="sxs-lookup"><span data-stu-id="e0b8e-107">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 <span data-ttu-id="e0b8e-108">介绍了由目标类型是否可以保存数据分类的转换。</span><span class="sxs-lookup"><span data-stu-id="e0b8e-108">Explains conversions classified by whether the destination type can hold the data.</span></span>  
  
 [<span data-ttu-id="e0b8e-109">隐式转换和显式转换</span><span class="sxs-lookup"><span data-stu-id="e0b8e-109">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 <span data-ttu-id="e0b8e-110">讨论来是否 Visual Basic 执行它们自动分类的转换。</span><span class="sxs-lookup"><span data-stu-id="e0b8e-110">Discusses conversions classified by whether Visual Basic performs them automatically.</span></span>  
  
 [<span data-ttu-id="e0b8e-111">字符串和其他类型之间的转换</span><span class="sxs-lookup"><span data-stu-id="e0b8e-111">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)  
 <span data-ttu-id="e0b8e-112">说明了将字符串转换为数字， `Boolean`，或日期/时间值。</span><span class="sxs-lookup"><span data-stu-id="e0b8e-112">Illustrates converting between strings and numeric, `Boolean`, or date/time values.</span></span>  
  
 [<span data-ttu-id="e0b8e-113">如何： 将对象转换为 Visual Basic 中的另一种类型</span><span class="sxs-lookup"><span data-stu-id="e0b8e-113">How to: Convert an Object to Another Type in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)  
 <span data-ttu-id="e0b8e-114">演示如何将转换`Object`变量为任何其他数据类型。</span><span class="sxs-lookup"><span data-stu-id="e0b8e-114">Shows how to convert an `Object` variable to any other data type.</span></span>  
  
 [<span data-ttu-id="e0b8e-115">数组转换</span><span class="sxs-lookup"><span data-stu-id="e0b8e-115">Array Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)  
 <span data-ttu-id="e0b8e-116">指导你完成不同的数据类型的数组之间转换的过程。</span><span class="sxs-lookup"><span data-stu-id="e0b8e-116">Steps you through the process of converting between arrays of different data types.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e0b8e-117">相关章节</span><span class="sxs-lookup"><span data-stu-id="e0b8e-117">Related Sections</span></span>  
 [<span data-ttu-id="e0b8e-118">数据类型</span><span class="sxs-lookup"><span data-stu-id="e0b8e-118">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 <span data-ttu-id="e0b8e-119">介绍 Visual Basic 数据类型，并介绍了如何使用它们。</span><span class="sxs-lookup"><span data-stu-id="e0b8e-119">Introduces the Visual Basic data types and describes how to use them.</span></span>  
  
 [<span data-ttu-id="e0b8e-120">数据类型</span><span class="sxs-lookup"><span data-stu-id="e0b8e-120">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)  
 <span data-ttu-id="e0b8e-121">列出了由 Visual Basic 提供的基本数据类型。</span><span class="sxs-lookup"><span data-stu-id="e0b8e-121">Lists the elementary data types supplied by Visual Basic.</span></span>  
  
 [<span data-ttu-id="e0b8e-122">数据类型疑难解答</span><span class="sxs-lookup"><span data-stu-id="e0b8e-122">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 <span data-ttu-id="e0b8e-123">讨论在处理数据类型时，可能会出现一些常见问题。</span><span class="sxs-lookup"><span data-stu-id="e0b8e-123">Discusses some common problems that can arise when working with data types.</span></span>
