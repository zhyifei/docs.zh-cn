---
title: Erase 语句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Erase
helpviewer_keywords:
- Erase keyword [Visual Basic]
- Erase statement [Visual Basic]
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
ms.openlocfilehash: bf3eb6476dc1485faeddab475f29e508175d3378
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58840401"
---
# <a name="erase-statement-visual-basic"></a><span data-ttu-id="65894-102">Erase 语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="65894-102">Erase Statement (Visual Basic)</span></span>
<span data-ttu-id="65894-103">用于释放数组变量并解除分配用于其元素的内存。</span><span class="sxs-lookup"><span data-stu-id="65894-103">Used to release array variables and deallocate the memory used for their elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65894-104">语法</span><span class="sxs-lookup"><span data-stu-id="65894-104">Syntax</span></span>  
  
```  
Erase arraylist  
```  
  
## <a name="parts"></a><span data-ttu-id="65894-105">部件</span><span class="sxs-lookup"><span data-stu-id="65894-105">Parts</span></span>  
 `arraylist`  
 <span data-ttu-id="65894-106">必需。</span><span class="sxs-lookup"><span data-stu-id="65894-106">Required.</span></span> <span data-ttu-id="65894-107">要清除的数组变量的列表。</span><span class="sxs-lookup"><span data-stu-id="65894-107">List of array variables to be erased.</span></span> <span data-ttu-id="65894-108">以逗号分隔多个变量。</span><span class="sxs-lookup"><span data-stu-id="65894-108">Multiple variables are separated by commas.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="65894-109">备注</span><span class="sxs-lookup"><span data-stu-id="65894-109">Remarks</span></span>  
 <span data-ttu-id="65894-110">`Erase`语句只能出现在过程级别。</span><span class="sxs-lookup"><span data-stu-id="65894-110">The `Erase` statement can appear only at procedure level.</span></span> <span data-ttu-id="65894-111">这意味着，你可以释放过程内，但不能在类或模块级别的数组。</span><span class="sxs-lookup"><span data-stu-id="65894-111">This means you can release arrays inside a procedure but not at class or module level.</span></span>  
  
 <span data-ttu-id="65894-112">`Erase`语句是等效于分配`Nothing`到每个数组变量。</span><span class="sxs-lookup"><span data-stu-id="65894-112">The `Erase` statement is equivalent to assigning `Nothing` to each array variable.</span></span>  
  
## <a name="example"></a><span data-ttu-id="65894-113">示例</span><span class="sxs-lookup"><span data-stu-id="65894-113">Example</span></span>  
 <span data-ttu-id="65894-114">下面的示例使用`Erase`语句清除两个数组并释放其内存 (1000年和 100 个存储元素分别)。</span><span class="sxs-lookup"><span data-stu-id="65894-114">The following example uses the `Erase` statement to clear two arrays and free their memory (1000 and 100 storage elements, respectively).</span></span> <span data-ttu-id="65894-115">`ReDim`然后语句将新的数组实例分配给三维数组。</span><span class="sxs-lookup"><span data-stu-id="65894-115">The `ReDim` statement then assigns a new array instance to the three-dimensional array.</span></span>  
  
 [!code-vb[VbVbalrStatements#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="65894-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="65894-116">See also</span></span>

- [<span data-ttu-id="65894-117">Nothing</span><span class="sxs-lookup"><span data-stu-id="65894-117">Nothing</span></span>](../../../visual-basic/language-reference/nothing.md)
- [<span data-ttu-id="65894-118">ReDim 语句</span><span class="sxs-lookup"><span data-stu-id="65894-118">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)
