---
title: SslStreamSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: 18130d50-8996-4257-9c60-bc457f8654d8
author: BrucePerlerMS
ms.openlocfilehash: 35cbd44cd1cf488b9309eef677516733c6379b96
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2018
ms.locfileid: "47198431"
---
# <a name="sslstreamsecuritybindingelement"></a>SslStreamSecurityBindingElement
SslStreamSecurityBindingElement  
  
## <a name="syntax"></a>语法  
  
```  
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
