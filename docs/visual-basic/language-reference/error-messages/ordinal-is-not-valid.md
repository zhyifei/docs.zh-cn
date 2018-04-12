---
title: 序号无效
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID452
ms.assetid: 7459562b-cd4f-4590-95e0-6126ae3589a5
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d31d0fba19cc16004c0b56786af30603d0c509ea
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="ordinal-is-not-valid"></a><span data-ttu-id="02928-102">序号无效</span><span class="sxs-lookup"><span data-stu-id="02928-102">Ordinal is not valid</span></span>
<span data-ttu-id="02928-103">对动态链接库 (DLL) 的调用指示而不是过程名称，后面使用一个数字使用`#num`语法。</span><span class="sxs-lookup"><span data-stu-id="02928-103">Your call to a dynamic-link library (DLL) indicated to use a number instead of a procedure name, using the `#num` syntax.</span></span> <span data-ttu-id="02928-104">此错误具有以下可能的原因：</span><span class="sxs-lookup"><span data-stu-id="02928-104">This error has the following possible causes:</span></span>  
  
-   <span data-ttu-id="02928-105">尝试转换`#num`为序号失败的表达式。</span><span class="sxs-lookup"><span data-stu-id="02928-105">An attempt to convert the `#num` expression to an ordinal failed.</span></span>  
  
-   <span data-ttu-id="02928-106">`#num`指定 DLL 中未指定任何函数。</span><span class="sxs-lookup"><span data-stu-id="02928-106">The `#num` specified does not specify any function in the DLL.</span></span>  
  
-   <span data-ttu-id="02928-107">类型库中有一个无效的声明，从而导致无效的序号在内部使用。</span><span class="sxs-lookup"><span data-stu-id="02928-107">A type library has an invalid declaration resulting in internal use of an invalid ordinal number.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="02928-108">更正此错误</span><span class="sxs-lookup"><span data-stu-id="02928-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="02928-109">请确保表达式表示一个有效的数字，或者按名称调用的过程。</span><span class="sxs-lookup"><span data-stu-id="02928-109">Make sure the expression represents a valid number, or call the procedure by name.</span></span>  
  
2.  <span data-ttu-id="02928-110">请确保`#num`标识 DLL 中的有效函数。</span><span class="sxs-lookup"><span data-stu-id="02928-110">Make sure `#num` identifies a valid function in the DLL.</span></span>  
  
3.  <span data-ttu-id="02928-111">隔离导致问题的注释掉的代码的过程调用。</span><span class="sxs-lookup"><span data-stu-id="02928-111">Isolate the procedure call causing the problem by commenting out the code.</span></span> <span data-ttu-id="02928-112">编写`Declare`语句的过程中和报表的问题类型库供应商联系。</span><span class="sxs-lookup"><span data-stu-id="02928-112">Write a `Declare` statement for the procedure, and report the problem to the type library vendor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02928-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="02928-113">See Also</span></span>  
 [<span data-ttu-id="02928-114">Declare 语句</span><span class="sxs-lookup"><span data-stu-id="02928-114">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
