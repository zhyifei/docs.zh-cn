---
title: SymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: b2e182b6-c041-4d80-a926-6058068d9f79
author: BrucePerlerMS
ms.openlocfilehash: 180b64f6f37e5c765585e52b292319816618be28
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "47076505"
---
# <a name="symmetricsecuritybindingelement"></a>SymmetricSecurityBindingElement
SymmetricSecurityBindingElement  
  
## <a name="syntax"></a>语法  
  
```  
class SymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a>方法  
 SymmetricSecurityBindingElement 类不定义任何方法。  
  
## <a name="properties"></a>属性  
 SymmetricSecurityBindingElement 类具有下列属性：  
  
### <a name="messageprotectionorder"></a>MessageProtectionOrder  
 数据类型：String  
  
 访问类型：只读  
  
 此绑定的消息加密和签名的顺序。  
  
### <a name="requiresignatureconfirmation"></a>RequireSignatureConfirmation  
 数据类型：Boolean  
  
 访问类型：只读  
  
 此绑定是否需要签名确认。  
  
## <a name="requirements"></a>要求  
  
|MOF|已在 Servicemodel.mof 中声明。|  
|---------|-----------------------------------|  
|命名空间|已在 root\ServiceModel 中定义|  
  
## <a name="see-also"></a>请参阅  
 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>
