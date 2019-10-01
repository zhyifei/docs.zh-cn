---
title: Is 运算符 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.is
helpviewer_keywords:
- comparison operators [Visual Basic]
- equivalent objects
- TypeOf...Is expression
- Is operator [Visual Basic]
ms.assetid: 8045a6c8-2a83-45b6-ad47-d09a704c656d
ms.openlocfilehash: 0351d224d9bf08a8f3ca74090de7b9c51c2c61bf
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701368"
---
# <a name="is-operator-visual-basic"></a><span data-ttu-id="10b71-102">Is 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="10b71-102">Is Operator (Visual Basic)</span></span>
<span data-ttu-id="10b71-103">比较两个对象引用变量。</span><span class="sxs-lookup"><span data-stu-id="10b71-103">Compares two object reference variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10b71-104">语法</span><span class="sxs-lookup"><span data-stu-id="10b71-104">Syntax</span></span>  
  
```vb  
result = object1 Is object2  
```  
  
## <a name="parts"></a><span data-ttu-id="10b71-105">部件</span><span class="sxs-lookup"><span data-stu-id="10b71-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="10b71-106">必需。</span><span class="sxs-lookup"><span data-stu-id="10b71-106">Required.</span></span> <span data-ttu-id="10b71-107">任何 @no__t 0 值。</span><span class="sxs-lookup"><span data-stu-id="10b71-107">Any `Boolean` value.</span></span>  
  
 `object1`  
 <span data-ttu-id="10b71-108">必需。</span><span class="sxs-lookup"><span data-stu-id="10b71-108">Required.</span></span> <span data-ttu-id="10b71-109">任何 @no__t 0 的名称。</span><span class="sxs-lookup"><span data-stu-id="10b71-109">Any `Object` name.</span></span>  
  
 `object2`  
 <span data-ttu-id="10b71-110">必需。</span><span class="sxs-lookup"><span data-stu-id="10b71-110">Required.</span></span> <span data-ttu-id="10b71-111">任何 @no__t 0 的名称。</span><span class="sxs-lookup"><span data-stu-id="10b71-111">Any `Object` name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="10b71-112">备注</span><span class="sxs-lookup"><span data-stu-id="10b71-112">Remarks</span></span>  
 <span data-ttu-id="10b71-113">@No__t-0 运算符确定两个对象引用是否引用同一对象。</span><span class="sxs-lookup"><span data-stu-id="10b71-113">The `Is` operator determines if two object references refer to the same object.</span></span> <span data-ttu-id="10b71-114">但是，它不会执行值比较。</span><span class="sxs-lookup"><span data-stu-id="10b71-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="10b71-115">如果 @no__t 0 和 `object2` 都引用完全相同的对象实例，`result` 为 `True`;否则，`result` `False`。</span><span class="sxs-lookup"><span data-stu-id="10b71-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `True`; if they do not, `result` is `False`.</span></span>  
  
 <span data-ttu-id="10b71-116">@no__t，还可以与 `TypeOf` 关键字一起使用，以生成 `TypeOf` ... `Is` 表达式，该表达式测试对象变量是否与数据类型兼容。</span><span class="sxs-lookup"><span data-stu-id="10b71-116">`Is` can also be used with the `TypeOf` keyword to make a `TypeOf`...`Is` expression, which tests whether an object variable is compatible with a data type.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="10b71-117">"Select ..." 中也使用了 @no__t 0 关键字[Case 语句](../../../visual-basic/language-reference/statements/select-case-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="10b71-117">The `Is` keyword is also used in the [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="10b71-118">示例</span><span class="sxs-lookup"><span data-stu-id="10b71-118">Example</span></span>  
 <span data-ttu-id="10b71-119">下面的示例使用 `Is` 运算符来比较对象引用对。</span><span class="sxs-lookup"><span data-stu-id="10b71-119">The following example uses the `Is` operator to compare pairs of object references.</span></span> <span data-ttu-id="10b71-120">结果分配给一个 @no__t 0 值，表示两个对象是否相同。</span><span class="sxs-lookup"><span data-stu-id="10b71-120">The results are assigned to a `Boolean` value representing whether the two objects are identical.</span></span>  
  
 [!code-vb[VbVbalrOperators#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#27)]  
  
 <span data-ttu-id="10b71-121">如前面的示例所示，可以使用 `Is` 运算符来测试早期绑定对象和后期绑定对象。</span><span class="sxs-lookup"><span data-stu-id="10b71-121">As the preceding example demonstrates, you can use the `Is` operator to test both early bound and late bound objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10b71-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="10b71-122">See also</span></span>

- [<span data-ttu-id="10b71-123">TypeOf 运算符</span><span class="sxs-lookup"><span data-stu-id="10b71-123">TypeOf Operator</span></span>](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [<span data-ttu-id="10b71-124">IsNot 运算符</span><span class="sxs-lookup"><span data-stu-id="10b71-124">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="10b71-125">Visual Basic 中的比较运算符</span><span class="sxs-lookup"><span data-stu-id="10b71-125">Comparison Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [<span data-ttu-id="10b71-126">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="10b71-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="10b71-127">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="10b71-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="10b71-128">运算符和表达式</span><span class="sxs-lookup"><span data-stu-id="10b71-128">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
