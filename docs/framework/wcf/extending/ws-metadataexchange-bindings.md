---
title: WS-MetadataExchange 绑定
ms.date: 03/30/2017
ms.assetid: 10f8de5d-b81d-4ea7-b37e-7f2c00c39714
ms.openlocfilehash: 384e5bb05ba4263f245f6901b84e2388ea19bd73
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="ws-metadataexchange-bindings"></a>WS-MetadataExchange 绑定
本主题说明如何为各种传输构造默认的元数据交换绑定。  
  
## <a name="the-default-bindings"></a>默认绑定  
  
|默认绑定名称|绑定的构造方式|  
|--------------------------|------------------------------------|  
|MexHttpBinding|一个禁用传输级安全性的 <xref:System.ServiceModel.WSHttpBinding>。|  
|MexHttpsBinding|一个支持传输级安全性的 <xref:System.ServiceModel.WSHttpBinding>。|  
|MexNamedPipeBinding|一个 <xref:System.ServiceModel.Channels.CustomBinding>，它具有使用默认值的 <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>。|  
|MexTcpBinding|一个 <xref:System.ServiceModel.Channels.CustomBinding>，它具有使用默认值的 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>。|
