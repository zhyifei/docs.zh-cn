---
title: WF 中的运行时活动
ms.date: 03/30/2017
ms.assetid: e5ae8c31-19bc-4655-88b3-6b75cd6a1bd5
ms.openlocfilehash: 7981d3f75c8fd2d0ddd2ae0233f425c2907c270c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="runtime-activities-in-wf"></a>WF 中的运行时活动
[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] 为访问工作流运行时的功能提供若干系统提供的活动，如持久性和终止。  
  
|Activity|描述|  
|--------------|-----------------|  
|<xref:System.Activities.Statements.Persist>|显式请求工作流持久保存其状态。|  
|<xref:System.Activities.Statements.TerminateWorkflow>|终止运行工作流实例。|  
|<xref:System.Activities.Statements.NoPersistScope>|可防止子活动持久化的容器活动。|
