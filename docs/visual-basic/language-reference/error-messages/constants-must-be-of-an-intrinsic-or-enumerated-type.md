---
title: 常量必须是内部类型或者枚举类型，不能是类、结构、类型参数或数组类型
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30424
- bc30424
helpviewer_keywords:
- BC30424
ms.assetid: 2d402c2f-27ad-428b-b699-d45cd62f7196
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 702472751810c2d2bd08ece944ef0ffafc2049b5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="constants-must-be-of-an-intrinsic-or-enumerated-type-not-a-class-structure-type-parameter-or-array-type"></a><span data-ttu-id="ef6e5-102">常量必须是内部类型或者枚举类型，不能是类、结构、类型参数或数组类型</span><span class="sxs-lookup"><span data-stu-id="ef6e5-102">Constants must be of an intrinsic or enumerated type, not a class, structure, type parameter, or array type</span></span>
<span data-ttu-id="ef6e5-103">已尝试声明为类、 结构或数组类型，或由包含泛型类型定义的类型参数的常量。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-103">You have attempted to declare a constant as a class, structure, or array type, or as a type parameter defined by a containing generic type.</span></span>  
  
 <span data-ttu-id="ef6e5-104">常量必须是内部类型 (`Boolean`， `Byte`， `Date`， `Decimal`， `Double`， `Integer`， `Long`， `Object`， `SByte`， `Short`， `Single`， `String`， `UInteger`， `ULong`，或`UShort`)，或`Enum`类型基于整型类型之一。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-104">Constants must be of an intrinsic type (`Boolean`, `Byte`, `Date`, `Decimal`, `Double`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong`, or `UShort`), or an `Enum` type based on one of the integral types.</span></span>  
  
 <span data-ttu-id="ef6e5-105">**错误 ID:** BC30424</span><span class="sxs-lookup"><span data-stu-id="ef6e5-105">**Error ID:** BC30424</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ef6e5-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="ef6e5-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="ef6e5-107">声明常量用作内部函数或`Enum`类型。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-107">Declare the constant as an intrinsic or `Enum` type.</span></span>  
  
2.  <span data-ttu-id="ef6e5-108">一个常数，也可以是一个特殊值如`True`， `False`，或`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-108">A constant can also be a special value such as `True`, `False`, or `Nothing`.</span></span> <span data-ttu-id="ef6e5-109">编译器认为这些预定义的值为相应的内部类型。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-109">The compiler considers these predefined values to be of the appropriate intrinsic type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef6e5-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ef6e5-110">See Also</span></span>  
 [<span data-ttu-id="ef6e5-111">常量和枚举</span><span class="sxs-lookup"><span data-stu-id="ef6e5-111">Constants and Enumerations</span></span>](../../../visual-basic/language-reference/constants-and-enumerations.md)  
 [<span data-ttu-id="ef6e5-112">数据类型</span><span class="sxs-lookup"><span data-stu-id="ef6e5-112">Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [<span data-ttu-id="ef6e5-113">数据类型</span><span class="sxs-lookup"><span data-stu-id="ef6e5-113">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)
