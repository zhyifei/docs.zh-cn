---
title: 需要声明
ms.date: 07/20/2015
f1_keywords:
- vbc30188
- bc30188
helpviewer_keywords:
- BC30188
ms.assetid: da6b1df3-fe6b-4415-88e6-0977e5189e0b
ms.openlocfilehash: 64ee75c93615f57b15fea29f06fff500a395ba0c
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58834174"
---
# <a name="declaration-expected"></a><span data-ttu-id="70acb-102">需要声明</span><span class="sxs-lookup"><span data-stu-id="70acb-102">Declaration expected</span></span>
<span data-ttu-id="70acb-103">非声明语句，如分配或循环语句发生在外的任何过程。</span><span class="sxs-lookup"><span data-stu-id="70acb-103">A nondeclarative statement, such as an assignment or loop statement, occurs outside any procedure.</span></span> <span data-ttu-id="70acb-104">只有声明允许外部过程。</span><span class="sxs-lookup"><span data-stu-id="70acb-104">Only declarations are allowed outside procedures.</span></span>  
  
 <span data-ttu-id="70acb-105">或者，编程元素声明不声明关键字如`Dim`或`Const`。</span><span class="sxs-lookup"><span data-stu-id="70acb-105">Alternatively, a programming element is declared without a declaration keyword such as `Dim` or `Const`.</span></span>  
  
 <span data-ttu-id="70acb-106">**错误 ID:** BC30188</span><span class="sxs-lookup"><span data-stu-id="70acb-106">**Error ID:** BC30188</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="70acb-107">更正此错误</span><span class="sxs-lookup"><span data-stu-id="70acb-107">To correct this error</span></span>  
  
-   <span data-ttu-id="70acb-108">将非声明语句移动到过程的正文。</span><span class="sxs-lookup"><span data-stu-id="70acb-108">Move the nondeclarative statement to the body of a procedure.</span></span>  
  
-   <span data-ttu-id="70acb-109">开始使用适当的声明关键字声明。</span><span class="sxs-lookup"><span data-stu-id="70acb-109">Begin the declaration with an appropriate declaration keyword.</span></span>  
  
-   <span data-ttu-id="70acb-110">请确保声明关键字没有拼写错误。</span><span class="sxs-lookup"><span data-stu-id="70acb-110">Ensure that a declaration keyword is not misspelled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70acb-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="70acb-111">See also</span></span>

- [<span data-ttu-id="70acb-112">过程</span><span class="sxs-lookup"><span data-stu-id="70acb-112">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="70acb-113">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="70acb-113">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
