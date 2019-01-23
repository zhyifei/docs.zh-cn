---
title: 该上下文中不支持可以为 null 的类型推理
ms.date: 07/20/2015
f1_keywords:
- vbc36629
- bc36629
helpviewer_keywords:
- BC36629
ms.assetid: 0a1e2dbc-d9a4-433d-9306-c5540782b81d
ms.openlocfilehash: 7dffc5233656257cd892f573a2f8b9f91d781c21
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54611886"
---
# <a name="nullable-type-inference-is-not-supported-in-this-context"></a><span data-ttu-id="07afe-102">该上下文中不支持可以为 null 的类型推理</span><span class="sxs-lookup"><span data-stu-id="07afe-102">Nullable type inference is not supported in this context</span></span>
<span data-ttu-id="07afe-103">值类型和结构可以声明可以为 null。</span><span class="sxs-lookup"><span data-stu-id="07afe-103">Value types and structures can be declared nullable.</span></span>  
  
```vb  
Dim a? As Integer  
Dim b As Integer?  
```  
  
 <span data-ttu-id="07afe-104">但是，不能与类型推断结合使用可以为 null 的声明。</span><span class="sxs-lookup"><span data-stu-id="07afe-104">However, you cannot use the nullable declaration in combination with type inference.</span></span> <span data-ttu-id="07afe-105">下面的示例会导致此错误。</span><span class="sxs-lookup"><span data-stu-id="07afe-105">The following examples cause this error.</span></span>  
  
```vb  
' Not valid.  
' Dim c? = 10  
' Dim d? = a  
```  
  
 <span data-ttu-id="07afe-106">**错误 ID:** BC36629</span><span class="sxs-lookup"><span data-stu-id="07afe-106">**Error ID:** BC36629</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="07afe-107">更正此错误</span><span class="sxs-lookup"><span data-stu-id="07afe-107">To correct this error</span></span>  
  
-   <span data-ttu-id="07afe-108">使用`As`子句，以将变量声明为可以为 null。</span><span class="sxs-lookup"><span data-stu-id="07afe-108">Use an `As` clause to declare the variable as nullable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07afe-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="07afe-109">See also</span></span>
- [<span data-ttu-id="07afe-110">可以为 null 的值类型</span><span class="sxs-lookup"><span data-stu-id="07afe-110">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="07afe-111">局部类型推理</span><span class="sxs-lookup"><span data-stu-id="07afe-111">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
