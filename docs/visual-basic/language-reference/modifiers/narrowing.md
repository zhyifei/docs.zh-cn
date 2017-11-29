---
title: Narrowing (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.narrowing
helpviewer_keywords:
- conversions [Visual Basic], type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- Narrowing keyword [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: a207ee91-aca4-4771-b4e2-713f029bf2bb
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 50116c6212e919d4b9b35fc933d80dee14bd4ecf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="narrowing-visual-basic"></a><span data-ttu-id="1cb66-102">Narrowing (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1cb66-102">Narrowing (Visual Basic)</span></span>
<span data-ttu-id="1cb66-103">指示转换运算符 (`CType`) 将一个类或结构转换为可能无法保存某些可能的值的原始类或结构类型。</span><span class="sxs-lookup"><span data-stu-id="1cb66-103">Indicates that a conversion operator (`CType`) converts a class or structure to a type that might not be able to hold some of the possible values of the original class or structure.</span></span>  
  
## <a name="converting-with-the-narrowing-keyword"></a><span data-ttu-id="1cb66-104">转换使用收缩关键字</span><span class="sxs-lookup"><span data-stu-id="1cb66-104">Converting with the Narrowing Keyword</span></span>  
 <span data-ttu-id="1cb66-105">必须指定转换过程`Public Shared`除了`Narrowing`。</span><span class="sxs-lookup"><span data-stu-id="1cb66-105">The conversion procedure must specify `Public Shared` in addition to `Narrowing`.</span></span>  
  
 <span data-ttu-id="1cb66-106">收缩转换执行并非总是在运行时，成功，失败或导致数据丢失。</span><span class="sxs-lookup"><span data-stu-id="1cb66-106">Narrowing conversions do not always succeed at run time, and can fail or incur data loss.</span></span> <span data-ttu-id="1cb66-107">示例包括`Long`到`Integer`，`String`到`Date`，以及从基类型转换为派生类型。</span><span class="sxs-lookup"><span data-stu-id="1cb66-107">Examples are `Long` to `Integer`, `String` to `Date`, and a base type to a derived type.</span></span> <span data-ttu-id="1cb66-108">最后一个转换收缩转换，因为基类型可能不包含派生类型的所有成员，因此不是派生类型的实例。</span><span class="sxs-lookup"><span data-stu-id="1cb66-108">This last conversion is narrowing because the base type might not contain all the members of the derived type and thus is not an instance of the derived type.</span></span>  
  
 <span data-ttu-id="1cb66-109">如果`Option Strict`是`On`，则使用代码必须使用`CType`针对所有收缩转换。</span><span class="sxs-lookup"><span data-stu-id="1cb66-109">If `Option Strict` is `On`, the consuming code must use `CType` for all narrowing conversions.</span></span>  
  
 <span data-ttu-id="1cb66-110">`Narrowing`关键字可在此上下文中：</span><span class="sxs-lookup"><span data-stu-id="1cb66-110">The `Narrowing` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="1cb66-111">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="1cb66-111">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="1cb66-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1cb66-112">See Also</span></span>  
 [<span data-ttu-id="1cb66-113">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="1cb66-113">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [<span data-ttu-id="1cb66-114">Widening</span><span class="sxs-lookup"><span data-stu-id="1cb66-114">Widening</span></span>](../../../visual-basic/language-reference/modifiers/widening.md)  
 [<span data-ttu-id="1cb66-115">扩大转换和收缩转换</span><span class="sxs-lookup"><span data-stu-id="1cb66-115">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [<span data-ttu-id="1cb66-116">如何：定义运算符</span><span class="sxs-lookup"><span data-stu-id="1cb66-116">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [<span data-ttu-id="1cb66-117">CType 函数</span><span class="sxs-lookup"><span data-stu-id="1cb66-117">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)  
 [<span data-ttu-id="1cb66-118">Option Strict 语句</span><span class="sxs-lookup"><span data-stu-id="1cb66-118">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
