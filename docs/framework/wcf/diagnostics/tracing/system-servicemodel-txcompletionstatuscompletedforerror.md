---
title: System.ServiceModel.TxCompletionStatusCompletedForError
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8ade4722-a6d5-471c-b960-1cfea4ea2aa9
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f6a05f838e37d5cd56a572dc73b032bec2d2abea
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="systemservicemodeltxcompletionstatuscompletedforerror"></a><span data-ttu-id="601e5-102">System.ServiceModel.TxCompletionStatusCompletedForError</span><span class="sxs-lookup"><span data-stu-id="601e5-102">System.ServiceModel.TxCompletionStatusCompletedForError</span></span>
<span data-ttu-id="601e5-103">由于未处理的执行异常，导致指定操作的指定事务处于完成状态。</span><span class="sxs-lookup"><span data-stu-id="601e5-103">The specified transaction for the specified operation was completed due to an unhandled execution exception.</span></span>  
  
## <a name="description"></a><span data-ttu-id="601e5-104">描述</span><span class="sxs-lookup"><span data-stu-id="601e5-104">Description</span></span>  
 <span data-ttu-id="601e5-105">在尝试完成当前事务过程中发生错误时跟踪。</span><span class="sxs-lookup"><span data-stu-id="601e5-105">Traced when an error occurs during an attempt to complete the current transaction.</span></span> <span data-ttu-id="601e5-106">在将答复或错误发送给调用方之前，会发生此情况。</span><span class="sxs-lookup"><span data-stu-id="601e5-106">This happens before a reply or fault is sent to the caller.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="601e5-107">疑难解答</span><span class="sxs-lookup"><span data-stu-id="601e5-107">Troubleshooting</span></span>  
 <span data-ttu-id="601e5-108">检查跟踪的消息，以查找异常消息和所有可操作的项。</span><span class="sxs-lookup"><span data-stu-id="601e5-108">Inspect the traced message for the exception message and any actionable items.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="601e5-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="601e5-109">See Also</span></span>  
 [<span data-ttu-id="601e5-110">跟踪</span><span class="sxs-lookup"><span data-stu-id="601e5-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="601e5-111">使用跟踪来排查你的应用程序</span><span class="sxs-lookup"><span data-stu-id="601e5-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="601e5-112">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="601e5-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
