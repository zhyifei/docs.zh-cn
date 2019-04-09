---
title: System.ServiceModel.Activation.WebHostServiceCloseFailed
ms.date: 03/30/2017
ms.assetid: 3cab9856-a5cf-4f0e-a0cb-89425e368f8e
ms.openlocfilehash: afe84db3d4df8914ff1ed001b064439d581ead89
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59085384"
---
# <a name="systemservicemodelactivationwebhostserviceclosefailed"></a><span data-ttu-id="5b868-102">System.ServiceModel.Activation.WebHostServiceCloseFailed</span><span class="sxs-lookup"><span data-stu-id="5b868-102">System.ServiceModel.Activation.WebHostServiceCloseFailed</span></span>
<span data-ttu-id="5b868-103">当服务无法正常关闭并中止时发生。</span><span class="sxs-lookup"><span data-stu-id="5b868-103">Occurs when a service cannot be closed gracefully and is aborted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="5b868-104">描述</span><span class="sxs-lookup"><span data-stu-id="5b868-104">Description</span></span>  
 <span data-ttu-id="5b868-105">此错误代码仅出现在日志文件中。</span><span class="sxs-lookup"><span data-stu-id="5b868-105">This error code only appears in the log file.</span></span> <span data-ttu-id="5b868-106">它通常指示编程错误，例如，在已经调用 Abort 之后尝试关闭服务的时候。</span><span class="sxs-lookup"><span data-stu-id="5b868-106">It usually indicates a programming error, for example, when you try to close a service after Abort has already been called.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="5b868-107">疑难解答</span><span class="sxs-lookup"><span data-stu-id="5b868-107">Troubleshooting</span></span>  
 <span data-ttu-id="5b868-108">请检查应用程序源代码。</span><span class="sxs-lookup"><span data-stu-id="5b868-108">Check the application source code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b868-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="5b868-109">See also</span></span>

- [<span data-ttu-id="5b868-110">跟踪</span><span class="sxs-lookup"><span data-stu-id="5b868-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="5b868-111">使用跟踪来排除应用程序故障</span><span class="sxs-lookup"><span data-stu-id="5b868-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="5b868-112">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="5b868-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
