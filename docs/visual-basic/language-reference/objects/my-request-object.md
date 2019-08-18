---
title: Request 对象 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Request
- My.Request
helpviewer_keywords:
- My.Request object
ms.assetid: 93d5f0e2-6b60-4a2c-8652-d90216f6ad10
ms.openlocfilehash: da17872acb839cdcdfa7f80c3f58f26dc25d0ab5
ms.sourcegitcommit: 29a9b29d8b7d07b9c59d46628da754a8bff57fa4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/17/2019
ms.locfileid: "69567471"
---
# <a name="myrequest-object"></a><span data-ttu-id="455cf-102">My.Request 对象</span><span class="sxs-lookup"><span data-stu-id="455cf-102">My.Request Object</span></span>
<span data-ttu-id="455cf-103">获取所请求的页面的 <xref:System.Web.HttpRequest> 对象。</span><span class="sxs-lookup"><span data-stu-id="455cf-103">Gets the <xref:System.Web.HttpRequest> object for the requested page.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="455cf-104">备注</span><span class="sxs-lookup"><span data-stu-id="455cf-104">Remarks</span></span>  
 <span data-ttu-id="455cf-105">`My.Request` 对象包含当前 HTTP 请求的相关信息。</span><span class="sxs-lookup"><span data-stu-id="455cf-105">The `My.Request` object contains information about the current HTTP request.</span></span>  
  
 <span data-ttu-id="455cf-106">`My.Request` 对象仅适用于 ASP.NET 应用程序。</span><span class="sxs-lookup"><span data-stu-id="455cf-106">The `My.Request` object is available only for ASP.NET applications.</span></span>  
  
## <a name="example"></a><span data-ttu-id="455cf-107">示例</span><span class="sxs-lookup"><span data-stu-id="455cf-107">Example</span></span>  
 <span data-ttu-id="455cf-108">下面的示例从`My.Request`对象获取标头集合, 并`My.Response`使用对象将其写入到 ASP.NET 页。</span><span class="sxs-lookup"><span data-stu-id="455cf-108">The following example gets the header collection from the `My.Request` object and uses the `My.Response` object to write it to the ASP.NET page.</span></span>  
  
 [!code-aspx-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a><span data-ttu-id="455cf-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="455cf-109">See also</span></span>

- <xref:System.Web.HttpRequest>
- [<span data-ttu-id="455cf-110">My.Response 对象</span><span class="sxs-lookup"><span data-stu-id="455cf-110">My.Response Object</span></span>](../../../visual-basic/language-reference/objects/my-response-object.md)
