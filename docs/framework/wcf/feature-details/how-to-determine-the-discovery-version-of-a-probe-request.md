---
title: 如何：确定探测请求的发现版本
ms.date: 03/30/2017
ms.assetid: b3c4e2e2-2957-4074-ae6a-776a5ca84278
ms.openlocfilehash: 8fbc3936278a5c6f403f48b59390c69c64378004
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/28/2019
ms.locfileid: "67425272"
---
# <a name="how-todetermine-the-discovery-version-of-a-probe-request"></a>如何：确定探测请求的发现版本

发现代理可能会公开使用不同发现版本的多个发现终结点。 当 UDP 多播探测请求到达代理时，代理应响应多播的禁止消息。 若要执行此操作，它需要知道请求的发现版本。

## <a name="to-determine-the-discovery-version-of-a-probe-request"></a>确定探测请求的发现版本

在响应探测请求的方法 (例如<xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A?displayProperty=nameWithType>) 使用静态<xref:System.ServiceModel.OperationContext.Current%2A?displayProperty=nameWithType>属性来搜索<xref:System.ServiceModel.Discovery.DiscoveryOperationContextExtension>，如下面的代码中所示。

```csharp
DiscoveryOperationContextExtension doce = OperationContext.Current.Extensions.Find<DiscoveryOperationContextExtension>();
// Access the discovery version from the DiscoveryOperationContextExtension
doce.DiscoveryVersion;
```

## <a name="see-also"></a>请参阅

- <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion%2A>
- [实现发现代理](../../../../docs/framework/wcf/feature-details/implementing-a-discovery-proxy.md)
