---
title: "IsNot 运算符 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.isnot
helpviewer_keywords: IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 969fdebdf15a1f779075c58616ccd16c64976a35
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="isnot-operator-visual-basic"></a><span data-ttu-id="314b9-102">IsNot 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="314b9-102">IsNot Operator (Visual Basic)</span></span>
<span data-ttu-id="314b9-103">比较两个对象引用变量。</span><span class="sxs-lookup"><span data-stu-id="314b9-103">Compares two object reference variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="314b9-104">语法</span><span class="sxs-lookup"><span data-stu-id="314b9-104">Syntax</span></span>  
  
```  
result = object1 IsNot object2  
```  
  
## <a name="parts"></a><span data-ttu-id="314b9-105">部件</span><span class="sxs-lookup"><span data-stu-id="314b9-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="314b9-106">必需。</span><span class="sxs-lookup"><span data-stu-id="314b9-106">Required.</span></span> <span data-ttu-id="314b9-107">一个 `Boolean` 值。</span><span class="sxs-lookup"><span data-stu-id="314b9-107">A `Boolean` value.</span></span>  
  
 `object1`  
 <span data-ttu-id="314b9-108">必需。</span><span class="sxs-lookup"><span data-stu-id="314b9-108">Required.</span></span> <span data-ttu-id="314b9-109">任何`Object`变量或表达式。</span><span class="sxs-lookup"><span data-stu-id="314b9-109">Any `Object` variable or expression.</span></span>  
  
 `object2`  
 <span data-ttu-id="314b9-110">必需。</span><span class="sxs-lookup"><span data-stu-id="314b9-110">Required.</span></span> <span data-ttu-id="314b9-111">任何`Object`变量或表达式。</span><span class="sxs-lookup"><span data-stu-id="314b9-111">Any `Object` variable or expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="314b9-112">备注</span><span class="sxs-lookup"><span data-stu-id="314b9-112">Remarks</span></span>  
 <span data-ttu-id="314b9-113">`IsNot`运算符确定两个对象引用是否引用不同的对象。</span><span class="sxs-lookup"><span data-stu-id="314b9-113">The `IsNot` operator determines if two object references refer to different objects.</span></span> <span data-ttu-id="314b9-114">但是，它不执行值的比较。</span><span class="sxs-lookup"><span data-stu-id="314b9-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="314b9-115">如果`object1`和`object2`都是指完全相同的对象实例，`result`是`False`; 如果不是这样，`result`是`True`。</span><span class="sxs-lookup"><span data-stu-id="314b9-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `False`; if they do not, `result` is `True`.</span></span>  
  
 <span data-ttu-id="314b9-116">`IsNot`截然相反`Is`运算符。</span><span class="sxs-lookup"><span data-stu-id="314b9-116">`IsNot` is the opposite of the `Is` operator.</span></span> <span data-ttu-id="314b9-117">利用`IsNot`是你可以避免繁琐语法与`Not`和`Is`，这可能很难读取。</span><span class="sxs-lookup"><span data-stu-id="314b9-117">The advantage of `IsNot` is that you can avoid awkward syntax with `Not` and `Is`, which can be difficult to read.</span></span>  
  
 <span data-ttu-id="314b9-118">你可以使用`Is`和`IsNot`运算符来测试早期绑定和后期绑定对象。</span><span class="sxs-lookup"><span data-stu-id="314b9-118">You can use the `Is` and `IsNot` operators to test both early-bound and late-bound objects.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="314b9-119">`IsNot`运算符不能用于比较表达式从返回`TypeOf`运算符。</span><span class="sxs-lookup"><span data-stu-id="314b9-119">The `IsNot` operator cannot be used to compare expressions returned from the `TypeOf` operator.</span></span> <span data-ttu-id="314b9-120">相反，你必须使用`Not`和`Is`运算符。</span><span class="sxs-lookup"><span data-stu-id="314b9-120">Instead, you must use the `Not` and `Is` operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="314b9-121">示例</span><span class="sxs-lookup"><span data-stu-id="314b9-121">Example</span></span>  
 <span data-ttu-id="314b9-122">下面的代码示例使用这两个`Is`运算符和`IsNot`运算符，以完成相同的比较。</span><span class="sxs-lookup"><span data-stu-id="314b9-122">The following code example uses both the `Is` operator and the `IsNot` operator to accomplish the same comparison.</span></span>  
  
 [!code-vb[VbVbalrOperators#29](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/isnot-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="314b9-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="314b9-123">See Also</span></span>  
 [<span data-ttu-id="314b9-124">Is 运算符</span><span class="sxs-lookup"><span data-stu-id="314b9-124">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)  
 [<span data-ttu-id="314b9-125">TypeOf 运算符</span><span class="sxs-lookup"><span data-stu-id="314b9-125">TypeOf Operator</span></span>](../../../visual-basic/language-reference/operators/typeof-operator.md)  
 [<span data-ttu-id="314b9-126">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="314b9-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="314b9-127">如何：测试两个对象是否相同</span><span class="sxs-lookup"><span data-stu-id="314b9-127">How to: Test Whether Two Objects Are the Same</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
