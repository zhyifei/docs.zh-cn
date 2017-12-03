---
title: Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3e8fc825-9f22-47e7-9c16-d64ef291c932
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 98ce61e4a46f8853e61e0ef44fdc78cf3e94431a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="microsofttransactionstransactionbridgevolatileparticipantindoubt"></a><span data-ttu-id="f980a-102">Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt</span><span class="sxs-lookup"><span data-stu-id="f980a-102">Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt</span></span>
<span data-ttu-id="f980a-103">协议服务从无法识别的可变参与者接收到已准备或重播消息。</span><span class="sxs-lookup"><span data-stu-id="f980a-103">The WS-AT protocol service received a Prepared or Replay message from an unrecognized volatile participant.</span></span> <span data-ttu-id="f980a-104">已向参与者返回错误，声明事务的结果不确定。</span><span class="sxs-lookup"><span data-stu-id="f980a-104">A fault was returned to the participant, declares that the transaction's outcome is in doubt.</span></span>  
  
## <a name="description"></a><span data-ttu-id="f980a-105">描述</span><span class="sxs-lookup"><span data-stu-id="f980a-105">Description</span></span>  
 <span data-ttu-id="f980a-106">在本地事务管理器从它已经忘记的可变参与者接收到已准备或重播消息时进行跟踪。</span><span class="sxs-lookup"><span data-stu-id="f980a-106">Traced when the local Transaction Manager receives a Prepared or Replay message from a Volatile enlistment that it has already forgotten.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="f980a-107">疑难解答</span><span class="sxs-lookup"><span data-stu-id="f980a-107">Troubleshooting</span></span>  
 <span data-ttu-id="f980a-108">调查来自可变参与者的最新消息的可能原因。</span><span class="sxs-lookup"><span data-stu-id="f980a-108">Investigate potential causes of late messages coming from the Volatile participant.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f980a-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f980a-109">See Also</span></span>  
 [<span data-ttu-id="f980a-110">跟踪</span><span class="sxs-lookup"><span data-stu-id="f980a-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="f980a-111">使用跟踪来排查你的应用程序</span><span class="sxs-lookup"><span data-stu-id="f980a-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="f980a-112">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="f980a-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
