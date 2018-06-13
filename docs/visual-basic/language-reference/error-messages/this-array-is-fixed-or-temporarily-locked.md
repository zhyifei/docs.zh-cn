---
title: 此数组被固定或临时锁定 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrID10
ms.assetid: de6713a6-51d7-4edb-8515-d5fb544e2091
ms.openlocfilehash: e912bd202603d9a0f427418708ad584c7d6203e9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33593559"
---
# <a name="this-array-is-fixed-or-temporarily-locked-visual-basic"></a><span data-ttu-id="610ee-102">此数组被固定或临时锁定 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="610ee-102">This array is fixed or temporarily locked (Visual Basic)</span></span>
<span data-ttu-id="610ee-103">此错误具有以下可能的原因：</span><span class="sxs-lookup"><span data-stu-id="610ee-103">This error has the following possible causes:</span></span>  
  
-   <span data-ttu-id="610ee-104">使用`ReDim`若要更改的固定大小数组的元素数。</span><span class="sxs-lookup"><span data-stu-id="610ee-104">Using `ReDim` to change the number of elements of a fixed-size array.</span></span>  
  
-   <span data-ttu-id="610ee-105">Redimensioning 模块级别动态数组，其中的一个元素具有作为参数传递给过程。</span><span class="sxs-lookup"><span data-stu-id="610ee-105">Redimensioning a module-level dynamic array, in which one element has been passed as an argument to a procedure.</span></span> <span data-ttu-id="610ee-106">如果元素已传递，数组被锁定以防止释放内存过程内引用参数。</span><span class="sxs-lookup"><span data-stu-id="610ee-106">If an element is passed, the array is locked to prevent deallocating memory for the reference parameter within the procedure.</span></span>  
  
-   <span data-ttu-id="610ee-107">尝试将值赋给`Variant`变量包含一个数组，但`Variant`当前已锁定。</span><span class="sxs-lookup"><span data-stu-id="610ee-107">Attempting to assign a value to a `Variant` variable containing an array, but the `Variant` is currently locked.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="610ee-108">更正此错误</span><span class="sxs-lookup"><span data-stu-id="610ee-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="610ee-109">使原始数组而不是由声明它具有固定动态`ReDim`（如果声明数组过程中），或通过声明而无需指定元素的数目 （如果在模块级别声明数组。</span><span class="sxs-lookup"><span data-stu-id="610ee-109">Make the original array dynamic rather than fixed by declaring it with `ReDim` (if the array is declared within a procedure), or by declaring it without specifying the number of elements (if the array is declared at the module level.</span></span>  
  
2.  <span data-ttu-id="610ee-110">确定是否真的需要传递了元素，因为它是在模块中的所有过程内可见。</span><span class="sxs-lookup"><span data-stu-id="610ee-110">Determine whether you really need to pass the element, since it is visible within all procedures in the module.</span></span>  
  
3.  <span data-ttu-id="610ee-111">确定锁定`Variant`并更正它。</span><span class="sxs-lookup"><span data-stu-id="610ee-111">Determine what is locking the `Variant` and remedy it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="610ee-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="610ee-112">See Also</span></span>  
 [<span data-ttu-id="610ee-113">数组</span><span class="sxs-lookup"><span data-stu-id="610ee-113">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
