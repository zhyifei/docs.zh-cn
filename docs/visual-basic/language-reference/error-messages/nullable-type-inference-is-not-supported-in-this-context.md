---
title: 该上下文中不支持可以为 null 的类型推理
ms.date: 07/20/2015
f1_keywords:
- vbc36629
- bc36629
helpviewer_keywords:
- BC36629
ms.assetid: 0a1e2dbc-d9a4-433d-9306-c5540782b81d
ms.openlocfilehash: 9f7f878649d8b96f050b56d5b878eb3d67e027ff
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58819237"
---
# <a name="nullable-type-inference-is-not-supported-in-this-context"></a><span data-ttu-id="1027a-102">该上下文中不支持可以为 null 的类型推理</span><span class="sxs-lookup"><span data-stu-id="1027a-102">Nullable type inference is not supported in this context</span></span>
<span data-ttu-id="1027a-103">值类型和结构可以声明可以为 null。</span><span class="sxs-lookup"><span data-stu-id="1027a-103">Value types and structures can be declared nullable.</span></span>  
  
```vb  
Dim a? As Integer  
Dim b As Integer?  
```  
  
 <span data-ttu-id="1027a-104">但是，不能与类型推断结合使用可以为 null 的声明。</span><span class="sxs-lookup"><span data-stu-id="1027a-104">However, you cannot use the nullable declaration in combination with type inference.</span></span> <span data-ttu-id="1027a-105">下面的示例会导致此错误。</span><span class="sxs-lookup"><span data-stu-id="1027a-105">The following examples cause this error.</span></span>  
  
```vb  
' Not valid.  
' Dim c? = 10  
' Dim d? = a  
```  
  
 <span data-ttu-id="1027a-106">**错误 ID:** BC36629</span><span class="sxs-lookup"><span data-stu-id="1027a-106">**Error ID:** BC36629</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1027a-107">更正此错误</span><span class="sxs-lookup"><span data-stu-id="1027a-107">To correct this error</span></span>  
  
-   <span data-ttu-id="1027a-108">使用`As`子句，以将变量声明为可以为 null。</span><span class="sxs-lookup"><span data-stu-id="1027a-108">Use an `As` clause to declare the variable as nullable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1027a-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="1027a-109">See also</span></span>

- [<span data-ttu-id="1027a-110">可以为 null 的值类型</span><span class="sxs-lookup"><span data-stu-id="1027a-110">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="1027a-111">局部类型推理</span><span class="sxs-lookup"><span data-stu-id="1027a-111">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
