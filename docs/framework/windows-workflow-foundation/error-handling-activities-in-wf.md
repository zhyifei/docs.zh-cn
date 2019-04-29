---
title: WF 中的错误处理活动
ms.date: 03/30/2017
ms.assetid: 24b68bd3-cef5-4413-ab82-2e2625f209aa
ms.openlocfilehash: 410c481745cc62a55a2b6e840d82b01fcc7f5766
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774018"
---
# <a name="error-handling-activities-in-wf"></a><span data-ttu-id="0375f-102">WF 中的错误处理活动</span><span class="sxs-lookup"><span data-stu-id="0375f-102">Error Handling Activities in WF</span></span>
[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]<span data-ttu-id="0375f-103">提供多个系统提供的活动，用于实现错误处理和恢复。</span><span class="sxs-lookup"><span data-stu-id="0375f-103">provides several system-provided activities for implementing error handling and recovery.</span></span> <span data-ttu-id="0375f-104">有关更多信息，请参见 [异常](exceptions.md)中定义的接口的私有 C++ 特定实现。</span><span class="sxs-lookup"><span data-stu-id="0375f-104">For more information, see [Exceptions](exceptions.md).</span></span>  
  
## <a name="error-handling-activities"></a><span data-ttu-id="0375f-105">错误处理活动</span><span class="sxs-lookup"><span data-stu-id="0375f-105">Error handling activities</span></span>  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.Rethrow>|<span data-ttu-id="0375f-106">重新引发从 `TryCatch` 活动中引发的最后一个异常。</span><span class="sxs-lookup"><span data-stu-id="0375f-106">Rethrows the last exception thrown from within a `TryCatch` activity.</span></span>|  
|<xref:System.Activities.Statements.Throw>|<span data-ttu-id="0375f-107">引发异常。</span><span class="sxs-lookup"><span data-stu-id="0375f-107">Throws an exception.</span></span>|  
|<xref:System.Activities.Statements.TryCatch>|<span data-ttu-id="0375f-108">实现异常处理。</span><span class="sxs-lookup"><span data-stu-id="0375f-108">Implements exception handling.</span></span>|
