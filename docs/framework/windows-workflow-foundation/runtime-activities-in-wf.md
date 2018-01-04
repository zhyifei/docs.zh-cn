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
ms.workload: dotnet
ms.openlocfilehash: 3386138f01d4865b02ca821a30da68e5d73b64e0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="runtime-activities-in-wf"></a>WF 中的运行时活动
[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] 为访问工作流运行时的功能提供若干系统提供的活动，如持久性和终止。  
  
|Activity|描述|  
|--------------|-----------------|  
|<xref:System.Activities.Statements.Persist>|显式请求工作流持久保存其状态。|  
|<xref:System.Activities.Statements.TerminateWorkflow>|终止运行工作流实例。|  
|<xref:System.Activities.Statements.NoPersistScope>|可防止子活动持久化的容器活动。|
