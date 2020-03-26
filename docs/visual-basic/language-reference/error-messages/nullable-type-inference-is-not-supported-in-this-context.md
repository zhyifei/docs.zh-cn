---
title: 该上下文中不支持可以为 null 的类型推理
ms.date: 07/20/2015
f1_keywords:
- vbc36629
- bc36629
helpviewer_keywords:
- BC36629
ms.assetid: 0a1e2dbc-d9a4-433d-9306-c5540782b81d
ms.openlocfilehash: 42bde0b1843e52bbc16118bb056ade791591904e
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249495"
---
# <a name="nullable-type-inference-is-not-supported-in-this-context"></a><span data-ttu-id="4a711-102">该上下文中不支持可以为 null 的类型推理</span><span class="sxs-lookup"><span data-stu-id="4a711-102">Nullable type inference is not supported in this context</span></span>
<span data-ttu-id="4a711-103">值类型和结构可以声明为空。</span><span class="sxs-lookup"><span data-stu-id="4a711-103">Value types and structures can be declared nullable.</span></span>  
  
```vb  
Dim a? As Integer  
Dim b As Integer?  
```  
  
 <span data-ttu-id="4a711-104">但是，不能将可无效声明与类型推理结合使用。</span><span class="sxs-lookup"><span data-stu-id="4a711-104">However, you cannot use the nullable declaration in combination with type inference.</span></span> <span data-ttu-id="4a711-105">以下示例导致此错误。</span><span class="sxs-lookup"><span data-stu-id="4a711-105">The following examples cause this error.</span></span>  
  
```vb  
' Not valid.  
' Dim c? = 10  
' Dim d? = a  
```  
  
 <span data-ttu-id="4a711-106">**错误 ID：** BC36629</span><span class="sxs-lookup"><span data-stu-id="4a711-106">**Error ID:** BC36629</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4a711-107">更正此错误</span><span class="sxs-lookup"><span data-stu-id="4a711-107">To correct this error</span></span>  
  
- <span data-ttu-id="4a711-108">使用`As`子句将变量声明为空值类型。</span><span class="sxs-lookup"><span data-stu-id="4a711-108">Use an `As` clause to declare the variable as a nullable value type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a711-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="4a711-109">See also</span></span>

- [<span data-ttu-id="4a711-110">可以为 null 的值类型</span><span class="sxs-lookup"><span data-stu-id="4a711-110">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="4a711-111">局部类型推理</span><span class="sxs-lookup"><span data-stu-id="4a711-111">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
