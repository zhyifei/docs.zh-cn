---
title: Narrowing (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.narrowing
helpviewer_keywords:
- conversions [Visual Basic], type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- Narrowing keyword [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: a207ee91-aca4-4771-b4e2-713f029bf2bb
ms.openlocfilehash: eb5f021371291483b8eb2a13727a9fda94540638
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "58838841"
---
# <a name="narrowing-visual-basic"></a><span data-ttu-id="67aa0-102">Narrowing (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="67aa0-102">Narrowing (Visual Basic)</span></span>
<span data-ttu-id="67aa0-103">指示转换运算符 (`CType`) 将类或结构转换为可能无法保存某些原始类或结构的可能值的类型。</span><span class="sxs-lookup"><span data-stu-id="67aa0-103">Indicates that a conversion operator (`CType`) converts a class or structure to a type that might not be able to hold some of the possible values of the original class or structure.</span></span>  
  
## <a name="converting-with-the-narrowing-keyword"></a><span data-ttu-id="67aa0-104">转换与收缩关键字</span><span class="sxs-lookup"><span data-stu-id="67aa0-104">Converting with the Narrowing Keyword</span></span>  
 <span data-ttu-id="67aa0-105">转换过程都必须指定`Public Shared`除了`Narrowing`。</span><span class="sxs-lookup"><span data-stu-id="67aa0-105">The conversion procedure must specify `Public Shared` in addition to `Narrowing`.</span></span>  
  
 <span data-ttu-id="67aa0-106">收缩转换执行不总是在运行时，成功和可以故障或会导致数据丢失。</span><span class="sxs-lookup"><span data-stu-id="67aa0-106">Narrowing conversions do not always succeed at run time, and can fail or incur data loss.</span></span> <span data-ttu-id="67aa0-107">示例包括`Long`到`Integer`，`String`到`Date`，并为派生类型的基类型。</span><span class="sxs-lookup"><span data-stu-id="67aa0-107">Examples are `Long` to `Integer`, `String` to `Date`, and a base type to a derived type.</span></span> <span data-ttu-id="67aa0-108">最后一个转换收缩转换，因为基类型可能不包含派生类型的所有成员，因此不是派生类型的实例。</span><span class="sxs-lookup"><span data-stu-id="67aa0-108">This last conversion is narrowing because the base type might not contain all the members of the derived type and thus is not an instance of the derived type.</span></span>  
  
 <span data-ttu-id="67aa0-109">如果`Option Strict`是`On`，则使用代码必须使用`CType`收缩的所有转换。</span><span class="sxs-lookup"><span data-stu-id="67aa0-109">If `Option Strict` is `On`, the consuming code must use `CType` for all narrowing conversions.</span></span>  
  
 <span data-ttu-id="67aa0-110">`Narrowing`关键字可在此上下文中：</span><span class="sxs-lookup"><span data-stu-id="67aa0-110">The `Narrowing` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="67aa0-111">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="67aa0-111">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="67aa0-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="67aa0-112">See also</span></span>

- [<span data-ttu-id="67aa0-113">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="67aa0-113">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="67aa0-114">Widening</span><span class="sxs-lookup"><span data-stu-id="67aa0-114">Widening</span></span>](../../../visual-basic/language-reference/modifiers/widening.md)
- [<span data-ttu-id="67aa0-115">扩大转换和收缩转换</span><span class="sxs-lookup"><span data-stu-id="67aa0-115">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="67aa0-116">如何：定义运算符</span><span class="sxs-lookup"><span data-stu-id="67aa0-116">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="67aa0-117">CType 函数</span><span class="sxs-lookup"><span data-stu-id="67aa0-117">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)
- [<span data-ttu-id="67aa0-118">Option Strict 语句</span><span class="sxs-lookup"><span data-stu-id="67aa0-118">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
