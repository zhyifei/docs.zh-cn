---
title: System.ServiceModel.MessageProcessingPaused
ms.date: 03/30/2017
ms.assetid: 36b5302a-93cc-478a-9bb2-8a1601fba1df
ms.openlocfilehash: ac1dacef94d6446aa407e4a390b9561d033af1bb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59087464"
---
# <a name="systemservicemodelmessageprocessingpaused"></a><span data-ttu-id="bf60e-102">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="bf60e-102">System.ServiceModel.MessageProcessingPaused</span></span>
<span data-ttu-id="bf60e-103">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="bf60e-103">System.ServiceModel.MessageProcessingPaused</span></span>  
  
## <a name="description"></a><span data-ttu-id="bf60e-104">描述</span><span class="sxs-lookup"><span data-stu-id="bf60e-104">Description</span></span>  
 <span data-ttu-id="bf60e-105">线程在处理消息时切换。</span><span class="sxs-lookup"><span data-stu-id="bf60e-105">The threads were switched while processing a message.</span></span>  
  
 <span data-ttu-id="bf60e-106">消息处理可以因为以下原因而暂停：</span><span class="sxs-lookup"><span data-stu-id="bf60e-106">Message processing can be paused by the following reasons:</span></span>  
  
-   <span data-ttu-id="bf60e-107">ConcurrencyMode 为 single 或 reentrant，并且服务正在处理另一条消息。</span><span class="sxs-lookup"><span data-stu-id="bf60e-107">ConcurrencyMode is single or reentrant, and the service is processing another message.</span></span>  
  
-   <span data-ttu-id="bf60e-108">启用了事务，并且服务正在处理另一个事务。</span><span class="sxs-lookup"><span data-stu-id="bf60e-108">Transaction is enabled and the service is processing another transaction.</span></span>  
  
-   <span data-ttu-id="bf60e-109">同步上下文不是最新。</span><span class="sxs-lookup"><span data-stu-id="bf60e-109">Synchronization context is not current.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf60e-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="bf60e-110">See also</span></span>

- [<span data-ttu-id="bf60e-111">跟踪</span><span class="sxs-lookup"><span data-stu-id="bf60e-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="bf60e-112">使用跟踪来排除应用程序故障</span><span class="sxs-lookup"><span data-stu-id="bf60e-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="bf60e-113">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="bf60e-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
