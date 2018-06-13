---
title: WF 中的运行时活动
ms.date: 03/30/2017
ms.assetid: e5ae8c31-19bc-4655-88b3-6b75cd6a1bd5
ms.openlocfilehash: 7981d3f75c8fd2d0ddd2ae0233f425c2907c270c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33513030"
---
# <a name="runtime-activities-in-wf"></a><span data-ttu-id="7e901-102">WF 中的运行时活动</span><span class="sxs-lookup"><span data-stu-id="7e901-102">Runtime Activities in WF</span></span>
[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]<span data-ttu-id="7e901-103"> 为访问工作流运行时的功能提供若干系统提供的活动，如持久性和终止。</span><span class="sxs-lookup"><span data-stu-id="7e901-103"> provides several system-provided activities for accessing the features of the workflow runtime, such as persistence and termination.</span></span>  
  
|<span data-ttu-id="7e901-104">Activity</span><span class="sxs-lookup"><span data-stu-id="7e901-104">Activity</span></span>|<span data-ttu-id="7e901-105">描述</span><span class="sxs-lookup"><span data-stu-id="7e901-105">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.Activities.Statements.Persist>|<span data-ttu-id="7e901-106">显式请求工作流持久保存其状态。</span><span class="sxs-lookup"><span data-stu-id="7e901-106">Explicitly requests that the workflow persist its state.</span></span>|  
|<xref:System.Activities.Statements.TerminateWorkflow>|<span data-ttu-id="7e901-107">终止运行工作流实例。</span><span class="sxs-lookup"><span data-stu-id="7e901-107">Terminates the running workflow instance.</span></span>|  
|<xref:System.Activities.Statements.NoPersistScope>|<span data-ttu-id="7e901-108">可防止子活动持久化的容器活动。</span><span class="sxs-lookup"><span data-stu-id="7e901-108">A container activity that prevents child activities from persisting.</span></span>|
