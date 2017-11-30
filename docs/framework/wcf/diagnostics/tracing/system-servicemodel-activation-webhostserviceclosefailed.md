---
title: System.ServiceModel.Activation.WebHostServiceCloseFailed
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3cab9856-a5cf-4f0e-a0cb-89425e368f8e
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 8550c30f74968d4f58d9a2fd1deac69bf9d3abe7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="systemservicemodelactivationwebhostserviceclosefailed"></a><span data-ttu-id="bb7d7-102">System.ServiceModel.Activation.WebHostServiceCloseFailed</span><span class="sxs-lookup"><span data-stu-id="bb7d7-102">System.ServiceModel.Activation.WebHostServiceCloseFailed</span></span>
<span data-ttu-id="bb7d7-103">当服务无法正常关闭并中止时发生。</span><span class="sxs-lookup"><span data-stu-id="bb7d7-103">Occurs when a service cannot be closed gracefully and is aborted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="bb7d7-104">描述</span><span class="sxs-lookup"><span data-stu-id="bb7d7-104">Description</span></span>  
 <span data-ttu-id="bb7d7-105">此错误代码仅出现在日志文件中。</span><span class="sxs-lookup"><span data-stu-id="bb7d7-105">This error code only appears in the log file.</span></span> <span data-ttu-id="bb7d7-106">它通常指示编程错误，例如，在已经调用 Abort 之后尝试关闭服务的时候。</span><span class="sxs-lookup"><span data-stu-id="bb7d7-106">It usually indicates a programming error, for example, when you try to close a service after Abort has already been called.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="bb7d7-107">疑难解答</span><span class="sxs-lookup"><span data-stu-id="bb7d7-107">Troubleshooting</span></span>  
 <span data-ttu-id="bb7d7-108">请检查应用程序源代码。</span><span class="sxs-lookup"><span data-stu-id="bb7d7-108">Check the application source code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb7d7-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bb7d7-109">See Also</span></span>  
 [<span data-ttu-id="bb7d7-110">跟踪</span><span class="sxs-lookup"><span data-stu-id="bb7d7-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="bb7d7-111">使用跟踪来排查你的应用程序</span><span class="sxs-lookup"><span data-stu-id="bb7d7-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="bb7d7-112">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="bb7d7-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
