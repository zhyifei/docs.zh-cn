---
title: My.Request 对象 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Request
- My.Request
helpviewer_keywords:
- My.Request object
ms.assetid: 93d5f0e2-6b60-4a2c-8652-d90216f6ad10
ms.openlocfilehash: 7a4e292968cf1d30977b8cacdc8f77152e5cc770
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/01/2019
ms.locfileid: "57200957"
---
# <a name="myrequest-object"></a>My.Request 对象
获取所请求的页面的 <xref:System.Web.HttpRequest> 对象。  
  
## <a name="remarks"></a>备注  
 `My.Request` 对象包含当前 HTTP 请求的相关信息。  
  
 `My.Request` 对象仅适用于 ASP.NET 应用程序。  
  
## <a name="example"></a>示例  
 下面的示例获取的标头集合`My.Request`对象，并使用`My.Response`要写入到 ASP.NET 页面对象。  
  
 [!code-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a>请参阅
- <xref:System.Web.HttpRequest>
- [My.Response 对象](../../../visual-basic/language-reference/objects/my-response-object.md)
