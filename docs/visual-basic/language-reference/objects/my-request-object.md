---
title: My.Request 对象 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Request
- My.Request
helpviewer_keywords:
- My.Request object
ms.assetid: 93d5f0e2-6b60-4a2c-8652-d90216f6ad10
ms.openlocfilehash: 08212dc5fe563ce84be02ab706b56195a0636894
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "58836618"
---
# <a name="myrequest-object"></a><span data-ttu-id="23ad6-102">My.Request 对象</span><span class="sxs-lookup"><span data-stu-id="23ad6-102">My.Request Object</span></span>
<span data-ttu-id="23ad6-103">获取所请求的页面的 <xref:System.Web.HttpRequest> 对象。</span><span class="sxs-lookup"><span data-stu-id="23ad6-103">Gets the <xref:System.Web.HttpRequest> object for the requested page.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="23ad6-104">备注</span><span class="sxs-lookup"><span data-stu-id="23ad6-104">Remarks</span></span>  
 <span data-ttu-id="23ad6-105">`My.Request` 对象包含当前 HTTP 请求的相关信息。</span><span class="sxs-lookup"><span data-stu-id="23ad6-105">The `My.Request` object contains information about the current HTTP request.</span></span>  
  
 <span data-ttu-id="23ad6-106">`My.Request` 对象仅适用于 ASP.NET 应用程序。</span><span class="sxs-lookup"><span data-stu-id="23ad6-106">The `My.Request` object is available only for ASP.NET applications.</span></span>  
  
## <a name="example"></a><span data-ttu-id="23ad6-107">示例</span><span class="sxs-lookup"><span data-stu-id="23ad6-107">Example</span></span>  
 <span data-ttu-id="23ad6-108">下面的示例获取的标头集合`My.Request`对象，并使用`My.Response`要写入到 ASP.NET 页面对象。</span><span class="sxs-lookup"><span data-stu-id="23ad6-108">The following example gets the header collection from the `My.Request` object and uses the `My.Response` object to write it to the ASP.NET page.</span></span>  
  
 [!code-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a><span data-ttu-id="23ad6-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="23ad6-109">See also</span></span>

- <xref:System.Web.HttpRequest>
- [<span data-ttu-id="23ad6-110">My.Response 对象</span><span class="sxs-lookup"><span data-stu-id="23ad6-110">My.Response Object</span></span>](../../../visual-basic/language-reference/objects/my-response-object.md)
