---
title: My Response 对象 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Response
- My.Response
helpviewer_keywords:
- My.Response object
ms.assetid: 626359bc-3165-40b4-bfaf-2c610e26eb5b
ms.openlocfilehash: a50701998011c25c600c2a3763459c1aba3cc59a
ms.sourcegitcommit: 29a9b29d8b7d07b9c59d46628da754a8bff57fa4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/17/2019
ms.locfileid: "69567450"
---
# <a name="myresponse-object"></a>My.Response 对象
获取与关联的<xref:System.Web.HttpResponse>对象。 <xref:System.Web.UI.Page> 使用此对象，可以将 HTTP 响应数据发送到客户端，并包含此响应的相关信息。  
  
## <a name="remarks"></a>备注  
 对象包含与页关联<xref:System.Web.HttpResponse>的当前对象。 `My.Response`  
  
 `My.Response`对象仅适用于 ASP.NET 应用程序。  
  
## <a name="example"></a>示例  
 下面的示例从`My.Request`对象获取标头集合, 并`My.Response`使用对象将其写入到 ASP.NET 页。  
  
 [!code-aspx-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.Web.HttpResponse>
- [My.Request 对象](../../../visual-basic/language-reference/objects/my-request-object.md)
