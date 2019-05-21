---
title: 将 NetTcpBinding 应用程序转换为对等通道应用程序
ms.date: 03/30/2017
ms.assetid: d4137292-a923-4b8f-8594-42276f2d3ce2
ms.openlocfilehash: 362945959a781fac360c42475148fee1e47a1183
ms.sourcegitcommit: ffd7dd79468a81bbb0d6449f6d65513e050c04c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/21/2019
ms.locfileid: "65960135"
---
# <a name="converting-a-nettcpbinding-application-to-a-peer-channel-application"></a>将 NetTcpBinding 应用程序转换为对等通道应用程序
可以创建使用 WinFX 使用描述连接的参数绑定的客户端之间的连接。 将.NET Framework 应用程序以使用对等连接转换需要进行客户端连接时支持此技术的绑定。 对等通道提供了一种称为 <xref:System.ServiceModel.NetPeerTcpBinding> 的绑定，其使用方式与 <xref:System.ServiceModel.NetTcpBinding> 类似。 关键区别包括指定解析程序服务和定义安全设置。  
  
 如果应用程序使用默认解析程序和安全设置，那么将基于客户端/服务器的标准应用程序转换为使用对等通道需要在应用程序配置文件中将绑定名称从“NetTcpBinding”更改为“NetPeerTcpBinding”，而无需更改应用程序基本代码。  
  
## <a name="see-also"></a>请参阅

- [生成对等通道应用程序](../../../../docs/framework/wcf/feature-details/building-a-peer-channel-application.md)
- [系统提供的绑定](../../../../docs/framework/wcf/system-provided-bindings.md)
