---
title: "My.Response 对象 |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- My.MyWebExtension.Response
- My.Response
dev_langs:
- VB
helpviewer_keywords:
- My.Response object
ms.assetid: 626359bc-3165-40b4-bfaf-2c610e26eb5b
caps.latest.revision: 9
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
ms.openlocfilehash: b9b34c9df31536f6d553cda2e26677a2645768c2
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="myresponse-object"></a><span data-ttu-id="123b8-102">My.Response 对象</span><span class="sxs-lookup"><span data-stu-id="123b8-102">My.Response Object</span></span>
<span data-ttu-id="123b8-103">获取<xref:System.Web.HttpResponse>与<xref:System.Web.UI.Page>。</xref:System.Web.UI.Page>关联的对象</xref:System.Web.HttpResponse></span><span class="sxs-lookup"><span data-stu-id="123b8-103">Gets the <xref:System.Web.HttpResponse> object associated with the <xref:System.Web.UI.Page>.</span></span> <span data-ttu-id="123b8-104">此对象可用于将 HTTP 响应数据发送到客户端，并包含有关该响应的信息。</span><span class="sxs-lookup"><span data-stu-id="123b8-104">This object allows you to send HTTP response data to a client and contains information about that response.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="123b8-105">备注</span><span class="sxs-lookup"><span data-stu-id="123b8-105">Remarks</span></span>  
 <span data-ttu-id="123b8-106">`My.Response`对象包含当前<xref:System.Web.HttpResponse>与页关联的对象。</xref:System.Web.HttpResponse></span><span class="sxs-lookup"><span data-stu-id="123b8-106">The `My.Response` object contains the current <xref:System.Web.HttpResponse> object associated with the page.</span></span>  
  
 <span data-ttu-id="123b8-107">`My.Response`对象功能仅适用于[!INCLUDE[vstecasp](../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)]应用程序。</span><span class="sxs-lookup"><span data-stu-id="123b8-107">The `My.Response` object is only available for [!INCLUDE[vstecasp](../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)] applications.</span></span>  
  
## <a name="example"></a><span data-ttu-id="123b8-108">示例</span><span class="sxs-lookup"><span data-stu-id="123b8-108">Example</span></span>  
 <span data-ttu-id="123b8-109">下面的示例获取该标头集合`My.Request`对象，并使用`My.Response`要写入到 ASP.NET 页面对象。</span><span class="sxs-lookup"><span data-stu-id="123b8-109">The following example gets the header collection from the `My.Request` object and uses the `My.Response` object to write it to the ASP.NET page.</span></span>  
  
 <span data-ttu-id="123b8-110">[!code-vb[VbVbalrMyWeb #&1;](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-response-object_1.aspx)]</span><span class="sxs-lookup"><span data-stu-id="123b8-110">[!code-vb[VbVbalrMyWeb#1](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-response-object_1.aspx)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="123b8-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="123b8-111">See Also</span></span>  
 <span data-ttu-id="123b8-112"><xref:System.Web.HttpResponse></xref:System.Web.HttpResponse></span><span class="sxs-lookup"><span data-stu-id="123b8-112"><xref:System.Web.HttpResponse></span></span>   
<span data-ttu-id="123b8-113"> [My.Request 对象](../../../visual-basic/language-reference/objects/my-request-object.md)</span><span class="sxs-lookup"><span data-stu-id="123b8-113"> [My.Request Object](../../../visual-basic/language-reference/objects/my-request-object.md)</span></span>
