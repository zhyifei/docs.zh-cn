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
# <a name="workflow-activity-authoring-using-the-activity-class"></a><span data-ttu-id="2ded2-102">使用 Activity 类的工作流活动创作</span><span class="sxs-lookup"><span data-stu-id="2ded2-102">Workflow Activity Authoring Using the Activity Class</span></span>
<span data-ttu-id="2ded2-103">创建活动使用的最基本方法[!INCLUDE[wf](../../../includes/wf-md.md)]中[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]是创建继承自的类<xref:System.Activities.Activity>创建功能通过组合来自定义从活动或[内置活动库](../../../docs/framework/windows-workflow-foundation/net-framework-4-5-built-in-activity-library.md).</span><span class="sxs-lookup"><span data-stu-id="2ded2-103">The most basic way to create an activity using [!INCLUDE[wf](../../../includes/wf-md.md)] in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] is to create a class that inherits from <xref:System.Activities.Activity> that creates functionality by assembling custom activities or activities from the [Built-In Activity Library](../../../docs/framework/windows-workflow-foundation/net-framework-4-5-built-in-activity-library.md).</span></span> <span data-ttu-id="2ded2-104">本主题演示如何创建向控制台写入两个消息的活动。</span><span class="sxs-lookup"><span data-stu-id="2ded2-104">This topic demonstrates how to create an activity that writes two messages to the console.</span></span>  
  
### <a name="to-create-a-custom-activity-using-the-activity-designer"></a><span data-ttu-id="2ded2-105">使用活动设计器创建自定义活动</span><span class="sxs-lookup"><span data-stu-id="2ded2-105">To create a custom Activity using the activity designer</span></span>  
  
1.  <span data-ttu-id="2ded2-106">打开 [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="2ded2-106">Open [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)].</span></span>  
  
2.  <span data-ttu-id="2ded2-107">依次选择“文件”、“新建”和“项目”。</span><span class="sxs-lookup"><span data-stu-id="2ded2-107">Select File, New, Project.</span></span> <span data-ttu-id="2ded2-108">选择**Workflow 4.0**下**Visual C#**中**项目类型**窗口中，然后选择**v2010**节点。</span><span class="sxs-lookup"><span data-stu-id="2ded2-108">Select **Workflow 4.0** under **Visual C#** in the **Project Types** window, and select the **v2010** node.</span></span> <span data-ttu-id="2ded2-109">选择**活动库**中**模板**窗口。</span><span class="sxs-lookup"><span data-stu-id="2ded2-109">Select **Activity Library** in the **Templates** window.</span></span> <span data-ttu-id="2ded2-110">将新项目命名为 HelloActivity。</span><span class="sxs-lookup"><span data-stu-id="2ded2-110">Name the new project HelloActivity.</span></span>  
  
3.  <span data-ttu-id="2ded2-111">打开新的活动。</span><span class="sxs-lookup"><span data-stu-id="2ded2-111">Open the new activity.</span></span>  <span data-ttu-id="2ded2-112">将 <xref:System.Activities.Statements.Sequence> 活动从工具箱拖到设计器图面。</span><span class="sxs-lookup"><span data-stu-id="2ded2-112">Drag a <xref:System.Activities.Statements.Sequence> activity from the toolbox onto the designer surface.</span></span>  
  
4.  <span data-ttu-id="2ded2-113">将 <xref:System.Activities.Statements.WriteLine> 活动拖到 <xref:System.Activities.Statements.Sequence> 活动中。</span><span class="sxs-lookup"><span data-stu-id="2ded2-113">Drag a <xref:System.Activities.Statements.WriteLine> activity into the <xref:System.Activities.Statements.Sequence> activity.</span></span> <span data-ttu-id="2ded2-114">输入`"Hello World"`（带引号） 到**文本**字段。</span><span class="sxs-lookup"><span data-stu-id="2ded2-114">Enter `"Hello World"` (with quotes) into the **Text** field.</span></span>  
  
5.  <span data-ttu-id="2ded2-115">将第二个 <xref:System.Activities.Statements.WriteLine> 活动拖到 <xref:System.Activities.Statements.Sequence> 活动中并将其放置在第一个活动的下面。</span><span class="sxs-lookup"><span data-stu-id="2ded2-115">Drag a second <xref:System.Activities.Statements.WriteLine> activity into the <xref:System.Activities.Statements.Sequence> activity, below the first one.</span></span> <span data-ttu-id="2ded2-116">输入`"Goodbye"`（带引号） 到**文本**字段。</span><span class="sxs-lookup"><span data-stu-id="2ded2-116">Enter `"Goodbye"` (with quotes) into the **Text** field.</span></span>
