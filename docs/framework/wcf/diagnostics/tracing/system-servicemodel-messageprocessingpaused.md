---
title: System.ServiceModel.MessageProcessingPaused
ms.date: 03/30/2017
ms.assetid: 36b5302a-93cc-478a-9bb2-8a1601fba1df
ms.openlocfilehash: ac1dacef94d6446aa407e4a390b9561d033af1bb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59087464"
---
# <a name="systemservicemodelmessageprocessingpaused"></a><span data-ttu-id="1ef68-102">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="1ef68-102">System.ServiceModel.MessageProcessingPaused</span></span>
<span data-ttu-id="1ef68-103">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="1ef68-103">System.ServiceModel.MessageProcessingPaused</span></span>  
  
## <a name="description"></a><span data-ttu-id="1ef68-104">描述</span><span class="sxs-lookup"><span data-stu-id="1ef68-104">Description</span></span>  
 <span data-ttu-id="1ef68-105">线程在处理消息时切换。</span><span class="sxs-lookup"><span data-stu-id="1ef68-105">The threads were switched while processing a message.</span></span>  
  
 <span data-ttu-id="1ef68-106">消息处理可以因为以下原因而暂停：</span><span class="sxs-lookup"><span data-stu-id="1ef68-106">Message processing can be paused by the following reasons:</span></span>  
  
-   <span data-ttu-id="1ef68-107">ConcurrencyMode 为 single 或 reentrant，并且服务正在处理另一条消息。</span><span class="sxs-lookup"><span data-stu-id="1ef68-107">ConcurrencyMode is single or reentrant, and the service is processing another message.</span></span>  
  
-   <span data-ttu-id="1ef68-108">启用了事务，并且服务正在处理另一个事务。</span><span class="sxs-lookup"><span data-stu-id="1ef68-108">Transaction is enabled and the service is processing another transaction.</span></span>  
  
-   <span data-ttu-id="1ef68-109">同步上下文不是最新。</span><span class="sxs-lookup"><span data-stu-id="1ef68-109">Synchronization context is not current.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ef68-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="1ef68-110">See also</span></span>

- [<span data-ttu-id="1ef68-111">跟踪</span><span class="sxs-lookup"><span data-stu-id="1ef68-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="1ef68-112">使用跟踪来排除应用程序故障</span><span class="sxs-lookup"><span data-stu-id="1ef68-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="1ef68-113">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="1ef68-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
