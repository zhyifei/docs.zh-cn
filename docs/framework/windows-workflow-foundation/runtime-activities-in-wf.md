---
title: "WF 中的运行时活动"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e5ae8c31-19bc-4655-88b3-6b75cd6a1bd5
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 022f12448d697ba179fb3705f18962e6b0c44239
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="runtime-activities-in-wf"></a><span data-ttu-id="09c76-102">WF 中的运行时活动</span><span class="sxs-lookup"><span data-stu-id="09c76-102">Runtime Activities in WF</span></span>
[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]<span data-ttu-id="09c76-103"> 为访问工作流运行时的功能提供若干系统提供的活动，如持久性和终止。</span><span class="sxs-lookup"><span data-stu-id="09c76-103"> provides several system-provided activities for accessing the features of the workflow runtime, such as persistence and termination.</span></span>  
  
|<span data-ttu-id="09c76-104">Activity</span><span class="sxs-lookup"><span data-stu-id="09c76-104">Activity</span></span>|<span data-ttu-id="09c76-105">描述</span><span class="sxs-lookup"><span data-stu-id="09c76-105">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.Activities.Statements.Persist>|<span data-ttu-id="09c76-106">显式请求工作流持久保存其状态。</span><span class="sxs-lookup"><span data-stu-id="09c76-106">Explicitly requests that the workflow persist its state.</span></span>|  
|<xref:System.Activities.Statements.TerminateWorkflow>|<span data-ttu-id="09c76-107">终止运行工作流实例。</span><span class="sxs-lookup"><span data-stu-id="09c76-107">Terminates the running workflow instance.</span></span>|  
|<xref:System.Activities.Statements.NoPersistScope>|<span data-ttu-id="09c76-108">可防止子活动持久化的容器活动。</span><span class="sxs-lookup"><span data-stu-id="09c76-108">A container activity that prevents child activities from persisting.</span></span>|
