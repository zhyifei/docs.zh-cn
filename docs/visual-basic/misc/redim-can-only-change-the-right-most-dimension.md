---
title: "&#39;ReDim &#39;只能更改最右边的维度"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrArray_TypeMismatch
ms.assetid: d53cf41b-7a7a-466c-a29a-920d99698fa9
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 752e0e54c48b3b348a477787e5e911f1b1777667
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="39redim39-can-only-change-the-right-most-dimension"></a><span data-ttu-id="e2ca5-102">&#39;ReDim &#39;只能更改最右边的维度</span><span class="sxs-lookup"><span data-stu-id="e2ca5-102">&#39;ReDim&#39; can only change the right-most dimension</span></span>
<span data-ttu-id="e2ca5-103">`ReDim` 语句尝试使用 `Preserve` 关键字来更改一个数组的维度，它不是最后一个维度。</span><span class="sxs-lookup"><span data-stu-id="e2ca5-103">A `ReDim` statement attempted to use the `Preserve` keyword to change a dimension of an array that is not the last dimension.</span></span> <span data-ttu-id="e2ca5-104">使用 `Preserve`时，只能调整数组最后一个维度的大小。</span><span class="sxs-lookup"><span data-stu-id="e2ca5-104">When using `Preserve`, you can resize only the last dimension of an array.</span></span> <span data-ttu-id="e2ca5-105">对于其他所有维度，必须指定与现有数组相同的大小。</span><span class="sxs-lookup"><span data-stu-id="e2ca5-105">For all other dimensions, you must specify the same size as for the existing array.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e2ca5-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="e2ca5-106">To correct this error</span></span>  
  
-   <span data-ttu-id="e2ca5-107">删除 `Preserve` 关键字。</span><span class="sxs-lookup"><span data-stu-id="e2ca5-107">Remove the `Preserve` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2ca5-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="e2ca5-108">See Also</span></span>  
 [<span data-ttu-id="e2ca5-109">Visual Basic 中的数组</span><span class="sxs-lookup"><span data-stu-id="e2ca5-109">Arrays in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="e2ca5-110">在 Visual Basic 中的数组维数</span><span class="sxs-lookup"><span data-stu-id="e2ca5-110">Array dimensions in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/array-dimensions.md)  
 [<span data-ttu-id="e2ca5-111">ReDim 语句</span><span class="sxs-lookup"><span data-stu-id="e2ca5-111">ReDim Statement</span></span>](../../visual-basic/language-reference/statements/redim-statement.md)  
 [<span data-ttu-id="e2ca5-112">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="e2ca5-112">Dim Statement</span></span>](../../visual-basic/language-reference/statements/dim-statement.md)  
 [<span data-ttu-id="e2ca5-113">保留-删除</span><span class="sxs-lookup"><span data-stu-id="e2ca5-113">Preserve - delete</span></span>](http://msdn.microsoft.com/library/91badeab-b4e0-48b6-92c9-9f0c8f995d81)
