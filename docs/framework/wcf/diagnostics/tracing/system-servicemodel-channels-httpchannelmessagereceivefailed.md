---
title: System.ServiceModel.Channels.HttpChannelMessageReceiveFailed
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9eb311da-fdcc-4dd3-9d85-05b3280dfdda
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 46bc39237f0a6f0b9b25b9616782ec3e97fa22ca
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="systemservicemodelchannelshttpchannelmessagereceivefailed"></a><span data-ttu-id="8d73e-102">System.ServiceModel.Channels.HttpChannelMessageReceiveFailed</span><span class="sxs-lookup"><span data-stu-id="8d73e-102">System.ServiceModel.Channels.HttpChannelMessageReceiveFailed</span></span>
<span data-ttu-id="8d73e-103">未能通过 HTTP 通道接收消息。</span><span class="sxs-lookup"><span data-stu-id="8d73e-103">Failed to receive a message over an HTTP channel.</span></span>  
  
## <a name="description"></a><span data-ttu-id="8d73e-104">描述</span><span class="sxs-lookup"><span data-stu-id="8d73e-104">Description</span></span>  
 <span data-ttu-id="8d73e-105">此跟踪可作为警告或错误发出。</span><span class="sxs-lookup"><span data-stu-id="8d73e-105">This trace can be emitted as a warning or an error.</span></span> <span data-ttu-id="8d73e-106">在这两种情况下，跟踪都是在未找到传入 HTTP 请求的兼容侦听器并丢弃了该 HTTP 请求时发出的。</span><span class="sxs-lookup"><span data-stu-id="8d73e-106">In both cases, the trace is emitted when a compatible listener is not found for an incoming HTTP request and the HTTP request is discarded.</span></span> <span data-ttu-id="8d73e-107">之所以会发生此情况，原因在于任何 HTTP 侦听器都未能识别请求的 HTTP 谓词，或是没有任何侦听器在请求的目标地址上进行侦听。</span><span class="sxs-lookup"><span data-stu-id="8d73e-107">This could happen because the request’s HTTP verb was not recognized by any HTTP listener, or because no listener was listening on the address the request was targeted for.</span></span> <span data-ttu-id="8d73e-108">在自承载情况下，跟踪会作为警告发出，如果服务是在 IIS 中承载的，则跟踪会作为错误发出。</span><span class="sxs-lookup"><span data-stu-id="8d73e-108">The trace is emitted as a warning in the self-hosted case, and as an error when the service is hosted in IIS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d73e-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="8d73e-109">See Also</span></span>  
 [<span data-ttu-id="8d73e-110">跟踪</span><span class="sxs-lookup"><span data-stu-id="8d73e-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="8d73e-111">使用跟踪来排除应用程序故障</span><span class="sxs-lookup"><span data-stu-id="8d73e-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="8d73e-112">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="8d73e-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
