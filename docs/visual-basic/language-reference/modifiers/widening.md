---
title: Widening
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
ms.openlocfilehash: 1c9aa78549ca6e41c9fe54c12e0aaec8e7cc30cb
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347834"
---
# <a name="widening-visual-basic"></a><span data-ttu-id="935fa-102">Widening (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="935fa-102">Widening (Visual Basic)</span></span>
<span data-ttu-id="935fa-103">指示转换运算符（`CType`）将类或结构转换为可以保存原始类或结构的所有可能值的类型。</span><span class="sxs-lookup"><span data-stu-id="935fa-103">Indicates that a conversion operator (`CType`) converts a class or structure to a type that can hold all possible values of the original class or structure.</span></span>  
  
## <a name="converting-with-the-widening-keyword"></a><span data-ttu-id="935fa-104">用扩大关键字转换</span><span class="sxs-lookup"><span data-stu-id="935fa-104">Converting with the Widening Keyword</span></span>  
 <span data-ttu-id="935fa-105">除 `Widening`之外，转换过程必须指定 `Public Shared`。</span><span class="sxs-lookup"><span data-stu-id="935fa-105">The conversion procedure must specify `Public Shared` in addition to `Widening`.</span></span>  
  
 <span data-ttu-id="935fa-106">扩大转换始终会在运行时成功，不会导致数据丢失。</span><span class="sxs-lookup"><span data-stu-id="935fa-106">Widening conversions always succeed at run time and never incur data loss.</span></span> <span data-ttu-id="935fa-107">示例 `Single` `Double`，`Char` `String`，并将派生类型为其基类型。</span><span class="sxs-lookup"><span data-stu-id="935fa-107">Examples are `Single` to `Double`, `Char` to `String`, and a derived type to its base type.</span></span> <span data-ttu-id="935fa-108">由于派生类型包含基类型的所有成员，因此是最新的转换，因此是基类型的实例。</span><span class="sxs-lookup"><span data-stu-id="935fa-108">This last conversion is widening because the derived type contains all the members of the base type and thus is an instance of the base type.</span></span>  
  
 <span data-ttu-id="935fa-109">使用代码不必使用 `CType` 进行扩大转换，即使 `On``Option Strict` 也是如此。</span><span class="sxs-lookup"><span data-stu-id="935fa-109">The consuming code does not have to use `CType` for widening conversions, even if `Option Strict` is `On`.</span></span>  
  
 <span data-ttu-id="935fa-110">可以在此上下文中使用 `Widening` 关键字：</span><span class="sxs-lookup"><span data-stu-id="935fa-110">The `Widening` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="935fa-111">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="935fa-111">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 <span data-ttu-id="935fa-112">有关扩展和收缩转换运算符的定义示例，请参阅[如何：定义转换运算符](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="935fa-112">For example definitions of widening and narrowing conversion operators, see [How to: Define a Conversion Operator](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="935fa-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="935fa-113">See also</span></span>

- [<span data-ttu-id="935fa-114">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="935fa-114">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="935fa-115">Narrowing</span><span class="sxs-lookup"><span data-stu-id="935fa-115">Narrowing</span></span>](../../../visual-basic/language-reference/modifiers/narrowing.md)
- [<span data-ttu-id="935fa-116">扩大转换和收缩转换</span><span class="sxs-lookup"><span data-stu-id="935fa-116">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="935fa-117">如何：定义运算符</span><span class="sxs-lookup"><span data-stu-id="935fa-117">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="935fa-118">CType Function</span><span class="sxs-lookup"><span data-stu-id="935fa-118">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)
- [<span data-ttu-id="935fa-119">Option Strict 语句</span><span class="sxs-lookup"><span data-stu-id="935fa-119">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="935fa-120">如何：定义转换运算符</span><span class="sxs-lookup"><span data-stu-id="935fa-120">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
