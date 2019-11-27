---
title: My.Response 对象
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Response
- My.Response
helpviewer_keywords:
- My.Response object
ms.assetid: 626359bc-3165-40b4-bfaf-2c610e26eb5b
ms.openlocfilehash: 522814ad48fb7548032b8a37779bb3ff6ca62413
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350660"
---
# <a name="myresponse-object"></a>My.Response 对象
获取与 <xref:System.Web.UI.Page>关联的 <xref:System.Web.HttpResponse> 对象。 使用此对象，可以将 HTTP 响应数据发送到客户端，并包含此响应的相关信息。  
  
## <a name="remarks"></a>备注  
 `My.Response` 对象包含与页关联的当前 <xref:System.Web.HttpResponse> 对象。  
  
 `My.Response` 对象仅适用于 ASP.NET 应用程序。  
  
## <a name="example"></a>示例  
 下面的示例从 `My.Request` 对象获取标头集合，并使用 `My.Response` 对象将其写入到 ASP.NET 页。  
  
 [!code-aspx-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Web.HttpResponse>
- [My.Request 对象](../../../visual-basic/language-reference/objects/my-request-object.md)
