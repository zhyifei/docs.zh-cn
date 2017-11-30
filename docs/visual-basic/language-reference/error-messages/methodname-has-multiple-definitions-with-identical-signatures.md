---
title: "&#39;&lt;methodname&gt;&#39; 具有多个完全相同的签名定义"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30269
- bc30269
helpviewer_keywords: BC30269
ms.assetid: 39489621-6617-4e5c-9b24-c2faf8273891
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1a71d51690d6318a559a94ac81de625289d7587d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="39ltmethodnamegt39-has-multiple-definitions-with-identical-signatures"></a><span data-ttu-id="487bd-102">&#39;&lt;methodname&gt;&#39; 具有多个完全相同的签名定义</span><span class="sxs-lookup"><span data-stu-id="487bd-102">&#39;&lt;methodname&gt;&#39; has multiple definitions with identical signatures</span></span>
<span data-ttu-id="487bd-103">A`Function`或`Sub`过程声明与以前的声明将使用相同的过程名称和自变量列表。</span><span class="sxs-lookup"><span data-stu-id="487bd-103">A `Function` or `Sub` procedure declaration uses the identical procedure name and argument list as a previous declaration.</span></span> <span data-ttu-id="487bd-104">一个可能的原因是尝试重载原始的过程。</span><span class="sxs-lookup"><span data-stu-id="487bd-104">One possible cause is an attempt to overload the original procedure.</span></span> <span data-ttu-id="487bd-105">重载的过程必须具有不同的自变量列表。</span><span class="sxs-lookup"><span data-stu-id="487bd-105">Overloaded procedures must have different argument lists.</span></span>  
  
 <span data-ttu-id="487bd-106">**错误 ID:** BC30269</span><span class="sxs-lookup"><span data-stu-id="487bd-106">**Error ID:** BC30269</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="487bd-107">更正此错误</span><span class="sxs-lookup"><span data-stu-id="487bd-107">To correct this error</span></span>  
  
-   <span data-ttu-id="487bd-108">更改过程名称或自变量列表中，或删除重复的声明。</span><span class="sxs-lookup"><span data-stu-id="487bd-108">Change the procedure name or the argument list, or remove the duplicate declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="487bd-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="487bd-109">See Also</span></span>  
 [<span data-ttu-id="487bd-110">对已声明元素的引用</span><span class="sxs-lookup"><span data-stu-id="487bd-110">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [<span data-ttu-id="487bd-111">重载过程注意事项</span><span class="sxs-lookup"><span data-stu-id="487bd-111">Considerations in Overloading Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)
