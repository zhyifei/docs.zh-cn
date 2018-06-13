---
title: Erase 语句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Erase
helpviewer_keywords:
- Erase keyword [Visual Basic]
- Erase statement [Visual Basic]
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
ms.openlocfilehash: 317e2a7dc5facb08388f3a3e635734e4daed5eac
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33601788"
---
# <a name="erase-statement-visual-basic"></a><span data-ttu-id="440ef-102">Erase 语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="440ef-102">Erase Statement (Visual Basic)</span></span>
<span data-ttu-id="440ef-103">用于释放数组变量和解除分配的内存用于其元素。</span><span class="sxs-lookup"><span data-stu-id="440ef-103">Used to release array variables and deallocate the memory used for their elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="440ef-104">语法</span><span class="sxs-lookup"><span data-stu-id="440ef-104">Syntax</span></span>  
  
```  
Erase arraylist  
```  
  
## <a name="parts"></a><span data-ttu-id="440ef-105">部件</span><span class="sxs-lookup"><span data-stu-id="440ef-105">Parts</span></span>  
 `arraylist`  
 <span data-ttu-id="440ef-106">必须的。</span><span class="sxs-lookup"><span data-stu-id="440ef-106">Required.</span></span> <span data-ttu-id="440ef-107">要消除的数组变量的列表。</span><span class="sxs-lookup"><span data-stu-id="440ef-107">List of array variables to be erased.</span></span> <span data-ttu-id="440ef-108">以逗号分隔多个变量。</span><span class="sxs-lookup"><span data-stu-id="440ef-108">Multiple variables are separated by commas.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="440ef-109">备注</span><span class="sxs-lookup"><span data-stu-id="440ef-109">Remarks</span></span>  
 <span data-ttu-id="440ef-110">`Erase`语句只能出现在过程级别。</span><span class="sxs-lookup"><span data-stu-id="440ef-110">The `Erase` statement can appear only at procedure level.</span></span> <span data-ttu-id="440ef-111">这意味着，你可以释放在过程中而不是在类或模块级别的数组。</span><span class="sxs-lookup"><span data-stu-id="440ef-111">This means you can release arrays inside a procedure but not at class or module level.</span></span>  
  
 <span data-ttu-id="440ef-112">`Erase`语句是等效于分配`Nothing`给每个数组变量。</span><span class="sxs-lookup"><span data-stu-id="440ef-112">The `Erase` statement is equivalent to assigning `Nothing` to each array variable.</span></span>  
  
## <a name="example"></a><span data-ttu-id="440ef-113">示例</span><span class="sxs-lookup"><span data-stu-id="440ef-113">Example</span></span>  
 <span data-ttu-id="440ef-114">下面的示例使用`Erase`语句以清除两个数组，并释放其内存 (1000年和 100 个存储元素分别)。</span><span class="sxs-lookup"><span data-stu-id="440ef-114">The following example uses the `Erase` statement to clear two arrays and free their memory (1000 and 100 storage elements, respectively).</span></span> <span data-ttu-id="440ef-115">`ReDim`语句随后将新的数组实例分配给三维数组。</span><span class="sxs-lookup"><span data-stu-id="440ef-115">The `ReDim` statement then assigns a new array instance to the three-dimensional array.</span></span>  
  
 [!code-vb[VbVbalrStatements#19](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/erase-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="440ef-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="440ef-116">See Also</span></span>  
 [<span data-ttu-id="440ef-117">Nothing</span><span class="sxs-lookup"><span data-stu-id="440ef-117">Nothing</span></span>](../../../visual-basic/language-reference/nothing.md)  
 [<span data-ttu-id="440ef-118">ReDim 语句</span><span class="sxs-lookup"><span data-stu-id="440ef-118">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)
