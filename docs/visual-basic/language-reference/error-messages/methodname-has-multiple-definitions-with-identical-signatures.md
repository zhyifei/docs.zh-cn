---
title: “<methodname>”具有多个带有相同签名的定义
ms.date: 07/20/2015
f1_keywords:
- vbc30269
- bc30269
helpviewer_keywords:
- BC30269
ms.assetid: 39489621-6617-4e5c-9b24-c2faf8273891
ms.openlocfilehash: b884220053bbcec633c964a41892bc8df42f41c7
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64602444"
---
# <a name="methodname-has-multiple-definitions-with-identical-signatures"></a><span data-ttu-id="c1600-102">\<方法名称 > 具有多个带有相同签名的定义</span><span class="sxs-lookup"><span data-stu-id="c1600-102">'\<methodname>' has multiple definitions with identical signatures</span></span>
<span data-ttu-id="c1600-103">一个`Function`或`Sub`过程声明使用相同的过程名称和参数列表与以前的声明。</span><span class="sxs-lookup"><span data-stu-id="c1600-103">A `Function` or `Sub` procedure declaration uses the identical procedure name and argument list as a previous declaration.</span></span> <span data-ttu-id="c1600-104">一个可能的原因是尝试重载原始过程。</span><span class="sxs-lookup"><span data-stu-id="c1600-104">One possible cause is an attempt to overload the original procedure.</span></span> <span data-ttu-id="c1600-105">重载的过程必须具有不同的参数列表。</span><span class="sxs-lookup"><span data-stu-id="c1600-105">Overloaded procedures must have different argument lists.</span></span>  
  
 <span data-ttu-id="c1600-106">**错误 ID:** BC30269</span><span class="sxs-lookup"><span data-stu-id="c1600-106">**Error ID:** BC30269</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c1600-107">更正此错误</span><span class="sxs-lookup"><span data-stu-id="c1600-107">To correct this error</span></span>  
  
- <span data-ttu-id="c1600-108">过程名称或参数列表中，更改或删除重复的声明。</span><span class="sxs-lookup"><span data-stu-id="c1600-108">Change the procedure name or the argument list, or remove the duplicate declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1600-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="c1600-109">See also</span></span>

- [<span data-ttu-id="c1600-110">对已声明元素的引用</span><span class="sxs-lookup"><span data-stu-id="c1600-110">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="c1600-111">重载过程注意事项</span><span class="sxs-lookup"><span data-stu-id="c1600-111">Considerations in Overloading Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)
