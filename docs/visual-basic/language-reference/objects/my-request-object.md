---
title: "My.Request 对象"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- My.MyWebExtension.Request
- My.Request
helpviewer_keywords: My.Request object
ms.assetid: 93d5f0e2-6b60-4a2c-8652-d90216f6ad10
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e0e67c8fd85860eacc57bcc7dd7f15f97097efe3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="myrequest-object"></a><span data-ttu-id="3b875-102">My.Request 对象</span><span class="sxs-lookup"><span data-stu-id="3b875-102">My.Request Object</span></span>
<span data-ttu-id="3b875-103">获取所请求的页面的 <xref:System.Web.HttpRequest> 对象。</span><span class="sxs-lookup"><span data-stu-id="3b875-103">Gets the <xref:System.Web.HttpRequest> object for the requested page.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3b875-104">备注</span><span class="sxs-lookup"><span data-stu-id="3b875-104">Remarks</span></span>  
 <span data-ttu-id="3b875-105">`My.Request` 对象包含当前 HTTP 请求的相关信息。</span><span class="sxs-lookup"><span data-stu-id="3b875-105">The `My.Request` object contains information about the current HTTP request.</span></span>  
  
 <span data-ttu-id="3b875-106">`My.Request` 对象仅适用于 ASP.NET 应用程序。</span><span class="sxs-lookup"><span data-stu-id="3b875-106">The `My.Request` object is available only for ASP.NET applications.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3b875-107">示例</span><span class="sxs-lookup"><span data-stu-id="3b875-107">Example</span></span>  
 <span data-ttu-id="3b875-108">下面的示例获取该标头集合`My.Request`对象，并使用`My.Response`要写入到 ASP.NET 页对象。</span><span class="sxs-lookup"><span data-stu-id="3b875-108">The following example gets the header collection from the `My.Request` object and uses the `My.Response` object to write it to the ASP.NET page.</span></span>  
  
 [!code-vb[VbVbalrMyWeb#1](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-request-object_1.aspx)]  
  
## <a name="see-also"></a><span data-ttu-id="3b875-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3b875-109">See Also</span></span>  
 <xref:System.Web.HttpRequest>  
 [<span data-ttu-id="3b875-110">My.Response 对象</span><span class="sxs-lookup"><span data-stu-id="3b875-110">My.Response Object</span></span>](../../../visual-basic/language-reference/objects/my-response-object.md)
