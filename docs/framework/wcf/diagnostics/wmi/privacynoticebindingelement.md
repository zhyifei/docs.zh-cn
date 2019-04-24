---
title: PrivacyNoticeBindingElement
ms.date: 03/30/2017
ms.assetid: 0cf110b1-e25b-4d67-986b-10cb04dc4826
ms.openlocfilehash: 04c65d0aa589d99766b4ffc8f1550036d2880718
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2019
ms.locfileid: "59976373"
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

- <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>
