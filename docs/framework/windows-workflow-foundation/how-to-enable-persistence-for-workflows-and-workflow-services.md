---
title: 如何：对工作流和工作流服务启用持久性
ms.date: 03/30/2017
ms.assetid: 2b1c8bf3-9866-45a4-b06d-ee562393e503
ms.openlocfilehash: 35158c45217e764bc2e27dac26f8d680e5897fa9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33514413"
---
# <a name="how-to-enable-persistence-for-workflows-and-workflow-services"></a><span data-ttu-id="b8dd6-102">如何：对工作流和工作流服务启用持久性</span><span class="sxs-lookup"><span data-stu-id="b8dd6-102">How to: Enable Persistence for Workflows and Workflow Services</span></span>
<span data-ttu-id="b8dd6-103">本主题说明如何对工作流和工作流服务启用持久性。</span><span class="sxs-lookup"><span data-stu-id="b8dd6-103">This topic describes how to enable persistence for workflows and workflow services.</span></span>  
  
## <a name="enable-persistence-for-workflows"></a><span data-ttu-id="b8dd6-104">对工作流启用持久性</span><span class="sxs-lookup"><span data-stu-id="b8dd6-104">Enable Persistence for Workflows</span></span>  
 <span data-ttu-id="b8dd6-105">您还可以将与实例存储区相关联**WorkflowApplication**使用<xref:System.Activities.WorkflowApplication.InstanceStore%2A>属性<xref:System.Activities.WorkflowApplication>类。</span><span class="sxs-lookup"><span data-stu-id="b8dd6-105">You can associate an instance store with a **WorkflowApplication** by using the <xref:System.Activities.WorkflowApplication.InstanceStore%2A> property of the <xref:System.Activities.WorkflowApplication> class.</span></span> <span data-ttu-id="b8dd6-106"><xref:System.Activities.WorkflowApplication.Persist%2A> 方法将工作流保存或持久保存到与应用程序关联的实例存储中。</span><span class="sxs-lookup"><span data-stu-id="b8dd6-106">The <xref:System.Activities.WorkflowApplication.Persist%2A> method saves or persists a workflow into the instance store associated with the application.</span></span> <span data-ttu-id="b8dd6-107"><xref:System.Activities.WorkflowApplication.Unload%2A> 方法将工作流保存到实例存储中，然后从内存中卸载该实例。</span><span class="sxs-lookup"><span data-stu-id="b8dd6-107">The <xref:System.Activities.WorkflowApplication.Unload%2A> method persists a workflow into the instance store and then unloads the instance from the memory.</span></span> <span data-ttu-id="b8dd6-108">**负载**方法将工作流加载到内存使用实例持久性存储区中存储的工作流数据。</span><span class="sxs-lookup"><span data-stu-id="b8dd6-108">The **Load** method loads a workflow into memory using the workflow data stored in the instance persistence store.</span></span>  
  
 <span data-ttu-id="b8dd6-109">**保留**方法执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="b8dd6-109">The **Persist** method performs the following steps:</span></span>  
  
1.  <span data-ttu-id="b8dd6-110">暂停工作流计划程序并等待，直至工作流进入空闲状态。</span><span class="sxs-lookup"><span data-stu-id="b8dd6-110">Pauses the workflow scheduler and waits until the workflow enters the idle state.</span></span>  
  
2.  <span data-ttu-id="b8dd6-111">将工作流持久保存或保存到持久性存储。</span><span class="sxs-lookup"><span data-stu-id="b8dd6-111">Persists or saves the workflow into the persistence store.</span></span>  
  
3.  <span data-ttu-id="b8dd6-112">恢复工作流计划程序。</span><span class="sxs-lookup"><span data-stu-id="b8dd6-112">Resumes the workflow scheduler.</span></span>  
  
 <span data-ttu-id="b8dd6-113">**卸载**方法执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="b8dd6-113">The **Unload** method performs the following steps:</span></span>  
  
1.  <span data-ttu-id="b8dd6-114">暂停工作流计划程序并等待，直至工作流进入空闲状态。</span><span class="sxs-lookup"><span data-stu-id="b8dd6-114">Pauses the workflow scheduler and waits until the workflow enters the idle state.</span></span>  
  
2.  <span data-ttu-id="b8dd6-115">将工作流持久保存或保存到持久性存储。</span><span class="sxs-lookup"><span data-stu-id="b8dd6-115">Persists or saves the workflow into the persistence store.</span></span>  
  
3.  <span data-ttu-id="b8dd6-116">在内存中释放工作流实例。</span><span class="sxs-lookup"><span data-stu-id="b8dd6-116">Disposes the workflow instance in the memory.</span></span>  
  
 <span data-ttu-id="b8dd6-117">这两个**保留**和**卸载**在工作流是在非持久性区域中，直到工作流退出非持久性区域时，将阻止方法。</span><span class="sxs-lookup"><span data-stu-id="b8dd6-117">Both the **Persist** and **Unload** methods will block while a workflow is in a no-persist zone until the workflow exits the no-persist zone.</span></span> <span data-ttu-id="b8dd6-118">在完成非持久性区域之后，该方法将继续执行保存或卸载操作。</span><span class="sxs-lookup"><span data-stu-id="b8dd6-118">The method continues with the persist or unload operation after the no-persist zone completes.</span></span> <span data-ttu-id="b8dd6-119">如果在完成非持久性区域之前发生超时，或者如果持久性进程的时间太长，则将引发 TimeoutException。</span><span class="sxs-lookup"><span data-stu-id="b8dd6-119">If the no-persist zone does not complete before the time-out elapses, or if the persistence process takes too long, a TimeoutException will be thrown.</span></span>  
  
## <a name="enable-persistence-for-workflow-services-in-code"></a><span data-ttu-id="b8dd6-120">在代码中实现工作流服务的持久性</span><span class="sxs-lookup"><span data-stu-id="b8dd6-120">Enable Persistence for Workflow Services in Code</span></span>  
 <span data-ttu-id="b8dd6-121">**DurableInstancingOptions**的成员<xref:System.ServiceModel.WorkflowServiceHost>类有一个名为**InstanceStore** ，你可以使用关联与实例存储区**WorkflowServiceHost**.</span><span class="sxs-lookup"><span data-stu-id="b8dd6-121">The **DurableInstancingOptions** member of the <xref:System.ServiceModel.WorkflowServiceHost> class has a property named **InstanceStore** that you can use to associate an instance store with the **WorkflowServiceHost**.</span></span>  
  
```  
// wsh is an instance of WorkflowServiceHost class  
wsh.DurableInstancingOptions.InstanceStore = new SqlWorkflowInstanceStore();  
```  
  
 <span data-ttu-id="b8dd6-122">当**WorkflowServiceHost**是打开，持久性将自动启用如果**DurableInstancingOptions.InstanceStore**不为 null。</span><span class="sxs-lookup"><span data-stu-id="b8dd6-122">When the **WorkflowServiceHost** is opened, persistence is automatically enabled if the **DurableInstancingOptions.InstanceStore** is not null.</span></span>  
  
 <span data-ttu-id="b8dd6-123">通常情况下，服务行为提供要通过使用与工作流服务主机的具体实例存储区**InstanceStore**属性。</span><span class="sxs-lookup"><span data-stu-id="b8dd6-123">Typically, a service behavior provides the concrete instance store to be used with a workflow service host by using the **InstanceStore** property.</span></span> <span data-ttu-id="b8dd6-124">例如，SqlWorkflowInstanceStoreBehavior 创建的实例**SqlWorkflowInstanceStore**、 配置，并将它分配给**DurableInstancingOptions.InstanceStore**。</span><span class="sxs-lookup"><span data-stu-id="b8dd6-124">For example, the SqlWorkflowInstanceStoreBehavior creates an instance of the **SqlWorkflowInstanceStore**, configures it, and assigns it to the **DurableInstancingOptions.InstanceStore**.</span></span>  
  
## <a name="enable-persistence-for-workflow-services-using-an-application-configuration-file"></a><span data-ttu-id="b8dd6-125">使用应用程序配置文件实现工作流服务的持久性</span><span class="sxs-lookup"><span data-stu-id="b8dd6-125">Enable Persistence for Workflow Services Using an Application Configuration File</span></span>  
 <span data-ttu-id="b8dd6-126">可以通过将以下代码添加到您 app.config 或 web.config 文件中，使用应用程序配置文件来实现持久性：</span><span class="sxs-lookup"><span data-stu-id="b8dd6-126">Persistence can be enabled using an application configuration file by adding the following code to your app.config or web.config file:</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="myBehavior">  
          <SqlWorkflowInstanceStore connectionString="Data Source=myDatatbaseServer;Initial Catalog=myPersistenceDatabase">  
        </behavior>  
      </serviceBehaviors>  
    <behaviors>  
  </system.serviceModel>  
</configuration>  
```
