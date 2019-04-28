---
title: 使用 Activity 类的工作流活动创作
ms.date: 03/30/2017
ms.assetid: 7b7b1c66-f093-43c3-b4d1-7173b46516da
ms.openlocfilehash: 1bec10b6ae9fb43319cfb6acbf59133e1acca09c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61755501"
---
# <a name="workflow-activity-authoring-using-the-activity-class"></a><span data-ttu-id="ecc60-102">使用 Activity 类的工作流活动创作</span><span class="sxs-lookup"><span data-stu-id="ecc60-102">Workflow Activity Authoring Using the Activity Class</span></span>
<span data-ttu-id="ecc60-103">若要创建使用 Windows Workflow Foundation (WF) 中的活动的最基本方法[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]是创建继承的类<xref:System.Activities.Activity>，创建功能通过组装自定义活动或活动从[内置活动库](net-framework-4-5-built-in-activity-library.md)。</span><span class="sxs-lookup"><span data-stu-id="ecc60-103">The most basic way to create an activity using Windows Workflow Foundation (WF) in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] is to create a class that inherits from <xref:System.Activities.Activity> that creates functionality by assembling custom activities or activities from the [Built-In Activity Library](net-framework-4-5-built-in-activity-library.md).</span></span> <span data-ttu-id="ecc60-104">本主题演示如何创建向控制台写入两个消息的活动。</span><span class="sxs-lookup"><span data-stu-id="ecc60-104">This topic demonstrates how to create an activity that writes two messages to the console.</span></span>

### <a name="to-create-a-custom-activity-using-the-activity-designer"></a><span data-ttu-id="ecc60-105">使用活动设计器创建自定义活动</span><span class="sxs-lookup"><span data-stu-id="ecc60-105">To create a custom Activity using the activity designer</span></span>

1. <span data-ttu-id="ecc60-106">打开 Visual Studio 2012。</span><span class="sxs-lookup"><span data-stu-id="ecc60-106">Open Visual Studio 2012.</span></span>

2. <span data-ttu-id="ecc60-107">依次选择“文件”、“新建”和“项目”。</span><span class="sxs-lookup"><span data-stu-id="ecc60-107">Select File, New, Project.</span></span> <span data-ttu-id="ecc60-108">选择**Workflow 4.0**下**Visual C#** 中**项目类型**窗口中，然后选择**v2010**节点。</span><span class="sxs-lookup"><span data-stu-id="ecc60-108">Select **Workflow 4.0** under **Visual C#** in the **Project Types** window, and select the **v2010** node.</span></span> <span data-ttu-id="ecc60-109">选择**活动库**中**模板**窗口。</span><span class="sxs-lookup"><span data-stu-id="ecc60-109">Select **Activity Library** in the **Templates** window.</span></span> <span data-ttu-id="ecc60-110">将新项目命名为 HelloActivity。</span><span class="sxs-lookup"><span data-stu-id="ecc60-110">Name the new project HelloActivity.</span></span>

3. <span data-ttu-id="ecc60-111">打开新的活动。</span><span class="sxs-lookup"><span data-stu-id="ecc60-111">Open the new activity.</span></span>  <span data-ttu-id="ecc60-112">将 <xref:System.Activities.Statements.Sequence> 活动从工具箱拖到设计器图面。</span><span class="sxs-lookup"><span data-stu-id="ecc60-112">Drag a <xref:System.Activities.Statements.Sequence> activity from the toolbox onto the designer surface.</span></span>

4. <span data-ttu-id="ecc60-113">将 <xref:System.Activities.Statements.WriteLine> 活动拖到 <xref:System.Activities.Statements.Sequence> 活动中。</span><span class="sxs-lookup"><span data-stu-id="ecc60-113">Drag a <xref:System.Activities.Statements.WriteLine> activity into the <xref:System.Activities.Statements.Sequence> activity.</span></span> <span data-ttu-id="ecc60-114">输入`"Hello World"`（带引号） 入**文本**字段。</span><span class="sxs-lookup"><span data-stu-id="ecc60-114">Enter `"Hello World"` (with quotes) into the **Text** field.</span></span>

5. <span data-ttu-id="ecc60-115">将第二个 <xref:System.Activities.Statements.WriteLine> 活动拖到 <xref:System.Activities.Statements.Sequence> 活动中并将其放置在第一个活动的下面。</span><span class="sxs-lookup"><span data-stu-id="ecc60-115">Drag a second <xref:System.Activities.Statements.WriteLine> activity into the <xref:System.Activities.Statements.Sequence> activity, below the first one.</span></span> <span data-ttu-id="ecc60-116">输入`"Goodbye"`（带引号） 入**文本**字段。</span><span class="sxs-lookup"><span data-stu-id="ecc60-116">Enter `"Goodbye"` (with quotes) into the **Text** field.</span></span>
