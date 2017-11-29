---
title: "使用 Activity 类的工作流活动创作"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7b7b1c66-f093-43c3-b4d1-7173b46516da
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f4fc6d0807c07952e9b3abe2861ef04bc225142f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="workflow-activity-authoring-using-the-activity-class"></a>使用 Activity 类的工作流活动创作
创建活动使用的最基本方法[!INCLUDE[wf](../../../includes/wf-md.md)]中[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]是创建继承自的类<xref:System.Activities.Activity>创建功能通过组合来自定义从活动或[内置活动库](../../../docs/framework/windows-workflow-foundation/net-framework-4-5-built-in-activity-library.md). 本主题演示如何创建向控制台写入两个消息的活动。  
  
### <a name="to-create-a-custom-activity-using-the-activity-designer"></a>使用活动设计器创建自定义活动  
  
1.  打开 [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)]。  
  
2.  依次选择“文件”、“新建”和“项目”。 选择**Workflow 4.0**下**Visual C#**中**项目类型**窗口中，然后选择**v2010**节点。 选择**活动库**中**模板**窗口。 将新项目命名为 HelloActivity。  
  
3.  打开新的活动。  将 <xref:System.Activities.Statements.Sequence> 活动从工具箱拖到设计器图面。  
  
4.  将 <xref:System.Activities.Statements.WriteLine> 活动拖到 <xref:System.Activities.Statements.Sequence> 活动中。 输入`"Hello World"`（带引号） 到**文本**字段。  
  
5.  将第二个 <xref:System.Activities.Statements.WriteLine> 活动拖到 <xref:System.Activities.Statements.Sequence> 活动中并将其放置在第一个活动的下面。 输入`"Goodbye"`（带引号） 到**文本**字段。
