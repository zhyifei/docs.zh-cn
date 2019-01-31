---
title: “Module”语句只能出现在文件级或命名空间级
ms.date: 07/20/2015
f1_keywords:
- bc30617
- vbc30617
helpviewer_keywords:
- BC30617
ms.assetid: 5e9de8e5-d26b-4fb2-9e28-814413fe9cef
ms.openlocfilehash: 0820763cce9cc27f9a379ed5e766e0691a75f36b
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55271260"
---
# <a name="module-statements-can-occur-only-at-file-or-namespace-level"></a><span data-ttu-id="1e8dc-102">“Module”语句只能出现在文件级或命名空间级</span><span class="sxs-lookup"><span data-stu-id="1e8dc-102">'Module' statements can occur only at file or namespace level</span></span>
<span data-ttu-id="1e8dc-103">`Module` 语句必须出现在源文件的顶部后立即`Option`和`Imports`语句、 全局属性和命名空间声明，但所有其他声明之前。</span><span class="sxs-lookup"><span data-stu-id="1e8dc-103">`Module` statements must appear at the top of your source file immediately after `Option` and `Imports` statements, global attributes, and namespace declarations, but before all other declarations.</span></span>  
  
 <span data-ttu-id="1e8dc-104">**错误 ID:** BC30617</span><span class="sxs-lookup"><span data-stu-id="1e8dc-104">**Error ID:** BC30617</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1e8dc-105">更正此错误</span><span class="sxs-lookup"><span data-stu-id="1e8dc-105">To correct this error</span></span>  
  
-   <span data-ttu-id="1e8dc-106">将 `Module` 语句移动到命名空间声明或源文件的顶部。</span><span class="sxs-lookup"><span data-stu-id="1e8dc-106">Move the `Module` statement to the top of your namespace declaration or source file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e8dc-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="1e8dc-107">See also</span></span>
- [<span data-ttu-id="1e8dc-108">Module 语句</span><span class="sxs-lookup"><span data-stu-id="1e8dc-108">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)
