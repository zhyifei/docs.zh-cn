---
title: "My.Response 对象"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- My.MyWebExtension.Response
- My.Response
helpviewer_keywords: My.Response object
ms.assetid: 626359bc-3165-40b4-bfaf-2c610e26eb5b
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 76d0e701107add0d5bd468ba7a829759739e0cd9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="myresponse-object"></a>My.Response 对象
获取<xref:System.Web.HttpResponse>与关联的对象<xref:System.Web.UI.Page>。 使用此对象，可以将 HTTP 响应数据发送到客户端，并包含此响应的相关信息。  
  
## <a name="remarks"></a>备注  
 `My.Response`对象包含当前<xref:System.Web.HttpResponse>与页关联的对象。  
  
 `My.Response`对象功能仅适用于[!INCLUDE[vstecasp](~/includes/vstecasp-md.md)]应用程序。  
  
## <a name="example"></a>示例  
 下面的示例获取该标头集合`My.Request`对象，并使用`My.Response`要写入到 ASP.NET 页对象。  
  
 [!code-vb[VbVbalrMyWeb#1](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-response-object_1.aspx)]  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Web.HttpResponse>  
 [My.Request 对象](../../../visual-basic/language-reference/objects/my-request-object.md)
