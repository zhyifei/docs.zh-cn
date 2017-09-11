---
title: "访问用户数据 (Visual Basic)"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- domain names, retrieving
- data [Visual Basic], accessing user data
- My.User object, tasks
- user data, domain
- user names, retrieving
- user data, accessing
- login names
- examples [Visual Basic], accessing user data
ms.assetid: 32492a15-ee59-4a63-a1f1-9b24cc13140a
caps.latest.revision: 17
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 396ae45d26551c3a44a8a8fa6334a744508734a7
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="accessing-user-data-visual-basic"></a><span data-ttu-id="f1737-102">访问用户数据 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f1737-102">Accessing User Data (Visual Basic)</span></span>
<span data-ttu-id="f1737-103">本部分包含有关处理 `My.User` 对象的主题以及可通过该操作完成的任务。</span><span class="sxs-lookup"><span data-stu-id="f1737-103">This section contains topics dealing with the `My.User` object and tasks that you can accomplish with it.</span></span>  
  
 <span data-ttu-id="f1737-104">`My.User` 对象通过返回实现 <xref:System.Security.Principal.IPrincipal> 接口的对象，提供有关登录用户的信息的访问权限。</span><span class="sxs-lookup"><span data-stu-id="f1737-104">The `My.User` object provides access to information about the logged-on user by returning an object that implements the <xref:System.Security.Principal.IPrincipal> interface.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="f1737-105">任务</span><span class="sxs-lookup"><span data-stu-id="f1737-105">Tasks</span></span>  
  
|<span data-ttu-id="f1737-106">到</span><span class="sxs-lookup"><span data-stu-id="f1737-106">To</span></span>|<span data-ttu-id="f1737-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="f1737-107">See</span></span>|  
|--------|---------|  
|<span data-ttu-id="f1737-108">获取用户的登录名</span><span class="sxs-lookup"><span data-stu-id="f1737-108">Get the user's login name</span></span>|<xref:Microsoft.VisualBasic.ApplicationServices.User.Name%2A>|  
|<span data-ttu-id="f1737-109">如果应用程序使用 Windows 身份验证，则获取用户的域名</span><span class="sxs-lookup"><span data-stu-id="f1737-109">Get the user's domain name, if the application uses Windows authentication</span></span>|<xref:Microsoft.VisualBasic.ApplicationServices.User.CurrentPrincipal>|  
|<span data-ttu-id="f1737-110">确定用户的角色</span><span class="sxs-lookup"><span data-stu-id="f1737-110">Determine the user's role</span></span>|<xref:Microsoft.VisualBasic.ApplicationServices.User.IsInRole%2A>|  
  
## <a name="see-also"></a><span data-ttu-id="f1737-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f1737-111">See Also</span></span>  
 <xref:Microsoft.VisualBasic.ApplicationServices.User>

