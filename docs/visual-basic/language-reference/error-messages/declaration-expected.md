---
title: 需要声明
ms.date: 07/20/2015
f1_keywords:
- vbc30188
- bc30188
helpviewer_keywords:
- BC30188
ms.assetid: da6b1df3-fe6b-4415-88e6-0977e5189e0b
ms.openlocfilehash: c5c9b665b78c7c63c55292e38cc96ee8b2962a61
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33583885"
---
# <a name="declaration-expected"></a><span data-ttu-id="d7f53-102">需要声明</span><span class="sxs-lookup"><span data-stu-id="d7f53-102">Declaration expected</span></span>
<span data-ttu-id="d7f53-103">非声明语句，如分配或循环语句发生在任何过程外。</span><span class="sxs-lookup"><span data-stu-id="d7f53-103">A nondeclarative statement, such as an assignment or loop statement, occurs outside any procedure.</span></span> <span data-ttu-id="d7f53-104">只有声明允许外部过程。</span><span class="sxs-lookup"><span data-stu-id="d7f53-104">Only declarations are allowed outside procedures.</span></span>  
  
 <span data-ttu-id="d7f53-105">或者，声明的编程元素是没有用声明关键字如`Dim`或`Const`。</span><span class="sxs-lookup"><span data-stu-id="d7f53-105">Alternatively, a programming element is declared without a declaration keyword such as `Dim` or `Const`.</span></span>  
  
 <span data-ttu-id="d7f53-106">**错误 ID:** BC30188</span><span class="sxs-lookup"><span data-stu-id="d7f53-106">**Error ID:** BC30188</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d7f53-107">更正此错误</span><span class="sxs-lookup"><span data-stu-id="d7f53-107">To correct this error</span></span>  
  
-   <span data-ttu-id="d7f53-108">将非声明语句移动到过程的正文。</span><span class="sxs-lookup"><span data-stu-id="d7f53-108">Move the nondeclarative statement to the body of a procedure.</span></span>  
  
-   <span data-ttu-id="d7f53-109">开始使用适当的声明关键字声明。</span><span class="sxs-lookup"><span data-stu-id="d7f53-109">Begin the declaration with an appropriate declaration keyword.</span></span>  
  
-   <span data-ttu-id="d7f53-110">确保声明关键字没有拼写错误。</span><span class="sxs-lookup"><span data-stu-id="d7f53-110">Ensure that a declaration keyword is not misspelled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7f53-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="d7f53-111">See Also</span></span>  
 [<span data-ttu-id="d7f53-112">过程</span><span class="sxs-lookup"><span data-stu-id="d7f53-112">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [<span data-ttu-id="d7f53-113">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="d7f53-113">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
