---
title: SslStreamSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: 18130d50-8996-4257-9c60-bc457f8654d8
author: BrucePerlerMS
ms.openlocfilehash: 73855197d0fb518d49d6273d0587ddcf1f28885c
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "49371118"
---
# <a name="sslstreamsecuritybindingelement"></a>SslStreamSecurityBindingElement
SslStreamSecurityBindingElement  
  
## <a name="syntax"></a>语法  
  
```csharp
class SslStreamSecurityBindingElement : BindingElement  
{  
  boolean RequireClientCertificate;  
};  
```  
  
## <a name="methods"></a>方法  
 SslStreamSecurityBindingElement 类不定义任何方法。  
  
## <a name="properties"></a>属性  
 SslStreamSecurityBindingElement 类具有以下属性：  
  
### <a name="requireclientcertificate"></a>RequireClientCertificate  
 数据类型：Boolean  
  
 访问类型：只读  
  
 指定此绑定是否需要客户端证书。  
  
## <a name="requirements"></a>要求  
  
|MOF|已在 Servicemodel.mof 中声明。|  
|---------|-----------------------------------|  
|命名空间|已在 root\ServiceModel 中定义|  
  
## <a name="see-also"></a>请参阅  
 <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>
