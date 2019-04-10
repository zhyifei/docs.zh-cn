---
title: 如何：使用配置文件发布服务的元数据
ms.date: 03/30/2017
ms.assetid: f061443f-92df-4824-b36a-609c4cd14a17
ms.openlocfilehash: 367ebeee5c12d809a758f1bee73dfaadda85788d
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59295531"
---
# <a name="how-to-publish-metadata-for-a-service-using-a-configuration-file"></a><span data-ttu-id="31ee8-102">如何：使用配置文件发布服务的元数据</span><span class="sxs-lookup"><span data-stu-id="31ee8-102">How to: Publish Metadata for a Service Using a Configuration File</span></span>
<span data-ttu-id="31ee8-103">这是个演示 Windows Communication Foundation (WCF) 服务的发布元数据的两个帮助主题之一。</span><span class="sxs-lookup"><span data-stu-id="31ee8-103">This is one of two how-to topics that demonstrate publishing metadata for a Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="31ee8-104">有两种方式可以指定服务应如何发布元数据：使用配置文件和使用代码。</span><span class="sxs-lookup"><span data-stu-id="31ee8-104">There are two ways to specify how a service should publish metadata, using a configuration file and using code.</span></span> <span data-ttu-id="31ee8-105">本主题演示如何使用配置文件发布服务的元数据。</span><span class="sxs-lookup"><span data-stu-id="31ee8-105">This topic shows how to publish metadata for a service using a configuration file.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="31ee8-106">本主题演示如何以不安全的方式发布元数据。</span><span class="sxs-lookup"><span data-stu-id="31ee8-106">This topic shows how to publish metadata in an unsecure manner.</span></span> <span data-ttu-id="31ee8-107">任何客户端都可以检索服务的元数据。</span><span class="sxs-lookup"><span data-stu-id="31ee8-107">Any client can retrieve the metadata from the service.</span></span> <span data-ttu-id="31ee8-108">如果您要求服务以安全方式发布元数据，请参阅[自定义安全元数据终结点](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md)。</span><span class="sxs-lookup"><span data-stu-id="31ee8-108">If you require your service to publish metadata in a secure manner, see [Custom Secure Metadata Endpoint](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md).</span></span>  
  
 <span data-ttu-id="31ee8-109">有关在代码中发布元数据的详细信息，请参阅[如何：发布使用代码为服务的元数据](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)。</span><span class="sxs-lookup"><span data-stu-id="31ee8-109">For more information about publishing metadata in code, see [How to: Publish Metadata for a Service Using Code](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md).</span></span> <span data-ttu-id="31ee8-110">通过发布元数据，客户端可以使用 WS-Transfer GET 请求或使用 `?wsdl` 查询字符串的 HTTP/GET 来检索元数据。</span><span class="sxs-lookup"><span data-stu-id="31ee8-110">Publishing metadata allows clients to retrieve the metadata using a WS-Transfer GET request or an HTTP/GET request using the `?wsdl` query string.</span></span> <span data-ttu-id="31ee8-111">若要确保的代码正常工作，创建一个基本的 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="31ee8-111">To be sure that the code is working, create a basic WCF service.</span></span> <span data-ttu-id="31ee8-112">为了简单起见，将在以下代码中提供一个基本的自承载服务。</span><span class="sxs-lookup"><span data-stu-id="31ee8-112">For simplicity, a basic self-hosted service is provided in the following code.</span></span>  
  
```csharp  
using System;  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.ServiceModel.Description;  
  
namespace Metadata.Samples  
{  
    [ServiceContract]  
    public interface ISimpleService  
    {  
        [OperationContract]  
        string SimpleMethod(string msg);  
    }  
  
    class SimpleService : ISimpleService  
    {  
        public string SimpleMethod(string msg)  
        {  
            Console.WriteLine("The caller passed in " + msg);  
            return "Hello " + msg;  
        }  
    }  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            ServiceHost host = new ServiceHost(typeof(SimpleService),  
                new Uri("http://localhost:8001/MetadataSample"));   
            try  
            {  
                // Open the service host to accept incoming calls  
                host.Open();  
  
                // The service can now be accessed.  
                Console.WriteLine("The service is ready.");  
                Console.WriteLine("Press <ENTER> to terminate service.");  
                Console.WriteLine();  
                Console.ReadLine();  
  
                // Close the ServiceHostBase to shutdown the service.  
                host.Close();  
            }  
            catch (CommunicationException commProblem)  
            {  
                Console.WriteLine("There was a communication problem. " + commProblem.Message);  
                Console.Read();  
            }  
        }  
    }  
}  
```  
  
 <span data-ttu-id="31ee8-113">此服务为自承载服务，并且是使用配置文件配置的。</span><span class="sxs-lookup"><span data-stu-id="31ee8-113">This service is a self-hosted service, which is configured using a configuration file.</span></span> <span data-ttu-id="31ee8-114">下面的配置文件作为开始点。</span><span class="sxs-lookup"><span data-stu-id="31ee8-114">The following configuration file serves as a starting point.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service name="Metadata.Example.SimpleService">  
        <endpoint address=""  
                  binding="basicHttpBinding"  
                  contract="Metadata.Example.ISimpleService" />  
      </service>  
    </services>  
    <behaviors>  
  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
### <a name="to-publish-metadata-for-a-wcf-service-using-an-application-configuration-file"></a><span data-ttu-id="31ee8-115">使用应用程序配置文件发布 WCF 服务的元数据</span><span class="sxs-lookup"><span data-stu-id="31ee8-115">To publish metadata for a WCF service using an application configuration file</span></span>  
  
1. <span data-ttu-id="31ee8-116">在 App.config 文件内，在结束 `</services>`&lt;behaviors&gt; 元素之后创建`<behaviors>` 元素。</span><span class="sxs-lookup"><span data-stu-id="31ee8-116">Within the App.config file, after the closing `</services>` element, create a `<behaviors>` element.</span></span>  

2. <span data-ttu-id="31ee8-117">在 `<behaviors>` 元素内，添加一个 `<serviceBehaviors>` 元素。</span><span class="sxs-lookup"><span data-stu-id="31ee8-117">Within the `<behaviors>` element, add a `<serviceBehaviors>` element.</span></span>  

3. <span data-ttu-id="31ee8-118">向 `<behavior>``<serviceBehaviors>` 元素中添加一个 `name` 元素，并为 元素的 `<behavior>` 属性指定一个值。</span><span class="sxs-lookup"><span data-stu-id="31ee8-118">Add a `<behavior>` element to the `<serviceBehaviors>` element and specify a value for the `name` attribute of the `<behavior>` element.</span></span>  

4. <span data-ttu-id="31ee8-119">向 `<serviceMetadata>` 元素中添加一个 `<behavior>` 元素。</span><span class="sxs-lookup"><span data-stu-id="31ee8-119">Add a `<serviceMetadata>` element to the `<behavior>` element.</span></span> <span data-ttu-id="31ee8-120">将 `httpGetEnabled` 属性设置为 `true`，并将 `policyVersion` 属性设置为 Policy15。</span><span class="sxs-lookup"><span data-stu-id="31ee8-120">Set the `httpGetEnabled` attribute to `true` and the `policyVersion` attribute to Policy15.</span></span> `httpGetEnabled` <span data-ttu-id="31ee8-121">允许服务发出的 HTTP GET 请求的元数据请求做出响应。</span><span class="sxs-lookup"><span data-stu-id="31ee8-121">allows the service to respond to metadata requests made by an HTTP GET request.</span></span> `policyVersion` <span data-ttu-id="31ee8-122">指示服务来生成元数据时符合 Ws-policy 1.5。</span><span class="sxs-lookup"><span data-stu-id="31ee8-122">tells the service to conform to WS-Policy 1.5 when generating metadata.</span></span>  

5. <span data-ttu-id="31ee8-123">将 `behaviorConfiguration` 特性添加到 `<service>` 元素，并指定在步骤 1 中添加的 `name` 元素的 `<behavior>` 特性，如下面的代码示例所示。</span><span class="sxs-lookup"><span data-stu-id="31ee8-123">Add a `behaviorConfiguration` attribute to the `<service>` element and specify the `name` attribute of the `<behavior>` element added in step 1, as shown in the following code example.</span></span>  
  
    ```xml  
    <services>  
      <service  
          name="Metadata.Example.SimpleService"  
          behaviorConfiguration="SimpleServiceBehavior">  
        ...  
      </service>  
    </services>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="SimpleServiceBehavior">  
          <serviceMetadata httpGetEnabled="True" policyVersion="Policy15" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    ```  
  
6. <span data-ttu-id="31ee8-124">添加一个或多个其协定设置为 `<endpoint>` 的 `IMetadataExchange` 元素，如下面的代码示例所示。</span><span class="sxs-lookup"><span data-stu-id="31ee8-124">Add one or more `<endpoint>` elements with the contract set to `IMetadataExchange`, as shown in the following code example.</span></span>  
  
    ```xml  
    <services>  
      <service  
          name="Metadata.Example.SimpleService"  
          behaviorConfiguration="SimpleServiceBehavior">  
  
        <endpoint address=""  
                  binding="wsHttpBinding"  
                  contract="Metadata.Example.ISimpleService" />  
  
        <endpoint address="mex"  
                  binding="mexHttpBinding"  
                  contract="IMetadataExchange" />  
      </service>  
    </services>  
    ```  
  
7. <span data-ttu-id="31ee8-125">对于上一步中添加的元数据终结点，将 `binding` 特性设置为下列值之一：</span><span class="sxs-lookup"><span data-stu-id="31ee8-125">For the metadata endpoints added in the previous step, set the `binding` attribute to one of the following:</span></span>  
  
    -   `mexHttpBinding` <span data-ttu-id="31ee8-126">对于 HTTP 发布。</span><span class="sxs-lookup"><span data-stu-id="31ee8-126">for HTTP publication.</span></span>  
  
    -   `mexHttpsBinding` <span data-ttu-id="31ee8-127">对于 HTTPS 发布。</span><span class="sxs-lookup"><span data-stu-id="31ee8-127">for HTTPS publication.</span></span>  
  
    -   `mexNamedPipeBinding` <span data-ttu-id="31ee8-128">对于命名管道发布。</span><span class="sxs-lookup"><span data-stu-id="31ee8-128">for named pipe publication.</span></span>  
  
    -   `mexTcpBinding` <span data-ttu-id="31ee8-129">对于 TCP 发布。</span><span class="sxs-lookup"><span data-stu-id="31ee8-129">for TCP publication.</span></span>  
  
8. <span data-ttu-id="31ee8-130">对于上一步中添加的元数据终结点，将地址设置为等于：</span><span class="sxs-lookup"><span data-stu-id="31ee8-130">For the metadata endpoints added in a previous step, set the address equal to:</span></span>  
  
    -   <span data-ttu-id="31ee8-131">一个空字符串，以在基址和元数据绑定相同的情况下将主机应用程序的基址用作发布点。</span><span class="sxs-lookup"><span data-stu-id="31ee8-131">An empty string to use the host application's base address as the publication point if the base address is the same as the metadata binding.</span></span>  
  
    -   <span data-ttu-id="31ee8-132">一个相对地址，前提是主机应用程序具有一个基址。</span><span class="sxs-lookup"><span data-stu-id="31ee8-132">A relative address if the host application has a base address.</span></span>  
  
    -   <span data-ttu-id="31ee8-133">一个绝对地址。</span><span class="sxs-lookup"><span data-stu-id="31ee8-133">An absolute address.</span></span>  
  
9. <span data-ttu-id="31ee8-134">生成并运行控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="31ee8-134">Build and run the console application.</span></span>  
  
10. <span data-ttu-id="31ee8-135">使用 Internet Explorer 浏览到该服务的基址 (http://localhost:8001/MetadataSample在此示例中)，并验证是否已打开元数据发布。</span><span class="sxs-lookup"><span data-stu-id="31ee8-135">Use Internet Explorer to browse to the base address of the service (http://localhost:8001/MetadataSample in this sample) and verify that the metadata publishing is turned on.</span></span> <span data-ttu-id="31ee8-136">如果没有，则显示一条消息，在生成的页面的顶部："元数据发布，此服务当前已禁用。"</span><span class="sxs-lookup"><span data-stu-id="31ee8-136">If not, a message at the top of the resulting page displays: "Metadata publishing for this service is currently disabled."</span></span>  
  
### <a name="to-use-default-endpoints"></a><span data-ttu-id="31ee8-137">使用默认终结点</span><span class="sxs-lookup"><span data-stu-id="31ee8-137">To use default endpoints</span></span>  
  
1. <span data-ttu-id="31ee8-138">若要配置使用默认终结点的服务上的元数据，请在上一个示例中的配置文件中指定 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>，但不要指定任何终结点。</span><span class="sxs-lookup"><span data-stu-id="31ee8-138">To configure metadata on a service that uses default endpoints, specify the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> in the configuration file as in the previous example, but do not specify any endpoints.</span></span> <span data-ttu-id="31ee8-139">配置文件将类似如下所示。</span><span class="sxs-lookup"><span data-stu-id="31ee8-139">The configuration file would then look like this.</span></span>  
  
    ```xml  
    <configuration>  
      <system.serviceModel>  
        <behaviors>  
          <serviceBehaviors>  
            <behavior name="SimpleServiceBehavior">  
              <serviceMetadata httpGetEnabled="True" policyVersion="Policy12" />  
            </behavior>  
          </serviceBehaviors>  
        </behaviors>  
  
      </system.serviceModel>  
    </configuration>  
    ```  
  
     <span data-ttu-id="31ee8-140">由于该服务有一个 <xref:System.ServiceModel.Description.ServiceMetadataBehavior> 设置为 `httpGetEnabled` 的 `true`，因此该服务启用了发布元数据，但是由于未显式添加任何终结点，因此运行时添加默认终结点。</span><span class="sxs-lookup"><span data-stu-id="31ee8-140">Because the service has a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> with the `httpGetEnabled` set to `true`, the service has publishing metadata enabled, and because no endpoints were explicitly added, the runtime adds the default endpoints.</span></span> <span data-ttu-id="31ee8-141">有关默认终结点、绑定和行为的详细信息，请参阅[简化配置](../../../../docs/framework/wcf/simplified-configuration.md)和 [WCF 服务的简化配置](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)。</span><span class="sxs-lookup"><span data-stu-id="31ee8-141">For more information about default endpoints, bindings, and behaviors, see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="31ee8-142">示例</span><span class="sxs-lookup"><span data-stu-id="31ee8-142">Example</span></span>  
 <span data-ttu-id="31ee8-143">下面的代码示例演示一个基本的 WCF 服务和发布服务元数据的配置文件的实现。</span><span class="sxs-lookup"><span data-stu-id="31ee8-143">The following code example shows the implementation of a basic WCF service and the configuration file that publishes metadata for the service.</span></span>  
  
```csharp  
using System;  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.ServiceModel.Description;  
  
namespace Metadata.Samples  
{  
    [ServiceContract]  
    public interface ISimpleService  
    {  
        [OperationContract]  
        string SimpleMethod(string msg);  
    }  
  
    class SimpleService : ISimpleService  
    {  
        public string SimpleMethod(string msg)  
        {  
            Console.WriteLine("The caller passed in " + msg);  
            return "Hello " + msg;  
        }  
    }  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            ServiceHost host = new ServiceHost(typeof(SimpleService),  
                new Uri("http://localhost:8001/MetadataSample"));   
            try  
            {  
                // Open the service host to accept incoming calls  
                host.Open();  
  
                // The service can now be accessed.  
                Console.WriteLine("The service is ready.");  
                Console.WriteLine("Press <ENTER> to terminate service.");  
                Console.WriteLine();  
                Console.ReadLine();  
  
                // Close the ServiceHostBase to shutdown the service.  
                host.Close();  
            }  
            catch (CommunicationException commProblem)  
            {  
                Console.WriteLine("There was a communication problem. " + commProblem.Message);  
                Console.Read();  
            }  
        }  
    }  
}  
```  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="SimpleServiceBehavior">  
          <serviceMetadata httpGetEnabled="True" policyVersion="Policy12" />  
          <serviceDebug includeExceptionDetailInFaults="False" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="31ee8-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="31ee8-144">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceMetadataBehavior>
- [<span data-ttu-id="31ee8-145">如何：在托管应用程序中承载 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="31ee8-145">How to: Host a WCF Service in a Managed Application</span></span>](../../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md)
- [<span data-ttu-id="31ee8-146">自承载</span><span class="sxs-lookup"><span data-stu-id="31ee8-146">Self-Host</span></span>](../../../../docs/framework/wcf/samples/self-host.md)
- [<span data-ttu-id="31ee8-147">元数据体系结构概述</span><span class="sxs-lookup"><span data-stu-id="31ee8-147">Metadata Architecture Overview</span></span>](../../../../docs/framework/wcf/feature-details/metadata-architecture-overview.md)
- [<span data-ttu-id="31ee8-148">使用元数据</span><span class="sxs-lookup"><span data-stu-id="31ee8-148">Using Metadata</span></span>](../../../../docs/framework/wcf/feature-details/using-metadata.md)
- [<span data-ttu-id="31ee8-149">如何：使用代码发布服务的元数据</span><span class="sxs-lookup"><span data-stu-id="31ee8-149">How to: Publish Metadata for a Service Using Code</span></span>](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)
