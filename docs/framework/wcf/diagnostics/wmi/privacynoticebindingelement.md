---
title: PrivacyNoticeBindingElement
ms.date: 03/30/2017
ms.assetid: 0cf110b1-e25b-4d67-986b-10cb04dc4826
ms.openlocfilehash: fdaf30e78b1a74a733753542acd6a41f15f176bd
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2018
ms.locfileid: "50135255"
---
# <a name="privacynoticebindingelement"></a>PrivacyNoticeBindingElement
PrivacyNoticeBindingElement  
  
## <a name="syntax"></a>语法  
  
```csharp
class PrivacyNoticeBindingElement : BindingElement  
{  
  sint32 PrivacyNoticeVersion;  
  string Url;  
};  
```  
  
## <a name="methods"></a>方法  
 PrivacyNoticeBindingElement 类未定义任何方法。  
  
## <a name="properties"></a>属性  
 PrivacyNoticeBindingElement 类具有以下属性：  
  
### <a name="privacynoticeversion"></a>PrivacyNoticeVersion  
 数据类型：sint32  
  
 访问类型：只读  
  
 隐私声明版本。  
  
### <a name="url"></a>URL  
 数据类型：String  
  
 访问类型：只读  
  
 隐私声明所在的 URL。  
  
## <a name="requirements"></a>要求  
  
|MOF|已在 Servicemodel.mof 中声明。|  
|---------|-----------------------------------|  
|命名空间|已在 root\ServiceModel 中定义|  
  
## <a name="see-also"></a>请参阅  
 <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>
