---
title: 如何：对工作流和工作流服务启用持久性
ms.date: 03/30/2017
ms.assetid: 2b1c8bf3-9866-45a4-b06d-ee562393e503
ms.openlocfilehash: 5d0eeb8ad40f2f4f3349ab48487316014a561a1b
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460891"
---
# <a name="how-to-enable-persistence-for-workflows-and-workflow-services"></a><span data-ttu-id="cc8f8-102">如何：对工作流和工作流服务启用持久性</span><span class="sxs-lookup"><span data-stu-id="cc8f8-102">How to: Enable Persistence for Workflows and Workflow Services</span></span>

<span data-ttu-id="cc8f8-103">本主题说明如何对工作流和工作流服务启用持久性。</span><span class="sxs-lookup"><span data-stu-id="cc8f8-103">This topic describes how to enable persistence for workflows and workflow services.</span></span>

## <a name="enable-persistence-for-workflows"></a><span data-ttu-id="cc8f8-104">对工作流启用持久性</span><span class="sxs-lookup"><span data-stu-id="cc8f8-104">Enable Persistence for Workflows</span></span>

<span data-ttu-id="cc8f8-105">可以通过使用 <xref:System.Activities.WorkflowApplication> 类的 <xref:System.Activities.WorkflowApplication.InstanceStore%2A> 属性将实例存储与**WorkflowApplication**关联。</span><span class="sxs-lookup"><span data-stu-id="cc8f8-105">You can associate an instance store with a **WorkflowApplication** by using the <xref:System.Activities.WorkflowApplication.InstanceStore%2A> property of the <xref:System.Activities.WorkflowApplication> class.</span></span> <span data-ttu-id="cc8f8-106"><xref:System.Activities.WorkflowApplication.Persist%2A> 方法将工作流保存或持久保存到与应用程序关联的实例存储中。</span><span class="sxs-lookup"><span data-stu-id="cc8f8-106">The <xref:System.Activities.WorkflowApplication.Persist%2A> method saves or persists a workflow into the instance store associated with the application.</span></span> <span data-ttu-id="cc8f8-107"><xref:System.Activities.WorkflowApplication.Unload%2A> 方法将工作流保存到实例存储中，然后从内存中卸载该实例。</span><span class="sxs-lookup"><span data-stu-id="cc8f8-107">The <xref:System.Activities.WorkflowApplication.Unload%2A> method persists a workflow into the instance store and then unloads the instance from the memory.</span></span> <span data-ttu-id="cc8f8-108">**Load**方法使用实例持久性存储区中存储的工作流数据将工作流加载到内存中。</span><span class="sxs-lookup"><span data-stu-id="cc8f8-108">The **Load** method loads a workflow into memory using the workflow data stored in the instance persistence store.</span></span>

<span data-ttu-id="cc8f8-109">**持久性**方法执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="cc8f8-109">The **Persist** method performs the following steps:</span></span>

1. <span data-ttu-id="cc8f8-110">暂停工作流计划程序并等待，直至工作流进入空闲状态。</span><span class="sxs-lookup"><span data-stu-id="cc8f8-110">Pauses the workflow scheduler and waits until the workflow enters the idle state.</span></span>

2. <span data-ttu-id="cc8f8-111">将工作流持久保存或保存到持久性存储。</span><span class="sxs-lookup"><span data-stu-id="cc8f8-111">Persists or saves the workflow into the persistence store.</span></span>

3. <span data-ttu-id="cc8f8-112">恢复工作流计划程序。</span><span class="sxs-lookup"><span data-stu-id="cc8f8-112">Resumes the workflow scheduler.</span></span>

 <span data-ttu-id="cc8f8-113">**Unload**方法执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="cc8f8-113">The **Unload** method performs the following steps:</span></span>

1. <span data-ttu-id="cc8f8-114">暂停工作流计划程序并等待，直至工作流进入空闲状态。</span><span class="sxs-lookup"><span data-stu-id="cc8f8-114">Pauses the workflow scheduler and waits until the workflow enters the idle state.</span></span>

2. <span data-ttu-id="cc8f8-115">将工作流持久保存或保存到持久性存储。</span><span class="sxs-lookup"><span data-stu-id="cc8f8-115">Persists or saves the workflow into the persistence store.</span></span>

3. <span data-ttu-id="cc8f8-116">在内存中释放工作流实例。</span><span class="sxs-lookup"><span data-stu-id="cc8f8-116">Disposes the workflow instance in the memory.</span></span>

<span data-ttu-id="cc8f8-117">当工作流处于非持久性区域中时，始终会阻止**持久性**和**Unload**方法，直到工作流退出非持久性区域。</span><span class="sxs-lookup"><span data-stu-id="cc8f8-117">Both the **Persist** and **Unload** methods will block while a workflow is in a no-persist zone until the workflow exits the no-persist zone.</span></span> <span data-ttu-id="cc8f8-118">在完成非持久性区域之后，该方法将继续执行保存或卸载操作。</span><span class="sxs-lookup"><span data-stu-id="cc8f8-118">The method continues with the persist or unload operation after the no-persist zone completes.</span></span> <span data-ttu-id="cc8f8-119">如果在完成非持久性区域之前发生超时，或者如果持久性进程的时间太长，则将引发 TimeoutException。</span><span class="sxs-lookup"><span data-stu-id="cc8f8-119">If the no-persist zone does not complete before the time-out elapses, or if the persistence process takes too long, a TimeoutException will be thrown.</span></span>

## <a name="enable-persistence-for-workflow-services-in-code"></a><span data-ttu-id="cc8f8-120">在代码中实现工作流服务的持久性</span><span class="sxs-lookup"><span data-stu-id="cc8f8-120">Enable Persistence for Workflow Services in Code</span></span>

<span data-ttu-id="cc8f8-121"><xref:System.ServiceModel.WorkflowServiceHost> 类的**DurableInstancingOptions**成员具有一个名为**InstanceStore**的属性，可用于将实例存储与**WorkflowServiceHost**相关联。</span><span class="sxs-lookup"><span data-stu-id="cc8f8-121">The **DurableInstancingOptions** member of the <xref:System.ServiceModel.WorkflowServiceHost> class has a property named **InstanceStore** that you can use to associate an instance store with the **WorkflowServiceHost**.</span></span>

```csharp
// wsh is an instance of WorkflowServiceHost class
wsh.DurableInstancingOptions.InstanceStore = new SqlWorkflowInstanceStore();
```

<span data-ttu-id="cc8f8-122">当**WorkflowServiceHost**打开时，如果**DurableInstancingOptions**不为 null，则会自动启用持久性。</span><span class="sxs-lookup"><span data-stu-id="cc8f8-122">When the **WorkflowServiceHost** is opened, persistence is automatically enabled if the **DurableInstancingOptions.InstanceStore** is not null.</span></span>

<span data-ttu-id="cc8f8-123">通常，服务行为通过使用**InstanceStore**属性提供要与工作流服务主机一起使用的具体实例存储区。</span><span class="sxs-lookup"><span data-stu-id="cc8f8-123">Typically, a service behavior provides the concrete instance store to be used with a workflow service host by using the **InstanceStore** property.</span></span> <span data-ttu-id="cc8f8-124">例如，SqlWorkflowInstanceStoreBehavior 创建了一个**SqlWorkflowInstanceStore**实例，对其进行配置，并将其分配给**DurableInstancingOptions**。</span><span class="sxs-lookup"><span data-stu-id="cc8f8-124">For example, the SqlWorkflowInstanceStoreBehavior creates an instance of the **SqlWorkflowInstanceStore**, configures it, and assigns it to the **DurableInstancingOptions.InstanceStore**.</span></span>

## <a name="enable-persistence-for-workflow-services-using-an-application-configuration-file"></a><span data-ttu-id="cc8f8-125">使用应用程序配置文件实现工作流服务的持久性</span><span class="sxs-lookup"><span data-stu-id="cc8f8-125">Enable Persistence for Workflow Services Using an Application Configuration File</span></span>

<span data-ttu-id="cc8f8-126">可以通过将以下代码添加到您 app.config 或 web.config 文件中，使用应用程序配置文件来实现持久性：</span><span class="sxs-lookup"><span data-stu-id="cc8f8-126">Persistence can be enabled using an application configuration file by adding the following code to your app.config or web.config file:</span></span>

```xml
<configuration>
  <system.serviceModel>
    <behaviors>
      <serviceBehaviors>
        <behavior name="myBehavior">
          <sqlWorkflowInstanceStore connectionString="Data Source=myDatabaseServer;Initial Catalog=myPersistenceDatabase" />
        </behavior>
      </serviceBehaviors>
    </behaviors>
  </system.serviceModel>
</configuration>
```
