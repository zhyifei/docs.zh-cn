---
title: PeerSecuritySettings
ms.date: 03/30/2017
ms.assetid: 24ae0d35-f3a3-419b-afd6-686e22aae27b
ms.openlocfilehash: 92aca4c790607de91314aacf6414d0dfacea9a9f
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/25/2018
ms.locfileid: "50045725"
---
# <a name="peersecuritysettings"></a>PeerSecuritySettings
PeerSecuritySettings  
  
## <a name="syntax"></a>语法  
  
```csharp
class PeerSecuritySettings  
{  
  string Mode;  
  PeerTransportSecuritySettings Transport;  
};  
```  
  
## <a name="methods"></a>方法  
 PeerSecuritySettings 类不定义任何方法。  
  
## <a name="properties"></a>属性  
 PeerSecuritySettings 类具有下列属性：  
  
### <a name="mode"></a>模式  
 数据类型：String  
  
 访问类型：只读  
  
 配置有绑定的终结点是否使用消息级别和传输级别安全。  
  
### <a name="transport"></a>传输  
 数据类型：PeerTransportSecuritySettings  
  
 访问类型：只读  
  
 传输安全设置。  
  
## <a name="requirements"></a>要求  
  
|MOF|已在 Servicemodel.mof 中声明。|  
|---------|-----------------------------------|  
|命名空间|已在 root\ServiceModel 中定义|  
  
## <a name="see-also"></a>请参阅  
 <xref:System.ServiceModel.PeerSecuritySettings>
