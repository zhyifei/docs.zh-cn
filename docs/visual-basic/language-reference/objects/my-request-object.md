---
title: My.Request 对象 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Request
- My.Request
helpviewer_keywords:
- My.Request object
ms.assetid: 93d5f0e2-6b60-4a2c-8652-d90216f6ad10
ms.openlocfilehash: a9af211df358b8c87cc9735f05d18c191b49500e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54716190"
---
# <a name="myrequest-object"></a><span data-ttu-id="a548d-102">My.Request 对象</span><span class="sxs-lookup"><span data-stu-id="a548d-102">My.Request Object</span></span>
<span data-ttu-id="a548d-103">获取所请求的页面的 <xref:System.Web.HttpRequest> 对象。</span><span class="sxs-lookup"><span data-stu-id="a548d-103">Gets the <xref:System.Web.HttpRequest> object for the requested page.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a548d-104">备注</span><span class="sxs-lookup"><span data-stu-id="a548d-104">Remarks</span></span>  
 <span data-ttu-id="a548d-105">`My.Request` 对象包含当前 HTTP 请求的相关信息。</span><span class="sxs-lookup"><span data-stu-id="a548d-105">The `My.Request` object contains information about the current HTTP request.</span></span>  
  
 <span data-ttu-id="a548d-106">`My.Request` 对象仅适用于 ASP.NET 应用程序。</span><span class="sxs-lookup"><span data-stu-id="a548d-106">The `My.Request` object is available only for ASP.NET applications.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a548d-107">示例</span><span class="sxs-lookup"><span data-stu-id="a548d-107">Example</span></span>  
 <span data-ttu-id="a548d-108">下面的示例获取的标头集合`My.Request`对象，并使用`My.Response`要写入到 ASP.NET 页面对象。</span><span class="sxs-lookup"><span data-stu-id="a548d-108">The following example gets the header collection from the `My.Request` object and uses the `My.Response` object to write it to the ASP.NET page.</span></span>  
  
 [!code-vb[VbVbalrMyWeb#1](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-request-object_1.aspx)]  
  
## <a name="see-also"></a><span data-ttu-id="a548d-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="a548d-109">See also</span></span>
- <xref:System.Web.HttpRequest>
- [<span data-ttu-id="a548d-110">My.Response 对象</span><span class="sxs-lookup"><span data-stu-id="a548d-110">My.Response Object</span></span>](../../../visual-basic/language-reference/objects/my-response-object.md)
