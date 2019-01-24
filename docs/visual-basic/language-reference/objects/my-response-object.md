---
title: My.Response 对象 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Response
- My.Response
helpviewer_keywords:
- My.Response object
ms.assetid: 626359bc-3165-40b4-bfaf-2c610e26eb5b
ms.openlocfilehash: c133e46b1adff0c100d49c4bfe5e17db4314a0bb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54738808"
---
# <a name="myresponse-object"></a><span data-ttu-id="73ae7-102">My.Response 对象</span><span class="sxs-lookup"><span data-stu-id="73ae7-102">My.Response Object</span></span>
<span data-ttu-id="73ae7-103">获取<xref:System.Web.HttpResponse>对象与关联<xref:System.Web.UI.Page>。</span><span class="sxs-lookup"><span data-stu-id="73ae7-103">Gets the <xref:System.Web.HttpResponse> object associated with the <xref:System.Web.UI.Page>.</span></span> <span data-ttu-id="73ae7-104">使用此对象，可以将 HTTP 响应数据发送到客户端，并包含此响应的相关信息。</span><span class="sxs-lookup"><span data-stu-id="73ae7-104">This object allows you to send HTTP response data to a client and contains information about that response.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="73ae7-105">备注</span><span class="sxs-lookup"><span data-stu-id="73ae7-105">Remarks</span></span>  
 <span data-ttu-id="73ae7-106">`My.Response`对象包含当前<xref:System.Web.HttpResponse>与页关联的对象。</span><span class="sxs-lookup"><span data-stu-id="73ae7-106">The `My.Response` object contains the current <xref:System.Web.HttpResponse> object associated with the page.</span></span>  
  
 <span data-ttu-id="73ae7-107">`My.Response`对象功能仅适用于[!INCLUDE[vstecasp](~/includes/vstecasp-md.md)]应用程序。</span><span class="sxs-lookup"><span data-stu-id="73ae7-107">The `My.Response` object is only available for [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] applications.</span></span>  
  
## <a name="example"></a><span data-ttu-id="73ae7-108">示例</span><span class="sxs-lookup"><span data-stu-id="73ae7-108">Example</span></span>  
 <span data-ttu-id="73ae7-109">下面的示例获取的标头集合`My.Request`对象，并使用`My.Response`要写入到 ASP.NET 页面对象。</span><span class="sxs-lookup"><span data-stu-id="73ae7-109">The following example gets the header collection from the `My.Request` object and uses the `My.Response` object to write it to the ASP.NET page.</span></span>  
  
 [!code-vb[VbVbalrMyWeb#1](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-response-object_1.aspx)]  
  
## <a name="see-also"></a><span data-ttu-id="73ae7-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="73ae7-110">See also</span></span>
- <xref:System.Web.HttpResponse>
- [<span data-ttu-id="73ae7-111">My.Request 对象</span><span class="sxs-lookup"><span data-stu-id="73ae7-111">My.Request Object</span></span>](../../../visual-basic/language-reference/objects/my-request-object.md)
