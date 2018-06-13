---
title: OneWayBindingElement
ms.date: 03/30/2017
ms.assetid: 5c7e17c3-39b9-4214-ae08-9e6141734305
ms.openlocfilehash: ee7cfed20234175ba54dd25dbbbab4615c1ed7af
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33485733"
---
# <a name="onewaybindingelement"></a>OneWayBindingElement
OneWayBindingElement  
  
## <a name="syntax"></a>语法  
  
```  
class OneWayBindingElement : BindingElement  
{  
  ChannelPoolSettings ChannelPoolSettings;  
  sint32 MaxAcceptedChannels;  
  boolean PacketRoutable;  
};  
```  
  
## <a name="methods"></a>方法  
 OneWayBindingElement 类未定义任何方法。  
  
## <a name="properties"></a>属性  
 OneWayBindingElement 类具有以下属性：  
  
### <a name="channelpoolsettings"></a>ChannelPoolSettings  
 数据类型：ChannelPoolSettings  
  
 访问类型：只读  
  
 通道池设置。  
  
### <a name="maxacceptedchannels"></a>MaxAcceptedChannels  
 数据类型：sint32  
  
 访问类型：只读  
  
 接受的最大通道数。  
  
### <a name="packetroutable"></a>PacketRoutable  
 数据类型：Boolean  
  
 访问类型：只读  
  
 一个值，该值指示数据包是否可路由。  
  
## <a name="requirements"></a>要求  
  
|MOF|已在 Servicemodel.mof 中声明。|  
|---------|-----------------------------------|  
|命名空间|已在 root\ServiceModel 中定义|  
  
## <a name="see-also"></a>请参阅  
 <xref:System.ServiceModel.Channels.OneWayBindingElement>
