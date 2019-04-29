---
title: Widening (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.widening
helpviewer_keywords:
- conversions [Visual Basic], type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- Widening keyword [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: 646ae263-94d3-40a2-b0cc-64f619292f56
ms.openlocfilehash: d7d43d4f5f931881d5c8b663c719fe7f92559799
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61778659"
---
# <a name="widening-visual-basic"></a><span data-ttu-id="c6e06-102">Widening (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c6e06-102">Widening (Visual Basic)</span></span>
<span data-ttu-id="c6e06-103">指示转换运算符 (`CType`) 将类或结构转换为可以保存原始类或结构的所有可能的值的类型。</span><span class="sxs-lookup"><span data-stu-id="c6e06-103">Indicates that a conversion operator (`CType`) converts a class or structure to a type that can hold all possible values of the original class or structure.</span></span>  
  
## <a name="converting-with-the-widening-keyword"></a><span data-ttu-id="c6e06-104">转换使用扩大关键字</span><span class="sxs-lookup"><span data-stu-id="c6e06-104">Converting with the Widening Keyword</span></span>  
 <span data-ttu-id="c6e06-105">转换过程都必须指定`Public Shared`除了`Widening`。</span><span class="sxs-lookup"><span data-stu-id="c6e06-105">The conversion procedure must specify `Public Shared` in addition to `Widening`.</span></span>  
  
 <span data-ttu-id="c6e06-106">扩大转换在运行时始终成功，并且永远不会导致数据丢失。</span><span class="sxs-lookup"><span data-stu-id="c6e06-106">Widening conversions always succeed at run time and never incur data loss.</span></span> <span data-ttu-id="c6e06-107">示例包括`Single`到`Double`，`Char`到`String`，并为其基类型的派生的类型。</span><span class="sxs-lookup"><span data-stu-id="c6e06-107">Examples are `Single` to `Double`, `Char` to `String`, and a derived type to its base type.</span></span> <span data-ttu-id="c6e06-108">最后一个转换扩大转换，因为所派生的类型包含基类型的所有成员，因此基类型的实例。</span><span class="sxs-lookup"><span data-stu-id="c6e06-108">This last conversion is widening because the derived type contains all the members of the base type and thus is an instance of the base type.</span></span>  
  
 <span data-ttu-id="c6e06-109">使用代码无需使用`CType`进行扩大转换，即使`Option Strict`是`On`。</span><span class="sxs-lookup"><span data-stu-id="c6e06-109">The consuming code does not have to use `CType` for widening conversions, even if `Option Strict` is `On`.</span></span>  
  
 <span data-ttu-id="c6e06-110">`Widening`关键字可在此上下文中：</span><span class="sxs-lookup"><span data-stu-id="c6e06-110">The `Widening` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="c6e06-111">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="c6e06-111">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 <span data-ttu-id="c6e06-112">有关示例请参阅的扩大转换和收缩转换运算符定义[如何：定义转换运算符](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="c6e06-112">For example definitions of widening and narrowing conversion operators, see [How to: Define a Conversion Operator](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6e06-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="c6e06-113">See also</span></span>

- [<span data-ttu-id="c6e06-114">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="c6e06-114">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="c6e06-115">Narrowing</span><span class="sxs-lookup"><span data-stu-id="c6e06-115">Narrowing</span></span>](../../../visual-basic/language-reference/modifiers/narrowing.md)
- [<span data-ttu-id="c6e06-116">扩大转换和收缩转换</span><span class="sxs-lookup"><span data-stu-id="c6e06-116">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="c6e06-117">如何：定义运算符</span><span class="sxs-lookup"><span data-stu-id="c6e06-117">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="c6e06-118">CType 函数</span><span class="sxs-lookup"><span data-stu-id="c6e06-118">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)
- [<span data-ttu-id="c6e06-119">Option Strict 语句</span><span class="sxs-lookup"><span data-stu-id="c6e06-119">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="c6e06-120">如何：定义转换运算符</span><span class="sxs-lookup"><span data-stu-id="c6e06-120">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
