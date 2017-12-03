---
title: System.ServiceModel.MessageProcessingPaused
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 36b5302a-93cc-478a-9bb2-8a1601fba1df
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 33d05eaa94ec0efdf6d18d03d9d38bda6f0c9eb7
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="systemservicemodelmessageprocessingpaused"></a><span data-ttu-id="f684a-102">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="f684a-102">System.ServiceModel.MessageProcessingPaused</span></span>
<span data-ttu-id="f684a-103">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="f684a-103">System.ServiceModel.MessageProcessingPaused</span></span>  
  
## <a name="description"></a><span data-ttu-id="f684a-104">描述</span><span class="sxs-lookup"><span data-stu-id="f684a-104">Description</span></span>  
 <span data-ttu-id="f684a-105">线程在处理消息时切换。</span><span class="sxs-lookup"><span data-stu-id="f684a-105">The threads were switched while processing a message.</span></span>  
  
 <span data-ttu-id="f684a-106">消息处理可以因为以下原因而暂停：</span><span class="sxs-lookup"><span data-stu-id="f684a-106">Message processing can be paused by the following reasons:</span></span>  
  
-   <span data-ttu-id="f684a-107">ConcurrencyMode 为 single 或 reentrant，并且服务正在处理另一条消息。</span><span class="sxs-lookup"><span data-stu-id="f684a-107">ConcurrencyMode is single or reentrant, and the service is processing another message.</span></span>  
  
-   <span data-ttu-id="f684a-108">启用了事务，并且服务正在处理另一个事务。</span><span class="sxs-lookup"><span data-stu-id="f684a-108">Transaction is enabled and the service is processing another transaction.</span></span>  
  
-   <span data-ttu-id="f684a-109">同步上下文不是最新。</span><span class="sxs-lookup"><span data-stu-id="f684a-109">Synchronization context is not current.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f684a-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f684a-110">See Also</span></span>  
 [<span data-ttu-id="f684a-111">跟踪</span><span class="sxs-lookup"><span data-stu-id="f684a-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="f684a-112">使用跟踪来排查你的应用程序</span><span class="sxs-lookup"><span data-stu-id="f684a-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="f684a-113">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="f684a-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
