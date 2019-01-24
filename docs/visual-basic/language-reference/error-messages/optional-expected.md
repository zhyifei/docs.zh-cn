---
title: '&#39;可选&#39;预期'
ms.date: 07/20/2015
f1_keywords:
- bc30202
- vbc30202
helpviewer_keywords:
- BC30202
ms.assetid: 6f75060c-2db4-4a79-b5d1-5780c09a74cd
ms.openlocfilehash: 46bd84e2bcf5c5bea11a5c9d8b6e9254c49e3021
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54642472"
---
# <a name="39optional39-expected"></a><span data-ttu-id="5b257-102">&#39;可选&#39;预期</span><span class="sxs-lookup"><span data-stu-id="5b257-102">&#39;Optional&#39; expected</span></span>
<span data-ttu-id="5b257-103">过程声明中的可选自变量后跟一个必需的参数。</span><span class="sxs-lookup"><span data-stu-id="5b257-103">An optional argument in a procedure declaration is followed by a required argument.</span></span> <span data-ttu-id="5b257-104">每个自变量跟在可选参数还必须是可选的。</span><span class="sxs-lookup"><span data-stu-id="5b257-104">Every argument following an optional argument must also be optional.</span></span>  
  
 <span data-ttu-id="5b257-105">**错误 ID:** BC30202</span><span class="sxs-lookup"><span data-stu-id="5b257-105">**Error ID:** BC30202</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5b257-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="5b257-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="5b257-107">如果参数是要将所需，移动它，以在参数列表中前面的第一个可选参数。</span><span class="sxs-lookup"><span data-stu-id="5b257-107">If the argument is intended to be required, move it to precede the first optional argument in the argument list.</span></span>  
  
2.  <span data-ttu-id="5b257-108">如果此参数是为可选，使用`Optional`关键字。</span><span class="sxs-lookup"><span data-stu-id="5b257-108">If the argument is intended to be optional, use the `Optional` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b257-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="5b257-109">See also</span></span>
- [<span data-ttu-id="5b257-110">可选参数</span><span class="sxs-lookup"><span data-stu-id="5b257-110">Optional Parameters</span></span>](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)
