---
title: 此数组被固定或临时锁定 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrID10
ms.assetid: de6713a6-51d7-4edb-8515-d5fb544e2091
ms.openlocfilehash: f0b80e2be007ff44569365f37a2331f1ecd7a216
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58839400"
---
# <a name="this-array-is-fixed-or-temporarily-locked-visual-basic"></a><span data-ttu-id="47df2-102">此数组被固定或临时锁定 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="47df2-102">This array is fixed or temporarily locked (Visual Basic)</span></span>
<span data-ttu-id="47df2-103">此错误具有以下可能的原因：</span><span class="sxs-lookup"><span data-stu-id="47df2-103">This error has the following possible causes:</span></span>  
  
-   <span data-ttu-id="47df2-104">使用`ReDim`若要更改的固定大小数组的元素数。</span><span class="sxs-lookup"><span data-stu-id="47df2-104">Using `ReDim` to change the number of elements of a fixed-size array.</span></span>  
  
-   <span data-ttu-id="47df2-105">Redimensioning 模块级别动态数组，其中的一个元素具有作为参数传递给过程。</span><span class="sxs-lookup"><span data-stu-id="47df2-105">Redimensioning a module-level dynamic array, in which one element has been passed as an argument to a procedure.</span></span> <span data-ttu-id="47df2-106">如果传递一个元素，则数组将被锁定以防止取消分配内存的过程中的引用参数。</span><span class="sxs-lookup"><span data-stu-id="47df2-106">If an element is passed, the array is locked to prevent deallocating memory for the reference parameter within the procedure.</span></span>  
  
-   <span data-ttu-id="47df2-107">尝试将一个值赋给`Variant`变量包含一个数组，但`Variant`当前被锁定。</span><span class="sxs-lookup"><span data-stu-id="47df2-107">Attempting to assign a value to a `Variant` variable containing an array, but the `Variant` is currently locked.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="47df2-108">更正此错误</span><span class="sxs-lookup"><span data-stu-id="47df2-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="47df2-109">将原始数组而不是通过声明它具有固定动态`ReDim`（如果声明数组过程中），或通过声明而无需指定的元素数 （如果在模块级别声明数组。</span><span class="sxs-lookup"><span data-stu-id="47df2-109">Make the original array dynamic rather than fixed by declaring it with `ReDim` (if the array is declared within a procedure), or by declaring it without specifying the number of elements (if the array is declared at the module level.</span></span>  
  
2.  <span data-ttu-id="47df2-110">确定是否真的需要传递了元素，因为它是在模块中的所有过程中可见。</span><span class="sxs-lookup"><span data-stu-id="47df2-110">Determine whether you really need to pass the element, since it is visible within all procedures in the module.</span></span>  
  
3.  <span data-ttu-id="47df2-111">确定锁定`Variant`并更正它。</span><span class="sxs-lookup"><span data-stu-id="47df2-111">Determine what is locking the `Variant` and remedy it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47df2-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="47df2-112">See also</span></span>

- [<span data-ttu-id="47df2-113">数组</span><span class="sxs-lookup"><span data-stu-id="47df2-113">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
