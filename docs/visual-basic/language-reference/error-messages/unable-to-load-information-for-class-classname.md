---
title: "无法加载类的信息&lt;classname&gt;&quot; |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30712
- bc30712
dev_langs:
- VB
helpviewer_keywords:
- BC30712
ms.assetid: c7ffbd6d-05c6-4261-b44b-1bcd521bb350
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 0e95ba21e7ec751fe0276244dd1ce49552b178ab
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="unable-to-load-information-for-class-39ltclassnamegt39"></a><span data-ttu-id="46b40-102">无法加载类的信息&lt;classname&gt;</span><span class="sxs-lookup"><span data-stu-id="46b40-102">Unable to load information for class &#39;&lt;classname&gt;&#39;</span></span>
<span data-ttu-id="46b40-103">一个引用了不可用的类。</span><span class="sxs-lookup"><span data-stu-id="46b40-103">A reference was made to a class that is not available.</span></span>  
  
 <span data-ttu-id="46b40-104">**错误 ID:** BC30712</span><span class="sxs-lookup"><span data-stu-id="46b40-104">**Error ID:** BC30712</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="46b40-105">更正此错误</span><span class="sxs-lookup"><span data-stu-id="46b40-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="46b40-106">验证定义了类和名称拼写正确。</span><span class="sxs-lookup"><span data-stu-id="46b40-106">Verify that the class is defined and that you spelled the name correctly.</span></span>  
  
2.  <span data-ttu-id="46b40-107">尝试访问该模块中声明的其中一个成员。</span><span class="sxs-lookup"><span data-stu-id="46b40-107">Try accessing one of the members declared in the module.</span></span> <span data-ttu-id="46b40-108">在某些情况下，调试环境找不到成员，因为尚未加载在其中声明成员的模块。</span><span class="sxs-lookup"><span data-stu-id="46b40-108">In some cases, the debugging environment cannot locate members because the modules where they are declared have not been loaded yet.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46b40-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="46b40-109">See Also</span></span>  
 [<span data-ttu-id="46b40-110">在 Visual Studio 中进行调试</span><span class="sxs-lookup"><span data-stu-id="46b40-110">Debugging in Visual Studio</span></span>](https://docs.microsoft.com/visualstudio/debugger/debugging-in-visual-studio)
