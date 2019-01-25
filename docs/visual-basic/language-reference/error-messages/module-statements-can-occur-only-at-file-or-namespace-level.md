---
title: '&#39;模块&#39;语句只能出现在文件级或命名空间级'
ms.date: 07/20/2015
f1_keywords:
- bc30617
- vbc30617
helpviewer_keywords:
- BC30617
ms.assetid: 5e9de8e5-d26b-4fb2-9e28-814413fe9cef
ms.openlocfilehash: bdbf8df5942e9df4b9696aeea4e3492121efe21a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54746307"
---
# <a name="39module39-statements-can-occur-only-at-file-or-namespace-level"></a><span data-ttu-id="becd5-102">&#39;模块&#39;语句只能出现在文件级或命名空间级</span><span class="sxs-lookup"><span data-stu-id="becd5-102">&#39;Module&#39; statements can occur only at file or namespace level</span></span>
<span data-ttu-id="becd5-103">`Module` 语句必须出现在源文件的顶部后立即`Option`和`Imports`语句、 全局属性和命名空间声明，但所有其他声明之前。</span><span class="sxs-lookup"><span data-stu-id="becd5-103">`Module` statements must appear at the top of your source file immediately after `Option` and `Imports` statements, global attributes, and namespace declarations, but before all other declarations.</span></span>  
  
 <span data-ttu-id="becd5-104">**错误 ID:** BC30617</span><span class="sxs-lookup"><span data-stu-id="becd5-104">**Error ID:** BC30617</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="becd5-105">更正此错误</span><span class="sxs-lookup"><span data-stu-id="becd5-105">To correct this error</span></span>  
  
-   <span data-ttu-id="becd5-106">将 `Module` 语句移动到命名空间声明或源文件的顶部。</span><span class="sxs-lookup"><span data-stu-id="becd5-106">Move the `Module` statement to the top of your namespace declaration or source file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="becd5-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="becd5-107">See also</span></span>
- [<span data-ttu-id="becd5-108">Module 语句</span><span class="sxs-lookup"><span data-stu-id="becd5-108">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)
