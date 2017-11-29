---
title: System.ServiceModel.Channels.FailedPipeConnect
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a827e0f-fb91-46bb-bd54-926d4b74d8a6
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9a64f5885fd32d2486c90ebe4f8e0c739a025d0f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="systemservicemodelchannelsfailedpipeconnect"></a><span data-ttu-id="c6f37-102">System.ServiceModel.Channels.FailedPipeConnect</span><span class="sxs-lookup"><span data-stu-id="c6f37-102">System.ServiceModel.Channels.FailedPipeConnect</span></span>
<span data-ttu-id="c6f37-103">尝试连接到指定的管道终结点失败。</span><span class="sxs-lookup"><span data-stu-id="c6f37-103">An attempt to connect to the named pipe endpoint failed.</span></span> <span data-ttu-id="c6f37-104">将在指定的超时期限内再次进行尝试。</span><span class="sxs-lookup"><span data-stu-id="c6f37-104">Another attempt is made within the specified timeout period.</span></span>  
  
## <a name="description"></a><span data-ttu-id="c6f37-105">描述</span><span class="sxs-lookup"><span data-stu-id="c6f37-105">Description</span></span>  
 <span data-ttu-id="c6f37-106">此信息跟踪指示未能连接到指定的管道终结点。</span><span class="sxs-lookup"><span data-stu-id="c6f37-106">This informational trace indicates a failure to connect to a named pipe endpoint.</span></span> <span data-ttu-id="c6f37-107">如果未找到指定的管道终结点或指定的管道终结点正忙，则可能会发生此情况。</span><span class="sxs-lookup"><span data-stu-id="c6f37-107">This could happen if the named pipe endpoint is not found or is busy.</span></span> <span data-ttu-id="c6f37-108">将进行更多的尝试（两次尝试之间的时间较短），直到尝试成功或 OpenTimeout 过期。</span><span class="sxs-lookup"><span data-stu-id="c6f37-108">Additional attempts are made, each separated by a short amount of time, until one succeeds or the OpenTimeout expires.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6f37-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c6f37-109">See Also</span></span>  
 [<span data-ttu-id="c6f37-110">跟踪</span><span class="sxs-lookup"><span data-stu-id="c6f37-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="c6f37-111">使用跟踪来排查你的应用程序</span><span class="sxs-lookup"><span data-stu-id="c6f37-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="c6f37-112">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="c6f37-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
