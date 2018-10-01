---
title: 应用程序开发中的 PNRP
ms.date: 03/30/2017
ms.assetid: 265615d6-4423-4b5d-8626-752e456f4f4e
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 0f86b2569b9d4864586a0a7daea0ae5d3b901fd4
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/27/2018
ms.locfileid: "47205260"
---
# <a name="pnrp-in-application-development"></a>应用程序开发中的 PNRP
Windows Vista 中，网络应用程序可以通过简化的 PNRP 应用程序编程接口 (API) 访问名称发布和解析函数。  
  
## <a name="implementing-the-peer-name-resolution-protocol"></a>执行对等名称解析协议  
 借助简化的 PNRP API，无需显式指定云注册名称和地址，PNRP 组件自动决定要加入的合适的云以及要在云中发布的地址。  
  
 对于 Windows Vista 中高度简化的 PNRP 名称解析, PNRP 名称现已集成到 getaddrinfo() Windows 套接字函数。 若要使用 PNRP 将名称解析为 IPv6 地址，应用程序可以使用 getaddrinfo() 函数解析完全限定的域名 (FQDN) name.prnp.net，其中名称是正在解析的对等名称。 pnrp.net 域是 Windows Vista 中保留用于 PNRP 名称解析的域。  
  
 PeerToPeer 应用程序之间传递的消息仍由基础体系结构处理，例如 PeerChannel 和 WCF [大型数据和流](https://go.microsoft.com/fwlink/?LinkID=179652)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Net.PeerToPeer>
