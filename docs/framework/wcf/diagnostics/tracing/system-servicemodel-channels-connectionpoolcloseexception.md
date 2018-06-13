---
title: System.ServiceModel.Channels.ConnectionPoolCloseException
ms.date: 03/30/2017
ms.assetid: 8358898e-129e-4fac-a6bf-bf3aa4293ae2
ms.openlocfilehash: f3474fc1bb0ed0d11df6289ed6470447d815f5ce
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33475746"
---
# <a name="systemservicemodelchannelsconnectionpoolcloseexception"></a><span data-ttu-id="b6299-102">System.ServiceModel.Channels.ConnectionPoolCloseException</span><span class="sxs-lookup"><span data-stu-id="b6299-102">System.ServiceModel.Channels.ConnectionPoolCloseException</span></span>
<span data-ttu-id="b6299-103">关闭此连接池中的连接时发生异常。</span><span class="sxs-lookup"><span data-stu-id="b6299-103">An exception occurred while closing the connections in this connection pool.</span></span>  
  
## <a name="description"></a><span data-ttu-id="b6299-104">描述</span><span class="sxs-lookup"><span data-stu-id="b6299-104">Description</span></span>  
 <span data-ttu-id="b6299-105">此错误级别跟踪指示关闭 Windows Communication Foundation (WCF) 的连接池功能使用的连接池时已发生错误。</span><span class="sxs-lookup"><span data-stu-id="b6299-105">This error level trace indicates that an error has occurred while closing the connection pools used by Windows Communication Foundation (WCF)’s connection pooling feature.</span></span> <span data-ttu-id="b6299-106">一种可能的原因是一个池连接或一组池连接在 CloseTimeout 内未成功关闭。</span><span class="sxs-lookup"><span data-stu-id="b6299-106">One possible reason for this is an unsuccessful closure of a pooled connection, or a set of pooled connections within the CloseTimeout.</span></span> <span data-ttu-id="b6299-107">当引发此异常时，将中止该池内所有剩余的未关闭连接，并放弃其他池内的未关闭连接。</span><span class="sxs-lookup"><span data-stu-id="b6299-107">When this exception is thrown, any remaining unclosed connections within that pool are aborted; unclosed connections within other pools are abandoned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6299-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="b6299-108">See Also</span></span>  
 [<span data-ttu-id="b6299-109">跟踪</span><span class="sxs-lookup"><span data-stu-id="b6299-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="b6299-110">使用跟踪来排除应用程序故障</span><span class="sxs-lookup"><span data-stu-id="b6299-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="b6299-111">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="b6299-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
