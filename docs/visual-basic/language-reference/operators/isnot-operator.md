---
title: IsNot 运算符 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: 7e1ac1004e671f592c03bd44ee7ec2e8cc572933
ms.sourcegitcommit: 8b8dd14dde727026fd0b6ead1ec1df2e9d747a48
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/27/2019
ms.locfileid: "71331629"
---
# <a name="isnot-operator-visual-basic"></a><span data-ttu-id="789db-102">IsNot 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="789db-102">IsNot Operator (Visual Basic)</span></span>
<span data-ttu-id="789db-103">比较两个对象引用变量。</span><span class="sxs-lookup"><span data-stu-id="789db-103">Compares two object reference variables.</span></span>

## <a name="syntax"></a><span data-ttu-id="789db-104">语法</span><span class="sxs-lookup"><span data-stu-id="789db-104">Syntax</span></span>

```vb
result = object1 IsNot object2
```

## <a name="parts"></a><span data-ttu-id="789db-105">部件</span><span class="sxs-lookup"><span data-stu-id="789db-105">Parts</span></span>
 <span data-ttu-id="789db-106">`result`（必需）。</span><span class="sxs-lookup"><span data-stu-id="789db-106">`result` Required.</span></span> <span data-ttu-id="789db-107">一个 `Boolean` 值。</span><span class="sxs-lookup"><span data-stu-id="789db-107">A `Boolean` value.</span></span>

 <span data-ttu-id="789db-108">`object1`（必需）。</span><span class="sxs-lookup"><span data-stu-id="789db-108">`object1` Required.</span></span> <span data-ttu-id="789db-109">任何 @no__t 的变量或表达式。</span><span class="sxs-lookup"><span data-stu-id="789db-109">Any `Object` variable or expression.</span></span>

 <span data-ttu-id="789db-110">`object2`（必需）。</span><span class="sxs-lookup"><span data-stu-id="789db-110">`object2` Required.</span></span> <span data-ttu-id="789db-111">任何 @no__t 的变量或表达式。</span><span class="sxs-lookup"><span data-stu-id="789db-111">Any `Object` variable or expression.</span></span>

## <a name="remarks"></a><span data-ttu-id="789db-112">备注</span><span class="sxs-lookup"><span data-stu-id="789db-112">Remarks</span></span>
 <span data-ttu-id="789db-113">@No__t-0 运算符确定两个对象引用是否引用不同的对象。</span><span class="sxs-lookup"><span data-stu-id="789db-113">The `IsNot` operator determines if two object references refer to different objects.</span></span> <span data-ttu-id="789db-114">但是，它不会执行值比较。</span><span class="sxs-lookup"><span data-stu-id="789db-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="789db-115">如果 @no__t 0 和 `object2` 都引用完全相同的对象实例，`result` 为 `False`;否则，`result` `True`。</span><span class="sxs-lookup"><span data-stu-id="789db-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `False`; if they do not, `result` is `True`.</span></span>

 <span data-ttu-id="789db-116">@no__t 为 `Is` 运算符。</span><span class="sxs-lookup"><span data-stu-id="789db-116">`IsNot` is the opposite of the `Is` operator.</span></span> <span data-ttu-id="789db-117">@No__t-0 的优点是你可以避免使用 `Not` 和 `Is` 的语法，这可能会很难阅读。</span><span class="sxs-lookup"><span data-stu-id="789db-117">The advantage of `IsNot` is that you can avoid awkward syntax with `Not` and `Is`, which can be difficult to read.</span></span>

 <span data-ttu-id="789db-118">您可以使用 @no__t 0 和 `IsNot` 运算符来测试早期绑定对象和后期绑定对象。</span><span class="sxs-lookup"><span data-stu-id="789db-118">You can use the `Is` and `IsNot` operators to test both early-bound and late-bound objects.</span></span>

## <a name="example"></a><span data-ttu-id="789db-119">示例</span><span class="sxs-lookup"><span data-stu-id="789db-119">Example</span></span>
 <span data-ttu-id="789db-120">下面的代码示例使用 `Is` 运算符和 `IsNot` 运算符来完成相同的比较。</span><span class="sxs-lookup"><span data-stu-id="789db-120">The following code example uses both the `Is` operator and the `IsNot` operator to accomplish the same comparison.</span></span>

 [!code-vb[VbVbalrOperators#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#29)]

## <a name="see-also"></a><span data-ttu-id="789db-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="789db-121">See also</span></span>

- [<span data-ttu-id="789db-122">Is 运算符</span><span class="sxs-lookup"><span data-stu-id="789db-122">Is Operator</span></span>](is-operator.md)
- [<span data-ttu-id="789db-123">TypeOf 运算符</span><span class="sxs-lookup"><span data-stu-id="789db-123">TypeOf Operator</span></span>](typeof-operator.md)
- [<span data-ttu-id="789db-124">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="789db-124">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- <span data-ttu-id="789db-125">[如何：测试两个对象是否相同 @ no__t-0</span><span class="sxs-lookup"><span data-stu-id="789db-125">[How to: Test Whether Two Objects Are the Same](../../programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)</span></span>
