---
title: "没有可访问重载 &#39;&lt;methodname&gt;&#39; 可以使用未进行收缩转换这些自变量调用：&lt;列表&gt;"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrAmbiguousCall2
ms.assetid: 13b20ffa-9f02-4971-a3cb-e08b402fd971
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4d0024289e64b97dc5c3ac253697d51194040a57
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="no-accessible-overloaded-39ltmethodnamegt39-can-be-called-with-these-arguments-without-a-narrowing-conversion-ltlistgt"></a><span data-ttu-id="c9978-102">没有可访问重载 &#39;&lt;methodname&gt;&#39; 可以使用未进行收缩转换这些自变量调用：&lt;列表&gt;</span><span class="sxs-lookup"><span data-stu-id="c9978-102">No accessible overloaded &#39;&lt;methodname&gt;&#39; can be called with these arguments without a narrowing conversion: &lt;list&gt;</span></span>
<span data-ttu-id="c9978-103">调用了重载方法，但是该方法必须进行缩放转换才能与提供的参数列表匹配。</span><span class="sxs-lookup"><span data-stu-id="c9978-103">An overloaded method was called, but the method cannot be matched with the list of provided arguments without a narrowing conversion.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c9978-104">更正此错误</span><span class="sxs-lookup"><span data-stu-id="c9978-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="c9978-105">指定 `Option``Strict` `Off`。</span><span class="sxs-lookup"><span data-stu-id="c9978-105">Specify `Option``Strict` `Off`.</span></span>  
  
2.  <span data-ttu-id="c9978-106">更改参数以匹配重载方法的签名。</span><span class="sxs-lookup"><span data-stu-id="c9978-106">Change the arguments to match a signature of the overloaded method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9978-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c9978-107">See Also</span></span>  
 [<span data-ttu-id="c9978-108">按值和按引用传递自变量</span><span class="sxs-lookup"><span data-stu-id="c9978-108">Passing Arguments by Value and by Reference</span></span>](../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="c9978-109">扩大转换和收缩转换</span><span class="sxs-lookup"><span data-stu-id="c9978-109">Widening and Narrowing Conversions</span></span>](../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
