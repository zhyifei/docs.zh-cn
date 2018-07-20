---
title: 如何：在 IIS 中承载非服务工作流
ms.date: 03/30/2017
ms.assetid: f362562c-767d-401b-8257-916616568fd4
ms.openlocfilehash: 70fd6aca94f2addd7ee568e897171ae1da86db67
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33496741"
---
# <a name="how-to-host-a-non-service-workflow-in-iis"></a><span data-ttu-id="377dc-102">如何：在 IIS 中承载非服务工作流</span><span class="sxs-lookup"><span data-stu-id="377dc-102">How to: Host a non-service workflow in IIS</span></span>
<span data-ttu-id="377dc-103">可在 IIS/WAS 下承载不属于工作流服务的工作流。</span><span class="sxs-lookup"><span data-stu-id="377dc-103">Workflows that are not workflow services can be hosted under IIS/WAS.</span></span> <span data-ttu-id="377dc-104">这在您需要承载他人编写的工作流时非常有用。</span><span class="sxs-lookup"><span data-stu-id="377dc-104">This is useful when you need to host a workflow written by somebody else.</span></span> <span data-ttu-id="377dc-105">例如，如果您重新承载工作流设计器，并允许用户创建自己的工作流。</span><span class="sxs-lookup"><span data-stu-id="377dc-105">For example, if you rehost the workflow designer and allow users to create their own workflows.</span></span>  <span data-ttu-id="377dc-106">通过在 IIS 中承载非服务工作流，可支持进程回收、空闲时关闭、进程运行状况监视和基于消息的激活等功能。</span><span class="sxs-lookup"><span data-stu-id="377dc-106">Hosting non-service workflows in IIS provides support for features like process recycling, idle shutdown, process health monitoring, and message-based activation.</span></span> <span data-ttu-id="377dc-107">承载于 IIS 的工作流服务包含 <xref:System.ServiceModel.Activities.Receive> 活动，并在 IIS 接收到消息时激活。</span><span class="sxs-lookup"><span data-stu-id="377dc-107">Workflow services hosted in IIS contain <xref:System.ServiceModel.Activities.Receive> activities and are activated when a message is received by IIS.</span></span> <span data-ttu-id="377dc-108">非服务工作流不包含消息传递活动，默认情况下无法通过发送消息激活这些工作流。</span><span class="sxs-lookup"><span data-stu-id="377dc-108">Non-service workflows do not contain messaging activities, and by default cannot be activated by sending a message.</span></span>  <span data-ttu-id="377dc-109">您必须从 <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> 派生一个类，并定义包含创建工作流实例的操作的服务协定。</span><span class="sxs-lookup"><span data-stu-id="377dc-109">You must derive a class from <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> and define a service contract that contains operations to create an instance of the workflow.</span></span> <span data-ttu-id="377dc-110">本主题将指导你完成创建简单工作流、 定义客户端可用来激活工作流服务协定和派生类从<xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>它使用服务协定侦听工作流创建请求。</span><span class="sxs-lookup"><span data-stu-id="377dc-110">This topic will walk you through creating a simple workflow, defining a service contract a client can use to activate the workflow, and deriving a class from <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> which uses the service contract to listen for workflow creating requests.</span></span>  
  
### <a name="create-a-simple-workflow"></a><span data-ttu-id="377dc-111">创建简单工作流</span><span class="sxs-lookup"><span data-stu-id="377dc-111">Create a simple workflow</span></span>  
  
1.  <span data-ttu-id="377dc-112">新建一个名为 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 的新的空 `CreationEndpointTest` 解决方案。</span><span class="sxs-lookup"><span data-stu-id="377dc-112">Create a new [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] empty solution called `CreationEndpointTest`.</span></span>  
  
2.  <span data-ttu-id="377dc-113">向该解决方案添加一个名为 `SimpleWorkflow` 的新 WCF 工作流服务应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="377dc-113">Add a new WCF Workflow Service Application project called `SimpleWorkflow` to the solution.</span></span> <span data-ttu-id="377dc-114">工作流设计器将打开。</span><span class="sxs-lookup"><span data-stu-id="377dc-114">The workflow designer will open.</span></span>  
  
3.  <span data-ttu-id="377dc-115">删除 ReceiveRequest 和 SendResponse 活动。</span><span class="sxs-lookup"><span data-stu-id="377dc-115">Delete the ReceiveRequest and SendResponse activities.</span></span> <span data-ttu-id="377dc-116">这些是使工作流成为工作流服务的活动。</span><span class="sxs-lookup"><span data-stu-id="377dc-116">These activities are what makes a workflow a workflow service.</span></span> <span data-ttu-id="377dc-117">由于我们没有使用工作流服务，因此不再需要它们。</span><span class="sxs-lookup"><span data-stu-id="377dc-117">Since we are not working with a workflow service, we no longer need them.</span></span>  
  
4.  <span data-ttu-id="377dc-118">设置为"顺序工作流"的序列活动的 DisplayName。</span><span class="sxs-lookup"><span data-stu-id="377dc-118">Set the DisplayName for the sequence activity to "Sequential Workflow".</span></span>  
  
5.  <span data-ttu-id="377dc-119">将 Service1.xamlx 重命名为 Workflow1.xamlx。</span><span class="sxs-lookup"><span data-stu-id="377dc-119">Rename Service1.xamlx to Workflow1.xamlx.</span></span>  
  
6.  <span data-ttu-id="377dc-120">单击顺序活动外部的设计器并将设置为"Workflow1"的 Name 和 ConfigurationName 属性</span><span class="sxs-lookup"><span data-stu-id="377dc-120">Click the designer outside of the sequence activity, and set the Name and ConfigurationName properties to "Workflow1"</span></span>  
  
7.  <span data-ttu-id="377dc-121">将 <xref:System.Activities.Statements.WriteLine> 活动拖到 <xref:System.Activities.Statements.Sequence> 中。</span><span class="sxs-lookup"><span data-stu-id="377dc-121">Drag a <xref:System.Activities.Statements.WriteLine> activity into the <xref:System.Activities.Statements.Sequence>.</span></span> <span data-ttu-id="377dc-122"><xref:System.Activities.Statements.WriteLine>在找不到活动**基元**工具箱的部分。</span><span class="sxs-lookup"><span data-stu-id="377dc-122">The <xref:System.Activities.Statements.WriteLine> activity can be found in the **Primitives** section of the toolbox.</span></span> <span data-ttu-id="377dc-123">设置<xref:System.Activities.Statements.WriteLine.Text%2A>属性<xref:System.Activities.Statements.WriteLine>活动"Hello，world"。</span><span class="sxs-lookup"><span data-stu-id="377dc-123">Set the <xref:System.Activities.Statements.WriteLine.Text%2A> property of the <xref:System.Activities.Statements.WriteLine> activity to "Hello, world".</span></span>  
  
     <span data-ttu-id="377dc-124">现在，此工作流应该如下图所示。</span><span class="sxs-lookup"><span data-stu-id="377dc-124">The workflow should now look like the following diagram.</span></span>  
  
     <span data-ttu-id="377dc-125">![一个简单工作流](../../../../docs/framework/wcf/feature-details/media/simpleworkflow.png "SimpleWorkflow")</span><span class="sxs-lookup"><span data-stu-id="377dc-125">![A simple workflow](../../../../docs/framework/wcf/feature-details/media/simpleworkflow.png "SimpleWorkflow")</span></span>  
  
### <a name="create-the-workflow-creation-service-contract"></a><span data-ttu-id="377dc-126">创建工作流创建服务协定</span><span class="sxs-lookup"><span data-stu-id="377dc-126">Create the workflow creation service contract</span></span>  
  
1.  <span data-ttu-id="377dc-127">向 `Shared` 解决方案中添加一个名为 `CreationEndpointTest` 的新类库项目。</span><span class="sxs-lookup"><span data-stu-id="377dc-127">Add a new class library project called `Shared` to the `CreationEndpointTest` solution.</span></span>  
  
2.  <span data-ttu-id="377dc-128">向 `Shared` 项目中添加对 System.ServiceModel.dll、System.Configuration 和 System.ServiceModel.Activities 的引用。</span><span class="sxs-lookup"><span data-stu-id="377dc-128">Add a reference to System.ServiceModel.dll, System.Configuration, and System.ServiceModel.Activities to the `Shared` project.</span></span>  
  
3.  <span data-ttu-id="377dc-129">将 Class1.cs 文件重命名为 IWorkflowCreation.cs，并将以下代码添加到此文件中。</span><span class="sxs-lookup"><span data-stu-id="377dc-129">Rename the Class1.cs file to IWorkflowCreation.cs and the following code to the file.</span></span>  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Text;  
    using System.ServiceModel;  
  
    namespace Shared  
    {  
        //service contract exposed from the endpoint  
        [ServiceContract(Name = "IWorkflowCreation")]  
        public interface IWorkflowCreation  
        {  
            [OperationContract(Name = "Create")]  
            Guid Create(IDictionary<string, object> inputs);  
  
            [OperationContract(Name = "CreateWithInstanceId", IsOneWay = true)]  
            void CreateWithInstanceId(IDictionary<string, object> inputs, Guid instanceId);  
        }  
    }  
    ```  
  
     <span data-ttu-id="377dc-130">此协定定义两个操作，用于创建您刚刚创建的非服务工作流的新实例。</span><span class="sxs-lookup"><span data-stu-id="377dc-130">This contract defines two operations both create a new instance of the non-service workflow you just created.</span></span> <span data-ttu-id="377dc-131">一个操作创建具有生成的实例 ID 的新实例，另一个操作允许您为新工作流实例指定实例 ID。</span><span class="sxs-lookup"><span data-stu-id="377dc-131">One creates a new instance with a generated instance ID and the other allows you to specify the instance ID for the new workflow instance.</span></span>  <span data-ttu-id="377dc-132">两种方法都允许您向新工作流实例传入参数。</span><span class="sxs-lookup"><span data-stu-id="377dc-132">Both methods allow you to pass in parameters to the new workflow instance.</span></span> <span data-ttu-id="377dc-133">此协定将由公开<xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>以允许客户端创建非服务工作流的新实例。</span><span class="sxs-lookup"><span data-stu-id="377dc-133">This contract will be exposed by the <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> to allow clients to create new instances of a non-service workflow.</span></span>  
  
### <a name="derive-a-class-from-workflowhostingendpoint"></a><span data-ttu-id="377dc-134">从 WorkflowHostingEndpoint 派生类</span><span class="sxs-lookup"><span data-stu-id="377dc-134">Derive a class from WorkflowHostingEndpoint</span></span>  
  
1.  <span data-ttu-id="377dc-135">添加新的类调用`CreationEndpoint`派生自<xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>到`Shared`项目。</span><span class="sxs-lookup"><span data-stu-id="377dc-135">Add a new class called `CreationEndpoint` derived from <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> to the `Shared` project.</span></span>  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.Diagnostics;  
    using System.Globalization;  
    using System.ServiceModel;  
    using System.ServiceModel.Activities;  
    using System.ServiceModel.Channels;  
  
    namespace Shared  
    {  
        public class CreationEndpoint : WorkflowHostingEndpoint  
        {  
        }  
    }  
    ```  
  
2.  <span data-ttu-id="377dc-136">将名为 <xref:System.Uri> 的本地静态 `defaultBaseUri` 变量添加到 `CreationEndpoint` 类。</span><span class="sxs-lookup"><span data-stu-id="377dc-136">Add a local static <xref:System.Uri> variable called `defaultBaseUri` to the `CreationEndpoint` class.</span></span>  
  
    ```  
    public class CreationEndpoint : WorkflowHostingEndpoint  
    {  
        static Uri defaultBaseUri;  
    }  
    ```  
  
3.  <span data-ttu-id="377dc-137">将下面的构造函数添加到 `CreationEndpoint` 类。</span><span class="sxs-lookup"><span data-stu-id="377dc-137">Add the following constructor to the `CreationEndpoint` class.</span></span> <span data-ttu-id="377dc-138">请注意，在对基构造函数的调用中指定 `IWorkflowCreation` 服务协定。</span><span class="sxs-lookup"><span data-stu-id="377dc-138">Notice we specify the `IWorkflowCreation` service contract in the call to the base constructor.</span></span>  
  
    ```  
    public CreationEndpoint(Binding binding, EndpointAddress address)  
       : base(typeof(IWorkflowCreation), binding, address)  
       {  
       }  
    ```  
  
4.  <span data-ttu-id="377dc-139">将下面的默认构造函数添加到 `CreationEndpoint` 类。</span><span class="sxs-lookup"><span data-stu-id="377dc-139">Add the following default constructor to the `CreationEndpoint` class.</span></span>  
  
    ```  
    public CreationEndpoint()  
       : this(GetDefaultBinding(),  
       new EndpointAddress(new Uri(DefaultBaseUri, new Uri(Guid.NewGuid().ToString(), UriKind.Relative))))  
       {  
       }  
    ```  
  
5.  <span data-ttu-id="377dc-140">将静态 `DefaultBaseUri` 属性添加到 `CreationEndpoint` 类。</span><span class="sxs-lookup"><span data-stu-id="377dc-140">Add a static `DefaultBaseUri` property to the `CreationEndpoint` class.</span></span> <span data-ttu-id="377dc-141">此属性将用于保留默认的基 URL（如未提供）。</span><span class="sxs-lookup"><span data-stu-id="377dc-141">This property will be used to hold a default base URI if one is not provided.</span></span>  
  
    ```  
    static Uri DefaultBaseUri  
    {  
       get  
       {  
          if (defaultBaseUri == null)  
          {  
             defaultBaseUri = new Uri(string.Format(CultureInfo.InvariantCulture, "net.pipe://localhost/workflowCreationEndpoint/{0}/{1}",  
                Process.GetCurrentProcess().Id,  
                AppDomain.CurrentDomain.Id));  
          }  
          return defaultBaseUri;  
       }  
     }  
    ```  
  
6.  <span data-ttu-id="377dc-142">创建下面的方法来获取默认绑定，以供创建终结点使用。</span><span class="sxs-lookup"><span data-stu-id="377dc-142">Create the following method to get the default binding to use for the creation endpoint.</span></span>  
  
    ```  
    //defaults to NetNamedPipeBinding  
    public static Binding GetDefaultBinding()  
    {  
       return new NetNamedPipeBinding(NetNamedPipeSecurityMode.None) { TransactionFlow = true };  
    }  
    ```  
  
7.  <span data-ttu-id="377dc-143">重写 <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint.OnGetInstanceId%2A> 方法以返回工作流实例 ID。</span><span class="sxs-lookup"><span data-stu-id="377dc-143">Override the <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint.OnGetInstanceId%2A> method to return the workflow instance ID.</span></span> <span data-ttu-id="377dc-144">如果`Action`标头"创建"以返回一个空 GUID，如果`Action`标头以"CreateWithInstanceId"返回 GUID 传递到方法。</span><span class="sxs-lookup"><span data-stu-id="377dc-144">If the `Action` header ends with "Create" return an empty GUID, if the `Action` header ends with "CreateWithInstanceId" return the GUID passed into the method.</span></span> <span data-ttu-id="377dc-145">否则，将引发 <xref:System.InvalidOperationException>。</span><span class="sxs-lookup"><span data-stu-id="377dc-145">Otherwise, throw an <xref:System.InvalidOperationException>.</span></span> <span data-ttu-id="377dc-146">这些 `Action` 标头与 `IWorkflowCreation` 服务协定中定义的两个操作相对应。</span><span class="sxs-lookup"><span data-stu-id="377dc-146">These `Action` headers correspond to the two operations defined in the `IWorkflowCreation` service contract.</span></span>  
  
    ```  
    protected override Guid OnGetInstanceId(object[] inputs, OperationContext operationContext)  
    {  
       //Create was called by client  
       if (operationContext.IncomingMessageHeaders.Action.EndsWith("Create"))  
       {  
          return Guid.Empty;  
       }  
       //CreateWithInstanceId was called by client  
       else if (operationContext.IncomingMessageHeaders.Action.EndsWith("CreateWithInstanceId"))  
       {  
          return (Guid)inputs[1];  
       }  
       else  
       {  
          throw new InvalidOperationException("Invalid Action: " + operationContext.IncomingMessageHeaders.Action);  
       }  
    }  
    ```  
  
8.  <span data-ttu-id="377dc-147">重写 <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint.OnGetCreationContext%2A> 方法以创建 <xref:System.ServiceModel.Activities.WorkflowCreationContext> 并为工作流添加任何参数，将实例 ID 发送到客户端，然后返回 <xref:System.ServiceModel.Activities.WorkflowCreationContext>。</span><span class="sxs-lookup"><span data-stu-id="377dc-147">Override the <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint.OnGetCreationContext%2A> method to create a <xref:System.ServiceModel.Activities.WorkflowCreationContext> and add any arguments for the workflow, send the instance ID to the client, and then return the <xref:System.ServiceModel.Activities.WorkflowCreationContext>.</span></span>  
  
    ```  
    protected override WorkflowCreationContext OnGetCreationContext(object[] inputs, OperationContext operationContext, Guid instanceId, WorkflowHostingResponseContext responseContext)  
    {  
       WorkflowCreationContext creationContext = new WorkflowCreationContext();  
       if (operationContext.IncomingMessageHeaders.Action.EndsWith("Create") || (operationContext.IncomingMessageHeaders.Action.EndsWith("CreateWithInstanceId")))  
       {  
          Dictionary<string, object> arguments = (Dictionary<string, object>)inputs[0];  
          if (arguments != null && arguments.Count > 0)  
          {  
             foreach (KeyValuePair<string, object> pair in arguments)  
             {  
                //arguments to pass to the workflow  
                creationContext.WorkflowArguments.Add(pair.Key, pair.Value);  
             }  
          }  
          //reply to client with instanceId  
          responseContext.SendResponse(instanceId, null);  
       }  
       else  
       {  
          throw new InvalidOperationException("Invalid Action: " + operationContext.IncomingMessageHeaders.Action);  
       }  
       return creationContext;  
    }  
    ```  
  
### <a name="create-a-standard-endpoint-element-to-allow-you-to-configure-the-workflowcreationendpoint"></a><span data-ttu-id="377dc-148">创建标准终结点元素以允许您配置 WorkflowCreationEndpoint</span><span class="sxs-lookup"><span data-stu-id="377dc-148">Create a standard endpoint element to allow you to configure the WorkflowCreationEndpoint</span></span>  
  
1.  <span data-ttu-id="377dc-149">添加对 `CreationEndpoint` 项目中的 Shared 的引用。</span><span class="sxs-lookup"><span data-stu-id="377dc-149">Add a reference to Shared in the `CreationEndpoint` project</span></span>  
  
2.  <span data-ttu-id="377dc-150">向 `CreationEndpointElement` 项目中添加一个派生自 <xref:System.ServiceModel.Configuration.StandardEndpointElement> 的名为 `CreationEndpoint` 的新类。</span><span class="sxs-lookup"><span data-stu-id="377dc-150">Add a new class called `CreationEndpointElement`, derived from <xref:System.ServiceModel.Configuration.StandardEndpointElement> to the `CreationEndpoint` project.</span></span> <span data-ttu-id="377dc-151">此类将表示 web.config 文件中的 `CreationEndpoint`。</span><span class="sxs-lookup"><span data-stu-id="377dc-151">This class will represent a `CreationEndpoint` in a web.config file.</span></span>  
  
    ```  
    using System;  
    using System.Configuration;  
    using System.ServiceModel.Activities;  
    using System.ServiceModel.Configuration;  
    using System.ServiceModel.Description;  
    using Shared;  
  
    namespace CreationEndpointTest  
    {  
        //config element for CreationEndpoint  
        public class CreationEndpointElement : StandardEndpointElement  
        {  
       }  
    ```  
  
3.  <span data-ttu-id="377dc-152">添加名为 `EndpointType` 的属性以返回终结点的类型。</span><span class="sxs-lookup"><span data-stu-id="377dc-152">Add a property called `EndpointType` to return the type of the endpoint.</span></span>  
  
    ```  
    protected override Type EndpointType  
    {  
       get { return typeof(CreationEndpoint); }  
    }  
    ```  
  
4.  <span data-ttu-id="377dc-153">重写 <xref:System.ServiceModel.Configuration.StandardEndpointElement.CreateServiceEndpoint%2A> 方法并返回新的 `CreationEndpoint`。</span><span class="sxs-lookup"><span data-stu-id="377dc-153">Override the <xref:System.ServiceModel.Configuration.StandardEndpointElement.CreateServiceEndpoint%2A> method and return a new `CreationEndpoint`.</span></span>  
  
    ```  
    protected override ServiceEndpoint CreateServiceEndpoint(ContractDescription contractDescription)  
    {  
       return new CreationEndpoint();  
    }  
    ```  
  
5.  <span data-ttu-id="377dc-154">重载 <xref:System.ServiceModel.Configuration.StandardEndpointElement.OnApplyConfiguration%2A>、<xref:System.ServiceModel.Configuration.StandardEndpointElement.OnApplyConfiguration%2A>、<xref:System.ServiceModel.Configuration.StandardEndpointElement.OnInitializeAndValidate%2A> 和 <xref:System.ServiceModel.Configuration.StandardEndpointElement.OnInitializeAndValidate%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="377dc-154">Overload the <xref:System.ServiceModel.Configuration.StandardEndpointElement.OnApplyConfiguration%2A>, <xref:System.ServiceModel.Configuration.StandardEndpointElement.OnApplyConfiguration%2A>, <xref:System.ServiceModel.Configuration.StandardEndpointElement.OnInitializeAndValidate%2A>, and <xref:System.ServiceModel.Configuration.StandardEndpointElement.OnInitializeAndValidate%2A> methods.</span></span> <span data-ttu-id="377dc-155">只需定义这些方法，无需向其中添加任何代码。</span><span class="sxs-lookup"><span data-stu-id="377dc-155">These methods just need to be defined, you do not need to add any code to them.</span></span>  
  
    ```  
    protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ChannelEndpointElement channelEndpointElement)  
    {  
    }  
  
    protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ServiceEndpointElement serviceEndpointElement)  
    {  
    }  
  
    protected override void OnInitializeAndValidate(ChannelEndpointElement channelEndpointElement)  
    {  
    }  
  
    protected override void OnInitializeAndValidate(ServiceEndpointElement serviceEndpointElement)  
    {  
    }  
    ```  
  
6.  <span data-ttu-id="377dc-156">将 `CreationEndpoint` 的集合类添加到 `CreationEndpoint` 项目的 CreationEndpointElement.cs 文件中。</span><span class="sxs-lookup"><span data-stu-id="377dc-156">Add the collection class for `CreationEndpoint` to the CreationEndpointElement.cs file in the `CreationEndpoint` project.</span></span> <span data-ttu-id="377dc-157">配置使用此类来保留 web.config 文件中的大量 `CreationEndpoint` 实例。</span><span class="sxs-lookup"><span data-stu-id="377dc-157">This class is used by configuration to hold a number of `CreationEndpoint` instances in a web.config file.</span></span>  
  
    ```  
    public class CreationEndpointCollection : StandardEndpointCollectionElement<CreationEndpoint, CreationEndpointElement>  
    {  
    }  
    ```  
  
7.  <span data-ttu-id="377dc-158">生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="377dc-158">Build the solution.</span></span>  
  
### <a name="host-the-workflow-in-iis"></a><span data-ttu-id="377dc-159">在 IIS 中承载工作流</span><span class="sxs-lookup"><span data-stu-id="377dc-159">Host the workflow in IIS</span></span>  
  
1.  <span data-ttu-id="377dc-160">在 IIS 中新建一个名为 `MyCreationEndpoint` 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="377dc-160">Create a new application called `MyCreationEndpoint` in IIS.</span></span>  
  
2.  <span data-ttu-id="377dc-161">将工作流设计器生成的 workflow1.xaml 文件复制到应用程序目录中，并将此文件重命名为 workflow1.xamlx。</span><span class="sxs-lookup"><span data-stu-id="377dc-161">Copy the workflow1.xaml file generated by the workflow designer to the application directory and rename it to workflow1.xamlx.</span></span>  
  
3.  <span data-ttu-id="377dc-162">将 shared.dll 和 CreationEndpoint.dll 文件复制到应用程序的 bin 目录（如果 bin 目录不存在，则创建它）。</span><span class="sxs-lookup"><span data-stu-id="377dc-162">Copy the shared.dll and CreationEndpoint.dll files to the application’s bin directory (create the bin directory if it is not present).</span></span>  
  
4.  <span data-ttu-id="377dc-163">用下面的代码替换 `CreationEndpoint` 项目中 Web.config 文件的内容。</span><span class="sxs-lookup"><span data-stu-id="377dc-163">Replace the contents of the Web.config file in the `CreationEndpoint` project with the following code.</span></span>  
  
    ```xaml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <system.web>  
        <compilation debug="true" targetFramework="4.0" />  
      </system.web>   
    </configuration>  
    ```  
  
5.  <span data-ttu-id="377dc-164">在 `<system.web>` 元素后，通过添加下面的配置代码来注册 `CreationEndpoint`。</span><span class="sxs-lookup"><span data-stu-id="377dc-164">After the `<system.web>` element, register `CreationEndpoint` by adding the following configuration code.</span></span>  
  
    ```xml  
    <system.serviceModel>  
        <!--register CreationEndpoint-->  
        <serviceHostingEnvironment multipleSiteBindingsEnabled="true" />  
        <extensions>  
          <endpointExtensions>  
            <add name="creationEndpoint" type="CreationEndpointTest.CreationEndpointCollection, CreationEndpoint, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
          </endpointExtensions>  
        </extensions>  
    </system.serviceModel>  
    ```  
  
     <span data-ttu-id="377dc-165">这将注册 `CreationEndpointCollection` 类，以便您可以在 web.config 文件中配置 `CreationEndpoint`。</span><span class="sxs-lookup"><span data-stu-id="377dc-165">This registers the `CreationEndpointCollection` class so you can configure a `CreationEndpoint` in a web.config file.</span></span>  
  
6.  <span data-ttu-id="377dc-166">添加`<service>`元素 (后\</extensions > 标记) 与`CreationEndpoint`终结点将侦听传入消息。</span><span class="sxs-lookup"><span data-stu-id="377dc-166">Add a `<service>` element (after the \</extensions> tag) with a `CreationEndpoint` which will listen for incoming messages.</span></span>  
  
    ```xml  
    <services>  
          <!-- add endpoint to service-->  
          <service name="Workflow1" behaviorConfiguration="basicConfig" >  
            <endpoint kind="creationEndpoint" binding="basicHttpBinding" address=""/>  
          </service>  
        </services>  
    ```  
  
7.  <span data-ttu-id="377dc-167">添加\<行为 > 元素 (后 \< /> 标记) 以启用服务元数据。</span><span class="sxs-lookup"><span data-stu-id="377dc-167">Add a \<behaviors> element (after the \</services> tag) to enable service metadata.</span></span>  
  
    ```xml  
    <behaviors>  
          <serviceBehaviors>  
            <behavior name="basicConfig">  
              <serviceMetadata httpGetEnabled="true" />  
            </behavior>  
          </serviceBehaviors>  
        </behaviors>  
    ```  
  
8.  <span data-ttu-id="377dc-168">将 web.config 复制到你的 IIS 应用程序目录。</span><span class="sxs-lookup"><span data-stu-id="377dc-168">Copy the web.config to your IIS application directory.</span></span>  
  
9. <span data-ttu-id="377dc-169">测试以查看创建终结点是否正在工作通过启动 Internet Explorer 并浏览到 http://localhost/MyCreationEndpoint/Workflow1.xamlx 。</span><span class="sxs-lookup"><span data-stu-id="377dc-169">Test to see if the creation endpoint is working by starting Internet Explorer and browsing to http://localhost/MyCreationEndpoint/Workflow1.xamlx.</span></span> <span data-ttu-id="377dc-170">Internet Explorer 应显示下面的屏幕：</span><span class="sxs-lookup"><span data-stu-id="377dc-170">Internet Explorer should display the following screen:</span></span>  
  
     <span data-ttu-id="377dc-171">![正在测试服务](../../../../docs/framework/wcf/feature-details/media/testservice.gif "TestService")</span><span class="sxs-lookup"><span data-stu-id="377dc-171">![Testing the service](../../../../docs/framework/wcf/feature-details/media/testservice.gif "TestService")</span></span>  
  
### <a name="create-a-client-that-will-call-the-creationendpoint"></a><span data-ttu-id="377dc-172">创建将调用 CreationEndpoint 的客户端。</span><span class="sxs-lookup"><span data-stu-id="377dc-172">Create a client that will call the CreationEndpoint.</span></span>  
  
1.  <span data-ttu-id="377dc-173">将新控制台应用程序添加到 `CreationEndpointTest` 解决方案。</span><span class="sxs-lookup"><span data-stu-id="377dc-173">Add a new Console application to the `CreationEndpointTest` solution.</span></span>  
  
2.  <span data-ttu-id="377dc-174">添加对 System.ServiceModel.dll、System.ServiceModel.Activities 和 `Shared` 项目的引用。</span><span class="sxs-lookup"><span data-stu-id="377dc-174">Add references to System.ServiceModel.dll, System.ServiceModel.Activities, and the `Shared` project.</span></span>  
  
3.  <span data-ttu-id="377dc-175">在`Main`方法创建<xref:System.ServiceModel.ChannelFactory%601>类型的`IWorkflowCreation`并调用<xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A>。</span><span class="sxs-lookup"><span data-stu-id="377dc-175">In the `Main` method create a <xref:System.ServiceModel.ChannelFactory%601> of type `IWorkflowCreation` and call <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A>.</span></span> <span data-ttu-id="377dc-176">这将返回一个代理。</span><span class="sxs-lookup"><span data-stu-id="377dc-176">This will return a proxy.</span></span> <span data-ttu-id="377dc-177">然后，您可以对此代理调用 `Create` 以创建在 IIS 下承载的工作流实例：</span><span class="sxs-lookup"><span data-stu-id="377dc-177">You can then call `Create` on that proxy to create the workflow instance hosted under IIS:</span></span>  
  
    ```  
    using System.Text;  
    using Shared;  
    using System.ServiceModel;  
  
    namespace CreationEndpointClient  
    {  
        class Program  
        {  
            static void Main(string[] args)  
            {  
                try  
                {  
                    //client using BasicHttpBinding  
                    IWorkflowCreation client = new ChannelFactory<IWorkflowCreation>(new BasicHttpBinding(), new EndpointAddress("http://localhost/CreationEndpoint/Workflow1.xamlx")).CreateChannel();  
  
                    Console.WriteLine("Workflow Instance created using CreationEndpoint added in config. Instance Id: {0}", client.Create(null));  
                    Console.WriteLine("Press return to exit ...");  
                    Console.ReadLine();  
                }  
                catch (Exception ex)  
                {  
                    Console.WriteLine(ex);  
                    Console.ReadLine();  
                }  
            }  
        }  
    }  
    ```  
  
4.  <span data-ttu-id="377dc-178">运行 CreationEndpointClient。</span><span class="sxs-lookup"><span data-stu-id="377dc-178">Run the CreationEndpointClient.</span></span> <span data-ttu-id="377dc-179">输出应如下所示：</span><span class="sxs-lookup"><span data-stu-id="377dc-179">The output should look like the following:</span></span>  
  
    ```Output  
    Workflow Instance created using CreationEndpoint added in config. Instance Id: 0875dac0-2b8b-473e-b3cc-abcb235e9693Press return to exit ...  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="377dc-180">您将看不到工作流的输出，因为它正在 IIS 下运行，而 IIS 没有控制台输出。</span><span class="sxs-lookup"><span data-stu-id="377dc-180">You will not see the output of the workflow because it is running under IIS which has no console output.</span></span>  
  
## <a name="example"></a><span data-ttu-id="377dc-181">示例</span><span class="sxs-lookup"><span data-stu-id="377dc-181">Example</span></span>  
 <span data-ttu-id="377dc-182">以下是此示例的完整代码。</span><span class="sxs-lookup"><span data-stu-id="377dc-182">The following is the complete code for this sample.</span></span>  
  
```xaml  
<!-— workflow1.xamlx -->  
<WorkflowService mc:Ignorable="sap"   
                 ConfigurationName="Workflow1"   
                 sap:VirtualizedContainerService.HintSize="263,230"   
                 Name="Workflow1"   
                 mva:VisualBasic.Settings="Assembly references and imported namespaces serialized as XML namespaces"   
                 xmlns="http://schemas.microsoft.com/netfx/2009/xaml/servicemodel"   
                 xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"   
                 xmlns:mv="clr-namespace:Microsoft.VisualBasic;assembly=System"   
                 xmlns:mva="clr-namespace:Microsoft.VisualBasic.Activities;assembly=System.Activities"   
                 xmlns:p="http://schemas.microsoft.com/netfx/2009/xaml/activities"   
                 xmlns:s="clr-namespace:System;assembly=mscorlib"   
                 xmlns:s1="clr-namespace:System;assembly=System"   
                 xmlns:s2="clr-namespace:System;assembly=System.Xml"   
                 xmlns:s3="clr-namespace:System;assembly=System.Core"   
                 xmlns:sad="clr-namespace:System.Activities.Debugger;assembly=System.Activities"   
                 xmlns:sap="http://schemas.microsoft.com/netfx/2009/xaml/activities/presentation"   
                 xmlns:scg="clr-namespace:System.Collections.Generic;assembly=System"   
                 xmlns:scg1="clr-namespace:System.Collections.Generic;assembly=System.ServiceModel"   
                 xmlns:scg2="clr-namespace:System.Collections.Generic;assembly=System.Core"   
                 xmlns:scg3="clr-namespace:System.Collections.Generic;assembly=mscorlib"   
                 xmlns:sd="clr-namespace:System.Data;assembly=System.Data"   
                 xmlns:sl="clr-namespace:System.Linq;assembly=System.Core"   
                 xmlns:st="clr-namespace:System.Text;assembly=mscorlib"   
                 xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
  <p:Sequence DisplayName="Sequential Service"   
              sad:XamlDebuggerXmlReader.FileName="c:\projects\CreationEndpointTest\CreationEndpoint\Service1.xamlx"   
              sap:VirtualizedContainerService.HintSize="233,200"   
              mva:VisualBasic.Settings="Assembly references and imported namespaces serialized as XML namespaces">  
    <p:Sequence.Variables>  
      <p:Variable x:TypeArguments="CorrelationHandle" Name="handle" />  
      <p:Variable x:TypeArguments="x:Int32" Name="data" />  
    </p:Sequence.Variables>  
    <sap:WorkflowViewStateService.ViewState>  
      <scg3:Dictionary x:TypeArguments="x:String, x:Object">  
        <x:Boolean x:Key="IsExpanded">True</x:Boolean>  
      </scg3:Dictionary>  
    </sap:WorkflowViewStateService.ViewState>  
    <p:WriteLine sap:VirtualizedContainerService.HintSize="211,61" Text="Hello, world" />  
  </p:Sequence>  
</WorkflowService>  
```  
  
```csharp  
// CreationEndpointElement.cs  
using System;  
using System.Configuration;  
using System.ServiceModel.Activities;  
using System.ServiceModel.Configuration;  
using System.ServiceModel.Description;  
using Shared;  
  
namespace CreationEndpointTest  
{  
    //config element for CreationEndpoint  
    public class CreationEndpointElement : StandardEndpointElement  
    {  
        protected override Type EndpointType  
        {  
            get { return typeof(CreationEndpoint); }  
        }  
  
        protected override ConfigurationPropertyCollection Properties  
        {  
            get  
            {  
                ConfigurationPropertyCollection properties = base.Properties;  
                properties.Add(new ConfigurationProperty("name", typeof(String), null, ConfigurationPropertyOptions.IsRequired));  
                return properties;  
            }  
        }  
  
        protected override ServiceEndpoint CreateServiceEndpoint(ContractDescription contractDescription)  
        {  
            return new CreationEndpoint();  
        }  
  
        protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ChannelEndpointElement channelEndpointElement)  
        {  
        }  
  
        protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ServiceEndpointElement serviceEndpointElement)  
        {  
        }  
  
        protected override void OnInitializeAndValidate(ChannelEndpointElement channelEndpointElement)  
        {  
        }  
  
        protected override void OnInitializeAndValidate(ServiceEndpointElement serviceEndpointElement)  
        {  
        }  
    }  
  
    public class CreationEndpointCollection : StandardEndpointCollectionElement<CreationEndpoint, CreationEndpointElement>  
    {  
    }  
}  
```  
  
```xml  
<!-- web.config -->  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.web>  
    <compilation debug="true" targetFramework="4.0" />  
  </system.web>  
  <system.serviceModel>  
    <!--register CreationEndpoint-->  
    <serviceHostingEnvironment multipleSiteBindingsEnabled="true" />  
    <extensions>  
      <endpointExtensions>  
        <add name="creationEndpoint" type="CreationEndpointTest.CreationEndpointCollection, Shared, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
      </endpointExtensions>  
    </extensions>  
    <services>  
      <!-- add endpoint to service-->  
      <service name="Workflow1" behaviorConfiguration="basicConfig" >  
        <endpoint kind="creationEndpoint" binding="basicHttpBinding" address=""/>  
      </service>  
    </services>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="basicConfig">  
          <serviceMetadata httpGetEnabled="true" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
```csharp  
// IWorkflowCreation.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.ServiceModel;  
  
namespace Shared  
{  
    //service contract exposed from the endpoint  
    [ServiceContract(Name = "IWorkflowCreation")]  
    public interface IWorkflowCreation  
    {  
        [OperationContract(Name = "Create")]  
        Guid Create(IDictionary<string, object> inputs);  
  
        [OperationContract(Name = "CreateWithInstanceId", IsOneWay = true)]  
        void CreateWithInstanceId(IDictionary<string, object> inputs, Guid instanceId);  
    }  
}  
```  
  
```csharp  
// CreationEndpoint.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.ServiceModel.Activities;  
using System.ServiceModel.Channels;  
using System.ServiceModel;  
using System.Globalization;  
using System.Diagnostics;  
  
namespace Shared  
{  
    public class CreationEndpoint : WorkflowHostingEndpoint  
    {  
        static Uri defaultBaseUri;  
  
        public CreationEndpoint(Binding binding, EndpointAddress address)  
            : base(typeof(IWorkflowCreation), binding, address) { }  
  
        public CreationEndpoint()  
            : this(GetDefaultBinding(),  
                new EndpointAddress(new Uri(DefaultBaseUri, new Uri(Guid.NewGuid().ToString(), UriKind.Relative)))) { }  
  
        static Uri DefaultBaseUri  
        {  
            get  
            {  
                if (defaultBaseUri == null)  
                {  
                    defaultBaseUri = new Uri(string.Format(CultureInfo.InvariantCulture, "net.pipe://localhost/workflowCreationEndpoint/{0}/{1}",  
                        Process.GetCurrentProcess().Id,  
                        AppDomain.CurrentDomain.Id));  
                }  
                return defaultBaseUri;  
            }  
        }  
  
        //defaults to NetNamedPipeBinding  
        public static Binding GetDefaultBinding()  
        {  
            return new NetNamedPipeBinding(NetNamedPipeSecurityMode.None) { TransactionFlow = true };  
        }  
  
        protected override Guid OnGetInstanceId(object[] inputs, OperationContext operationContext)  
        {  
            //Create was called by client  
            if (operationContext.IncomingMessageHeaders.Action.EndsWith("Create"))  
            {  
                return Guid.Empty;  
            }  
  
            //CreateWithInstanceId was called by client  
            else if (operationContext.IncomingMessageHeaders.Action.EndsWith("CreateWithInstanceId"))  
            {  
                return (Guid)inputs[1];  
            }  
            else  
            {  
                throw new InvalidOperationException("Invalid Action: " + operationContext.IncomingMessageHeaders.Action);  
            }  
        }  
  
        protected override WorkflowCreationContext OnGetCreationContext(object[] inputs, OperationContext operationContext, Guid instanceId, WorkflowHostingResponseContext responseContext)  
        {  
            WorkflowCreationContext creationContext = new WorkflowCreationContext();  
            if (operationContext.IncomingMessageHeaders.Action.EndsWith("Create"))  
            {  
                Dictionary<string, object> arguments = (Dictionary<string, object>)inputs[0];  
                if (arguments != null && arguments.Count > 0)  
                {  
                    foreach (KeyValuePair<string, object> pair in arguments)  
                    {  
                        //arguments to pass to the workflow  
                        creationContext.WorkflowArguments.Add(pair.Key, pair.Value);  
                    }  
                }  
                //reply to client with instanceId  
                responseContext.SendResponse(instanceId, null);  
            }  
            else if (operationContext.IncomingMessageHeaders.Action.EndsWith("CreateWithInstanceId"))  
            {  
                Dictionary<string, object> arguments = (Dictionary<string, object>)inputs[0];  
                if (arguments != null && arguments.Count > 0)  
                {  
                    foreach (KeyValuePair<string, object> pair in arguments)  
                    {  
                        //arguments to pass to workflow  
                        creationContext.WorkflowArguments.Add(pair.Key, pair.Value);  
                    }  
                }  
            }  
            else  
            {  
                throw new InvalidOperationException("Invalid Action: " + operationContext.IncomingMessageHeaders.Action);  
            }  
            return creationContext;  
        }  
    }  
}  
```  
  
```csharp  
// CreationEndpointClient.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using Shared;  
using System.ServiceModel;  
  
namespace CreationClient  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            try  
            {  
                //client using BasicHttpBinding  
                IWorkflowCreation client = new ChannelFactory<IWorkflowCreation>(new BasicHttpBinding(), new EndpointAddress("http://localhost/MyCreationEndpoint/Workflow1.xamlx")).CreateChannel();  
  
                Console.WriteLine("Workflow Instance created using CreationEndpoint added in config. Instance Id: {0}", client.Create(null));  
                Console.WriteLine("Press return to exit ...");  
                Console.ReadLine();  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine(ex);  
                Console.ReadLine();  
            }  
  
        }  
    }  
  
}  
```  
  
 <span data-ttu-id="377dc-183">此示例可能看起来使人迷惑，因为您从未实现能实现 `IWorkflowCreation` 的服务。</span><span class="sxs-lookup"><span data-stu-id="377dc-183">This example may seem confusing because you never implement a service that implements `IWorkflowCreation`.</span></span> <span data-ttu-id="377dc-184">这是因为 `CreationEndpoint` 为您这么做了。</span><span class="sxs-lookup"><span data-stu-id="377dc-184">This is because the `CreationEndpoint` does this for you.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="377dc-185">请参阅</span><span class="sxs-lookup"><span data-stu-id="377dc-185">See Also</span></span>  
 [<span data-ttu-id="377dc-186">工作流服务</span><span class="sxs-lookup"><span data-stu-id="377dc-186">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)  
 [<span data-ttu-id="377dc-187">在 Internet Information Services 中承载</span><span class="sxs-lookup"><span data-stu-id="377dc-187">Hosting in Internet Information Services</span></span>](../../../../docs/framework/wcf/feature-details/hosting-in-internet-information-services.md)  
 [<span data-ttu-id="377dc-188">Internet Information Services 承载最佳做法</span><span class="sxs-lookup"><span data-stu-id="377dc-188">Internet Information Services Hosting Best Practices</span></span>](../../../../docs/framework/wcf/feature-details/internet-information-services-hosting-best-practices.md)  
 [<span data-ttu-id="377dc-189">Internet 信息服务承载说明</span><span class="sxs-lookup"><span data-stu-id="377dc-189">Internet Information Service Hosting Instructions</span></span>](../../../../docs/framework/wcf/samples/internet-information-service-hosting-instructions.md)  
 [<span data-ttu-id="377dc-190">Windows Workflow 体系结构</span><span class="sxs-lookup"><span data-stu-id="377dc-190">Windows Workflow Architecture</span></span>](../../../../docs/framework/windows-workflow-foundation/architecture.md)  
 [<span data-ttu-id="377dc-191">WorkflowHostingEndpoint 恢复书签</span><span class="sxs-lookup"><span data-stu-id="377dc-191">WorkflowHostingEndpoint Resume Bookmark</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/workflowhostingendpoint-resume-bookmark.md)  
 [<span data-ttu-id="377dc-192">重新托管工作流设计器</span><span class="sxs-lookup"><span data-stu-id="377dc-192">Rehosting the Workflow Designer</span></span>](../../../../docs/framework/windows-workflow-foundation/rehosting-the-workflow-designer.md)  
 [<span data-ttu-id="377dc-193">Windows Workflow 概述</span><span class="sxs-lookup"><span data-stu-id="377dc-193">Windows Workflow Overview</span></span>](../../../../docs/framework/windows-workflow-foundation/overview.md)
