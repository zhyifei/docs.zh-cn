---
title: System.ServiceModel.Channels.FailedPipeConnect
ms.date: 03/30/2017
ms.assetid: 9a827e0f-fb91-46bb-bd54-926d4b74d8a6
ms.openlocfilehash: 472821d880433cd6a3292838a48bcb0b5bb34c43
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59152290"
---
# <a name="systemservicemodelchannelsfailedpipeconnect"></a>System.ServiceModel.Channels.FailedPipeConnect
尝试连接到指定的管道终结点失败。 将在指定的超时期限内再次进行尝试。  
  
## <a name="description"></a>描述  
 此信息跟踪指示未能连接到指定的管道终结点。 如果未找到指定的管道终结点或指定的管道终结点正忙，则可能会发生此情况。 将进行更多的尝试（两次尝试之间的时间较短），直到尝试成功或 OpenTimeout 过期。  
  
## <a name="see-also"></a>请参阅

- [跟踪](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [使用跟踪来排除应用程序故障](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [管理和诊断](../../../../../docs/framework/wcf/diagnostics/index.md)
