---
title: WF 中的运行时活动
ms.date: 03/30/2017
ms.assetid: e5ae8c31-19bc-4655-88b3-6b75cd6a1bd5
ms.openlocfilehash: 7981d3f75c8fd2d0ddd2ae0233f425c2907c270c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938094"
---
# <a name="runtime-activities-in-wf"></a><span data-ttu-id="a2165-102">WF 中的运行时活动</span><span class="sxs-lookup"><span data-stu-id="a2165-102">Runtime Activities in WF</span></span>
[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] <span data-ttu-id="a2165-103">为访问工作流运行时的功能提供若干系统提供的活动，如持久性和终止。</span><span class="sxs-lookup"><span data-stu-id="a2165-103">provides several system-provided activities for accessing the features of the workflow runtime, such as persistence and termination.</span></span>  
  
|<span data-ttu-id="a2165-104">活动</span><span class="sxs-lookup"><span data-stu-id="a2165-104">Activity</span></span>|<span data-ttu-id="a2165-105">描述</span><span class="sxs-lookup"><span data-stu-id="a2165-105">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.Activities.Statements.Persist>|<span data-ttu-id="a2165-106">显式请求工作流持久保存其状态。</span><span class="sxs-lookup"><span data-stu-id="a2165-106">Explicitly requests that the workflow persist its state.</span></span>|  
|<xref:System.Activities.Statements.TerminateWorkflow>|<span data-ttu-id="a2165-107">终止运行工作流实例。</span><span class="sxs-lookup"><span data-stu-id="a2165-107">Terminates the running workflow instance.</span></span>|  
|<xref:System.Activities.Statements.NoPersistScope>|<span data-ttu-id="a2165-108">可防止子活动持久化的容器活动。</span><span class="sxs-lookup"><span data-stu-id="a2165-108">A container activity that prevents child activities from persisting.</span></span>|
