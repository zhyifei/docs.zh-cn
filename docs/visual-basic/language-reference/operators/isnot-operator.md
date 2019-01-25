---
title: IsNot 运算符 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: ffafff915af8a94e9bc135246064e4c049d41838
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54596457"
---
# <a name="isnot-operator-visual-basic"></a><span data-ttu-id="f4475-102">IsNot 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f4475-102">IsNot Operator (Visual Basic)</span></span>
<span data-ttu-id="f4475-103">两个对象引用变量进行比较。</span><span class="sxs-lookup"><span data-stu-id="f4475-103">Compares two object reference variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4475-104">语法</span><span class="sxs-lookup"><span data-stu-id="f4475-104">Syntax</span></span>  
  
```  
result = object1 IsNot object2  
```  
  
## <a name="parts"></a><span data-ttu-id="f4475-105">部件</span><span class="sxs-lookup"><span data-stu-id="f4475-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="f4475-106">必需。</span><span class="sxs-lookup"><span data-stu-id="f4475-106">Required.</span></span> <span data-ttu-id="f4475-107">一个 `Boolean` 值。</span><span class="sxs-lookup"><span data-stu-id="f4475-107">A `Boolean` value.</span></span>  
  
 `object1`  
 <span data-ttu-id="f4475-108">必需。</span><span class="sxs-lookup"><span data-stu-id="f4475-108">Required.</span></span> <span data-ttu-id="f4475-109">任何`Object`变量或表达式。</span><span class="sxs-lookup"><span data-stu-id="f4475-109">Any `Object` variable or expression.</span></span>  
  
 `object2`  
 <span data-ttu-id="f4475-110">必需。</span><span class="sxs-lookup"><span data-stu-id="f4475-110">Required.</span></span> <span data-ttu-id="f4475-111">任何`Object`变量或表达式。</span><span class="sxs-lookup"><span data-stu-id="f4475-111">Any `Object` variable or expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f4475-112">备注</span><span class="sxs-lookup"><span data-stu-id="f4475-112">Remarks</span></span>  
 <span data-ttu-id="f4475-113">`IsNot`运算符确定两个对象引用是否引用不同的对象。</span><span class="sxs-lookup"><span data-stu-id="f4475-113">The `IsNot` operator determines if two object references refer to different objects.</span></span> <span data-ttu-id="f4475-114">但是，它不会执行值的比较。</span><span class="sxs-lookup"><span data-stu-id="f4475-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="f4475-115">如果`object1`并`object2`都是指完全相同的对象实例`result`是`False`; 如果不是这样，`result`是`True`。</span><span class="sxs-lookup"><span data-stu-id="f4475-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `False`; if they do not, `result` is `True`.</span></span>  
  
 <span data-ttu-id="f4475-116">`IsNot` 与完全相反`Is`运算符。</span><span class="sxs-lookup"><span data-stu-id="f4475-116">`IsNot` is the opposite of the `Is` operator.</span></span> <span data-ttu-id="f4475-117">利用`IsNot`是可以避免使用的笨拙语法`Not`和`Is`，这可能很难阅读。</span><span class="sxs-lookup"><span data-stu-id="f4475-117">The advantage of `IsNot` is that you can avoid awkward syntax with `Not` and `Is`, which can be difficult to read.</span></span>  
  
 <span data-ttu-id="f4475-118">可以使用`Is`和`IsNot`运算符来测试早期绑定和后期绑定对象。</span><span class="sxs-lookup"><span data-stu-id="f4475-118">You can use the `Is` and `IsNot` operators to test both early-bound and late-bound objects.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f4475-119">`IsNot`运算符不能用于比较表达式返回从`TypeOf`运算符。</span><span class="sxs-lookup"><span data-stu-id="f4475-119">The `IsNot` operator cannot be used to compare expressions returned from the `TypeOf` operator.</span></span> <span data-ttu-id="f4475-120">相反，必须使用`Not`和`Is`运算符。</span><span class="sxs-lookup"><span data-stu-id="f4475-120">Instead, you must use the `Not` and `Is` operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f4475-121">示例</span><span class="sxs-lookup"><span data-stu-id="f4475-121">Example</span></span>  
 <span data-ttu-id="f4475-122">下面的代码示例使用这两个`Is`运算符和`IsNot`运算符，以完成相同的比较。</span><span class="sxs-lookup"><span data-stu-id="f4475-122">The following code example uses both the `Is` operator and the `IsNot` operator to accomplish the same comparison.</span></span>  
  
 [!code-vb[VbVbalrOperators#29](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/isnot-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="f4475-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="f4475-123">See also</span></span>
- [<span data-ttu-id="f4475-124">Is 运算符</span><span class="sxs-lookup"><span data-stu-id="f4475-124">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)
- [<span data-ttu-id="f4475-125">TypeOf 运算符</span><span class="sxs-lookup"><span data-stu-id="f4475-125">TypeOf Operator</span></span>](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [<span data-ttu-id="f4475-126">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="f4475-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="f4475-127">如何：测试两个对象是否相同</span><span class="sxs-lookup"><span data-stu-id="f4475-127">How to: Test Whether Two Objects Are the Same</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
