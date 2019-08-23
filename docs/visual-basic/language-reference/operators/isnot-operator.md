---
title: IsNot 运算符 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: 0a83b48e5e415bd6ca0c777cef6d34f7127691b5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966928"
---
# <a name="isnot-operator-visual-basic"></a><span data-ttu-id="034f1-102">IsNot 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="034f1-102">IsNot Operator (Visual Basic)</span></span>
<span data-ttu-id="034f1-103">比较两个对象引用变量。</span><span class="sxs-lookup"><span data-stu-id="034f1-103">Compares two object reference variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="034f1-104">语法</span><span class="sxs-lookup"><span data-stu-id="034f1-104">Syntax</span></span>  
  
```  
result = object1 IsNot object2  
```  
  
## <a name="parts"></a><span data-ttu-id="034f1-105">部件</span><span class="sxs-lookup"><span data-stu-id="034f1-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="034f1-106">必需。</span><span class="sxs-lookup"><span data-stu-id="034f1-106">Required.</span></span> <span data-ttu-id="034f1-107">一个 `Boolean` 值。</span><span class="sxs-lookup"><span data-stu-id="034f1-107">A `Boolean` value.</span></span>  
  
 `object1`  
 <span data-ttu-id="034f1-108">必需。</span><span class="sxs-lookup"><span data-stu-id="034f1-108">Required.</span></span> <span data-ttu-id="034f1-109">任何`Object`变量或表达式。</span><span class="sxs-lookup"><span data-stu-id="034f1-109">Any `Object` variable or expression.</span></span>  
  
 `object2`  
 <span data-ttu-id="034f1-110">必需。</span><span class="sxs-lookup"><span data-stu-id="034f1-110">Required.</span></span> <span data-ttu-id="034f1-111">任何`Object`变量或表达式。</span><span class="sxs-lookup"><span data-stu-id="034f1-111">Any `Object` variable or expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="034f1-112">备注</span><span class="sxs-lookup"><span data-stu-id="034f1-112">Remarks</span></span>  
 <span data-ttu-id="034f1-113">`IsNot`运算符确定两个对象引用是否引用不同的对象。</span><span class="sxs-lookup"><span data-stu-id="034f1-113">The `IsNot` operator determines if two object references refer to different objects.</span></span> <span data-ttu-id="034f1-114">但是, 它不会执行值比较。</span><span class="sxs-lookup"><span data-stu-id="034f1-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="034f1-115">如果`object1`和`False` `result` `result` `True`都引用完全相同的对象实例, 则为; 如果不是, 则为; 如果不是, 则为。 `object2`</span><span class="sxs-lookup"><span data-stu-id="034f1-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `False`; if they do not, `result` is `True`.</span></span>  
  
 <span data-ttu-id="034f1-116">`IsNot`与`Is`运算符相反。</span><span class="sxs-lookup"><span data-stu-id="034f1-116">`IsNot` is the opposite of the `Is` operator.</span></span> <span data-ttu-id="034f1-117">的`IsNot`优点是, 您可以避免使用`Not`和`Is`难以理解语法, 这会很难阅读。</span><span class="sxs-lookup"><span data-stu-id="034f1-117">The advantage of `IsNot` is that you can avoid awkward syntax with `Not` and `Is`, which can be difficult to read.</span></span>  
  
 <span data-ttu-id="034f1-118">您可以使用`Is`和`IsNot`运算符来测试早期绑定对象和后期绑定对象。</span><span class="sxs-lookup"><span data-stu-id="034f1-118">You can use the `Is` and `IsNot` operators to test both early-bound and late-bound objects.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="034f1-119">运算符不能用于比较从运算符返回的`TypeOf`表达式。 `IsNot`</span><span class="sxs-lookup"><span data-stu-id="034f1-119">The `IsNot` operator cannot be used to compare expressions returned from the `TypeOf` operator.</span></span> <span data-ttu-id="034f1-120">相反, 必须使用`Not`和`Is`运算符。</span><span class="sxs-lookup"><span data-stu-id="034f1-120">Instead, you must use the `Not` and `Is` operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="034f1-121">示例</span><span class="sxs-lookup"><span data-stu-id="034f1-121">Example</span></span>  
 <span data-ttu-id="034f1-122">下面的代码示例使用`Is`运算符`IsNot`和运算符来完成相同的比较。</span><span class="sxs-lookup"><span data-stu-id="034f1-122">The following code example uses both the `Is` operator and the `IsNot` operator to accomplish the same comparison.</span></span>  
  
 [!code-vb[VbVbalrOperators#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#29)]  
  
## <a name="see-also"></a><span data-ttu-id="034f1-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="034f1-123">See also</span></span>

- [<span data-ttu-id="034f1-124">Is 运算符</span><span class="sxs-lookup"><span data-stu-id="034f1-124">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)
- [<span data-ttu-id="034f1-125">TypeOf 运算符</span><span class="sxs-lookup"><span data-stu-id="034f1-125">TypeOf Operator</span></span>](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [<span data-ttu-id="034f1-126">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="034f1-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="034f1-127">如何：测试两个对象是否相同</span><span class="sxs-lookup"><span data-stu-id="034f1-127">How to: Test Whether Two Objects Are the Same</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
