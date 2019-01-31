---
title: “Declare”语句中不支持“As Any”
ms.date: 07/20/2015
f1_keywords:
- bc30828
- vbc30828
helpviewer_keywords:
- BC30828
ms.assetid: 7e5cf519-8b64-4ac5-8116-705fe26c846d
ms.openlocfilehash: bdf339e0d91106a6d6527e085608a06b0439951c
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55274074"
---
# <a name="as-any-is-not-supported-in-declare-statements"></a><span data-ttu-id="991c2-102">“Declare”语句中不支持“As Any”</span><span class="sxs-lookup"><span data-stu-id="991c2-102">'As Any' is not supported in 'Declare' statements</span></span>
<span data-ttu-id="991c2-103">`Any`数据类型用于`Declare`Visual Basic 6.0 和早期版本，以允许使用自变量，可以包含任何类型的数据中的语句。</span><span class="sxs-lookup"><span data-stu-id="991c2-103">The `Any` data type was used with `Declare` statements in Visual Basic 6.0 and earlier versions to permit the use of arguments that could contain any type of data.</span></span> <span data-ttu-id="991c2-104">Visual Basic 支持重载，但是，也因此使得`Any`数据类型已过时。</span><span class="sxs-lookup"><span data-stu-id="991c2-104">Visual Basic supports overloading, however, and so makes the `Any` data type obsolete.</span></span>  
  
 <span data-ttu-id="991c2-105">**错误 ID:** BC30828</span><span class="sxs-lookup"><span data-stu-id="991c2-105">**Error ID:** BC30828</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="991c2-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="991c2-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="991c2-107">声明你想要使用; 特定类型的参数有关示例。</span><span class="sxs-lookup"><span data-stu-id="991c2-107">Declare parameters of the specific type you want to use; for example.</span></span>  
  
     [!code-vb[VbVbalrStatements#95](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/as-any-is-not-supported-in-declare-statements_1.vb)]  
  
2.  <span data-ttu-id="991c2-108">使用<xref:System.Runtime.InteropServices.MarshalAsAttribute>属性指定`As Any`时`Void*`预期由被调用的过程。</span><span class="sxs-lookup"><span data-stu-id="991c2-108">Use the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute to specify `As Any` when `Void*` is expected by the procedure being called.</span></span>  
  
     [!code-vb[VbVbalrStatements#96](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/as-any-is-not-supported-in-declare-statements_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="991c2-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="991c2-109">See also</span></span>
- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="991c2-110">演练：调用 Windows API</span><span class="sxs-lookup"><span data-stu-id="991c2-110">Walkthrough: Calling Windows APIs</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
- [<span data-ttu-id="991c2-111">Declare 语句</span><span class="sxs-lookup"><span data-stu-id="991c2-111">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
- [<span data-ttu-id="991c2-112">在托管代码中创建原型</span><span class="sxs-lookup"><span data-stu-id="991c2-112">Creating Prototypes in Managed Code</span></span>](../../../framework/interop/creating-prototypes-in-managed-code.md)
