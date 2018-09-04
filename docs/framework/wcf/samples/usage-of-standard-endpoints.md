---
title: 标准终结点的用法
ms.date: 03/30/2017
ms.assetid: ecd6a62f-9619-4778-a497-6f888087a9ea
ms.openlocfilehash: b3e8cb32832763c7182f86f68c5c80d80ce8c3af
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43518221"
---
# <a name="usage-of-standard-endpoints"></a><span data-ttu-id="991c5-102">标准终结点的用法</span><span class="sxs-lookup"><span data-stu-id="991c5-102">Usage of Standard Endpoints</span></span>

<span data-ttu-id="991c5-103">此示例演示如何在服务配置文件中使用标准终结点。</span><span class="sxs-lookup"><span data-stu-id="991c5-103">This sample demonstrates how to use standard endpoints in service configuration files.</span></span> <span data-ttu-id="991c5-104">通过标准终结点，用户可以使用单个属性来描述地址、绑定和协定组合以及与其关联的附加属性，从而简化终结点定义。</span><span class="sxs-lookup"><span data-stu-id="991c5-104">A standard endpoint allows the user to simplify endpoint definitions by using a single property to describe an address, binding and contract combination with additional properties associated to it.</span></span> <span data-ttu-id="991c5-105">此示例演示如何定义和实现自定义标准终结点，以及如何在终结点中定义特定属性。</span><span class="sxs-lookup"><span data-stu-id="991c5-105">This sample demonstrates how to define and implement a custom standard endpoint and how to define specific properties in the endpoint.</span></span>

## <a name="sample-details"></a><span data-ttu-id="991c5-106">示例详细信息</span><span class="sxs-lookup"><span data-stu-id="991c5-106">Sample Details</span></span>

<span data-ttu-id="991c5-107">可以通过指定地址、绑定和协定这三个参数来指定服务终结点。</span><span class="sxs-lookup"><span data-stu-id="991c5-107">Service endpoints can be specified by supplying three parameters: address, binding and contract.</span></span> <span data-ttu-id="991c5-108">可以提供的其他参数包括行为配置、标头、侦听 URI 等。</span><span class="sxs-lookup"><span data-stu-id="991c5-108">Other parameters that can be supplied include behavior configuration, headers, listen URI, and so on.</span></span> <span data-ttu-id="991c5-109">在某些情况下，任何或所有地址、绑定和协定具有无法更改的值。</span><span class="sxs-lookup"><span data-stu-id="991c5-109">In some cases, any or all of addresses, bindings and contracts have values that cannot change.</span></span> <span data-ttu-id="991c5-110">因此，可以使用标准终结点。</span><span class="sxs-lookup"><span data-stu-id="991c5-110">For this reason, it is possible to use standard endpoints.</span></span> <span data-ttu-id="991c5-111">这类终结点包括元数据交换终结点和发现终结点。</span><span class="sxs-lookup"><span data-stu-id="991c5-111">Some examples of such endpoints include metadata exchange endpoints and discovery endpoints.</span></span> <span data-ttu-id="991c5-112">标准终结点还允许配置服务终结点，而不必提供固定性质的信息或创建其自己的标准终结点，从而提高了可用性，例如通过提供一组合理的默认值，从而降低配置文件的详细级别，来提高可用性。</span><span class="sxs-lookup"><span data-stu-id="991c5-112">Standard endpoints also improve usability by allowing configuration of service endpoints without having to provide information of a fixed nature or to create their own standard endpoints, for example to improve usability by supplying a reasonable set of default values and thus reducing the verbosity of configuration files.</span></span>

<span data-ttu-id="991c5-113">此示例由两个项目组成：定义两个标准终结点的服务以及与该服务通信的客户端。</span><span class="sxs-lookup"><span data-stu-id="991c5-113">This sample consists of two projects: the service that defines two standard endpoints and the client that communicates with the service.</span></span> <span data-ttu-id="991c5-114">下面的示例演示如何为配置文件中的服务定义标准终结点。</span><span class="sxs-lookup"><span data-stu-id="991c5-114">The way the standard endpoints are defined for the service in the configuration file is show in the following example.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <system.serviceModel>
    <extensions>
      <endpointExtensions>
        <add name="customEndpoint" type="Microsoft.Samples.StandardEndpoints.CustomEndpointCollectionElement, service" />
      </endpointExtensions>
    </extensions>
    <services>
      <service name="Microsoft.Samples.StandardEndpoints.CalculatorService">
        <endpoint address="http://localhost:8000/Samples/Service.svc/customEndpoint" contract="Microsoft.Samples.StandardEndpoints.ICalculator" kind="customEndpoint" />
        <endpoint kind="mexEndpoint" />
      </service>
    </services>
    <behaviors>
      <serviceBehaviors>
        <behavior>
          <serviceMetadata httpGetEnabled="True"/>
        </behavior>
      </serviceBehaviors>
    </behaviors>
    <standardEndpoints>
      <customEndpoint>
        <standardEndpoint property="True" />
      </customEndpoint>
    </standardEndpoints>
  </system.serviceModel>
</configuration>
```

<span data-ttu-id="991c5-115">为服务定义的第一个终结点的类型为 `customEndpoint`，其定义在 `<standardEndpoints>` 节中，其中为属性 `property` 提供了值 `true`。</span><span class="sxs-lookup"><span data-stu-id="991c5-115">The first endpoint defined for the service is of kind `customEndpoint`, whose definition can be seen in the `<standardEndpoints>` section, in which the property `property` is given the value `true`.</span></span> <span data-ttu-id="991c5-116">这是使用新属性自定义终结点的情况。</span><span class="sxs-lookup"><span data-stu-id="991c5-116">This is the case of an endpoint customized with a new property.</span></span> <span data-ttu-id="991c5-117">第二个终结点对应于元数据终结点，其中地址、绑定和协定的值是固定的。</span><span class="sxs-lookup"><span data-stu-id="991c5-117">The second endpoint corresponds to a metadata endpoint, in which the values for address, binding and contract are fixed.</span></span>

<span data-ttu-id="991c5-118">若要定义标准终结点元素，必须创建从 `StandardEndpointElement` 派生的类。</span><span class="sxs-lookup"><span data-stu-id="991c5-118">To define the standard endpoint element, a class that derives from `StandardEndpointElement` must be created.</span></span> <span data-ttu-id="991c5-119">在此示例中，已定义了 `CustomEndpointElement` 类，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="991c5-119">In the case of this sample, the `CustomEndpointElement` class has been defined as shown in the following example.</span></span>

```csharp
public class CustomEndpointElement : StandardEndpointElement
{
    public bool Property
    {
        get { return (bool)base["property"]; }
        set { base["property"] = value; }
    }

    protected override ConfigurationPropertyCollection Properties
    {
        get
        {
            ConfigurationPropertyCollection properties = base.Properties;
            properties.Add(new ConfigurationProperty("property", typeof(bool), false, ConfigurationPropertyOptions.None));
            return properties;
        }
    }

    protected override Type EndpointType
    {
        get { return typeof(CustomEndpoint); }
    }

    protected override ServiceEndpoint CreateServiceEndpoint(ContractDescription contract)
    {
        return new CustomEndpoint();
    }

    protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ServiceEndpointElement serviceEndpointElement)
    {
        CustomEndpoint customEndpoint = (CustomEndpoint)endpoint;
        customEndpoint.Property = this.Property;
    }

    protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ChannelEndpointElement channelEndpointElement)
    {
        CustomEndpoint customEndpoint = (CustomEndpoint)endpoint;
        customEndpoint.Property = this.Property;
    }

    protected override void OnInitializeAndValidate(ServiceEndpointElement serviceEndpointElement)
    {
    }

    protected override void OnInitializeAndValidate(ChannelEndpointElement channelEndpointElement)
    {
    }
}
```

<span data-ttu-id="991c5-120">在 `CreateServiceEndpoint` 函数中，创建了一个 `CustomEndpoint` 对象。</span><span class="sxs-lookup"><span data-stu-id="991c5-120">In the `CreateServiceEndpoint` function, a `CustomEndpoint` object is created.</span></span> <span data-ttu-id="991c5-121">其定义如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="991c5-121">Its definition is shown in the following example:</span></span>

```csharp
public class CustomEndpoint : ServiceEndpoint
{
    public CustomEndpoint() 
        : this(string.Empty)
    {
    }

    public CustomEndpoint(string address)
        : this(address, ContractDescription.GetContract(typeof(ICalculator)))
    {
    }

    public CustomEndpoint(string address, ContractDescription contract)
        : base(contract)
    {
        this.Binding = new BasicHttpBinding();
        this.IsSystemEndpoint = false;
    }

    public bool Property
    {
        get;
        set;
    }
}
```

 <span data-ttu-id="991c5-122">若要在服务与客户端之间执行通信，需要在客户端中创建对服务的服务引用。</span><span class="sxs-lookup"><span data-stu-id="991c5-122">To perform the communication between service and client, a service reference is created in the client to the service.</span></span> <span data-ttu-id="991c5-123">当生成和执行示例时，服务会执行，且客户端与之进行通信。</span><span class="sxs-lookup"><span data-stu-id="991c5-123">When the sample is built and executed, the service executes and the client communicates with it.</span></span> <span data-ttu-id="991c5-124">请注意，每次对服务进行更改时，都应更新服务引用。</span><span class="sxs-lookup"><span data-stu-id="991c5-124">Note that the service reference should be updated every time there is some change in the service.</span></span>

#### <a name="to-use-this-sample"></a><span data-ttu-id="991c5-125">使用此示例</span><span class="sxs-lookup"><span data-stu-id="991c5-125">To use this sample</span></span>

1.  <span data-ttu-id="991c5-126">使用 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 打开 StandardEndpoints.sln 文件。</span><span class="sxs-lookup"><span data-stu-id="991c5-126">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the StandardEndpoints.sln file.</span></span>

2.  <span data-ttu-id="991c5-127">使多个项目可以启动。</span><span class="sxs-lookup"><span data-stu-id="991c5-127">Enable multiple projects to start up.</span></span>

    1.  <span data-ttu-id="991c5-128">在中**解决方案资源管理器**，右键单击该标准终结点解决方案，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="991c5-128">In **Solution Explorer**, right-click the Standard Endpoints solution and then select **Properties**.</span></span>

    2.  <span data-ttu-id="991c5-129">在中**常见属性**，选择**启动项目**，然后单击**多个启动项目**。</span><span class="sxs-lookup"><span data-stu-id="991c5-129">In **Common Properties**, select **Startup Project**, and then click **Multiple Startup Projects**.</span></span>

    3.  <span data-ttu-id="991c5-130">利用将服务项目移到列表的开头**操作**设置为**启动**。</span><span class="sxs-lookup"><span data-stu-id="991c5-130">Move the Service project to the beginning of the list, with the **Action** set to **Start**.</span></span>

    4.  <span data-ttu-id="991c5-131">客户端将项目移动服务项目之后，还具有**操作**设置为**启动**。</span><span class="sxs-lookup"><span data-stu-id="991c5-131">Move the Client project after the Service project, also with the **Action** set to **Start**.</span></span>

         <span data-ttu-id="991c5-132">这指定客户端项目在服务项目之后执行。</span><span class="sxs-lookup"><span data-stu-id="991c5-132">This specifies that the Client project is executed after the Service project.</span></span>

3.  <span data-ttu-id="991c5-133">若要运行解决方案，请按 F5。</span><span class="sxs-lookup"><span data-stu-id="991c5-133">To run the solution, press F5.</span></span>

> [!NOTE]
> <span data-ttu-id="991c5-134">如果这些步骤不起作用，请确保，你的环境已正确设置，使用以下步骤：</span><span class="sxs-lookup"><span data-stu-id="991c5-134">If these steps don't work, then make sure that your environment has been properly set up, using the following steps:</span></span>
>
> 1. <span data-ttu-id="991c5-135">请确保您具有执行[的 Windows Communication Foundation 示例的一次性安装过程](one-time-setup-procedure-for-the-wcf-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="991c5-135">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>
> 2. <span data-ttu-id="991c5-136">若要生成解决方案，请按照中的说明[生成 Windows Communication Foundation 示例](building-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="991c5-136">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>
> 3. <span data-ttu-id="991c5-137">若要在一个或多个计算机配置中运行示例，请按照中的说明[运行 Windows Communication Foundation 示例](running-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="991c5-137">To run the sample in a single or multiple computer configurations, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="991c5-138">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="991c5-138">The samples may already be installed on your machine.</span></span> <span data-ttu-id="991c5-139">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="991c5-139">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="991c5-140">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="991c5-140">If this directory doesn't exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="991c5-141">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="991c5-141">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\StandardEndpoints`
