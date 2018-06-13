---
title: 序号无效
ms.date: 07/20/2015
f1_keywords:
- vbrID452
ms.assetid: 7459562b-cd4f-4590-95e0-6126ae3589a5
ms.openlocfilehash: 12d73b33e3c025b40c98d84e3507af7be1e1e91a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33593598"
---
# <a name="ordinal-is-not-valid"></a><span data-ttu-id="68818-102">序号无效</span><span class="sxs-lookup"><span data-stu-id="68818-102">Ordinal is not valid</span></span>
<span data-ttu-id="68818-103">对动态链接库 (DLL) 的调用指示而不是过程名称，后面使用一个数字使用`#num`语法。</span><span class="sxs-lookup"><span data-stu-id="68818-103">Your call to a dynamic-link library (DLL) indicated to use a number instead of a procedure name, using the `#num` syntax.</span></span> <span data-ttu-id="68818-104">此错误具有以下可能的原因：</span><span class="sxs-lookup"><span data-stu-id="68818-104">This error has the following possible causes:</span></span>  
  
-   <span data-ttu-id="68818-105">尝试转换`#num`为序号失败的表达式。</span><span class="sxs-lookup"><span data-stu-id="68818-105">An attempt to convert the `#num` expression to an ordinal failed.</span></span>  
  
-   <span data-ttu-id="68818-106">`#num`指定 DLL 中未指定任何函数。</span><span class="sxs-lookup"><span data-stu-id="68818-106">The `#num` specified does not specify any function in the DLL.</span></span>  
  
-   <span data-ttu-id="68818-107">类型库中有一个无效的声明，从而导致无效的序号在内部使用。</span><span class="sxs-lookup"><span data-stu-id="68818-107">A type library has an invalid declaration resulting in internal use of an invalid ordinal number.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="68818-108">更正此错误</span><span class="sxs-lookup"><span data-stu-id="68818-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="68818-109">请确保表达式表示一个有效的数字，或者按名称调用的过程。</span><span class="sxs-lookup"><span data-stu-id="68818-109">Make sure the expression represents a valid number, or call the procedure by name.</span></span>  
  
2.  <span data-ttu-id="68818-110">请确保`#num`标识 DLL 中的有效函数。</span><span class="sxs-lookup"><span data-stu-id="68818-110">Make sure `#num` identifies a valid function in the DLL.</span></span>  
  
3.  <span data-ttu-id="68818-111">隔离导致问题的注释掉的代码的过程调用。</span><span class="sxs-lookup"><span data-stu-id="68818-111">Isolate the procedure call causing the problem by commenting out the code.</span></span> <span data-ttu-id="68818-112">编写`Declare`语句的过程中和报表的问题类型库供应商联系。</span><span class="sxs-lookup"><span data-stu-id="68818-112">Write a `Declare` statement for the procedure, and report the problem to the type library vendor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68818-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="68818-113">See Also</span></span>  
 [<span data-ttu-id="68818-114">Declare 语句</span><span class="sxs-lookup"><span data-stu-id="68818-114">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
