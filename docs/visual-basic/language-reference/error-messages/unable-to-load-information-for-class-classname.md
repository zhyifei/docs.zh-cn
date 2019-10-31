---
title: 无法加载类“<classname>”的信息
ms.date: 07/20/2015
f1_keywords:
- vbc30712
- bc30712
helpviewer_keywords:
- BC30712
ms.assetid: c7ffbd6d-05c6-4261-b44b-1bcd521bb350
ms.openlocfilehash: b3ef2aa5e25d61f005159e06852e23c2c036fd54
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198182"
---
# <a name="unable-to-load-information-for-class-classname"></a><span data-ttu-id="a7a0b-102">无法加载类 "\<classname >" 的信息</span><span class="sxs-lookup"><span data-stu-id="a7a0b-102">Unable to load information for class '\<classname>'</span></span>
<span data-ttu-id="a7a0b-103">对不提供的类进行了引用。</span><span class="sxs-lookup"><span data-stu-id="a7a0b-103">A reference was made to a class that is not available.</span></span>  
  
 <span data-ttu-id="a7a0b-104">**错误 ID：** BC30712</span><span class="sxs-lookup"><span data-stu-id="a7a0b-104">**Error ID:** BC30712</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a7a0b-105">更正此错误</span><span class="sxs-lookup"><span data-stu-id="a7a0b-105">To correct this error</span></span>  
  
1. <span data-ttu-id="a7a0b-106">验证是否定义了类，并且是否正确拼写了名称。</span><span class="sxs-lookup"><span data-stu-id="a7a0b-106">Verify that the class is defined and that you spelled the name correctly.</span></span>  
  
2. <span data-ttu-id="a7a0b-107">尝试访问该模块中声明的其中一个成员。</span><span class="sxs-lookup"><span data-stu-id="a7a0b-107">Try accessing one of the members declared in the module.</span></span> <span data-ttu-id="a7a0b-108">在某些情况下，调试环境找不到成员，因为尚未加载在其中声明成员的模块。</span><span class="sxs-lookup"><span data-stu-id="a7a0b-108">In some cases, the debugging environment cannot locate members because the modules where they are declared have not been loaded yet.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7a0b-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="a7a0b-109">See also</span></span>

- [<span data-ttu-id="a7a0b-110">在 Visual Studio 中进行调试</span><span class="sxs-lookup"><span data-stu-id="a7a0b-110">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugger-feature-tour)
