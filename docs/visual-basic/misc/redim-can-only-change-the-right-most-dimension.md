---
title: “ReDim”只能更改最右边的维度
ms.date: 07/20/2015
f1_keywords:
- vbrArray_TypeMismatch
ms.assetid: d53cf41b-7a7a-466c-a29a-920d99698fa9
ms.openlocfilehash: d20d0374cd5183b6216d1c6e5b138256cf0a4f17
ms.sourcegitcommit: facefcacd7ae2e5645e463bc841df213c505ffd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2019
ms.locfileid: "55738950"
---
# <a name="redim-can-only-change-the-right-most-dimension"></a><span data-ttu-id="c13d8-102">“ReDim”只能更改最右边的维度</span><span class="sxs-lookup"><span data-stu-id="c13d8-102">'ReDim' can only change the right-most dimension</span></span>
<span data-ttu-id="c13d8-103">`ReDim` 语句尝试使用 `Preserve` 关键字来更改一个数组的维度，它不是最后一个维度。</span><span class="sxs-lookup"><span data-stu-id="c13d8-103">A `ReDim` statement attempted to use the `Preserve` keyword to change a dimension of an array that is not the last dimension.</span></span> <span data-ttu-id="c13d8-104">使用 `Preserve`时，只能调整数组最后一个维度的大小。</span><span class="sxs-lookup"><span data-stu-id="c13d8-104">When using `Preserve`, you can resize only the last dimension of an array.</span></span> <span data-ttu-id="c13d8-105">对于其他所有维度，必须指定与现有数组相同的大小。</span><span class="sxs-lookup"><span data-stu-id="c13d8-105">For all other dimensions, you must specify the same size as for the existing array.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c13d8-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="c13d8-106">To correct this error</span></span>  
  
-   <span data-ttu-id="c13d8-107">删除 `Preserve` 关键字。</span><span class="sxs-lookup"><span data-stu-id="c13d8-107">Remove the `Preserve` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c13d8-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="c13d8-108">See also</span></span>
- [<span data-ttu-id="c13d8-109">Visual Basic 中的数组</span><span class="sxs-lookup"><span data-stu-id="c13d8-109">Arrays in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="c13d8-110">在 Visual Basic 中的数组维数</span><span class="sxs-lookup"><span data-stu-id="c13d8-110">Array dimensions in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/array-dimensions.md)
- [<span data-ttu-id="c13d8-111">ReDim 语句</span><span class="sxs-lookup"><span data-stu-id="c13d8-111">ReDim Statement</span></span>](../../visual-basic/language-reference/statements/redim-statement.md)
- [<span data-ttu-id="c13d8-112">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="c13d8-112">Dim Statement</span></span>](../../visual-basic/language-reference/statements/dim-statement.md)
