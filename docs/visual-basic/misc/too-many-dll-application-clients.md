---
title: "太多 DLL 应用程序客户端 |Microsoft 文档"
ms.date: 2015-07-20
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
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 18781161d1208e7e8d01f99eb9d655803d249e6e
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="too-many-dll-application-clients"></a><span data-ttu-id="29ba0-102">DLL 应用程序客户端太多</span><span class="sxs-lookup"><span data-stu-id="29ba0-102">Too many DLL application clients</span></span>
<span data-ttu-id="29ba0-103">有关的动态链接库 (DLL)[!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]只能容纳通过有限数量的宿主应用程序的访问。</span><span class="sxs-lookup"><span data-stu-id="29ba0-103">The dynamic-link library (DLL) for [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] can only accommodate access by a limited number of host applications.</span></span> <span data-ttu-id="29ba0-104">您的应用程序和其他应用程序是[!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]所有试图访问 （其中一些可能会通过您的应用程序访问） 的主机[!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]DLL 在同一时间。</span><span class="sxs-lookup"><span data-stu-id="29ba0-104">Your application and other applications that are [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] hosts (some of which may be accessed by your application) are all attempting to access the [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] DLL at the same time.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="29ba0-105">更正此错误</span><span class="sxs-lookup"><span data-stu-id="29ba0-105">To correct this error</span></span>  
  
-   <span data-ttu-id="29ba0-106">减少打开的应用程序访问[!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]。</span><span class="sxs-lookup"><span data-stu-id="29ba0-106">Reduce the number of open applications accessing [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29ba0-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="29ba0-107">See Also</span></span>  
 [<span data-ttu-id="29ba0-108">错误类型</span><span class="sxs-lookup"><span data-stu-id="29ba0-108">Error Types</span></span>](../../visual-basic/programming-guide/language-features/error-types.md)
