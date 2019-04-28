---
title: System.ServiceModel.Channels.ConnectionPoolCloseException
ms.date: 03/30/2017
ms.assetid: 8358898e-129e-4fac-a6bf-bf3aa4293ae2
ms.openlocfilehash: 3dd28276cd3a39497c0387f5b9d0adec23d07c37
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61666828"
---
# <a name="systemservicemodelchannelsconnectionpoolcloseexception"></a><span data-ttu-id="152fe-102">System.ServiceModel.Channels.ConnectionPoolCloseException</span><span class="sxs-lookup"><span data-stu-id="152fe-102">System.ServiceModel.Channels.ConnectionPoolCloseException</span></span>
<span data-ttu-id="152fe-103">关闭此连接池中的连接时发生异常。</span><span class="sxs-lookup"><span data-stu-id="152fe-103">An exception occurred while closing the connections in this connection pool.</span></span>  
  
## <a name="description"></a><span data-ttu-id="152fe-104">描述</span><span class="sxs-lookup"><span data-stu-id="152fe-104">Description</span></span>  
 <span data-ttu-id="152fe-105">此错误级别跟踪指示错误发生时关闭由 Windows Communication Foundation (WCF) 的连接池功能使用的连接池。</span><span class="sxs-lookup"><span data-stu-id="152fe-105">This error level trace indicates that an error has occurred while closing the connection pools used by Windows Communication Foundation (WCF)’s connection pooling feature.</span></span> <span data-ttu-id="152fe-106">一种可能的原因是一个池连接或一组池连接在 CloseTimeout 内未成功关闭。</span><span class="sxs-lookup"><span data-stu-id="152fe-106">One possible reason for this is an unsuccessful closure of a pooled connection, or a set of pooled connections within the CloseTimeout.</span></span> <span data-ttu-id="152fe-107">当引发此异常时，将中止该池内所有剩余的未关闭连接，并放弃其他池内的未关闭连接。</span><span class="sxs-lookup"><span data-stu-id="152fe-107">When this exception is thrown, any remaining unclosed connections within that pool are aborted; unclosed connections within other pools are abandoned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="152fe-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="152fe-108">See also</span></span>

- [<span data-ttu-id="152fe-109">跟踪</span><span class="sxs-lookup"><span data-stu-id="152fe-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="152fe-110">使用跟踪来排除应用程序故障</span><span class="sxs-lookup"><span data-stu-id="152fe-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="152fe-111">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="152fe-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
