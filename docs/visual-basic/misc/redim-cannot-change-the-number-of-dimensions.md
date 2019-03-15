---
title: “ReDim”无法更改维数
ms.date: 07/20/2015
f1_keywords:
- vbrArray_RankMismatch
ms.assetid: 52505298-9985-4682-8f6e-ff7d56077f34
ms.openlocfilehash: b6bb78c3f1d7224e6e4b432fd3aef4589f2f1cd4
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2019
ms.locfileid: "58019390"
---
# <a name="redim-cannot-change-the-number-of-dimensions"></a><span data-ttu-id="e8b2a-102">“ReDim”无法更改维数</span><span class="sxs-lookup"><span data-stu-id="e8b2a-102">'ReDim' cannot change the number of dimensions</span></span>
<span data-ttu-id="e8b2a-103">某操作尝试使用 `ReDim` 更改数组的秩（维数）。</span><span class="sxs-lookup"><span data-stu-id="e8b2a-103">An operation attempts to use the `ReDim` statement to change the rank (number of dimensions) of an array.</span></span> <span data-ttu-id="e8b2a-104">`ReDim` 可以更改已形式声明的数组的一个或多个维度的大小，但它不能更改数组的秩。</span><span class="sxs-lookup"><span data-stu-id="e8b2a-104">`ReDim` can change the size of one or more dimensions of an array that has already been formally declared, but it cannot change an array's rank.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e8b2a-105">更正此错误</span><span class="sxs-lookup"><span data-stu-id="e8b2a-105">To correct this error</span></span>  
  
-   <span data-ttu-id="e8b2a-106">确保想要更改的是数组的秩而不是其维度的大小，尽可能使用 `Dim` 声明具有所需秩的新数组。</span><span class="sxs-lookup"><span data-stu-id="e8b2a-106">Ensure that you intend to change the array's rank and not the sizes of its dimensions, and if possible, use `Dim` to declare a new array with the desired rank.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8b2a-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="e8b2a-107">See also</span></span>

- [<span data-ttu-id="e8b2a-108">Visual Basic 中的数组</span><span class="sxs-lookup"><span data-stu-id="e8b2a-108">Arrays in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="e8b2a-109">在 Visual Basic 中的数组维数</span><span class="sxs-lookup"><span data-stu-id="e8b2a-109">Array dimensions in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/array-dimensions.md)
- [<span data-ttu-id="e8b2a-110">ReDim 语句</span><span class="sxs-lookup"><span data-stu-id="e8b2a-110">ReDim Statement</span></span>](../../visual-basic/language-reference/statements/redim-statement.md)
- [<span data-ttu-id="e8b2a-111">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="e8b2a-111">Dim Statement</span></span>](../../visual-basic/language-reference/statements/dim-statement.md)
