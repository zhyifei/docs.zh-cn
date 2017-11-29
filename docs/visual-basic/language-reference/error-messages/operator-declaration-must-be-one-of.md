---
title: "运算符声明必须是: +、-，*，-，-，^， &amp;，Like、 Mod，和，或 Xor，不是， &lt; &lt;， &gt; &gt;，=， &lt; &gt;， &lt;， &lt;=、 &gt;&gt;= CType，为 true 时，IsFalse"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc33000
- vbc33000
helpviewer_keywords: BC33000
ms.assetid: 15c5d8eb-3a8c-4141-8f41-33151afabf97
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 80c8358dd13105c18e73e94735a51b02d5bd22c5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="operator-declaration-must-be-one-of----amp-like-mod-and-or-xor-not-ltlt-gtgt"></a><span data-ttu-id="efd48-102">运算符声明必须是: +、-，*，\,/，^， &amp;，Like、 Mod，和，或 Xor，不是， &lt; &lt;， &gt; &gt;...</span><span class="sxs-lookup"><span data-stu-id="efd48-102">Operator declaration must be one of:  +,-,*,\,/,^, &amp;, Like, Mod, And, Or, Xor, Not, &lt;&lt;, &gt;&gt;...</span></span>
<span data-ttu-id="efd48-103">您可以声明仅有资格享受重载的运算符。</span><span class="sxs-lookup"><span data-stu-id="efd48-103">You can declare only an operator that is eligible for overloading.</span></span> <span data-ttu-id="efd48-104">下表列出可以声明的运算符。</span><span class="sxs-lookup"><span data-stu-id="efd48-104">The following table lists the operators you can declare.</span></span>  
  
|<span data-ttu-id="efd48-105">类型</span><span class="sxs-lookup"><span data-stu-id="efd48-105">Type</span></span>|<span data-ttu-id="efd48-106">运算符</span><span class="sxs-lookup"><span data-stu-id="efd48-106">Operators</span></span>|  
|----------|---------------|  
|<span data-ttu-id="efd48-107">一元</span><span class="sxs-lookup"><span data-stu-id="efd48-107">Unary</span></span>|<span data-ttu-id="efd48-108">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span><span class="sxs-lookup"><span data-stu-id="efd48-108">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span></span>|  
|<span data-ttu-id="efd48-109">二进制</span><span class="sxs-lookup"><span data-stu-id="efd48-109">Binary</span></span>|<span data-ttu-id="efd48-110">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span><span class="sxs-lookup"><span data-stu-id="efd48-110">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span></span>|  
|<span data-ttu-id="efd48-111">转换（一元）</span><span class="sxs-lookup"><span data-stu-id="efd48-111">Conversion (unary)</span></span>|`CType`|  
  
 <span data-ttu-id="efd48-112">请注意，`=`二元列表中的运算符是比较运算符，而不是赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="efd48-112">Note that the `=` operator in the binary list is the comparison operator, not the assignment operator.</span></span>  
  
 <span data-ttu-id="efd48-113">**错误 ID:** BC33000</span><span class="sxs-lookup"><span data-stu-id="efd48-113">**Error ID:** BC33000</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="efd48-114">更正此错误</span><span class="sxs-lookup"><span data-stu-id="efd48-114">To correct this error</span></span>  
  
1.  <span data-ttu-id="efd48-115">从一组可重载运算符中选择一个运算符。</span><span class="sxs-lookup"><span data-stu-id="efd48-115">Select an operator from the set of overloadable operators.</span></span>  
  
2.  <span data-ttu-id="efd48-116">如果你需要重载无法直接重载的运算符这一功能，请创建用于获取适当参数并返回适当值的 `Function` 过程。</span><span class="sxs-lookup"><span data-stu-id="efd48-116">If you need the functionality of overloading an operator that you cannot overload directly, create a `Function` procedure that takes the appropriate parameters and returns the appropriate value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efd48-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="efd48-117">See Also</span></span>  
 [<span data-ttu-id="efd48-118">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="efd48-118">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [<span data-ttu-id="efd48-119">运算符过程</span><span class="sxs-lookup"><span data-stu-id="efd48-119">Operator Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)  
 [<span data-ttu-id="efd48-120">如何：定义运算符</span><span class="sxs-lookup"><span data-stu-id="efd48-120">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [<span data-ttu-id="efd48-121">如何：定义转换运算符</span><span class="sxs-lookup"><span data-stu-id="efd48-121">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)  
 [<span data-ttu-id="efd48-122">Function 语句</span><span class="sxs-lookup"><span data-stu-id="efd48-122">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
