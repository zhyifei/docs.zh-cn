---
title: CustomBindingElement
ms.date: 03/30/2017
ms.assetid: df959dc5-1aef-4338-a123-6ff3e7bc37af
ms.openlocfilehash: ff0d7d8d6c6cb180043a834a60ca58159ca84c58
ms.sourcegitcommit: 7f7664837d35320a0bad3f7e4ecd68d6624633b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/30/2018
ms.locfileid: "52671955"
---
# <a name="custombindingelement"></a>CustomBindingElement
CustomBindingElement  
  
## <a name="syntax"></a>语法  
  
```csharp
class CustomBindingElement : BindingElement  
{  
  string Name;  
};  
```  
  
## <a name="methods"></a>方法  
 CustomBindingElement 类未定义任何方法。  
  
## <a name="properties"></a>属性  
 CustomBindingElement 类具有以下属性：  
  
### <a name="name"></a>名称  
 数据类型：String  
  
 访问类型：只读  
  
 一个包含绑定的配置名称的字符串。 此值是用户定义的一个字符串，可充当自定义绑定的标识字符串。  
  
## <a name="requirements"></a>要求  
  
|MOF|已在 Servicemodel.mof 中声明。|  
|---------|-----------------------------------|  
|命名空间|已在 root\ServiceModel 中定义|  
  
## <a name="see-also"></a>请参阅  
 <xref:System.ServiceModel.Channels.CustomBinding>
