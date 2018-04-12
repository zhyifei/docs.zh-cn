---
title: DLL 应用程序客户端太多
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID47
ms.assetid: 4b87780b-67ad-4c96-9253-db954a751dad
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d4b9278134e937ac8bf4626237954432d727ac0d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="too-many-dll-application-clients"></a><span data-ttu-id="0af58-102">DLL 应用程序客户端太多</span><span class="sxs-lookup"><span data-stu-id="0af58-102">Too many DLL application clients</span></span>
<span data-ttu-id="0af58-103">[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 的动态链接库 (DLL) 只能由有限个主机应用程序进行访问。</span><span class="sxs-lookup"><span data-stu-id="0af58-103">The dynamic-link library (DLL) for [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] can only accommodate access by a limited number of host applications.</span></span> <span data-ttu-id="0af58-104">你的应用程序和其他身为 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 主机的应用程序（你的应用程序可以访问其中某些主机应用程序）同时尝试访问 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] DLL。</span><span class="sxs-lookup"><span data-stu-id="0af58-104">Your application and other applications that are [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] hosts (some of which may be accessed by your application) are all attempting to access the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] DLL at the same time.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="0af58-105">更正此错误</span><span class="sxs-lookup"><span data-stu-id="0af58-105">To correct this error</span></span>  
  
-   <span data-ttu-id="0af58-106">减少打开的应用程序访问 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="0af58-106">Reduce the number of open applications accessing [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0af58-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0af58-107">See Also</span></span>  
 [<span data-ttu-id="0af58-108">错误类型</span><span class="sxs-lookup"><span data-stu-id="0af58-108">Error Types</span></span>](../../visual-basic/programming-guide/language-features/error-types.md)
