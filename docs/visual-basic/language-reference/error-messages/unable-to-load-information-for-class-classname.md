---
title: 无法加载类的信息&#39;&lt;类名&gt;&#39;
ms.date: 07/20/2015
f1_keywords:
- vbc30712
- bc30712
helpviewer_keywords:
- BC30712
ms.assetid: c7ffbd6d-05c6-4261-b44b-1bcd521bb350
ms.openlocfilehash: 368484d9138d1ae10efb8c63f6cfaa6bcefa6ed8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54528951"
---
# <a name="unable-to-load-information-for-class-39ltclassnamegt39"></a><span data-ttu-id="7f601-102">无法加载类的信息&#39;&lt;类名&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="7f601-102">Unable to load information for class &#39;&lt;classname&gt;&#39;</span></span>
<span data-ttu-id="7f601-103">引用了不可用的类。</span><span class="sxs-lookup"><span data-stu-id="7f601-103">A reference was made to a class that is not available.</span></span>  
  
 <span data-ttu-id="7f601-104">**错误 ID:** BC30712</span><span class="sxs-lookup"><span data-stu-id="7f601-104">**Error ID:** BC30712</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7f601-105">更正此错误</span><span class="sxs-lookup"><span data-stu-id="7f601-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="7f601-106">验证定义了类和名称拼写正确。</span><span class="sxs-lookup"><span data-stu-id="7f601-106">Verify that the class is defined and that you spelled the name correctly.</span></span>  
  
2.  <span data-ttu-id="7f601-107">尝试访问该模块中声明的其中一个成员。</span><span class="sxs-lookup"><span data-stu-id="7f601-107">Try accessing one of the members declared in the module.</span></span> <span data-ttu-id="7f601-108">在某些情况下，调试环境找不到成员，因为尚未加载在其中声明成员的模块。</span><span class="sxs-lookup"><span data-stu-id="7f601-108">In some cases, the debugging environment cannot locate members because the modules where they are declared have not been loaded yet.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f601-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="7f601-109">See also</span></span>
- [<span data-ttu-id="7f601-110">在 Visual Studio 中进行调试</span><span class="sxs-lookup"><span data-stu-id="7f601-110">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugging-in-visual-studio)
