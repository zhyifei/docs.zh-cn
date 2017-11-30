---
title: "Internet Explorer 完成的与 WCF 完成的服务证书验证之间的差异"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- service certificate validation [WCF]
- certificates [WCF], service certificate validation
ms.assetid: 9dffcab2-70a9-40f0-99fd-d3a0b296028f
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a58ea9f84571ede9943769e1f187a242383a88f0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="differences-between-service-certificate-validation-done-by-internet-explorer-and-wcf"></a>Internet Explorer 完成的与 WCF 完成的服务证书验证之间的差异
因为在使用 HTTPS 时，Internet Explorer 与 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 验证服务证书的方式不同，所以有可能 Internet Explorer 将无法访问帮助页或服务的 Web 服务描述语言 (WSDL)，即使 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 客户端可以向服务终结点成功发送消息时也将如此。 这是因为 Internet Explorer 会检查服务证书的增强使用标志中是否具有 `ServerAuthentication` 对象标识符 (OID)，而 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 则不施加此类约束。 如果 Internet 资源管理器无法访问服务帮助页或服务的 WSDL，请使用[ServiceModel 元数据实用工具 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)访问服务元数据。  
  
## <a name="see-also"></a>另请参阅  
 [HTTPS、 SSL over TCP 和 SOAP 安全之间的证书验证差异](../../../../docs/framework/wcf/feature-details/cert-val-diff-https-ssl-over-tcp-and-soap.md)  
 [如何： 检索元数据和实现兼容服务](../../../../docs/framework/wcf/feature-details/how-to-retrieve-metadata-and-implement-a-compliant-service.md)
