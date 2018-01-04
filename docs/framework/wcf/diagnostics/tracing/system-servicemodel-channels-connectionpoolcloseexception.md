---
title: System.ServiceModel.Channels.ConnectionPoolCloseException
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8358898e-129e-4fac-a6bf-bf3aa4293ae2
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c7a134a60656c6ee237203b69e1bce40656f13d2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="systemservicemodelchannelsconnectionpoolcloseexception"></a><span data-ttu-id="a295e-102">System.ServiceModel.Channels.ConnectionPoolCloseException</span><span class="sxs-lookup"><span data-stu-id="a295e-102">System.ServiceModel.Channels.ConnectionPoolCloseException</span></span>
<span data-ttu-id="a295e-103">关闭此连接池中的连接时发生异常。</span><span class="sxs-lookup"><span data-stu-id="a295e-103">An exception occurred while closing the connections in this connection pool.</span></span>  
  
## <a name="description"></a><span data-ttu-id="a295e-104">描述</span><span class="sxs-lookup"><span data-stu-id="a295e-104">Description</span></span>  
 <span data-ttu-id="a295e-105">此错误级别跟踪指示当关闭由 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 的连接池功能使用的连接池时发生了错误。</span><span class="sxs-lookup"><span data-stu-id="a295e-105">This error level trace indicates that an error has occurred while closing the connection pools used by [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]’s connection pooling feature.</span></span> <span data-ttu-id="a295e-106">一种可能的原因是一个池连接或一组池连接在 CloseTimeout 内未成功关闭。</span><span class="sxs-lookup"><span data-stu-id="a295e-106">One possible reason for this is an unsuccessful closure of a pooled connection, or a set of pooled connections within the CloseTimeout.</span></span> <span data-ttu-id="a295e-107">当引发此异常时，将中止该池内所有剩余的未关闭连接，并放弃其他池内的未关闭连接。</span><span class="sxs-lookup"><span data-stu-id="a295e-107">When this exception is thrown, any remaining unclosed connections within that pool are aborted; unclosed connections within other pools are abandoned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a295e-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="a295e-108">See Also</span></span>  
 [<span data-ttu-id="a295e-109">跟踪</span><span class="sxs-lookup"><span data-stu-id="a295e-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="a295e-110">使用跟踪来排除应用程序故障</span><span class="sxs-lookup"><span data-stu-id="a295e-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="a295e-111">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="a295e-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
