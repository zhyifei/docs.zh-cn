---
title: Erase 语句
ms.date: 07/20/2015
f1_keywords:
- vb.Erase
helpviewer_keywords:
- Erase keyword [Visual Basic]
- Erase statement [Visual Basic]
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
ms.openlocfilehash: 6d2052ceccbecd772c4e4bb18052aed74223a36e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343703"
---
# <a name="erase-statement-visual-basic"></a><span data-ttu-id="650b3-102">Erase 语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="650b3-102">Erase Statement (Visual Basic)</span></span>
<span data-ttu-id="650b3-103">用于释放数组变量并解除分配用于其元素的内存。</span><span class="sxs-lookup"><span data-stu-id="650b3-103">Used to release array variables and deallocate the memory used for their elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="650b3-104">语法</span><span class="sxs-lookup"><span data-stu-id="650b3-104">Syntax</span></span>  
  
```vb  
Erase arraylist  
```  
  
## <a name="parts"></a><span data-ttu-id="650b3-105">部件</span><span class="sxs-lookup"><span data-stu-id="650b3-105">Parts</span></span>  
 `arraylist`  
 <span data-ttu-id="650b3-106">必需。</span><span class="sxs-lookup"><span data-stu-id="650b3-106">Required.</span></span> <span data-ttu-id="650b3-107">要清除的数组变量的列表。</span><span class="sxs-lookup"><span data-stu-id="650b3-107">List of array variables to be erased.</span></span> <span data-ttu-id="650b3-108">以逗号分隔多个变量。</span><span class="sxs-lookup"><span data-stu-id="650b3-108">Multiple variables are separated by commas.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="650b3-109">备注</span><span class="sxs-lookup"><span data-stu-id="650b3-109">Remarks</span></span>  
 <span data-ttu-id="650b3-110">`Erase` 语句只能出现在过程级别。</span><span class="sxs-lookup"><span data-stu-id="650b3-110">The `Erase` statement can appear only at procedure level.</span></span> <span data-ttu-id="650b3-111">这意味着，可以在过程中释放数组，但不能在类或模块级别进行。</span><span class="sxs-lookup"><span data-stu-id="650b3-111">This means you can release arrays inside a procedure but not at class or module level.</span></span>  
  
 <span data-ttu-id="650b3-112">`Erase` 语句等效于将 `Nothing` 赋给每个数组变量。</span><span class="sxs-lookup"><span data-stu-id="650b3-112">The `Erase` statement is equivalent to assigning `Nothing` to each array variable.</span></span>  
  
## <a name="example"></a><span data-ttu-id="650b3-113">示例</span><span class="sxs-lookup"><span data-stu-id="650b3-113">Example</span></span>  
 <span data-ttu-id="650b3-114">下面的示例使用 `Erase` 语句来清除两个数组，并分别释放其内存（1000和100存储元素）。</span><span class="sxs-lookup"><span data-stu-id="650b3-114">The following example uses the `Erase` statement to clear two arrays and free their memory (1000 and 100 storage elements, respectively).</span></span> <span data-ttu-id="650b3-115">然后，`ReDim` 语句将新的数组实例赋给三维数组。</span><span class="sxs-lookup"><span data-stu-id="650b3-115">The `ReDim` statement then assigns a new array instance to the three-dimensional array.</span></span>  
  
 [!code-vb[VbVbalrStatements#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="650b3-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="650b3-116">See also</span></span>

- [<span data-ttu-id="650b3-117">Nothing</span><span class="sxs-lookup"><span data-stu-id="650b3-117">Nothing</span></span>](../../../visual-basic/language-reference/nothing.md)
- [<span data-ttu-id="650b3-118">ReDim 语句</span><span class="sxs-lookup"><span data-stu-id="650b3-118">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)
