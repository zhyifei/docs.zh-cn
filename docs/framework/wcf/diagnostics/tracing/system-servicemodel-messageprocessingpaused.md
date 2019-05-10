---
title: System.ServiceModel.MessageProcessingPaused
ms.date: 03/30/2017
ms.assetid: 36b5302a-93cc-478a-9bb2-8a1601fba1df
ms.openlocfilehash: 7dcdb9fdd6a283f692897cbbb49cd1f2d1dd661e
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64586794"
---
# <a name="systemservicemodelmessageprocessingpaused"></a><span data-ttu-id="8d4a0-102">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="8d4a0-102">System.ServiceModel.MessageProcessingPaused</span></span>
<span data-ttu-id="8d4a0-103">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="8d4a0-103">System.ServiceModel.MessageProcessingPaused</span></span>  
  
## <a name="description"></a><span data-ttu-id="8d4a0-104">描述</span><span class="sxs-lookup"><span data-stu-id="8d4a0-104">Description</span></span>  
 <span data-ttu-id="8d4a0-105">线程在处理消息时切换。</span><span class="sxs-lookup"><span data-stu-id="8d4a0-105">The threads were switched while processing a message.</span></span>  
  
 <span data-ttu-id="8d4a0-106">消息处理可以因为以下原因而暂停：</span><span class="sxs-lookup"><span data-stu-id="8d4a0-106">Message processing can be paused by the following reasons:</span></span>  
  
- <span data-ttu-id="8d4a0-107">ConcurrencyMode 为 single 或 reentrant，并且服务正在处理另一条消息。</span><span class="sxs-lookup"><span data-stu-id="8d4a0-107">ConcurrencyMode is single or reentrant, and the service is processing another message.</span></span>  
  
- <span data-ttu-id="8d4a0-108">启用了事务，并且服务正在处理另一个事务。</span><span class="sxs-lookup"><span data-stu-id="8d4a0-108">Transaction is enabled and the service is processing another transaction.</span></span>  
  
- <span data-ttu-id="8d4a0-109">同步上下文不是最新。</span><span class="sxs-lookup"><span data-stu-id="8d4a0-109">Synchronization context is not current.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d4a0-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="8d4a0-110">See also</span></span>

- [<span data-ttu-id="8d4a0-111">跟踪</span><span class="sxs-lookup"><span data-stu-id="8d4a0-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="8d4a0-112">使用跟踪来排除应用程序故障</span><span class="sxs-lookup"><span data-stu-id="8d4a0-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="8d4a0-113">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="8d4a0-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
