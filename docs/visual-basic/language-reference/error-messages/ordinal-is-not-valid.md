---
title: 序号无效
ms.date: 07/20/2015
f1_keywords:
- vbrID452
ms.assetid: 7459562b-cd4f-4590-95e0-6126ae3589a5
ms.openlocfilehash: 740243c744a7ba5391659894812a00d80555fd80
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64665669"
---
# <a name="ordinal-is-not-valid"></a><span data-ttu-id="25a83-102">序号无效</span><span class="sxs-lookup"><span data-stu-id="25a83-102">Ordinal is not valid</span></span>
<span data-ttu-id="25a83-103">对动态链接库 (DLL) 的调用指示应使用数字而不是过程名称，是使用`#num`语法。</span><span class="sxs-lookup"><span data-stu-id="25a83-103">Your call to a dynamic-link library (DLL) indicated to use a number instead of a procedure name, using the `#num` syntax.</span></span> <span data-ttu-id="25a83-104">此错误具有以下可能的原因：</span><span class="sxs-lookup"><span data-stu-id="25a83-104">This error has the following possible causes:</span></span>  
  
- <span data-ttu-id="25a83-105">尝试将转换`#num`为序号失败的表达式。</span><span class="sxs-lookup"><span data-stu-id="25a83-105">An attempt to convert the `#num` expression to an ordinal failed.</span></span>  
  
- <span data-ttu-id="25a83-106">`#num`指定 DLL 中未指定任何函数。</span><span class="sxs-lookup"><span data-stu-id="25a83-106">The `#num` specified does not specify any function in the DLL.</span></span>  
  
- <span data-ttu-id="25a83-107">类型库中有一个无效的声明，从而导致无效的序号的内部使用。</span><span class="sxs-lookup"><span data-stu-id="25a83-107">A type library has an invalid declaration resulting in internal use of an invalid ordinal number.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="25a83-108">更正此错误</span><span class="sxs-lookup"><span data-stu-id="25a83-108">To correct this error</span></span>  
  
1. <span data-ttu-id="25a83-109">请确保表达式表示的有效数字，或按名称调用该过程。</span><span class="sxs-lookup"><span data-stu-id="25a83-109">Make sure the expression represents a valid number, or call the procedure by name.</span></span>  
  
2. <span data-ttu-id="25a83-110">请确保`#num`标识 DLL 中有效的函数。</span><span class="sxs-lookup"><span data-stu-id="25a83-110">Make sure `#num` identifies a valid function in the DLL.</span></span>  
  
3. <span data-ttu-id="25a83-111">隔离导致问题的代码添加注释的过程调用。</span><span class="sxs-lookup"><span data-stu-id="25a83-111">Isolate the procedure call causing the problem by commenting out the code.</span></span> <span data-ttu-id="25a83-112">编写`Declare`语句过程中，并将问题报告给类型库供应商联系。</span><span class="sxs-lookup"><span data-stu-id="25a83-112">Write a `Declare` statement for the procedure, and report the problem to the type library vendor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25a83-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="25a83-113">See also</span></span>

- [<span data-ttu-id="25a83-114">Declare 语句</span><span class="sxs-lookup"><span data-stu-id="25a83-114">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
