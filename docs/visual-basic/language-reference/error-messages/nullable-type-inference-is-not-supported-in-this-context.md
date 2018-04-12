---
title: 该上下文中不支持可以为 null 的类型推理
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc36629
- bc36629
helpviewer_keywords:
- BC36629
ms.assetid: 0a1e2dbc-d9a4-433d-9306-c5540782b81d
caps.latest.revision: 5
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e7a5450d812260d3916296dff56abee27b3d586c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="nullable-type-inference-is-not-supported-in-this-context"></a><span data-ttu-id="73785-102">该上下文中不支持可以为 null 的类型推理</span><span class="sxs-lookup"><span data-stu-id="73785-102">Nullable type inference is not supported in this context</span></span>
<span data-ttu-id="73785-103">可以将值类型和结构声明可以为 null。</span><span class="sxs-lookup"><span data-stu-id="73785-103">Value types and structures can be declared nullable.</span></span>  
  
```vb  
Dim a? As Integer  
Dim b As Integer?  
```  
  
 <span data-ttu-id="73785-104">但是，不能与类型推理结合使用可以为 null 的声明。</span><span class="sxs-lookup"><span data-stu-id="73785-104">However, you cannot use the nullable declaration in combination with type inference.</span></span> <span data-ttu-id="73785-105">下面的示例会导致此错误。</span><span class="sxs-lookup"><span data-stu-id="73785-105">The following examples cause this error.</span></span>  
  
```vb  
' Not valid.  
' Dim c? = 10  
' Dim d? = a  
```  
  
 <span data-ttu-id="73785-106">**错误 ID:** BC36629</span><span class="sxs-lookup"><span data-stu-id="73785-106">**Error ID:** BC36629</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="73785-107">更正此错误</span><span class="sxs-lookup"><span data-stu-id="73785-107">To correct this error</span></span>  
  
-   <span data-ttu-id="73785-108">使用`As`子句来声明作为可以为 null 的变量。</span><span class="sxs-lookup"><span data-stu-id="73785-108">Use an `As` clause to declare the variable as nullable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73785-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="73785-109">See Also</span></span>  
 [<span data-ttu-id="73785-110">可以为 null 的值类型</span><span class="sxs-lookup"><span data-stu-id="73785-110">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)  
 [<span data-ttu-id="73785-111">局部类型推理</span><span class="sxs-lookup"><span data-stu-id="73785-111">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
