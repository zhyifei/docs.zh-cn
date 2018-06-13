---
title: '&#39;可选&#39;预期'
ms.date: 07/20/2015
f1_keywords:
- bc30202
- vbc30202
helpviewer_keywords:
- BC30202
ms.assetid: 6f75060c-2db4-4a79-b5d1-5780c09a74cd
ms.openlocfilehash: 52e4288255a246f78730b33beb55f6d2d83ff214
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33593949"
---
# <a name="39optional39-expected"></a><span data-ttu-id="f61e1-102">&#39;可选&#39;预期</span><span class="sxs-lookup"><span data-stu-id="f61e1-102">&#39;Optional&#39; expected</span></span>
<span data-ttu-id="f61e1-103">过程声明中的可选自变量后跟一个必需的参数。</span><span class="sxs-lookup"><span data-stu-id="f61e1-103">An optional argument in a procedure declaration is followed by a required argument.</span></span> <span data-ttu-id="f61e1-104">每个参数跟在可选参数还必须是可选的。</span><span class="sxs-lookup"><span data-stu-id="f61e1-104">Every argument following an optional argument must also be optional.</span></span>  
  
 <span data-ttu-id="f61e1-105">**错误 ID:** BC30202</span><span class="sxs-lookup"><span data-stu-id="f61e1-105">**Error ID:** BC30202</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f61e1-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="f61e1-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="f61e1-107">如果自变量用于需要请将其在第一个可选自变量参数列表中前面放置移。</span><span class="sxs-lookup"><span data-stu-id="f61e1-107">If the argument is intended to be required, move it to precede the first optional argument in the argument list.</span></span>  
  
2.  <span data-ttu-id="f61e1-108">如果参数旨在成为可选，使用`Optional`关键字。</span><span class="sxs-lookup"><span data-stu-id="f61e1-108">If the argument is intended to be optional, use the `Optional` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f61e1-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="f61e1-109">See Also</span></span>  
 [<span data-ttu-id="f61e1-110">可选参数</span><span class="sxs-lookup"><span data-stu-id="f61e1-110">Optional Parameters</span></span>](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)
