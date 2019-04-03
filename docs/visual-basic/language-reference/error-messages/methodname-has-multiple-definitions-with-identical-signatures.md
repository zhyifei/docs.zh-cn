---
title: “<methodname>”具有多个带有相同签名的定义
ms.date: 07/20/2015
f1_keywords:
- vbc30269
- bc30269
helpviewer_keywords:
- BC30269
ms.assetid: 39489621-6617-4e5c-9b24-c2faf8273891
ms.openlocfilehash: fe8d1d8e11e25bcd79894ed82a57dd06748c3d68
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58831873"
---
# <a name="methodname-has-multiple-definitions-with-identical-signatures"></a><span data-ttu-id="24745-102">\<方法名称 > 具有多个带有相同签名的定义</span><span class="sxs-lookup"><span data-stu-id="24745-102">'\<methodname>' has multiple definitions with identical signatures</span></span>
<span data-ttu-id="24745-103">一个`Function`或`Sub`过程声明使用相同的过程名称和参数列表与以前的声明。</span><span class="sxs-lookup"><span data-stu-id="24745-103">A `Function` or `Sub` procedure declaration uses the identical procedure name and argument list as a previous declaration.</span></span> <span data-ttu-id="24745-104">一个可能的原因是尝试重载原始过程。</span><span class="sxs-lookup"><span data-stu-id="24745-104">One possible cause is an attempt to overload the original procedure.</span></span> <span data-ttu-id="24745-105">重载的过程必须具有不同的参数列表。</span><span class="sxs-lookup"><span data-stu-id="24745-105">Overloaded procedures must have different argument lists.</span></span>  
  
 <span data-ttu-id="24745-106">**错误 ID:** BC30269</span><span class="sxs-lookup"><span data-stu-id="24745-106">**Error ID:** BC30269</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="24745-107">更正此错误</span><span class="sxs-lookup"><span data-stu-id="24745-107">To correct this error</span></span>  
  
-   <span data-ttu-id="24745-108">过程名称或参数列表中，更改或删除重复的声明。</span><span class="sxs-lookup"><span data-stu-id="24745-108">Change the procedure name or the argument list, or remove the duplicate declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24745-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="24745-109">See also</span></span>

- [<span data-ttu-id="24745-110">对已声明元素的引用</span><span class="sxs-lookup"><span data-stu-id="24745-110">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="24745-111">重载过程注意事项</span><span class="sxs-lookup"><span data-stu-id="24745-111">Considerations in Overloading Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)
