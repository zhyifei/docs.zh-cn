---
title: System.ServiceModel.MessageClosedAgain
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 24c274d4-65cd-4c91-9869-bc6eb34ef979
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7f3963fe28ccaf55b3946254e395b770619c8f22
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="systemservicemodelmessageclosedagain"></a><span data-ttu-id="00e87-102">System.ServiceModel.MessageClosedAgain</span><span class="sxs-lookup"><span data-stu-id="00e87-102">System.ServiceModel.MessageClosedAgain</span></span>
<span data-ttu-id="00e87-103">System.ServiceModel.MessageClosedAgain</span><span class="sxs-lookup"><span data-stu-id="00e87-103">System.ServiceModel.MessageClosedAgain</span></span>  
  
## <a name="description"></a><span data-ttu-id="00e87-104">描述</span><span class="sxs-lookup"><span data-stu-id="00e87-104">Description</span></span>  
 <span data-ttu-id="00e87-105">已再次关闭消息。</span><span class="sxs-lookup"><span data-stu-id="00e87-105">A message was closed again.</span></span>  
  
 <span data-ttu-id="00e87-106">消息只应关闭一次。</span><span class="sxs-lookup"><span data-stu-id="00e87-106">A message should be closed only once.</span></span> <span data-ttu-id="00e87-107">如果用户扩展代码发出此跟踪，则指示用户扩展代码正在关闭一个已经关闭的消息。</span><span class="sxs-lookup"><span data-stu-id="00e87-107">If this trace is being emitted in user extension code, it indicates that the user extension code is closing a message that has already been closed.</span></span> <span data-ttu-id="00e87-108">如果通过产品代码发出此跟踪，则指示用户扩展代码可能正在过早地关闭消息。</span><span class="sxs-lookup"><span data-stu-id="00e87-108">If this trace is being emitted through product code, it indicates that the user extension code could potentially be closing a message too early.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00e87-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="00e87-109">See Also</span></span>  
 [<span data-ttu-id="00e87-110">跟踪</span><span class="sxs-lookup"><span data-stu-id="00e87-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="00e87-111">使用跟踪来排查你的应用程序</span><span class="sxs-lookup"><span data-stu-id="00e87-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="00e87-112">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="00e87-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
