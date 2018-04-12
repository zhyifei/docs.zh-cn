---
title: Erase 语句 (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Erase
helpviewer_keywords:
- Erase keyword [Visual Basic]
- Erase statement [Visual Basic]
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 45a2b439cf5ad04d59cea59bb21d345d0057b322
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="erase-statement-visual-basic"></a><span data-ttu-id="df988-102">Erase 语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="df988-102">Erase Statement (Visual Basic)</span></span>
<span data-ttu-id="df988-103">用于释放数组变量和解除分配的内存用于其元素。</span><span class="sxs-lookup"><span data-stu-id="df988-103">Used to release array variables and deallocate the memory used for their elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df988-104">语法</span><span class="sxs-lookup"><span data-stu-id="df988-104">Syntax</span></span>  
  
```  
Erase arraylist  
```  
  
## <a name="parts"></a><span data-ttu-id="df988-105">部件</span><span class="sxs-lookup"><span data-stu-id="df988-105">Parts</span></span>  
 `arraylist`  
 <span data-ttu-id="df988-106">必需。</span><span class="sxs-lookup"><span data-stu-id="df988-106">Required.</span></span> <span data-ttu-id="df988-107">要消除的数组变量的列表。</span><span class="sxs-lookup"><span data-stu-id="df988-107">List of array variables to be erased.</span></span> <span data-ttu-id="df988-108">以逗号分隔多个变量。</span><span class="sxs-lookup"><span data-stu-id="df988-108">Multiple variables are separated by commas.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="df988-109">备注</span><span class="sxs-lookup"><span data-stu-id="df988-109">Remarks</span></span>  
 <span data-ttu-id="df988-110">`Erase`语句只能出现在过程级别。</span><span class="sxs-lookup"><span data-stu-id="df988-110">The `Erase` statement can appear only at procedure level.</span></span> <span data-ttu-id="df988-111">这意味着，你可以释放在过程中而不是在类或模块级别的数组。</span><span class="sxs-lookup"><span data-stu-id="df988-111">This means you can release arrays inside a procedure but not at class or module level.</span></span>  
  
 <span data-ttu-id="df988-112">`Erase`语句是等效于分配`Nothing`给每个数组变量。</span><span class="sxs-lookup"><span data-stu-id="df988-112">The `Erase` statement is equivalent to assigning `Nothing` to each array variable.</span></span>  
  
## <a name="example"></a><span data-ttu-id="df988-113">示例</span><span class="sxs-lookup"><span data-stu-id="df988-113">Example</span></span>  
 <span data-ttu-id="df988-114">下面的示例使用`Erase`语句以清除两个数组，并释放其内存 (1000年和 100 个存储元素分别)。</span><span class="sxs-lookup"><span data-stu-id="df988-114">The following example uses the `Erase` statement to clear two arrays and free their memory (1000 and 100 storage elements, respectively).</span></span> <span data-ttu-id="df988-115">`ReDim`语句随后将新的数组实例分配给三维数组。</span><span class="sxs-lookup"><span data-stu-id="df988-115">The `ReDim` statement then assigns a new array instance to the three-dimensional array.</span></span>  
  
 [!code-vb[VbVbalrStatements#19](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/erase-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="df988-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="df988-116">See Also</span></span>  
 [<span data-ttu-id="df988-117">Nothing</span><span class="sxs-lookup"><span data-stu-id="df988-117">Nothing</span></span>](../../../visual-basic/language-reference/nothing.md)  
 [<span data-ttu-id="df988-118">ReDim 语句</span><span class="sxs-lookup"><span data-stu-id="df988-118">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)
