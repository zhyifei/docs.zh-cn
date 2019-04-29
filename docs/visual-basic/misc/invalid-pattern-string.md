---
title: 无效模式字符串
ms.date: 07/20/2015
ms.assetid: ec1aecdb-5339-4a93-be71-eec56b1d7438
ms.openlocfilehash: 7390b9b32eea248969813b52f8d9799798718de0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790593"
---
# <a name="invalid-pattern-string"></a><span data-ttu-id="4d452-102">无效模式字符串</span><span class="sxs-lookup"><span data-stu-id="4d452-102">Invalid pattern string</span></span>
<span data-ttu-id="4d452-103">在搜索的 `Like` 操作中指定的模式字符串无效。</span><span class="sxs-lookup"><span data-stu-id="4d452-103">The pattern string specified in the `Like` operation of a search is invalid.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4d452-104">更正此错误</span><span class="sxs-lookup"><span data-stu-id="4d452-104">To correct this error</span></span>  
  
1. <span data-ttu-id="4d452-105">查看列表中表达式的有效字符。</span><span class="sxs-lookup"><span data-stu-id="4d452-105">Review the valid characters for list expressions.</span></span>  
  
2. <span data-ttu-id="4d452-106">在模式范围内，请确保起始范围字符小于结束范围字符，如 `[a-z]`中所示。</span><span class="sxs-lookup"><span data-stu-id="4d452-106">In the pattern range, ensure that the start range character is less than the end range character, as in `[a-z]`.</span></span>  
  
3. <span data-ttu-id="4d452-107">在模式范围内，请确保不存在彼此相邻的多个连字符，如 `[a--z]`中所示。</span><span class="sxs-lookup"><span data-stu-id="4d452-107">In the pattern range, ensure that there are not multiple hyphens next to each other, as in `[a--z]`.</span></span>  
  
4. <span data-ttu-id="4d452-108">以右括号结束模式范围。</span><span class="sxs-lookup"><span data-stu-id="4d452-108">End pattern ranges with a closing bracket.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d452-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="4d452-109">See also</span></span>

- [<span data-ttu-id="4d452-110">Like 运算符</span><span class="sxs-lookup"><span data-stu-id="4d452-110">Like Operator</span></span>](../../visual-basic/language-reference/operators/like-operator.md)
