---
title: PrivacyNoticeBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0cf110b1-e25b-4d67-986b-10cb04dc4826
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f79a71fe039add2969fab826e1f5ec2f00bee00c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="privacynoticebindingelement"></a>PrivacyNoticeBindingElement
PrivacyNoticeBindingElement  
  
## <a name="syntax"></a>语法  
  
```  
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
  
### <a name="url"></a>Url  
 数据类型：String  
  
 访问类型：只读  
  
 隐私声明所在的 URL。  
  
## <a name="requirements"></a>要求  
  
|MOF|已在 Servicemodel.mof 中声明。|  
|---------|-----------------------------------|  
|命名空间|已在 root\ServiceModel 中定义|  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>
