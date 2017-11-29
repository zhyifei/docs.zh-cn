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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1176af676673e19eb2d8cd54cc4d2d254c7ba324
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="systemservicemodelmessageprocessingpaused"></a><span data-ttu-id="2b301-102">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="2b301-102">System.ServiceModel.MessageProcessingPaused</span></span>
<span data-ttu-id="2b301-103">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="2b301-103">System.ServiceModel.MessageProcessingPaused</span></span>  
  
## <a name="description"></a><span data-ttu-id="2b301-104">描述</span><span class="sxs-lookup"><span data-stu-id="2b301-104">Description</span></span>  
 <span data-ttu-id="2b301-105">线程在处理消息时切换。</span><span class="sxs-lookup"><span data-stu-id="2b301-105">The threads were switched while processing a message.</span></span>  
  
 <span data-ttu-id="2b301-106">消息处理可以因为以下原因而暂停：</span><span class="sxs-lookup"><span data-stu-id="2b301-106">Message processing can be paused by the following reasons:</span></span>  
  
-   <span data-ttu-id="2b301-107">ConcurrencyMode 为 single 或 reentrant，并且服务正在处理另一条消息。</span><span class="sxs-lookup"><span data-stu-id="2b301-107">ConcurrencyMode is single or reentrant, and the service is processing another message.</span></span>  
  
-   <span data-ttu-id="2b301-108">启用了事务，并且服务正在处理另一个事务。</span><span class="sxs-lookup"><span data-stu-id="2b301-108">Transaction is enabled and the service is processing another transaction.</span></span>  
  
-   <span data-ttu-id="2b301-109">同步上下文不是最新。</span><span class="sxs-lookup"><span data-stu-id="2b301-109">Synchronization context is not current.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b301-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2b301-110">See Also</span></span>  
 [<span data-ttu-id="2b301-111">跟踪</span><span class="sxs-lookup"><span data-stu-id="2b301-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="2b301-112">使用跟踪来排查你的应用程序</span><span class="sxs-lookup"><span data-stu-id="2b301-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="2b301-113">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="2b301-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
