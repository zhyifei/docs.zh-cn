---
title: WF 中的错误处理活动
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 24b68bd3-cef5-4413-ab82-2e2625f209aa
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1c0459dd562f6292a8fe9a42f8b1b48cd175516a
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2018
---
# <a name="error-handling-activities-in-wf"></a><span data-ttu-id="7bb8c-102">WF 中的错误处理活动</span><span class="sxs-lookup"><span data-stu-id="7bb8c-102">Error Handling Activities in WF</span></span>
[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]<span data-ttu-id="7bb8c-103">提供多个系统提供的活动，用于实现错误处理和恢复。</span><span class="sxs-lookup"><span data-stu-id="7bb8c-103"> provides several system-provided activities for implementing error handling and recovery.</span></span> <span data-ttu-id="7bb8c-104">有关详细信息，请参阅[异常](../../../docs/framework/windows-workflow-foundation/exceptions.md)。</span><span class="sxs-lookup"><span data-stu-id="7bb8c-104">For more information, see [Exceptions](../../../docs/framework/windows-workflow-foundation/exceptions.md).</span></span>  
  
## <a name="error-handling-activities"></a><span data-ttu-id="7bb8c-105">错误处理活动</span><span class="sxs-lookup"><span data-stu-id="7bb8c-105">Error handling activities</span></span>  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.Rethrow>|<span data-ttu-id="7bb8c-106">重新引发从 `TryCatch` 活动中引发的最后一个异常。</span><span class="sxs-lookup"><span data-stu-id="7bb8c-106">Rethrows the last exception thrown from within a `TryCatch` activity.</span></span>|  
|<xref:System.Activities.Statements.Throw>|<span data-ttu-id="7bb8c-107">引发异常。</span><span class="sxs-lookup"><span data-stu-id="7bb8c-107">Throws an exception.</span></span>|  
|<xref:System.Activities.Statements.TryCatch>|<span data-ttu-id="7bb8c-108">实现异常处理。</span><span class="sxs-lookup"><span data-stu-id="7bb8c-108">Implements exception handling.</span></span>|
