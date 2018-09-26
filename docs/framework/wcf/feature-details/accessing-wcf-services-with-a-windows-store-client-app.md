---
title: 使用 Windows Store 应用商店客户端应用访问 WCF 服务
ms.date: 03/30/2017
ms.assetid: e2002ef4-5dee-4a54-9d87-03b33d35fc52
ms.openlocfilehash: a6324d5400e9fb15b3373eea4df0a15cd7c54887
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "47176329"
---
# <a name="accessing-wcf-services-with-a-windows-store-client-app"></a><span data-ttu-id="e3e0d-102">使用 Windows Store 应用商店客户端应用访问 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="e3e0d-102">Accessing WCF Services with a Windows Store Client App</span></span>
<span data-ttu-id="e3e0d-103">Windows 8 引入了一种新应用程序，称为 Windows 应用商店应用程序。</span><span class="sxs-lookup"><span data-stu-id="e3e0d-103">Windows 8 introduces a new type of application called Windows Store applications.</span></span> <span data-ttu-id="e3e0d-104">这些应用程序是围绕触摸屏界面设计的。</span><span class="sxs-lookup"><span data-stu-id="e3e0d-104">These applications are designed around a touch screen interface.</span></span> <span data-ttu-id="e3e0d-105">通过 .NET Framework 4.5，Windows 商店应用程序可以调用 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="e3e0d-105">.NET Framework 4.5 enables Windows Store applications to call WCF services.</span></span>  
  
## <a name="wcf-support-in-windows-store-applications"></a><span data-ttu-id="e3e0d-106">Windows 应用商店应用程序中的 WCF 支持</span><span class="sxs-lookup"><span data-stu-id="e3e0d-106">WCF Support in Windows Store Applications</span></span>  
 <span data-ttu-id="e3e0d-107">Windows 应用商店应用程序中提供了 WCF 功能的子集，请参见以下各节以了解更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="e3e0d-107">A subset of WCF functionality is available from within a Windows Store application, see the following sections for more details.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e3e0d-108">请使用 WinRT 联合 API 而不使用由 WCF 公开的 API。</span><span class="sxs-lookup"><span data-stu-id="e3e0d-108">Use the WinRT syndication APIs instead of those exposed by WCF.</span></span> <span data-ttu-id="e3e0d-109">有关详细信息，请参阅[WinRT 联合 API](https://go.microsoft.com/fwlink/?LinkId=236265)</span><span class="sxs-lookup"><span data-stu-id="e3e0d-109">For more information see, [WinRT Syndication API](https://go.microsoft.com/fwlink/?LinkId=236265)</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="e3e0d-110">不支持使用“添加服务引用”向 Windows 运行时组件添加 Web 服务引用。</span><span class="sxs-lookup"><span data-stu-id="e3e0d-110">Using Add Service Reference to add a web service reference to a Windows Runtime Component isn’t supported.</span></span>  
  
### <a name="supported-bindings"></a><span data-ttu-id="e3e0d-111">支持的绑定</span><span class="sxs-lookup"><span data-stu-id="e3e0d-111">Supported Bindings</span></span>  
 <span data-ttu-id="e3e0d-112">Windows 应用商店应用程序支持以下 WCF 绑定：</span><span class="sxs-lookup"><span data-stu-id="e3e0d-112">The following WCF bindings are supported in Windows Store Applications:</span></span>  
  
1.  <xref:System.ServiceModel.BasicHttpBinding>  
  
2.  <xref:System.ServiceModel.NetTcpBinding>  
  
3.  <xref:System.ServiceModel.NetHttpBinding>  
  
4.  <xref:System.ServiceModel.Channels.CustomBinding>
  
 <span data-ttu-id="e3e0d-113">Windows 应用商店应用程序支持以下绑定元素：</span><span class="sxs-lookup"><span data-stu-id="e3e0d-113">The following binding elements are supported in Windows Store Applications</span></span>  
  
1.  <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>  
  
2.  <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>  
  
3.  <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement>  
  
4.  <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>  
  
5.  <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>  
  
6.  <xref:System.ServiceModel.Channels.TcpTransportBindingElement>  
  
7.  <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
  
8.  <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>  
  
9. <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>  
  
 <span data-ttu-id="e3e0d-114">支持文本编码和二进制编码。</span><span class="sxs-lookup"><span data-stu-id="e3e0d-114">Both Text and Binary encodings are supported.</span></span> <span data-ttu-id="e3e0d-115">支持所有 WCF 传输模式。</span><span class="sxs-lookup"><span data-stu-id="e3e0d-115">All WCF transfer modes are supported.</span></span> <span data-ttu-id="e3e0d-116">有关更多信息，请参见 [Streaming Message Transfer](../../../../docs/framework/wcf/feature-details/streaming-message-transfer.md)。</span><span class="sxs-lookup"><span data-stu-id="e3e0d-116">For more information see, [Streaming Message Transfer](../../../../docs/framework/wcf/feature-details/streaming-message-transfer.md).</span></span>  
  
### <a name="add-service-reference"></a><span data-ttu-id="e3e0d-117">添加服务引用</span><span class="sxs-lookup"><span data-stu-id="e3e0d-117">Add Service Reference</span></span>  
 <span data-ttu-id="e3e0d-118">若要从 Windows 应用商店应用程序调用 WCF 服务，请使用 Visual Studio 2012 的“添加服务引用”功能。</span><span class="sxs-lookup"><span data-stu-id="e3e0d-118">To call a WCF service from a Windows Store application, use the Add Service Reference feature of Visual Studio 2012.</span></span> <span data-ttu-id="e3e0d-119">在 Windows 应用商店应用程序中完成操作后，您将注意到添加服务引用功能发生了一些变化。</span><span class="sxs-lookup"><span data-stu-id="e3e0d-119">You will notice a few changes in the functionality of Add Service Reference when done within a Windows Store application.</span></span> <span data-ttu-id="e3e0d-120">首先，不会生成配置文件。</span><span class="sxs-lookup"><span data-stu-id="e3e0d-120">First no configuration file is generated.</span></span> <span data-ttu-id="e3e0d-121">Windows 应用商店应用程序不使用配置文件，因此，必须用代码来对这些应用程序进行配置。</span><span class="sxs-lookup"><span data-stu-id="e3e0d-121">Windows Store applications do not use configuration files, so they must be configured in code.</span></span> <span data-ttu-id="e3e0d-122">此配置代码可在由添加服务引用功能生成的 References.cs 文件中找到。</span><span class="sxs-lookup"><span data-stu-id="e3e0d-122">This configuration code can be found in the References.cs file generated by Add Service Reference.</span></span> <span data-ttu-id="e3e0d-123">若要查看此文件，请确保在解决方案资源管理器中选择"显示所有文件"。</span><span class="sxs-lookup"><span data-stu-id="e3e0d-123">To see this file, make sure to select "Show All Files" in the solution explorer.</span></span> <span data-ttu-id="e3e0d-124">该文件位于项目中“服务引用”的 Reference.svcmap 节点下面。</span><span class="sxs-lookup"><span data-stu-id="e3e0d-124">The file will be located under the Service References and then Reference.svcmap nodes within the project.</span></span> <span data-ttu-id="e3e0d-125">为 Windows 应用商店应用程序中的 WCF 服务生成的所有操作都将使用基于任务的异步模式实现异步。</span><span class="sxs-lookup"><span data-stu-id="e3e0d-125">All operations generated for WCF services within a Windows Store application will be asynchronous using the Task-based asynchronous pattern.</span></span> <span data-ttu-id="e3e0d-126">有关详细信息，请参阅[基于任务的异步模式](https://msdn.microsoft.com/magazine/ff959203.aspx)。</span><span class="sxs-lookup"><span data-stu-id="e3e0d-126">For more information, see [Task-based Asynchronous Pattern](https://msdn.microsoft.com/magazine/ff959203.aspx).</span></span>  
  
 <span data-ttu-id="e3e0d-127">由于现在将使用代码生成配置，因此，每次更新服务引用时，都会覆盖 Reference.cs 文件中所做的任何更改。</span><span class="sxs-lookup"><span data-stu-id="e3e0d-127">Because configuration is now generated in code, any changes made in the Reference.cs file would be overwritten every time the service reference is updated.</span></span> <span data-ttu-id="e3e0d-128">为了纠正这种情况，将在一个部分方法中生成配置代码，您可以在客户端代理类中实现此部分方法。</span><span class="sxs-lookup"><span data-stu-id="e3e0d-128">To remedy this situation the configuration code is generated within a partial method, which you can implement in your client proxy class.</span></span> <span data-ttu-id="e3e0d-129">该部分方法的声明如下：</span><span class="sxs-lookup"><span data-stu-id="e3e0d-129">The partial method is declared as follows:</span></span>  
  
```csharp  
static partial void Configure(System.ServiceModel.Description.ServiceEndpoint serviceEndpoint,  
            System.ServiceModel.Description.ClientCredentials clientCredentials);  
```  
  
 <span data-ttu-id="e3e0d-130">然后，您可以实现此部分方法并更改您的客户端代理类中的绑定或终结点，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e3e0d-130">You can then implement this partial method and change the binding or endpoint in your client proxy class as follows:</span></span>  
  
```csharp  
public partial class Service1Client : System.ServiceModel.ClientBase<MetroWcfClient.ServiceRefMultiEndpt.IService1>, MetroWcfClient.ServiceRefMultiEndpt.IService1  
    {   
        static partial void Configure(System.ServiceModel.Description.ServiceEndpoint serviceEndpoint,   
            System.ServiceModel.Description.ClientCredentials clientCredentials)  
        {  
            if (serviceEndpoint.Name ==   
                    ServiceRefMultiEndpt.Service1Client.EndpointConfiguration.BasicHttpBinding_IService1.ToString())  
            {  
                serviceEndpoint.Binding.SendTimeout = new System.TimeSpan(0, 1, 0);  
            }  
            else if (serviceEndpoint.Name ==   
                    ServiceRefMultiEndpt.Service1Client.EndpointConfiguration.BasicHttpBinding_IService11.ToString())  
            {  
                serviceEndpoint.Binding.SendTimeout = new System.TimeSpan(0, 1, 0);  
                clientCredentials.UserName.UserName = "username1";  
                clientCredentials.UserName.Password = "password";  
            }  
            else if (serviceEndpoint.Name ==   
                    ServiceRefMultiEndpt.Service1Client.EndpointConfiguration.NetTcpBinding_IService1.ToString())  
            {  
                serviceEndpoint.Binding.Name = "MyTcpBinding";  
                serviceEndpoint.Address = new System.ServiceModel.EndpointAddress("net.tcp://localhost/tcp");  
            }  
        }  
    }  
```  
  
### <a name="serialization"></a><span data-ttu-id="e3e0d-131">序列化</span><span class="sxs-lookup"><span data-stu-id="e3e0d-131">Serialization</span></span>  
 <span data-ttu-id="e3e0d-132">Windows 应用商店应用程序支持以下序列化程序：</span><span class="sxs-lookup"><span data-stu-id="e3e0d-132">The following serializers are supported in Windows Store applications:</span></span>  
  
1.  <span data-ttu-id="e3e0d-133">DataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="e3e0d-133">DataContractSerializer</span></span>  
  
2.  <span data-ttu-id="e3e0d-134">DataContractJsonSerializer</span><span class="sxs-lookup"><span data-stu-id="e3e0d-134">DataContractJsonSerializer</span></span>  
  
3.  <span data-ttu-id="e3e0d-135">XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="e3e0d-135">XmlSerializer</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="e3e0d-136">XmlDictionaryWriter.Write(DateTime) 现在会将 DateTime 对象作为字符串写入。</span><span class="sxs-lookup"><span data-stu-id="e3e0d-136">XmlDictionaryWriter.Write(DateTime) now writes the DateTime object as a string.</span></span>  
  
### <a name="security"></a><span data-ttu-id="e3e0d-137">安全性</span><span class="sxs-lookup"><span data-stu-id="e3e0d-137">Security</span></span>  

<span data-ttu-id="e3e0d-138">在 Windows 应用商店应用程序中支持以下安全模式：</span><span class="sxs-lookup"><span data-stu-id="e3e0d-138">The following security modes are supported in Windows Store applications:</span></span>
  
1. <xref:System.ServiceModel.SecurityMode.None>  
  
2. <xref:System.ServiceModel.SecurityMode.Transport>  
  
3. <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>
  
4. <xref:System.ServiceModel.SecurityMode.Message>
  
<span data-ttu-id="e3e0d-139">在 Windows 应用商店应用程序中支持以下客户端凭据类型：</span><span class="sxs-lookup"><span data-stu-id="e3e0d-139">The following client credential types are supported in Windows Store applications:</span></span>
  
1.  <span data-ttu-id="e3e0d-140">无</span><span class="sxs-lookup"><span data-stu-id="e3e0d-140">None</span></span>  
  
2.  <span data-ttu-id="e3e0d-141">Basic</span><span class="sxs-lookup"><span data-stu-id="e3e0d-141">Basic</span></span>  
  
3.  <span data-ttu-id="e3e0d-142">摘要</span><span class="sxs-lookup"><span data-stu-id="e3e0d-142">Digest</span></span>  
  
4.  <span data-ttu-id="e3e0d-143">协商</span><span class="sxs-lookup"><span data-stu-id="e3e0d-143">Negotiate</span></span>  
  
5.  <span data-ttu-id="e3e0d-144">NTLM</span><span class="sxs-lookup"><span data-stu-id="e3e0d-144">NTLM</span></span>  
  
6.  <span data-ttu-id="e3e0d-145">Windows</span><span class="sxs-lookup"><span data-stu-id="e3e0d-145">Windows</span></span>  
  
7.  <span data-ttu-id="e3e0d-146">用户名（消息安全）</span><span class="sxs-lookup"><span data-stu-id="e3e0d-146">Username (Message Security)</span></span>  
  
8.  <span data-ttu-id="e3e0d-147">Windows（传输安全）</span><span class="sxs-lookup"><span data-stu-id="e3e0d-147">Windows (Transport Security)</span></span>  
  
 <span data-ttu-id="e3e0d-148">为了使 Windows 应用商店应用程序访问并发送默认的 Windows 凭据，您必须在 Package.appmanifest 文件中启用此功能。</span><span class="sxs-lookup"><span data-stu-id="e3e0d-148">In order for Windows Store applications to access and send default Windows credentials, you must enable this functionality within the Package.appmanifest file.</span></span> <span data-ttu-id="e3e0d-149">打开此文件，选择功能选项卡并选择"默认 Windows 凭据"。</span><span class="sxs-lookup"><span data-stu-id="e3e0d-149">Open this file and select the Capabilities tab and select "Default Windows Credentials".</span></span> <span data-ttu-id="e3e0d-150">这样，应用程序就可以连接到需要域凭据的 Intranet 资源。</span><span class="sxs-lookup"><span data-stu-id="e3e0d-150">This allows the application to connect to intranet resources that require domain credentials.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e3e0d-151">为了使 Windows 应用商店应用程序进行跨计算机调用必须启用另一个功能是名为"家庭/工作网络连接"。</span><span class="sxs-lookup"><span data-stu-id="e3e0d-151">In order for Windows Store applications to make cross machine calls you must enable another capability called "Home/Work Networking".</span></span> <span data-ttu-id="e3e0d-152">此设置也位于“功能”选项卡下面的 Package.appmanifest 文件中。选中“家庭/工作网络连接”复选框。</span><span class="sxs-lookup"><span data-stu-id="e3e0d-152">This setting is also in the Package.appmanifest file under the Capabilities tab. Select the Home/Work Networking checkbox.</span></span> <span data-ttu-id="e3e0d-153">这样，该应用程序就可以对用户的可信地点（家庭和工作地点）进行入站和出站访问。</span><span class="sxs-lookup"><span data-stu-id="e3e0d-153">This gives your application inbound and outbound access to the networks of the user’s trusted places like home and work.</span></span> <span data-ttu-id="e3e0d-154">将始终阻止关键入站端口。</span><span class="sxs-lookup"><span data-stu-id="e3e0d-154">Inbound critical ports are always blocked.</span></span> <span data-ttu-id="e3e0d-155">为了访问 Internet 上的服务，您还必须启用“Internet (客户端}”功能。</span><span class="sxs-lookup"><span data-stu-id="e3e0d-155">For accessing services on the internet you must also enable Internet (Client) capability.</span></span>  
  
### <a name="misc"></a><span data-ttu-id="e3e0d-156">杂项</span><span class="sxs-lookup"><span data-stu-id="e3e0d-156">Misc</span></span>  
 <span data-ttu-id="e3e0d-157">Windows 应用商店应用程序支持使用下面的类：</span><span class="sxs-lookup"><span data-stu-id="e3e0d-157">The use of the following classes is supported for Windows Store Applications:</span></span>  
  
1.  <xref:System.ServiceModel.ChannelFactory>  
  
2.  <xref:System.ServiceModel.DuplexChannelFactory%601>
  
3.  <xref:System.ServiceModel.CallbackBehaviorAttribute>  
  
### <a name="defining-service-contracts"></a><span data-ttu-id="e3e0d-158">定义服务协定</span><span class="sxs-lookup"><span data-stu-id="e3e0d-158">Defining Service Contracts</span></span>  
 <span data-ttu-id="e3e0d-159">建议使用基于任务的异步模式仅定义异步服务操作。</span><span class="sxs-lookup"><span data-stu-id="e3e0d-159">We recommend only defining asynchronous service operations using the task-based async pattern.</span></span> <span data-ttu-id="e3e0d-160">这可以确保 Windows 应用商店应用程序在调用服务操作时保持响应。</span><span class="sxs-lookup"><span data-stu-id="e3e0d-160">This ensures Windows Store applications remain responsive while calling a service operation.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="e3e0d-161">虽然在定义了同步操作的情况下不会不引发任何异常，但强烈建议仅定义异步操作。</span><span class="sxs-lookup"><span data-stu-id="e3e0d-161">While no exception will be thrown if you define a synchronous operation, it is strongly recommended to only define asynchronous operations.</span></span>  
  
### <a name="calling-wcf-services-from-windows-store-applications"></a><span data-ttu-id="e3e0d-162">从 Windows 应用商店应用程序调用 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="e3e0d-162">Calling WCF Services from Windows Store Applications</span></span>  
 <span data-ttu-id="e3e0d-163">正如前面所述，必须在生成的代理类中的 GetBindingForEndpoint 方法中用代码完成所有配置。</span><span class="sxs-lookup"><span data-stu-id="e3e0d-163">As mentioned before all configuration must be done in code in the GetBindingForEndpoint method in the generated proxy class.</span></span> <span data-ttu-id="e3e0d-164">调用服务操作的方式与调用任何基于任务的异步方法的方式相同，如下面的代码段所示：</span><span class="sxs-lookup"><span data-stu-id="e3e0d-164">Calling a service operation is done the same as calling any task-based asynchronous method as shown in the following code snippet.</span></span>  
  
```csharp  
void async SomeMethod()  
{  
    ServiceClient proxy = new ServiceClient();  
    Task<T> results = await proxy.CallAsync(param1, param2);  
    T result = results.Result;  
    if (result.Success)  
    {  
       // Do something with result  
    }  
}  
```  
  
 <span data-ttu-id="e3e0d-165">请注意进行异步调用的方法上 async 关键字的使用以及调用该异步方法时 await 关键字的使用。</span><span class="sxs-lookup"><span data-stu-id="e3e0d-165">Notice the use of the async keyword on the method making the asynchronous call and the await keyword when calling the asynchronous method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3e0d-166">请参阅</span><span class="sxs-lookup"><span data-stu-id="e3e0d-166">See Also</span></span>  
 [<span data-ttu-id="e3e0d-167">Windows 应用商店应用日志中的 WCF</span><span class="sxs-lookup"><span data-stu-id="e3e0d-167">WCF in Windows Store Apps Blog</span></span>](https://blogs.msdn.com/b/piyushjo/archive/2011/09/22/wcf-in-win8-metro-styled-apps-absolutely-supported.aspx)  
 [<span data-ttu-id="e3e0d-168">WCF Windows 应用商店客户端与安全性</span><span class="sxs-lookup"><span data-stu-id="e3e0d-168">WCF Windows Store Clients and Security</span></span>](https://blogs.msdn.com/b/piyushjo/archive/2011/10/11/calling-a-wcf-service-from-a-metro-application-adding-security.aspx)  
 [<span data-ttu-id="e3e0d-169">Windows 应用商店应用和跨计算机调用</span><span class="sxs-lookup"><span data-stu-id="e3e0d-169">Windows Store Apps and Cross Machine Calls</span></span>](https://blogs.msdn.com/b/piyushjo/archive/2011/10/22/calling-a-wcf-service-from-a-metro-application-cross-machine-scenario.aspx)  
 [<span data-ttu-id="e3e0d-170">调用基于 Windows 应用商店应用程序在 Azure 中部署的 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="e3e0d-170">Calling a WCF Service Deployed in Azure from a Windows Store App</span></span>](https://blogs.msdn.com/b/piyushjo/archive/2011/10/22/calling-a-wcf-service-from-a-metro-application-cross-machine-scenario.aspx)  
 [<span data-ttu-id="e3e0d-171">WCF 安全编程</span><span class="sxs-lookup"><span data-stu-id="e3e0d-171">Programming WCF Security</span></span>](../../../../docs/framework/wcf/feature-details/programming-wcf-security.md)  
 [<span data-ttu-id="e3e0d-172">绑定</span><span class="sxs-lookup"><span data-stu-id="e3e0d-172">Bindings</span></span>](../../../../docs/framework/wcf/bindings.md)
