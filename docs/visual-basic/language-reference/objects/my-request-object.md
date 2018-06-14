---
title: My.Request 对象
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Request
- My.Request
helpviewer_keywords:
- My.Request object
ms.assetid: 93d5f0e2-6b60-4a2c-8652-d90216f6ad10
ms.openlocfilehash: 88c3a9a01b50a97b556fa94026df391248bdf912
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33595883"
---
# <a name="myrequest-object"></a>My.Request 对象
获取所请求的页面的 <xref:System.Web.HttpRequest> 对象。  
  
## <a name="remarks"></a>备注  
 `My.Request` 对象包含当前 HTTP 请求的相关信息。  
  
 `My.Request` 对象仅适用于 ASP.NET 应用程序。  
  
## <a name="example"></a>示例  
 下面的示例获取该标头集合`My.Request`对象，并使用`My.Response`要写入到 ASP.NET 页对象。  
  
 [!code-vb[VbVbalrMyWeb#1](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-request-object_1.aspx)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Web.HttpRequest>  
 [My.Response 对象](../../../visual-basic/language-reference/objects/my-response-object.md)
