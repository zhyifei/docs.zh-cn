---
title: Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt
ms.date: 03/30/2017
ms.assetid: 3e8fc825-9f22-47e7-9c16-d64ef291c932
ms.openlocfilehash: b25debfd9b1e6de6b93fd4dfa8b96925718d9d87
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54550833"
---
# <a name="microsofttransactionstransactionbridgevolatileparticipantindoubt"></a><span data-ttu-id="92354-102">Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt</span><span class="sxs-lookup"><span data-stu-id="92354-102">Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt</span></span>
<span data-ttu-id="92354-103">协议服务从无法识别的可变参与者接收到已准备或重播消息。</span><span class="sxs-lookup"><span data-stu-id="92354-103">The WS-AT protocol service received a Prepared or Replay message from an unrecognized volatile participant.</span></span> <span data-ttu-id="92354-104">已向参与者返回错误，声明事务的结果不确定。</span><span class="sxs-lookup"><span data-stu-id="92354-104">A fault was returned to the participant, declares that the transaction's outcome is in doubt.</span></span>  
  
## <a name="description"></a><span data-ttu-id="92354-105">描述</span><span class="sxs-lookup"><span data-stu-id="92354-105">Description</span></span>  
 <span data-ttu-id="92354-106">在本地事务管理器从它已经忘记的可变参与者接收到已准备或重播消息时进行跟踪。</span><span class="sxs-lookup"><span data-stu-id="92354-106">Traced when the local Transaction Manager receives a Prepared or Replay message from a Volatile enlistment that it has already forgotten.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="92354-107">疑难解答</span><span class="sxs-lookup"><span data-stu-id="92354-107">Troubleshooting</span></span>  
 <span data-ttu-id="92354-108">调查来自可变参与者的最新消息的可能原因。</span><span class="sxs-lookup"><span data-stu-id="92354-108">Investigate potential causes of late messages coming from the Volatile participant.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92354-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="92354-109">See also</span></span>
- [<span data-ttu-id="92354-110">跟踪</span><span class="sxs-lookup"><span data-stu-id="92354-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="92354-111">使用跟踪来排除应用程序故障</span><span class="sxs-lookup"><span data-stu-id="92354-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="92354-112">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="92354-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
