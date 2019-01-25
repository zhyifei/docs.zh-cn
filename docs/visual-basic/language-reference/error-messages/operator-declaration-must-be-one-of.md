---
title: '运算符声明必须是之一: +、-，*，-、-、 ^， &amp;，Like、 Mod、 和，Or、 Xor、 没有，请&lt; &lt;， &gt; &gt;，=， &lt; &gt;， &lt;， &lt;=、 &gt;&gt;=、 CType、 IsTrue、 IsFalse'
ms.date: 07/20/2015
f1_keywords:
- bc33000
- vbc33000
helpviewer_keywords:
- BC33000
ms.assetid: 15c5d8eb-3a8c-4141-8f41-33151afabf97
ms.openlocfilehash: f32935dd4aaccd3040655b418badc13c1988c1b8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54622268"
---
# <a name="operator-declaration-must-be-one-of----amp-like-mod-and-or-xor-not-ltlt-gtgt"></a><span data-ttu-id="d99b0-102">运算符声明必须是其中一个: +、-，\*，\,/、 ^， &amp;，Like、 Mod、 和，Or、 Xor、 Not、 &lt; &lt;， &gt; &gt;...</span><span class="sxs-lookup"><span data-stu-id="d99b0-102">Operator declaration must be one of:  +,-,\*,\,/,^, &amp;, Like, Mod, And, Or, Xor, Not, &lt;&lt;, &gt;&gt;...</span></span>
<span data-ttu-id="d99b0-103">您可以声明只是进行重载的运算符。</span><span class="sxs-lookup"><span data-stu-id="d99b0-103">You can declare only an operator that is eligible for overloading.</span></span> <span data-ttu-id="d99b0-104">下表列出了可以声明的运算符。</span><span class="sxs-lookup"><span data-stu-id="d99b0-104">The following table lists the operators you can declare.</span></span>  
  
|<span data-ttu-id="d99b0-105">类型</span><span class="sxs-lookup"><span data-stu-id="d99b0-105">Type</span></span>|<span data-ttu-id="d99b0-106">运算符</span><span class="sxs-lookup"><span data-stu-id="d99b0-106">Operators</span></span>|  
|----------|---------------|  
|<span data-ttu-id="d99b0-107">一元</span><span class="sxs-lookup"><span data-stu-id="d99b0-107">Unary</span></span>|<span data-ttu-id="d99b0-108">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span><span class="sxs-lookup"><span data-stu-id="d99b0-108">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span></span>|  
|<span data-ttu-id="d99b0-109">二进制</span><span class="sxs-lookup"><span data-stu-id="d99b0-109">Binary</span></span>|<span data-ttu-id="d99b0-110">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span><span class="sxs-lookup"><span data-stu-id="d99b0-110">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span></span>|  
|<span data-ttu-id="d99b0-111">转换（一元）</span><span class="sxs-lookup"><span data-stu-id="d99b0-111">Conversion (unary)</span></span>|`CType`|  
  
 <span data-ttu-id="d99b0-112">请注意， `=` ，二元列表中的运算符是比较运算符，而不是赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="d99b0-112">Note that the `=` operator in the binary list is the comparison operator, not the assignment operator.</span></span>  
  
 <span data-ttu-id="d99b0-113">**错误 ID:** BC33000</span><span class="sxs-lookup"><span data-stu-id="d99b0-113">**Error ID:** BC33000</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d99b0-114">更正此错误</span><span class="sxs-lookup"><span data-stu-id="d99b0-114">To correct this error</span></span>  
  
1.  <span data-ttu-id="d99b0-115">从一组可重载运算符中选择一个运算符。</span><span class="sxs-lookup"><span data-stu-id="d99b0-115">Select an operator from the set of overloadable operators.</span></span>  
  
2.  <span data-ttu-id="d99b0-116">如果你需要重载无法直接重载的运算符这一功能，请创建用于获取适当参数并返回适当值的 `Function` 过程。</span><span class="sxs-lookup"><span data-stu-id="d99b0-116">If you need the functionality of overloading an operator that you cannot overload directly, create a `Function` procedure that takes the appropriate parameters and returns the appropriate value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d99b0-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="d99b0-117">See also</span></span>
- [<span data-ttu-id="d99b0-118">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="d99b0-118">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="d99b0-119">运算符过程</span><span class="sxs-lookup"><span data-stu-id="d99b0-119">Operator Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)
- [<span data-ttu-id="d99b0-120">如何：定义运算符</span><span class="sxs-lookup"><span data-stu-id="d99b0-120">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="d99b0-121">如何：定义转换运算符</span><span class="sxs-lookup"><span data-stu-id="d99b0-121">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="d99b0-122">Function 语句</span><span class="sxs-lookup"><span data-stu-id="d99b0-122">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
