---
title: System.ServiceModel.Activation.WebHostServiceCloseFailed
ms.date: 03/30/2017
ms.assetid: 3cab9856-a5cf-4f0e-a0cb-89425e368f8e
ms.openlocfilehash: 0ed3a9a1c16247f94c739a43d84d51e4750b3c2f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54597653"
---
# <a name="systemservicemodelactivationwebhostserviceclosefailed"></a><span data-ttu-id="e77b8-102">System.ServiceModel.Activation.WebHostServiceCloseFailed</span><span class="sxs-lookup"><span data-stu-id="e77b8-102">System.ServiceModel.Activation.WebHostServiceCloseFailed</span></span>
<span data-ttu-id="e77b8-103">当服务无法正常关闭并中止时发生。</span><span class="sxs-lookup"><span data-stu-id="e77b8-103">Occurs when a service cannot be closed gracefully and is aborted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="e77b8-104">描述</span><span class="sxs-lookup"><span data-stu-id="e77b8-104">Description</span></span>  
 <span data-ttu-id="e77b8-105">此错误代码仅出现在日志文件中。</span><span class="sxs-lookup"><span data-stu-id="e77b8-105">This error code only appears in the log file.</span></span> <span data-ttu-id="e77b8-106">它通常指示编程错误，例如，在已经调用 Abort 之后尝试关闭服务的时候。</span><span class="sxs-lookup"><span data-stu-id="e77b8-106">It usually indicates a programming error, for example, when you try to close a service after Abort has already been called.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="e77b8-107">疑难解答</span><span class="sxs-lookup"><span data-stu-id="e77b8-107">Troubleshooting</span></span>  
 <span data-ttu-id="e77b8-108">请检查应用程序源代码。</span><span class="sxs-lookup"><span data-stu-id="e77b8-108">Check the application source code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e77b8-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="e77b8-109">See also</span></span>
- [<span data-ttu-id="e77b8-110">跟踪</span><span class="sxs-lookup"><span data-stu-id="e77b8-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="e77b8-111">使用跟踪来排除应用程序故障</span><span class="sxs-lookup"><span data-stu-id="e77b8-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="e77b8-112">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="e77b8-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
