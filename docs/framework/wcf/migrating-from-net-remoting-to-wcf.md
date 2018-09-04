---
title: 从 .NET 远程处理迁移到 WCF
ms.date: 03/30/2017
ms.assetid: 16902a42-ef80-40e9-8c4c-90e61ddfdfe5
ms.openlocfilehash: e260ecaf422b5654364143b1fc529112b5ea0656
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43659727"
---
# <a name="migrating-from-net-remoting-to-wcf"></a><span data-ttu-id="876e1-102">从 .NET 远程处理迁移到 WCF</span><span class="sxs-lookup"><span data-stu-id="876e1-102">Migrating from .NET Remoting to WCF</span></span>
<span data-ttu-id="876e1-103">本文介绍如何迁移借助 .NET 远程处理来使用 Windows Communication Foundation (WCF) 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="876e1-103">This article describes how to migrate an application that uses .NET Remoting to use Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="876e1-104">本文对这些产品之间的相似概念进行比较，并介绍如何在 WCF 中完成若干常见的远程处理方案。</span><span class="sxs-lookup"><span data-stu-id="876e1-104">It compares similar concepts between these products and then describes how to accomplish several common Remoting scenarios in WCF.</span></span>  
  
 <span data-ttu-id="876e1-105">.NET 远程处理是一项传统技术，仅支持向后兼容性。</span><span class="sxs-lookup"><span data-stu-id="876e1-105">.NET Remoting is a legacy product that is supported only for backward compatibility.</span></span> <span data-ttu-id="876e1-106">由于它无法保持客户端和服务器之间的单独信任级别，因此它在混合信任环境中并不安全。</span><span class="sxs-lookup"><span data-stu-id="876e1-106">It is not secure across mixed-trust environments because it cannot maintain the separate trust levels between client and server.</span></span> <span data-ttu-id="876e1-107">例如，你绝不应将 .NET 远程处理终结点公开到 Internet 或不受信任的客户端中。</span><span class="sxs-lookup"><span data-stu-id="876e1-107">For example, you should never expose a .NET Remoting endpoint to the Internet or to untrusted clients.</span></span> <span data-ttu-id="876e1-108">我们建议将现有的远程处理应用程序迁移到更新和更安全的技术中。</span><span class="sxs-lookup"><span data-stu-id="876e1-108">We recommend existing Remoting applications be migrated to newer and more secure technologies.</span></span> <span data-ttu-id="876e1-109">如果应用程序的设计仅使用 HTTP 并且为 RESTful，那么我们建议迁移到 ASP.NET Web API。</span><span class="sxs-lookup"><span data-stu-id="876e1-109">If the application’s design uses only HTTP and is RESTful, we recommend ASP.NET Web API.</span></span> <span data-ttu-id="876e1-110">有关详细信息，请参阅 ASP.NET Web API。</span><span class="sxs-lookup"><span data-stu-id="876e1-110">For more information, see ASP.NET Web API.</span></span> <span data-ttu-id="876e1-111">如果应用程序基于 SOAP，或者需要非 Http 协议（如 TCP），那么我们建议迁移到 WCF。</span><span class="sxs-lookup"><span data-stu-id="876e1-111">If the application is based on SOAP or requires non-Http protocols such as TCP, we recommend WCF.</span></span>  

## <a name="comparing-net-remoting-to-wcf"></a><span data-ttu-id="876e1-112">比较 .NET 远程处理与 WCF</span><span class="sxs-lookup"><span data-stu-id="876e1-112">Comparing .NET Remoting to WCF</span></span>  
 <span data-ttu-id="876e1-113">本节将对 .NET 远程处理的基本构建基块与其 WCF 等效物进行比较。</span><span class="sxs-lookup"><span data-stu-id="876e1-113">This section compares the basic building blocks of .NET Remoting with their WCF equivalents.</span></span> <span data-ttu-id="876e1-114">稍后我们将使用这些构建基块创建一些 WCF 中常见的客户端-服务器方案。下表总结了 .NET 远程处理和 WCF 之间的主要异同。</span><span class="sxs-lookup"><span data-stu-id="876e1-114">We will use these building blocks later to create some common client-server scenarios in WCF.The following chart summarizes the main similarities and differences between .NET Remoting and WCF.</span></span>  
  
||<span data-ttu-id="876e1-115">.NET 远程处理</span><span class="sxs-lookup"><span data-stu-id="876e1-115">.NET Remoting</span></span>|<span data-ttu-id="876e1-116">WCF</span><span class="sxs-lookup"><span data-stu-id="876e1-116">WCF</span></span>|  
|-|-------------------|---------|  
|<span data-ttu-id="876e1-117">服务器类型</span><span class="sxs-lookup"><span data-stu-id="876e1-117">Server type</span></span>|<span data-ttu-id="876e1-118">子类 MarshalByRefObject</span><span class="sxs-lookup"><span data-stu-id="876e1-118">Subclass MarshalByRefObject</span></span>|<span data-ttu-id="876e1-119">标记为具有 [ServiceContract] 属性</span><span class="sxs-lookup"><span data-stu-id="876e1-119">Mark with [ServiceContract] attribute</span></span>|  
|<span data-ttu-id="876e1-120">服务操作</span><span class="sxs-lookup"><span data-stu-id="876e1-120">Service operations</span></span>|<span data-ttu-id="876e1-121">服务器类型上的公共方法</span><span class="sxs-lookup"><span data-stu-id="876e1-121">Public methods on server type</span></span>|<span data-ttu-id="876e1-122">标记为具有 [OperationContract] 属性</span><span class="sxs-lookup"><span data-stu-id="876e1-122">Mark with [OperationContract] attribute</span></span>|  
|<span data-ttu-id="876e1-123">序列化</span><span class="sxs-lookup"><span data-stu-id="876e1-123">Serialization</span></span>|<span data-ttu-id="876e1-124">ISerializable 或 [Serializable]</span><span class="sxs-lookup"><span data-stu-id="876e1-124">ISerializable or [Serializable]</span></span>|<span data-ttu-id="876e1-125">DataContractSerializer 或 XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="876e1-125">DataContractSerializer or XmlSerializer</span></span>|  
|<span data-ttu-id="876e1-126">传递的对象</span><span class="sxs-lookup"><span data-stu-id="876e1-126">Objects passed</span></span>|<span data-ttu-id="876e1-127">按值或按引用</span><span class="sxs-lookup"><span data-stu-id="876e1-127">By-value or by-reference</span></span>|<span data-ttu-id="876e1-128">仅按值</span><span class="sxs-lookup"><span data-stu-id="876e1-128">By-value only</span></span>|  
|<span data-ttu-id="876e1-129">错误/异常</span><span class="sxs-lookup"><span data-stu-id="876e1-129">Errors/exceptions</span></span>|<span data-ttu-id="876e1-130">任何可序列化的异常</span><span class="sxs-lookup"><span data-stu-id="876e1-130">Any serializable exception</span></span>|<span data-ttu-id="876e1-131">FaultContract\<TDetail></span><span class="sxs-lookup"><span data-stu-id="876e1-131">FaultContract\<TDetail></span></span>|  
|<span data-ttu-id="876e1-132">客户端代理对象</span><span class="sxs-lookup"><span data-stu-id="876e1-132">Client proxy objects</span></span>|<span data-ttu-id="876e1-133">从 MarshalByRefObjects 自动创建强类型透明代理</span><span class="sxs-lookup"><span data-stu-id="876e1-133">Strongly typed transparent proxies are created automatically from MarshalByRefObjects</span></span>|<span data-ttu-id="876e1-134">生成强类型化的代理按需使用 ChannelFactory\<TChannel ></span><span class="sxs-lookup"><span data-stu-id="876e1-134">Strongly typed proxies are generated on-demand using ChannelFactory\<TChannel></span></span>|  
|<span data-ttu-id="876e1-135">所需平台</span><span class="sxs-lookup"><span data-stu-id="876e1-135">Platform required</span></span>|<span data-ttu-id="876e1-136">客户端和服务器必须使用 Microsoft 操作系统和 .NET</span><span class="sxs-lookup"><span data-stu-id="876e1-136">Both client and server must use Microsoft OS and .NET</span></span>|<span data-ttu-id="876e1-137">跨平台</span><span class="sxs-lookup"><span data-stu-id="876e1-137">Cross-platform</span></span>|  
|<span data-ttu-id="876e1-138">消息格式</span><span class="sxs-lookup"><span data-stu-id="876e1-138">Message format</span></span>|<span data-ttu-id="876e1-139">Private</span><span class="sxs-lookup"><span data-stu-id="876e1-139">Private</span></span>|<span data-ttu-id="876e1-140">行业标准（SOAP、WS-\* 等。）</span><span class="sxs-lookup"><span data-stu-id="876e1-140">Industry standards (SOAP, WS-\*, etc.)</span></span>|  
  
### <a name="server-implementation-comparison"></a><span data-ttu-id="876e1-141">服务器实现比较</span><span class="sxs-lookup"><span data-stu-id="876e1-141">Server Implementation Comparison</span></span>  
  
#### <a name="creating-a-server-in-net-remoting"></a><span data-ttu-id="876e1-142">在 .NET 远程处理中创建服务器</span><span class="sxs-lookup"><span data-stu-id="876e1-142">Creating a Server in .NET Remoting</span></span>  
 <span data-ttu-id="876e1-143">.NET 远程处理服务器类型必须从 MarshalByRefObject 中派生，并定义客户端可以调用的方法，如下所示：</span><span class="sxs-lookup"><span data-stu-id="876e1-143">.NET Remoting server types must derive from MarshalByRefObject and define methods the client can call, like the following:</span></span>  
  
```csharp
public class RemotingServer : MarshalByRefObject  
{  
    public Customer GetCustomer(int customerId) { … }  
}  
```  
  
 <span data-ttu-id="876e1-144">此服务器类型的公共方法是客户端可使用的公开协定。</span><span class="sxs-lookup"><span data-stu-id="876e1-144">The public methods of this server type become the public contract available to clients.</span></span>  <span data-ttu-id="876e1-145">一种类型会处理服务器公共接口和其实现，而无需分离。</span><span class="sxs-lookup"><span data-stu-id="876e1-145">There is no separation between the server’s public interface and its implementation – one type handles both.</span></span>  
  
 <span data-ttu-id="876e1-146">一旦定义了服务器类型，其便可用于客户端，如下面示例所示：</span><span class="sxs-lookup"><span data-stu-id="876e1-146">Once the server type has been defined, it can be made available to clients, like in the following example:</span></span>  
  
```csharp
TcpChannel channel = new TcpChannel(8080);  
ChannelServices.RegisterChannel(channel, ensureSecurity : true);  
RemotingConfiguration.RegisterWellKnownServiceType(  
    typeof(RemotingServer),   
    "RemotingServer",   
    WellKnownObjectMode.Singleton);  
Console.WriteLine("RemotingServer is running.  Press ENTER to terminate...");  
Console.ReadLine();  
```  
  
 <span data-ttu-id="876e1-147">使远程处理类型作为服务器可用有多种方法，其中一种方法为使用配置文件。</span><span class="sxs-lookup"><span data-stu-id="876e1-147">There are many ways to make the Remoting type available as a server, including using configuration files.</span></span> <span data-ttu-id="876e1-148">这只是一个示例。</span><span class="sxs-lookup"><span data-stu-id="876e1-148">This is just one example.</span></span>  
  
#### <a name="creating-a-server-in-wcf"></a><span data-ttu-id="876e1-149">在 WCF 中创建服务器</span><span class="sxs-lookup"><span data-stu-id="876e1-149">Creating a Server in WCF</span></span>  
 <span data-ttu-id="876e1-150">WCF 中的等效步骤涉及创建两种类型 -- 公共“服务协定”类和具体实现。</span><span class="sxs-lookup"><span data-stu-id="876e1-150">The equivalent step in WCF involves creating two types -- the public "service contract" and the concrete implementation.</span></span> <span data-ttu-id="876e1-151">第一种类型为接口类，标记为 [ServiceContract]。</span><span class="sxs-lookup"><span data-stu-id="876e1-151">The first is declared as an interface marked with [ServiceContract].</span></span> <span data-ttu-id="876e1-152">客户端可用的方法都标有 [OperationContract]：</span><span class="sxs-lookup"><span data-stu-id="876e1-152">Methods available to clients are marked with [OperationContract]:</span></span>  
  
```csharp
[ServiceContract]  
public interface IWCFServer  
{  
    [OperationContract]  
    Customer GetCustomer(int customerId);  
}  
```  
  
 <span data-ttu-id="876e1-153">服务器的实现则定义在单独的具体的类中，如下面示例所示：</span><span class="sxs-lookup"><span data-stu-id="876e1-153">The server’s implementation is defined in a separate concrete class, like in the following example:</span></span>  
  
```csharp
public class WCFServer : IWCFServer  
{  
    public Customer GetCustomer(int customerId) { … }  
}  
```  
  
 <span data-ttu-id="876e1-154">完成定义这些类型后，WCF 服务器便可提供给客户端，如下面示例所示：</span><span class="sxs-lookup"><span data-stu-id="876e1-154">Once these types have been defined, the WCF server can be made available to clients, like in the following example:</span></span>  
  
```csharp
NetTcpBinding binding = new NetTcpBinding();  
Uri baseAddress = new Uri("net.tcp://localhost:8000/wcfserver");  
  
using (ServiceHost serviceHost = new ServiceHost(typeof(WCFServer), baseAddress))  
{  
    serviceHost.AddServiceEndpoint(typeof(IWCFServer), binding, baseAddress);  
    serviceHost.Open();  
  
    Console.WriteLine(String.Format("The WCF server is ready at {0}.",  
                                    baseAddress));  
    Console.WriteLine("Press <ENTER> to terminate service...");  
    Console.WriteLine();  
    Console.ReadLine();  
}  
```  
  
> [!NOTE]
>  <span data-ttu-id="876e1-155">这两个示例中的 TCP 用于使它们尽可能保持类似。</span><span class="sxs-lookup"><span data-stu-id="876e1-155">TCP is used in both examples to keep them as similar as possible.</span></span> <span data-ttu-id="876e1-156">请参阅本主题稍后的使用 HTTP 的示例方案演练。</span><span class="sxs-lookup"><span data-stu-id="876e1-156">Refer to the scenario walk-throughs later in this topic for examples using HTTP.</span></span>  
  
 <span data-ttu-id="876e1-157">有多种方法来配置和承载 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="876e1-157">There are many ways to configure and to host WCF services.</span></span> <span data-ttu-id="876e1-158">这仅仅是举一个例子，例如称为“自承载”的方法。</span><span class="sxs-lookup"><span data-stu-id="876e1-158">This is just one example, known as "self-hosted".</span></span> <span data-ttu-id="876e1-159">有关详细信息，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="876e1-159">For more information, see the following topics:</span></span>  
  
-   [<span data-ttu-id="876e1-160">如何：定义服务协定</span><span class="sxs-lookup"><span data-stu-id="876e1-160">How to: Define a Service Contract</span></span>](how-to-define-a-wcf-service-contract.md)  
  
-   [<span data-ttu-id="876e1-161">使用配置文件配置服务</span><span class="sxs-lookup"><span data-stu-id="876e1-161">Configuring Services Using Configuration Files</span></span>](configuring-services-using-configuration-files.md)  
  
-   [<span data-ttu-id="876e1-162">托管服务</span><span class="sxs-lookup"><span data-stu-id="876e1-162">Hosting Services</span></span>](hosting-services.md)  
  
### <a name="client-implementation-comparison"></a><span data-ttu-id="876e1-163">客户端实现比较</span><span class="sxs-lookup"><span data-stu-id="876e1-163">Client Implementation Comparison</span></span>  
  
#### <a name="creating-a-client-in-net-remoting"></a><span data-ttu-id="876e1-164">在 .NET 远程处理中创建客户端</span><span class="sxs-lookup"><span data-stu-id="876e1-164">Creating a Client in .NET Remoting</span></span>  
 <span data-ttu-id="876e1-165">一旦 .NET 远程处理服务器对象已经可用，其便可用于客户端，如下面示例所示：</span><span class="sxs-lookup"><span data-stu-id="876e1-165">Once a .NET Remoting server object has been made available, it can be consumed by clients, like in the following example:</span></span>  
  
```csharp
TcpChannel channel = new TcpChannel();  
ChannelServices.RegisterChannel(channel, ensureSecurity : true);  
RemotingServer server = (RemotingServer)Activator.GetObject(  
                            typeof(RemotingServer),   
                            "tcp://localhost:8080/RemotingServer");  
  
RemotingCustomer customer = server.GetCustomer(42);  
Console.WriteLine(String.Format("Customer {0} {1} received.",   
                                 customer.FirstName, customer.LastName));  
```  
  
 <span data-ttu-id="876e1-166">从 Activator.GetObject() 返回的 RemotingServer 实例称为“透明代理”。</span><span class="sxs-lookup"><span data-stu-id="876e1-166">The RemotingServer instance returned from Activator.GetObject() is known as a "transparent proxy."</span></span> <span data-ttu-id="876e1-167">它会实现客户端中的 RemotingServer 类型的公共 API，但所有方法都会调用运行在不同进程或计算机中的服务器对象。</span><span class="sxs-lookup"><span data-stu-id="876e1-167">It implements the public API for the RemotingServer type on the client, but all the methods call the server object running in a different process or machine.</span></span>  
  
#### <a name="creating-a-client-in-wcf"></a><span data-ttu-id="876e1-168">在 WCF 中创建客户端</span><span class="sxs-lookup"><span data-stu-id="876e1-168">Creating a Client in WCF</span></span>  
 <span data-ttu-id="876e1-169">WCF 中的等效步骤涉及使用通道工厂显式创建代理。</span><span class="sxs-lookup"><span data-stu-id="876e1-169">The equivalent step in WCF involves using a channel factory to create the proxy explicitly.</span></span> <span data-ttu-id="876e1-170">与远程处理相同，代理对象可用于调用服务器中的操作，如下面示例所示：</span><span class="sxs-lookup"><span data-stu-id="876e1-170">Like Remoting, the proxy object can be used to invoke operations on the server, like in the following example:</span></span>  
  
```csharp
NetTcpBinding binding = new NetTcpBinding();  
String url = "net.tcp://localhost:8000/wcfserver";  
EndpointAddress address = new EndpointAddress(url);  
ChannelFactory<IWCFServer> channelFactory =   
    new ChannelFactory<IWCFServer>(binding, address);  
IWCFServer server = channelFactory.CreateChannel();  
  
Customer customer = server.GetCustomer(42);  
Console.WriteLine(String.Format("  Customer {0} {1} received.",  
                    customer.FirstName, customer.LastName));  
```  
  
 <span data-ttu-id="876e1-171">此示例演示通道级编程，因为它非常类似于远程处理示例。</span><span class="sxs-lookup"><span data-stu-id="876e1-171">This example shows programming at the channel level because it is most similar to the Remoting example.</span></span> <span data-ttu-id="876e1-172">也可**添加服务引用**生成代码，以简化客户端编程的 Visual Studio 中的方法。</span><span class="sxs-lookup"><span data-stu-id="876e1-172">Also available is the **Add Service Reference** approach in Visual Studio that generates code to simplify client programming.</span></span> <span data-ttu-id="876e1-173">有关详细信息，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="876e1-173">For more information, see the following topics:</span></span>  
  
-   [<span data-ttu-id="876e1-174">客户端通道级编程</span><span class="sxs-lookup"><span data-stu-id="876e1-174">Client Channel-Level Programming</span></span>](./extending/client-channel-level-programming.md)  
  
-   [<span data-ttu-id="876e1-175">如何： 添加、 更新或删除服务引用</span><span class="sxs-lookup"><span data-stu-id="876e1-175">How to: Add, Update, or Remove a Service Reference</span></span>](/visualstudio/data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference)  
  
### <a name="serialization-usage"></a><span data-ttu-id="876e1-176">序列化用法</span><span class="sxs-lookup"><span data-stu-id="876e1-176">Serialization Usage</span></span>  
 <span data-ttu-id="876e1-177">.NET 远程处理和 WCF 均使用序列化发送客户端和服务器之间的对象，但它们在这些重要的方面有所区别：</span><span class="sxs-lookup"><span data-stu-id="876e1-177">Both .NET Remoting and WCF use serialization to send objects between client and server, but they differ in these important ways:</span></span>  
  
1.  <span data-ttu-id="876e1-178">它们使用不同的序列化程序和约定来指示如何序列化。</span><span class="sxs-lookup"><span data-stu-id="876e1-178">They use different serializers and conventions to indicate what to serialize.</span></span>  
  
2.  <span data-ttu-id="876e1-179">.NET 远程处理支持“按引用”序列化，即允许一个层上的方法或属性访问执行另一个层上的代码；此为跨安全边界。</span><span class="sxs-lookup"><span data-stu-id="876e1-179">.NET Remoting supports "by reference" serialization that allows method or property access on one tier to execute code on the other tier, which is across security boundaries.</span></span> <span data-ttu-id="876e1-180">这种功能会公开安全漏洞，并且也是为什么远程处理终结点应永远不向不受信任的客户端公开的主要原因之一。</span><span class="sxs-lookup"><span data-stu-id="876e1-180">This capability exposes security vulnerabilities and is one of the main reasons why Remoting endpoints should never be exposed to untrusted clients.</span></span>  
  
3.  <span data-ttu-id="876e1-181">远程处理使用的序列化会选择退出（显式排除不进行序列化的成员）和 WCF 序列化会选择性加入（显式标记要序列化的成员）。</span><span class="sxs-lookup"><span data-stu-id="876e1-181">Serialization used by Remoting is opt-out (explicitly exclude what not to serialize) and WCF serialization is opt-in (explicitly mark which members to serialize).</span></span>  
  
#### <a name="serialization-in-net-remoting"></a><span data-ttu-id="876e1-182">.NET 远程处理中的序列化</span><span class="sxs-lookup"><span data-stu-id="876e1-182">Serialization in .NET Remoting</span></span>  
 <span data-ttu-id="876e1-183">.NET 远程处理支持两种序列化和反序列化客户端和服务器之间的对象的方法：</span><span class="sxs-lookup"><span data-stu-id="876e1-183">.NET Remoting supports two ways to serialize and deserialize objects between the client and server:</span></span>  
  
-   <span data-ttu-id="876e1-184">*按值*– 跨层边界序列化对象的值和其他层上创建该对象的新实例。</span><span class="sxs-lookup"><span data-stu-id="876e1-184">*By value* – the values of the object are serialized across tier boundaries, and a new instance of that object is created on the other tier.</span></span> <span data-ttu-id="876e1-185">对该新实例的方法或属性的任何调用只是在本地执行，并不影响原始对象或层。</span><span class="sxs-lookup"><span data-stu-id="876e1-185">Any calls to methods or properties of that new instance execute only locally and do not affect the original object or tier.</span></span>  
  
-   <span data-ttu-id="876e1-186">*通过引用*– 跨层边界序列化的特殊"对象引用"。</span><span class="sxs-lookup"><span data-stu-id="876e1-186">*By reference* – a special "object reference" is serialized across tier boundaries.</span></span> <span data-ttu-id="876e1-187">当一个层与该对象的方法或属性进行交互时，此层会传输回至原始层上的原始对象。</span><span class="sxs-lookup"><span data-stu-id="876e1-187">When one tier interacts with methods or properties of that object, it communicates back to the original object on the original tier.</span></span> <span data-ttu-id="876e1-188">按引用对象可以在任一方向 – 服务器到客户端或客户端到服务器中流动。</span><span class="sxs-lookup"><span data-stu-id="876e1-188">By-reference objects can flow in either direction – server to client, or client to server.</span></span>  
  
 <span data-ttu-id="876e1-189">远程处理中按值类型会标记为 [Serializable] 属性或实现 ISerializable，如下面示例所示：</span><span class="sxs-lookup"><span data-stu-id="876e1-189">By-value types in Remoting are marked with the [Serializable] attribute or implement ISerializable, like in the following example:</span></span>  
  
```csharp
[Serializable]  
public class RemotingCustomer  
{  
    public string FirstName { get; set; }  
    public string LastName { get; set; }  
    public int CustomerId { get; set; }  
}  
```  
  
 <span data-ttu-id="876e1-190">按引用类型派生于 MarshalByRefObject 类，如下面示例所示：</span><span class="sxs-lookup"><span data-stu-id="876e1-190">By-reference types derive from the MarshalByRefObject class, like in the following example:</span></span>  
  
```csharp
public class RemotingCustomerReference : MarshalByRefObject  
{  
    public string FirstName { get; set; }  
    public string LastName { get; set; }  
    public int CustomerId { get; set; }  
}  
```  
  
 <span data-ttu-id="876e1-191">了解远程处理中按引用对象的影响尤其重要。</span><span class="sxs-lookup"><span data-stu-id="876e1-191">It is extremely important to understand the implications of Remoting’s by-reference objects.</span></span> <span data-ttu-id="876e1-192">如果任一层（客户端或服务器）将按引用对象发送至其他层，那么所有方法调用会在拥有此对象的层中进行执行。</span><span class="sxs-lookup"><span data-stu-id="876e1-192">If either tier (client or server) sends a by-reference object to the other tier, all method calls execute back on the tier owning the object.</span></span> <span data-ttu-id="876e1-193">例如，调用服务器返回的按引用对象中方法的客户端将在服务器中执行代码。</span><span class="sxs-lookup"><span data-stu-id="876e1-193">For example, a client calling methods on a by-reference object returned by the server will execute code on the server.</span></span> <span data-ttu-id="876e1-194">同样，调用客户端提供的按引用对象中方法的服务器将在客户端中执行代码。</span><span class="sxs-lookup"><span data-stu-id="876e1-194">Similarly, a server calling methods on a by-reference object provided by the client will execute code back on the client.</span></span> <span data-ttu-id="876e1-195">因此，建议只在完全信任环境中使用 .NET 远程处理。</span><span class="sxs-lookup"><span data-stu-id="876e1-195">For this reason, the use of .NET Remoting is recommended only within fully-trusted environments.</span></span> <span data-ttu-id="876e1-196">向不受信任的客户端公开公共 .NET 远程处理终结点将使远程处理服务器容易受到攻击。</span><span class="sxs-lookup"><span data-stu-id="876e1-196">Exposing a public .NET Remoting endpoint to untrusted clients will make a Remoting server vulnerable to attack.</span></span>  
  
#### <a name="serialization-in-wcf"></a><span data-ttu-id="876e1-197">WCF 中的序列化</span><span class="sxs-lookup"><span data-stu-id="876e1-197">Serialization in WCF</span></span>  
 <span data-ttu-id="876e1-198">WCF 仅支持按值序列化。</span><span class="sxs-lookup"><span data-stu-id="876e1-198">WCF supports only by-value serialization.</span></span> <span data-ttu-id="876e1-199">定义客户端和服务器之间交换的类型的最常见方法，如下面示例所示：</span><span class="sxs-lookup"><span data-stu-id="876e1-199">The most common way to define a type to exchange between client and server is like in the following example:</span></span>  
  
```csharp
[DataContract]  
public class WCFCustomer  
{  
    [DataMember]  
    public string FirstName { get; set; }  
  
    [DataMember]  
    public string LastName { get; set; }  
  
    [DataMember]  
    public int CustomerId { get; set; }  
}  
```  
  
 <span data-ttu-id="876e1-200">[DataContract] 特性标识此类型为可在客户端和服务器之间进行序列化和反序列化。</span><span class="sxs-lookup"><span data-stu-id="876e1-200">The [DataContract] attribute identifies this type as one that can be serialized and deserialized between client and server.</span></span> <span data-ttu-id="876e1-201">[DataMember] 特性标识要序列化的单个属性或字段。</span><span class="sxs-lookup"><span data-stu-id="876e1-201">The [DataMember] attribute identifies the individual properties or fields to serialize.</span></span>  
  
 <span data-ttu-id="876e1-202">当 WCF 跨多个层发送某个对象时，它仅序列化值并在另一个层上创建此对象的新实例。</span><span class="sxs-lookup"><span data-stu-id="876e1-202">When WCF sends an object across tiers, it serializes only the values and creates a new instance of the object on the other tier.</span></span> <span data-ttu-id="876e1-203">与此对象的值进行的任何交互仅发生在本地 – 它们不能如 .NET 远程处理中的按引用对象一样与其他层进行通信。</span><span class="sxs-lookup"><span data-stu-id="876e1-203">Any interactions with the values of the object occur only locally – they do not communicate with the other tier the way .NET Remoting by-reference objects do.</span></span> <span data-ttu-id="876e1-204">有关详细信息，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="876e1-204">For more information, see the following topics:</span></span>  
  
-   [<span data-ttu-id="876e1-205">序列化和反序列化</span><span class="sxs-lookup"><span data-stu-id="876e1-205">Serialization and Deserialization</span></span>](./feature-details/serialization-and-deserialization.md)  
  
-   [<span data-ttu-id="876e1-206">Windows Communication Foundation 中的序列化</span><span class="sxs-lookup"><span data-stu-id="876e1-206">Serialization in Windows Communication Foundation</span></span>](https://msdn.microsoft.com/magazine/cc163569.aspx)  
  
### <a name="exception-handling-capabilities"></a><span data-ttu-id="876e1-207">异常处理功能</span><span class="sxs-lookup"><span data-stu-id="876e1-207">Exception Handling Capabilities</span></span>  
  
#### <a name="exceptions-in-net-remoting"></a><span data-ttu-id="876e1-208">.NET 远程处理中的异常</span><span class="sxs-lookup"><span data-stu-id="876e1-208">Exceptions in .NET Remoting</span></span>  
 <span data-ttu-id="876e1-209">由远程处理服务器引发的异常会进行序列化、发送到客户端并如同其他异常一样引发在本地的客户端中。</span><span class="sxs-lookup"><span data-stu-id="876e1-209">Exceptions thrown by a Remoting server are serialized, sent to the client, and thrown locally on the client like any other exception.</span></span> <span data-ttu-id="876e1-210">可通过子类分类异常类型，并将其标记为 [Serializable] 来创建自定义异常。</span><span class="sxs-lookup"><span data-stu-id="876e1-210">Custom exceptions can be created by sub-classing the Exception type and marking it with [Serializable].</span></span>   <span data-ttu-id="876e1-211">多数 Framework 异常已以这种方法进行了标记，从而使多数异常由服务器引发、进行序列化并在客户端重新引发。</span><span class="sxs-lookup"><span data-stu-id="876e1-211">Most framework exceptions are already marked in this way, allowing most to be thrown by the server, serialized, and re-thrown on the client.</span></span> <span data-ttu-id="876e1-212">尽管这种设计在开发过程中的确方便，但服务器端信息却可以意外地泄露至客户端中。</span><span class="sxs-lookup"><span data-stu-id="876e1-212">Though this design is convenient during development, server-side information can inadvertently be disclosed to the client.</span></span> <span data-ttu-id="876e1-213">这是应仅在完全信任环境中使用远程处理的许多原因之一。</span><span class="sxs-lookup"><span data-stu-id="876e1-213">This is one of many reasons Remoting should be used only in fully-trusted environments.</span></span>  
  
#### <a name="exceptions-and-faults-in-wcf"></a><span data-ttu-id="876e1-214">WCF 中的异常和错误</span><span class="sxs-lookup"><span data-stu-id="876e1-214">Exceptions and Faults in WCF</span></span>  
 <span data-ttu-id="876e1-215">WCF 不允许任意异常类型从服务器返回到客户端，因为可能导致意外的信息泄露。</span><span class="sxs-lookup"><span data-stu-id="876e1-215">WCF does not allow arbitrary exception types to be returned from the server to the client because it could lead to inadvertent information disclosure.</span></span> <span data-ttu-id="876e1-216">如果服务操作引发了意外的异常，则会导致在客户端引发一般用途的 FaultException。</span><span class="sxs-lookup"><span data-stu-id="876e1-216">If a service operation throws an unexpected exception, it causes a general purpose FaultException to be thrown on the client.</span></span> <span data-ttu-id="876e1-217">此异常不会带有关于问题产生的原因或地点的任何信息，并且对于一些应用程序来讲，这些信息也就足够了。</span><span class="sxs-lookup"><span data-stu-id="876e1-217">This exception does not carry any information why or where the problem occurred, and for some applications this is sufficient.</span></span> <span data-ttu-id="876e1-218">通过定义错误协定，需要将更丰富的错误信息传递给客户端的应用程序会进行此操作。</span><span class="sxs-lookup"><span data-stu-id="876e1-218">Applications that need to communicate richer error information to the client do this by defining a fault contract.</span></span>  
  
 <span data-ttu-id="876e1-219">若要执行此操作，请首先创建 [DataContract] 类型，以执行故障信息。</span><span class="sxs-lookup"><span data-stu-id="876e1-219">To do this, first create a [DataContract] type to carry the fault information.</span></span>  
  
```csharp
[DataContract]  
public class CustomerServiceFault  
{  
    [DataMember]  
    public string ErrorMessage { get; set; }  
  
    [DataMember]  
    public int CustomerId {get;set;}  
}  
```  
  
 <span data-ttu-id="876e1-220">指定要用于每个服务操作的错误协定。</span><span class="sxs-lookup"><span data-stu-id="876e1-220">Specify the fault contract to use for each service operation.</span></span>  
  
```csharp
[ServiceContract]  
public interface IWCFServer  
{  
    [OperationContract]  
    [FaultContract(typeof(CustomerServiceFault))]  
    Customer GetCustomer(int customerId);  
}  
```  
  
 <span data-ttu-id="876e1-221">服务器会通过引发 FaultException 从而报告错误条件。</span><span class="sxs-lookup"><span data-stu-id="876e1-221">The server reports error conditions by throwing a FaultException.</span></span>  
  
```csharp
throw new FaultException<CustomerServiceFault>(  
    new CustomerServiceFault() {   
        CustomerId = customerId,   
        ErrorMessage = "Illegal customer Id"   
    });  
```  
  
 <span data-ttu-id="876e1-222">只要客户端向服务器发出请求，都可以作为正常异常进行捕获。</span><span class="sxs-lookup"><span data-stu-id="876e1-222">And whenever the client makes a request to the server, it can catch faults as normal exceptions.</span></span>  
  
```csharp
try  
{  
    Customer customer = server.GetCustomer(-1);  
}  
catch (FaultException<CustomerServiceFault> fault)  
{  
    Console.WriteLine(String.Format("Fault received: {0}",  
    fault.Detail.ErrorMessage));  
}  
```  
  
 <span data-ttu-id="876e1-223">有关故障协定的详细信息，请参阅 <xref:System.ServiceModel.FaultException>。</span><span class="sxs-lookup"><span data-stu-id="876e1-223">For more information about fault contracts, see <xref:System.ServiceModel.FaultException>.</span></span>  
  
### <a name="security-considerations"></a><span data-ttu-id="876e1-224">安全注意事项</span><span class="sxs-lookup"><span data-stu-id="876e1-224">Security Considerations</span></span>  
  
#### <a name="security-in-net-remoting"></a><span data-ttu-id="876e1-225">.NET 远程处理的安全性</span><span class="sxs-lookup"><span data-stu-id="876e1-225">Security in .NET Remoting</span></span>  
 <span data-ttu-id="876e1-226">某些 .NET 远程处理信道支持安全功能，比如通道层（IPC 和 TCP）中的身份验证和加密。</span><span class="sxs-lookup"><span data-stu-id="876e1-226">Some .NET Remoting channels support security features such as authentication and encryption at the channel layer (IPC and TCP).</span></span> <span data-ttu-id="876e1-227">HTTP 通道依赖于身份验证和加密的 Internet Information Services (IIS)。</span><span class="sxs-lookup"><span data-stu-id="876e1-227">The HTTP channel relies on Internet Information Services (IIS) for both authentication and encryption.</span></span> <span data-ttu-id="876e1-228">即使有这种支持，你仍应该将 .NET 远程处理认定为不安全的通信协议并只在完全信任的环境中使用。</span><span class="sxs-lookup"><span data-stu-id="876e1-228">Despite this support, you should consider .NET Remoting an unsecure communication protocol and use it only within fully-trusted environments.</span></span> <span data-ttu-id="876e1-229">永远不要将公共远程处理终结点公开到 Internet 或不受信任的客户端中。</span><span class="sxs-lookup"><span data-stu-id="876e1-229">Never expose a public Remoting endpoint to the Internet or untrusted clients.</span></span>  
  
#### <a name="security-in-wcf"></a><span data-ttu-id="876e1-230">WCF 中的安全性</span><span class="sxs-lookup"><span data-stu-id="876e1-230">Security in WCF</span></span>  
 <span data-ttu-id="876e1-231">WCF 中对于安全性的设计是为了解决出现在 .NET 远程处理中各种的漏洞。</span><span class="sxs-lookup"><span data-stu-id="876e1-231">WCF was designed with security in mind, in part to address the kinds of vulnerabilities found in .NET Remoting.</span></span> <span data-ttu-id="876e1-232">WCF 提供了传输和消息级别的安全性，并提供了多个用于身份验证、授权、加密等的选项。</span><span class="sxs-lookup"><span data-stu-id="876e1-232">WCF offers security at both the transport and message level, and offers many options for authentication, authorization, encryption, and so on.</span></span> <span data-ttu-id="876e1-233">有关详细信息，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="876e1-233">For more information, see the following topics:</span></span>  
  
-   [<span data-ttu-id="876e1-234">安全性</span><span class="sxs-lookup"><span data-stu-id="876e1-234">Security</span></span>](./feature-details/security.md)  
  
-   [<span data-ttu-id="876e1-235">WCF 安全指南</span><span class="sxs-lookup"><span data-stu-id="876e1-235">WCF Security Guidance</span></span>](./feature-details/security-guidance-and-best-practices.md)  
  
## <a name="migrating-to-wcf"></a><span data-ttu-id="876e1-236">迁移到 WCF</span><span class="sxs-lookup"><span data-stu-id="876e1-236">Migrating to WCF</span></span>  
  
### <a name="why-migrate-from-remoting-to-wcf"></a><span data-ttu-id="876e1-237">为什么从远程处理迁移到 WCF？</span><span class="sxs-lookup"><span data-stu-id="876e1-237">Why Migrate from Remoting to WCF?</span></span>  
  
-   <span data-ttu-id="876e1-238">**.NET 远程处理是一项传统技术。**</span><span class="sxs-lookup"><span data-stu-id="876e1-238">**.NET Remoting is a legacy product.**</span></span> <span data-ttu-id="876e1-239">如中所述[.NET 远程处理](https://msdn.microsoft.com/library/vstudio/72x4h507\(v=vs.100\).aspx)，被视为一项传统技术，不建议用于新开发。</span><span class="sxs-lookup"><span data-stu-id="876e1-239">As described in [.NET Remoting](https://msdn.microsoft.com/library/vstudio/72x4h507\(v=vs.100\).aspx), it is considered a legacy product and is not recommended for new development.</span></span> <span data-ttu-id="876e1-240">对于新的和现有的应用程序建议使用 WCF 或 ASP.NET Web API。</span><span class="sxs-lookup"><span data-stu-id="876e1-240">WCF or ASP.NET Web API are recommended for new and existing applications.</span></span>  
  
-   <span data-ttu-id="876e1-241">**WCF 使用跨平台标准。**</span><span class="sxs-lookup"><span data-stu-id="876e1-241">**WCF uses cross-platform standards.**</span></span> <span data-ttu-id="876e1-242">WCF 设计的跨平台互操作性支持许多行业标准（SOAP、Ws-security、Ws-trust 等。）。</span><span class="sxs-lookup"><span data-stu-id="876e1-242">WCF was designed with cross-platform interoperability in mind and supports many industry standards (SOAP, WS-Security, WS-Trust, etc.).</span></span> <span data-ttu-id="876e1-243">除了运行 Windows 操作系统的客户端之外，WCF 服务还可以与运行其他操作系统的客户端进行互操作。</span><span class="sxs-lookup"><span data-stu-id="876e1-243">A WCF service can interoperate with clients running on operating systems other than Windows.</span></span> <span data-ttu-id="876e1-244">远程处理是主要为其中的服务器和客户端应用程序使用 .NET framework 在 Windows 操作系统中运行的环境而设计的。</span><span class="sxs-lookup"><span data-stu-id="876e1-244">Remoting was designed primarily for environments where both the server and client applications run using the .NET framework on a Windows operating system.</span></span>  
  
-   <span data-ttu-id="876e1-245">**WCF 具有内置安全性。**</span><span class="sxs-lookup"><span data-stu-id="876e1-245">**WCF has built-in security.**</span></span> <span data-ttu-id="876e1-246">在设计 WCF 时便将安全性考虑在内，并提供了多个用于身份验证、传输级别安全、消息级别安全等的选项。远程处理旨在使应用程序的互操作性更加简单，但并不是使其在不受信任的环境中变得安全。</span><span class="sxs-lookup"><span data-stu-id="876e1-246">WCF was designed with security in mind and offers many options for authentication, transport level security, message level security, etc. Remoting was designed to make it easy for applications to interoperate but was not designed to be secure in non-trusted environments.</span></span> <span data-ttu-id="876e1-247">WCF 设计为可以在受信任和不受信任的两种环境中工作。</span><span class="sxs-lookup"><span data-stu-id="876e1-247">WCF was designed to work in both trusted and non-trusted environments.</span></span>  
  
### <a name="migration-recommendations"></a><span data-ttu-id="876e1-248">迁移建议</span><span class="sxs-lookup"><span data-stu-id="876e1-248">Migration Recommendations</span></span>  
 <span data-ttu-id="876e1-249">若要从 .NET 远程处理迁移到 WCF，建议步骤如下所示：</span><span class="sxs-lookup"><span data-stu-id="876e1-249">The following are the recommended steps to migrate from .NET Remoting to WCF:</span></span>  
  
-   <span data-ttu-id="876e1-250">**创建服务协定。**</span><span class="sxs-lookup"><span data-stu-id="876e1-250">**Create the service contract.**</span></span> <span data-ttu-id="876e1-251">定义服务接口类型，并将其标记为 [ServiceContract] 属性。标记所有允许客户端利用 [OperationContract] 调用的方法。</span><span class="sxs-lookup"><span data-stu-id="876e1-251">Define your service interface types, and mark them with the [ServiceContract] attribute.Mark all the methods the clients will be allowed to call with [OperationContract].</span></span>  
  
-   <span data-ttu-id="876e1-252">**创建数据协定。**</span><span class="sxs-lookup"><span data-stu-id="876e1-252">**Create the data contract.**</span></span> <span data-ttu-id="876e1-253">定义将在服务器和客户端之间进行交换的数据类型，并将其标记为 [DataContract] 属性。</span><span class="sxs-lookup"><span data-stu-id="876e1-253">Define the data types that will be exchanged between server and client, and mark them with the [DataContract] attribute.</span></span> <span data-ttu-id="876e1-254">标记允许客户端利用 [DataMember] 使用的所有字段和属性。</span><span class="sxs-lookup"><span data-stu-id="876e1-254">Mark all the fields and properties the client will be allowed to use with [DataMember].</span></span>  
  
-   <span data-ttu-id="876e1-255">**创建错误协定 （可选）。**</span><span class="sxs-lookup"><span data-stu-id="876e1-255">**Create the fault contract (optional).**</span></span> <span data-ttu-id="876e1-256">遇到错误时，请创建将在服务器和客户端之间进行交换的类型。</span><span class="sxs-lookup"><span data-stu-id="876e1-256">Create the types that will be exchanged between server and client when errors are encountered.</span></span> <span data-ttu-id="876e1-257">将这些类型标记为 [DataContract] 和 [DataMember] 以使其可序列化。</span><span class="sxs-lookup"><span data-stu-id="876e1-257">Mark these types with [DataContract] and [DataMember] to make them serializable.</span></span> <span data-ttu-id="876e1-258">对于标记为 [OperationContract] 的所有服务操作，还可将其标记为 [FaultContract]，以指示它们可能会返回哪些错误。</span><span class="sxs-lookup"><span data-stu-id="876e1-258">For all service operations you marked with [OperationContract], also mark them with [FaultContract] to indicate which errors they may return.</span></span>  
  
-   <span data-ttu-id="876e1-259">**配置和承载服务。**</span><span class="sxs-lookup"><span data-stu-id="876e1-259">**Configure and host the service.**</span></span> <span data-ttu-id="876e1-260">完成创建服务协定后，下一步则是配置一个绑定以公开终结点中的服务。</span><span class="sxs-lookup"><span data-stu-id="876e1-260">Once the service contract has been created, the next step is to configure a binding to expose the service at an endpoint.</span></span> <span data-ttu-id="876e1-261">有关详细信息，请参阅[终结点： 地址、 绑定和协定](./feature-details/endpoints-addresses-bindings-and-contracts.md)。</span><span class="sxs-lookup"><span data-stu-id="876e1-261">For more information, see [Endpoints: Addresses, Bindings, and Contracts](./feature-details/endpoints-addresses-bindings-and-contracts.md).</span></span>  
  
 <span data-ttu-id="876e1-262">将远程处理应用程序迁移到 WCF 后，删除 .NET 远程处理中的依赖仍然很重要。</span><span class="sxs-lookup"><span data-stu-id="876e1-262">Once a Remoting application has been migrated to WCF, it is still important to remove dependencies on .NET Remoting.</span></span> <span data-ttu-id="876e1-263">这可确保删除应用程序中的任何远程处理漏洞。</span><span class="sxs-lookup"><span data-stu-id="876e1-263">This ensures that any Remoting vulnerabilities are removed from the application.</span></span> <span data-ttu-id="876e1-264">这些步骤包括：</span><span class="sxs-lookup"><span data-stu-id="876e1-264">These steps include the following:</span></span>  
  
-   <span data-ttu-id="876e1-265">**停止使用 MarshalByRefObject。**</span><span class="sxs-lookup"><span data-stu-id="876e1-265">**Discontinue use of MarshalByRefObject.**</span></span> <span data-ttu-id="876e1-266">MarshalByRefObject 类型仅因远程处理而存在并且 WCF 并不使用此类型。</span><span class="sxs-lookup"><span data-stu-id="876e1-266">The MarshalByRefObject type exists only for Remoting and is not used by WCF.</span></span> <span data-ttu-id="876e1-267">应删除或更改子类 MarshalByRefObject 的任何应用程序类型。</span><span class="sxs-lookup"><span data-stu-id="876e1-267">Any application types that sub-class MarshalByRefObject should be removed or changed.</span></span> <span data-ttu-id="876e1-268">MarshalByRefObject 类型仅因远程处理而存在并且 WCF 并不使用此类型。</span><span class="sxs-lookup"><span data-stu-id="876e1-268">The MarshalByRefObject type exists only for Remoting and is not used by WCF.</span></span> <span data-ttu-id="876e1-269">应删除或更改子类 MarshalByRefObject 的任何应用程序类型。</span><span class="sxs-lookup"><span data-stu-id="876e1-269">Any application types that sub-class MarshalByRefObject should be removed or changed.</span></span>  
  
-   <span data-ttu-id="876e1-270">**停止使用 [Serializable] 和 ISerializable。**</span><span class="sxs-lookup"><span data-stu-id="876e1-270">**Discontinue use of [Serializable] and ISerializable.**</span></span> <span data-ttu-id="876e1-271">[Serializable] 属性和 ISerializable 接口最初用于在受信任的环境中序列化类型，并为远程处理所用。</span><span class="sxs-lookup"><span data-stu-id="876e1-271">The [Serializable] attribute and ISerializable interface were originally designed to serialize types within trusted environments, and they are used by Remoting.</span></span> <span data-ttu-id="876e1-272">WCF 序列化依赖于标记为 [DataContract] 和 [DataMember] 的类型。</span><span class="sxs-lookup"><span data-stu-id="876e1-272">WCF serialization relies on types being marked with [DataContract] and [DataMember].</span></span> <span data-ttu-id="876e1-273">若要使用 [DataContract]，而不是使用 ISerializable 或 [Serializable]，则应修改应用程序使用的数据类型。</span><span class="sxs-lookup"><span data-stu-id="876e1-273">Data types used by an application should be modified to use [DataContract] and not to use ISerializable or [Serializable].</span></span> <span data-ttu-id="876e1-274">[Serializable] 属性和 ISerializable 接口最初用于在受信任的环境中序列化类型，并为远程处理所用。</span><span class="sxs-lookup"><span data-stu-id="876e1-274">The [Serializable] attribute and ISerializable interface were originally designed to serialize types within trusted environments, and they are used by Remoting.</span></span> <span data-ttu-id="876e1-275">WCF 序列化依赖于标记为 [DataContract] 和 [DataMember] 的类型。</span><span class="sxs-lookup"><span data-stu-id="876e1-275">WCF serialization relies on types being marked with [DataContract] and [DataMember].</span></span> <span data-ttu-id="876e1-276">若要使用 [DataContract]，而不是使用 ISerializable 或 [Serializable]，则应修改应用程序使用的数据类型。</span><span class="sxs-lookup"><span data-stu-id="876e1-276">Data types used by an application should be modified to use [DataContract] and not to use ISerializable or [Serializable].</span></span>  
  
### <a name="migration-scenarios"></a><span data-ttu-id="876e1-277">迁移方案</span><span class="sxs-lookup"><span data-stu-id="876e1-277">Migration Scenarios</span></span>  
 <span data-ttu-id="876e1-278">现在让我们了解如何完成以下 WCF 中的常见远程处理方案：</span><span class="sxs-lookup"><span data-stu-id="876e1-278">Now let’s see how to accomplish the following common Remoting scenarios in WCF:</span></span>  
  
1.  <span data-ttu-id="876e1-279">服务器将对象按值返回到客户端</span><span class="sxs-lookup"><span data-stu-id="876e1-279">Server returns an object by-value to the client</span></span>  
  
2.  <span data-ttu-id="876e1-280">服务器将对象按引用返回到客户端</span><span class="sxs-lookup"><span data-stu-id="876e1-280">Server returns an object by-reference to the client</span></span>  
  
3.  <span data-ttu-id="876e1-281">客户端按值向服务器发送对象</span><span class="sxs-lookup"><span data-stu-id="876e1-281">Client sends an object by-value to the server</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="876e1-282">WCF 中不允许从客户端将对象按引用发送到服务器。</span><span class="sxs-lookup"><span data-stu-id="876e1-282">Sending an object by-reference from the client to the server is not allowed in WCF.</span></span>  
  
 <span data-ttu-id="876e1-283">阅读这些方案后，假定 .NET 远程处理的基线接口将如下面示例所示。</span><span class="sxs-lookup"><span data-stu-id="876e1-283">When reading through these scenarios, assume our baseline interfaces for .NET Remoting look like the following example.</span></span> <span data-ttu-id="876e1-284">由于在这里仅想说明如何使用 WCF 实现等效功能，因此 .NET 远程处理实现在此并不重要。</span><span class="sxs-lookup"><span data-stu-id="876e1-284">The .NET Remoting implementation is not important here because we want to illustrate only how to use WCF to implement equivalent functionality.</span></span>  
  
```csharp
public class RemotingServer : MarshalByRefObject  
{  
    // Demonstrates server returning object by-value  
    public Customer GetCustomer(int customerId) {…}  
  
    // Demonstrates server returning object by-reference  
    public CustomerReference GetCustomerReference(int customerId) {…}  
  
    // Demonstrates client passing object to server by-value  
    public bool UpdateCustomer(Customer customer) {…}  
}  
```  
  
#### <a name="scenario-1-service-returns-an-object-by-value"></a><span data-ttu-id="876e1-285">方案 1：服务按值返回对象</span><span class="sxs-lookup"><span data-stu-id="876e1-285">Scenario 1: Service Returns an Object by Value</span></span>  
 <span data-ttu-id="876e1-286">此方案演示服务器按值将对象返回至客户端。</span><span class="sxs-lookup"><span data-stu-id="876e1-286">This scenario demonstrates a server returning an object to the client by value.</span></span> <span data-ttu-id="876e1-287">WCF 始终按值从服务器中返回对象，因此以下步骤仅描述了如何创建普通 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="876e1-287">WCF always returns objects from the server by value, so the following steps simply describe how to build a normal WCF service.</span></span>  
  
1.  <span data-ttu-id="876e1-288">首先定义 WCF 服务的公共接口并标记 [ServiceContract] 属性。</span><span class="sxs-lookup"><span data-stu-id="876e1-288">Start by defining a public interface for the WCF service and mark it with the [ServiceContract] attribute.</span></span> <span data-ttu-id="876e1-289">使用 [OperationContract] 标识客户端将调用的服务器端方法。</span><span class="sxs-lookup"><span data-stu-id="876e1-289">We use [OperationContract] to identify the server-side methods our client will call.</span></span>  
  
   ```csharp
   [ServiceContract]  
   public interface ICustomerService  
   {  
       [OperationContract]  
       Customer GetCustomer(int customerId);  
  
       [OperationContract]  
       bool UpdateCustomer(Customer customer);  
   }  
   ```  
  
2.  <span data-ttu-id="876e1-290">下一步则是创建此服务的数据约定。</span><span class="sxs-lookup"><span data-stu-id="876e1-290">The next step is to create the data contract for this service.</span></span> <span data-ttu-id="876e1-291">通过创建具有 [DataContract] 属性标记的类（非接口）来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="876e1-291">We do this by creating classes (not interfaces) marked with the [DataContract] attribute.</span></span> <span data-ttu-id="876e1-292">希望对客户端和服务器可见的单独属性或字段标记为 [DataMember]。</span><span class="sxs-lookup"><span data-stu-id="876e1-292">The individual properties or fields we want visible to both client and server are marked with [DataMember].</span></span> <span data-ttu-id="876e1-293">如果希望使用允许派生的类型，则必须使用 [KnownType] 属性来进行标记。</span><span class="sxs-lookup"><span data-stu-id="876e1-293">If we want derived types to be allowed, we must use the [KnownType] attribute to identify them.</span></span> <span data-ttu-id="876e1-294">WCF 中允许为此服务进行序列化或反序列化的唯一类型是服务接口类型和“已知类型”。</span><span class="sxs-lookup"><span data-stu-id="876e1-294">The only types WCF will allow to be serialized or deserialized for this service are those in the service interface and these "known types".</span></span> <span data-ttu-id="876e1-295">拒绝尝试交换不在此列表中的任何其他类型。</span><span class="sxs-lookup"><span data-stu-id="876e1-295">Attempting to exchange any other type not in this list will be rejected.</span></span>  
  
   ```csharp
   [DataContract]  
   [KnownType(typeof(PremiumCustomer))]  
   public class Customer  
   {  
       [DataMember]  
       public string FirstName { get; set; }  
  
       [DataMember]  
       public string LastName { get; set; }  
  
       [DataMember]  
       public int CustomerId { get; set; }  
   }  
  
   [DataContract]  
   public class PremiumCustomer : Customer   
   {  
       [DataMember]  
       public int AccountId { get; set; }  
   }  
   ```  
  
3.  <span data-ttu-id="876e1-296">接下来，将提供服务接口的实现。</span><span class="sxs-lookup"><span data-stu-id="876e1-296">Next, we provide the implementation for the service interface.</span></span>  
  
   ```csharp  
   public class CustomerService : ICustomerService  
   {  
       public Customer GetCustomer(int customerId)  
       {  
           // read from database  
       }  
  
       public bool UpdateCustomer(Customer customer)  
       {  
           // write to database  
       }  
   }  
   ```  
  
4.  <span data-ttu-id="876e1-297">若要运行 WCF 服务，则需要声明终结点将公开使用特定 WCF 绑定的特定 URL 中的该服务接口。</span><span class="sxs-lookup"><span data-stu-id="876e1-297">To run the WCF service, we need to declare an endpoint that exposes that service interface at a specific URL using a specific WCF binding.</span></span> <span data-ttu-id="876e1-298">这通常通过向服务器项目的 web.config 文件中添加以下各节而实现的。</span><span class="sxs-lookup"><span data-stu-id="876e1-298">This is typically done by adding the following sections to the server project’s web.config file.</span></span>  
  
    ```xml  
    <configuration>  
      <system.serviceModel>  
        <services>  
          <service name="Server.CustomerService">  
            <endpoint address="http://localhost:8083/CustomerService"  
                      binding="basicHttpBinding"  
                      contract="Shared.ICustomerService" />  
          </service>  
        </services>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
5.  <span data-ttu-id="876e1-299">然后，可用下面的代码中启动 WCF 服务：</span><span class="sxs-lookup"><span data-stu-id="876e1-299">The WCF service can then be started with the following code:</span></span>  
  
   ```csharp
   ServiceHost customerServiceHost = new ServiceHost(typeof(CustomerService));  
       customerServiceHost.Open();  
   ```  
  
     <span data-ttu-id="876e1-300">当启动此 ServiceHost 时，它会使用 web.config 文件以建立适当的协定、绑定和终结点。</span><span class="sxs-lookup"><span data-stu-id="876e1-300">When this ServiceHost is started, it uses the web.config file to establish the proper contract, binding and endpoint.</span></span> <span data-ttu-id="876e1-301">有关配置文件的详细信息，请参阅[使用配置文件配置服务](./configuring-services-using-configuration-files.md)。</span><span class="sxs-lookup"><span data-stu-id="876e1-301">For more information about configuration files, see [Configuring Services Using Configuration Files](./configuring-services-using-configuration-files.md).</span></span> <span data-ttu-id="876e1-302">这种启动服务器的样式称为自我托管。</span><span class="sxs-lookup"><span data-stu-id="876e1-302">This style of starting the server is known as self-hosting.</span></span> <span data-ttu-id="876e1-303">若要了解有关托管 WCF 服务的其他选项的详细信息，请参阅[托管服务](./hosting-services.md)。</span><span class="sxs-lookup"><span data-stu-id="876e1-303">To learn more about other choices for hosting WCF services, see [Hosting Services](./hosting-services.md).</span></span>  
  
6.  <span data-ttu-id="876e1-304">客户端项目的 app.config 必须声明匹配服务终结点的绑定信息。</span><span class="sxs-lookup"><span data-stu-id="876e1-304">The client project’s app.config must declare matching binding information for the service’s endpoint.</span></span> <span data-ttu-id="876e1-305">Visual Studio 中执行此操作的最简单方法是使用**添加服务引用**，然后将自动更新 app.config 文件。</span><span class="sxs-lookup"><span data-stu-id="876e1-305">The easiest way to do this in Visual Studio is to use **Add Service Reference**, which will automatically update the app.config file.</span></span> <span data-ttu-id="876e1-306">或者，可以手动添加这些相同的更改。</span><span class="sxs-lookup"><span data-stu-id="876e1-306">Alternatively, these same changes can be added manually.</span></span>  
  
    ```xml  
    <configuration>  
      <system.serviceModel>  
        <client>  
          <endpoint name="customerservice"  
                    address="http://localhost:8083/CustomerService"  
                    binding="basicHttpBinding"  
                    contract="Shared.ICustomerService"/>  
        </client>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
     <span data-ttu-id="876e1-307">有关使用详细信息**添加服务引用**，请参阅[如何： 添加、 更新或删除服务引用](/visualstudio/data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference)。</span><span class="sxs-lookup"><span data-stu-id="876e1-307">For more information about using **Add Service Reference**, see [How to: Add, Update, or Remove a Service Reference](/visualstudio/data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference).</span></span>  
  
7.  <span data-ttu-id="876e1-308">现在可以从客户端中调用 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="876e1-308">Now we can call the WCF service from the client.</span></span> <span data-ttu-id="876e1-309">可通过创建该服务的通道工厂、要求提供通道以及直接调用想要用在该通道中的方法实现此操作。</span><span class="sxs-lookup"><span data-stu-id="876e1-309">We do this by creating a channel factory for that service, asking it for a channel, and directly calling the method we want on that channel.</span></span> <span data-ttu-id="876e1-310">可进行此操作的原因是通道可实现服务接口，并为我们处理基础的请求/答复逻辑。</span><span class="sxs-lookup"><span data-stu-id="876e1-310">We can do this because the channel implements the service’s interface and handles the underlying request/reply logic for us.</span></span> <span data-ttu-id="876e1-311">此方法调用的返回值是服务器响应的反序列化副本。</span><span class="sxs-lookup"><span data-stu-id="876e1-311">The return value from that method call is the deserialized copy of the server’s response.</span></span>  
  
   ```csharp
   ChannelFactory<ICustomerService> factory =  
       new ChannelFactory<ICustomerService>("customerservice");  
   ICustomerService service = factory.CreateChannel();  
   Customer customer = service.GetCustomer(42);  
   Console.WriteLine(String.Format("  Customer {0} {1} received.",  
           customer.FirstName, customer.LastName));  
   ```  
  
 <span data-ttu-id="876e1-312">由 WCF 从服务器返回到客户端的对象始终为按值返回。</span><span class="sxs-lookup"><span data-stu-id="876e1-312">Objects returned by WCF from the server to the client are always by value.</span></span> <span data-ttu-id="876e1-313">对象是由服务器发送的数据反序列化副本。</span><span class="sxs-lookup"><span data-stu-id="876e1-313">The objects are deserialized copies of the data sent by the server.</span></span> <span data-ttu-id="876e1-314">客户端可以对这些本地副本调用方法，而无需担心通过回调调用服务器。</span><span class="sxs-lookup"><span data-stu-id="876e1-314">The client can call methods on these local copies without any danger of invoking server code through callbacks.</span></span>  
  
#### <a name="scenario-2-server-returns-an-object-by-reference"></a><span data-ttu-id="876e1-315">方案 2：服务器按按引用返回对象</span><span class="sxs-lookup"><span data-stu-id="876e1-315">Scenario 2: Server Returns an Object By Reference</span></span>  
 <span data-ttu-id="876e1-316">此方案演示服务器按引用向客户端提供对象。</span><span class="sxs-lookup"><span data-stu-id="876e1-316">This scenario demonstrates the server providing an object to the client by reference.</span></span> <span data-ttu-id="876e1-317">在 .NET 远程处理中，这会自动处理任何派生自 MarshalByRefObject 的类型，即序列化的引用。</span><span class="sxs-lookup"><span data-stu-id="876e1-317">In .NET Remoting, this is handled automatically for any type derived from MarshalByRefObject, which is serialized by-reference.</span></span> <span data-ttu-id="876e1-318">此方案的一个示例是允许多个客户端拥有独立会话的服务端对象。</span><span class="sxs-lookup"><span data-stu-id="876e1-318">An example of this scenario is allowing multiple clients to have independent sessionful server-side objects.</span></span> <span data-ttu-id="876e1-319">正如前面所述，WCF 服务返回的对象始终按值返回，因此并没有直接对等的按引用对象，但是有可能实现类似于使用 <xref:System.ServiceModel.EndpointAddress10> 对象的按引用语义。</span><span class="sxs-lookup"><span data-stu-id="876e1-319">As previously mentioned, objects returned by a WCF service are always by value, so there is no direct equivalent of a by-reference object, but it is possible to achieve something similar to by-reference semantics using an <xref:System.ServiceModel.EndpointAddress10> object.</span></span> <span data-ttu-id="876e1-320">这是客户端用于获取服务器上会话按引用对象的可序列化的值对象。</span><span class="sxs-lookup"><span data-stu-id="876e1-320">This is a serializable by-value object that can be used by the client to obtain a sessionful by-reference object on the server.</span></span> <span data-ttu-id="876e1-321">这将使多个客户端拥有独立会话的服务器端对象的方案得以实现。</span><span class="sxs-lookup"><span data-stu-id="876e1-321">This enables the scenario of having multiple clients with independent sessionful server-side objects.</span></span>  
  
1.  <span data-ttu-id="876e1-322">首先，需要定义与会话对象本身对应的 WCF 服务协定。</span><span class="sxs-lookup"><span data-stu-id="876e1-322">First, we need to define a WCF service contract that corresponds to the sessionful object itself.</span></span>  
  
   ```csharp
   [ServiceContract(SessionMode = SessionMode.Allowed)]  
       public interface ISessionBoundObject  
       {  
           [OperationContract]  
           string GetCurrentValue();  
  
           [OperationContract]  
           void SetCurrentValue(string value);  
       }  
   ```  
  
    > [!TIP]
    >  <span data-ttu-id="876e1-323">请注意该会话对象用 [ServiceContract] 进行了标记，使其成为普通的 WCF 服务接口。</span><span class="sxs-lookup"><span data-stu-id="876e1-323">Notice that the sessionful object is marked with [ServiceContract], making it a normal WCF service interface.</span></span> <span data-ttu-id="876e1-324">设置 SessionMode 属性指示其将为会话服务。</span><span class="sxs-lookup"><span data-stu-id="876e1-324">Setting the SessionMode property indicates it will be a sessionful service.</span></span> <span data-ttu-id="876e1-325">在 WCF 中，会话是使两个终结点之间发送的多个消息关联的一种方法。</span><span class="sxs-lookup"><span data-stu-id="876e1-325">In WCF, a session is a way of correlating multiple messages sent between two endpoints.</span></span> <span data-ttu-id="876e1-326">这意味着一旦客户端获取与此服务的连接，将会建立客户端和服务器之间的会话。</span><span class="sxs-lookup"><span data-stu-id="876e1-326">This means that once a client obtains a connection to this service, a session will be established between the client and the server.</span></span> <span data-ttu-id="876e1-327">对于此单个会话中的所有交互，客户端都将使用服务器端对象的单个唯一实例。</span><span class="sxs-lookup"><span data-stu-id="876e1-327">The client will use a single unique instance of the server-side object for all its interactions within this single session.</span></span>  
  
2.  <span data-ttu-id="876e1-328">接下来，需要提供此服务接口的实现。</span><span class="sxs-lookup"><span data-stu-id="876e1-328">Next, we need to provide the implementation of this service interface.</span></span> <span data-ttu-id="876e1-329">通过使用 [ServiceBehavior] 进行表示，并设置 InstanceContextMode，将告知 WCF 希望使用每个会话的此类型的唯一实例。</span><span class="sxs-lookup"><span data-stu-id="876e1-329">By denoting it with [ServiceBehavior] and setting the InstanceContextMode, we tell WCF we want to use a unique instance of this type for an each session.</span></span>  
  
   ```csharp
   [ServiceBehavior(InstanceContextMode = InstanceContextMode.PerSession)]  
       public class MySessionBoundObject : ISessionBoundObject  
       {  
           private string _value;  
  
           public string GetCurrentValue()  
           {  
               return _value;  
           }  
  
           public void SetCurrentValue(string val)  
           {  
               _value = val;  
           }  
  
       }  
   ```  
  
3.  <span data-ttu-id="876e1-330">现在，需要一种方法以获取此会话对象的实例。</span><span class="sxs-lookup"><span data-stu-id="876e1-330">Now we need a way to obtain an instance of this sessionful object.</span></span> <span data-ttu-id="876e1-331">通过创建返回 EndpointAddress10 对象的另一个 WCF 服务接口来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="876e1-331">We do this by creating another WCF service interface that returns an EndpointAddress10 object.</span></span> <span data-ttu-id="876e1-332">这是一种客户端可用来创建会话对象的终结点的可序列化形式。</span><span class="sxs-lookup"><span data-stu-id="876e1-332">This is a serializable form of an endpoint that the client can use to create the sessionful object.</span></span>  
  
   ```csharp
   [ServiceContract]  
       public interface ISessionBoundFactory  
       {  
           [OperationContract]  
           EndpointAddress10 GetInstanceAddress();  
       }  
   ```  
  
     <span data-ttu-id="876e1-333">并且，我们实现此 WCF 服务：</span><span class="sxs-lookup"><span data-stu-id="876e1-333">And we implement this WCF service:</span></span>  
  
   ```csharp
   public class SessionBoundFactory : ISessionBoundFactory  
       {  
           public static ChannelFactory<ISessionBoundObject> _factory =   
               new ChannelFactory<ISessionBoundObject>("sessionbound");  
 
           public SessionBoundFactory()  
           {  
           }  
  
           public EndpointAddress10 GetInstanceAddress()  
           {  
               IClientChannel channel = (IClientChannel)_factory.CreateChannel();  
               return EndpointAddress10.FromEndpointAddress(channel.RemoteAddress);  
           }  
       }  
   ```  
  
     <span data-ttu-id="876e1-334">此实现维护单一实例通道工厂以创建会话对象。</span><span class="sxs-lookup"><span data-stu-id="876e1-334">This implementation maintains a singleton channel factory to create sessionful objects.</span></span> <span data-ttu-id="876e1-335">当调用 GetInstanceAddress() 时，它会创建一个通道，并创建一个有效地指向与此通道关联的远程地址的 EndpointAddress10 对象。</span><span class="sxs-lookup"><span data-stu-id="876e1-335">When GetInstanceAddress() is called, it creates a channel and creates an EndpointAddress10 object that effectively points to the remote address associated with this channel.</span></span> <span data-ttu-id="876e1-336">EndpointAddress10 只是一种可按值返回至客户端的数据类型。</span><span class="sxs-lookup"><span data-stu-id="876e1-336">EndpointAddress10 is simply a data type that can be returned to the client by-value.</span></span>  
  
4.  <span data-ttu-id="876e1-337">需要通过执行以下两个事件，修改服务器的配置文件，如下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="876e1-337">We need to modify the server’s configuration file by doing the following two things as shown in the example below:</span></span>  
  
    1.  <span data-ttu-id="876e1-338">声明\<客户端 > 描述会话对象终结点的部分。</span><span class="sxs-lookup"><span data-stu-id="876e1-338">Declare a \<client> section that describes the endpoint for the sessionful object.</span></span> <span data-ttu-id="876e1-339">此声明是必需的，原因是在此情况下此服务器还可作为客户端。</span><span class="sxs-lookup"><span data-stu-id="876e1-339">This is necessary because the server also acts as a client in this situation.</span></span>  
  
    2.  <span data-ttu-id="876e1-340">声明工厂和会话对象的终结点。</span><span class="sxs-lookup"><span data-stu-id="876e1-340">Declare endpoints for the factory and sessionful object.</span></span> <span data-ttu-id="876e1-341">此声明是必需，原因是这可允许客户端与服务终结点通信以获取 EndpointAddress10 并创建会话通道。</span><span class="sxs-lookup"><span data-stu-id="876e1-341">This is necessary to allow the client to communicate with the service endpoints to acquire the EndpointAddress10 and to create the sessionful channel.</span></span>  
  
    ```xml  
    <configuration>  
      <system.serviceModel>  
         <client>  
          <endpoint name="sessionbound"  
                    address="net.tcp://localhost:8081/SessionBoundObject"  
                    binding="netTcpBinding"  
                    contract="Shared.ISessionBoundObject"/>  
        </client>  
        <services>  
          <service name="Server.CustomerService">  
            <endpoint address="http://localhost:8083/CustomerService"  
                      binding="basicHttpBinding"  
                      contract="Shared.ICustomerService" />  
          </service>  
          <service name="Server.MySessionBoundObject">  
            <endpoint address="net.tcp://localhost:8081/SessionBoundObject"  
                      binding="netTcpBinding"  
                      contract="Shared.ISessionBoundObject" />  
          </service>  
          <service name="Server.SessionBoundFactory">  
            <endpoint address="net.tcp://localhost:8081/SessionBoundFactory"  
                      binding="netTcpBinding"  
                      contract="Shared.ISessionBoundFactory" />  
          </service>  
        </services>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
     <span data-ttu-id="876e1-342">然后便可启动这些服务：</span><span class="sxs-lookup"><span data-stu-id="876e1-342">And then we can start these services:</span></span>  
  
   ```csharp
   ServiceHost factoryHost = new ServiceHost(typeof(SessionBoundFactory));  
   factoryHost.Open();  
  
   ServiceHost sessionHost = new ServiceHost(typeof(MySessionBoundObject));  
   sessionHost.Open();  
   ```  
  
5.  <span data-ttu-id="876e1-343">可通过声明其项目 app.config 文件中这些相同的终结点配置客户端。</span><span class="sxs-lookup"><span data-stu-id="876e1-343">We configure the client by declaring these same endpoints in its project’s app.config file.</span></span>  
  
    ```xml  
    <configuration>  
      <system.serviceModel>  
        <client>  
          <endpoint name="customerservice"  
                    address="http://localhost:8083/CustomerService"  
                    binding="basicHttpBinding"  
                    contract="Shared.ICustomerService"/>  
          <endpoint name="sessionbound"  
                    address="net.tcp://localhost:8081/SessionBoundObject"  
                    binding="netTcpBinding"  
                    contract="Shared.ISessionBoundObject"/>  
          <endpoint name="factory"  
                    address="net.tcp://localhost:8081/SessionBoundFactory"  
                    binding="netTcpBinding"  
                    contract="Shared.ISessionBoundFactory"/>  
        </client>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
6.  <span data-ttu-id="876e1-344">为了创建和使用此会话对象，客户端必须执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="876e1-344">In order to create and use this sessionful object, the client must do the following steps:</span></span>  
  
    1.  <span data-ttu-id="876e1-345">创建 ISessionBoundFactory 服务的通道。</span><span class="sxs-lookup"><span data-stu-id="876e1-345">Create a channel to the ISessionBoundFactory service.</span></span>  
  
    2.  <span data-ttu-id="876e1-346">使用该通道调用该服务，以获取 EndpointAddress10。</span><span class="sxs-lookup"><span data-stu-id="876e1-346">Use that channel to invoke that service to obtain an EndpointAddress10.</span></span>  
  
    3.  <span data-ttu-id="876e1-347">使用 EndpointAddress10 创建一个通道，以获取会话对象。</span><span class="sxs-lookup"><span data-stu-id="876e1-347">Use the EndpointAddress10 to create a channel to obtain a sessionful object.</span></span>  
  
    4.  <span data-ttu-id="876e1-348">与会话对象进行交互，以演示多次调用间保持的同一个实例。</span><span class="sxs-lookup"><span data-stu-id="876e1-348">Interact with the sessionful object to demonstrate it remains the same instance across multiple calls.</span></span>  
  
   ```csharp
   ChannelFactory<ISessionBoundFactory> channelFactory =   
       new ChannelFactory<ISessionBoundFactory>("factory");  
   ISessionBoundFactory sessionFactory = channelFactory.CreateChannel();  
  
   EndpointAddress10 address1 = sessionFactory.GetInstanceAddress();  
   EndpointAddress10 address2 = sessionFactory.GetInstanceAddress();  
  
   ChannelFactory<ISessionBoundObject> sessionObjectFactory1 =   
       new ChannelFactory<ISessionBoundObject>(new NetTcpBinding(),   
                                               address1.ToEndpointAddress());  
   ChannelFactory<ISessionBoundObject> sessionObjectFactory2 =   
       new ChannelFactory<ISessionBoundObject>(new NetTcpBinding(),   
                                               address2.ToEndpointAddress());  
  
   ISessionBoundObject sessionInstance1 = sessionObjectFactory1.CreateChannel();  
   ISessionBoundObject sessionInstance2 = sessionObjectFactory2.CreateChannel();  
  
   sessionInstance1.SetCurrentValue("Hello");  
   sessionInstance2.SetCurrentValue("World");  
  
   if (sessionInstance1.GetCurrentValue() == "Hello" &&  
       sessionInstance2.GetCurrentValue() == "World")  
   {  
       Console.WriteLine("sessionful server object works as expected");  
   }  
   ```  
  
 <span data-ttu-id="876e1-349">WCF 将始终返回按值的对象，但是通过使用 EndpointAddress10 有可能支持按引用语义的等效项。</span><span class="sxs-lookup"><span data-stu-id="876e1-349">WCF always returns objects by value, but it is possible to support the equivalent of by-reference semantics through the use of EndpointAddress10.</span></span> <span data-ttu-id="876e1-350">这将允许客户端请求会话的 WCF 服务实例，此后客户端可以与此实例进行交互，与其他 WCF 服务并无差异。</span><span class="sxs-lookup"><span data-stu-id="876e1-350">This permits the client to request a sessionful WCF service instance, after which it can interact with it like any other WCF service.</span></span>  
  
#### <a name="scenario-3-client-sends-server-a-by-value-instance"></a><span data-ttu-id="876e1-351">方案 3：客户端向服务器发送按值实例</span><span class="sxs-lookup"><span data-stu-id="876e1-351">Scenario 3: Client Sends Server a By-Value Instance</span></span>  
 <span data-ttu-id="876e1-352">此方案演示客户端按值向服务器发送一个非基元对象实例。</span><span class="sxs-lookup"><span data-stu-id="876e1-352">This scenario demonstrates the client sending a non-primitive object instance to the server by value.</span></span> <span data-ttu-id="876e1-353">由于 WCF 仅发送按值对象，因此此方案演示正常使用 WCF 的情况。</span><span class="sxs-lookup"><span data-stu-id="876e1-353">Because WCF only sends objects by value, this scenario demonstrates normal WCF usage.</span></span>  
  
1.  <span data-ttu-id="876e1-354">使用与方案 1 中相同的 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="876e1-354">Use the same WCF Service from Scenario 1.</span></span>  
  
2.  <span data-ttu-id="876e1-355">使用客户端创建一个新的按值对象（客户）、创建与 ICustomerService 服务进行通信的通道，并向其发送该对象。</span><span class="sxs-lookup"><span data-stu-id="876e1-355">Use the client to create a new by-value object (Customer), create a channel to communicate with the ICustomerService service, and send the object to it.</span></span>  
  
   ```csharp
   ChannelFactory<ICustomerService> factory =  
       new ChannelFactory<ICustomerService>("customerservice");  
   ICustomerService service = factory.CreateChannel();  
   PremiumCustomer customer = new PremiumCustomer {   
   FirstName = "Bob",   
   LastName = "Jones",   
   CustomerId = 43,   
   AccountId = 99};  
   bool success = service.UpdateCustomer(customer);  
   Console.WriteLine(String.Format("  Server returned {0}.", success));  
   ```  
  
     <span data-ttu-id="876e1-356">将序列化客户对象，并将其发送到服务器，在其中将其反序列化为该对象的新副本。</span><span class="sxs-lookup"><span data-stu-id="876e1-356">The customer object will be serialized, and sent to the server, where it is deserialized into a new copy of that object.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="876e1-357">此代码还说明了发送派生的类型 (PremiumCustomer)。</span><span class="sxs-lookup"><span data-stu-id="876e1-357">This code also illustrates sending a derived type (PremiumCustomer).</span></span> <span data-ttu-id="876e1-358">服务接口需要 Customer 对象，但 Customer 类上的 [KnownType] 属性指示也允许使用 PremiumCustomer。</span><span class="sxs-lookup"><span data-stu-id="876e1-358">The service interface expects a Customer object, but the [KnownType] attribute on the Customer class indicated PremiumCustomer was also allowed.</span></span> <span data-ttu-id="876e1-359">WCF 通过此服务接口进行序列化或反序列化任何其他类型的尝试将失败。</span><span class="sxs-lookup"><span data-stu-id="876e1-359">WCF will fail any attempt to serialize or deserialize any other type through this service interface.</span></span>  
  
 <span data-ttu-id="876e1-360">正常的 WCF 数据交换是按值进行的。</span><span class="sxs-lookup"><span data-stu-id="876e1-360">Normal WCF exchanges of data are by value.</span></span> <span data-ttu-id="876e1-361">这可确保其中某个数据对象上的调用方法仅在本地执行 – 它将不会调用其他层上的代码。</span><span class="sxs-lookup"><span data-stu-id="876e1-361">This guarantees that invoking methods on one of these data objects executes only locally – it will not invoke code on the other tier.</span></span> <span data-ttu-id="876e1-362">虽然可以实现类似于按引用返回的对象*从*服务器，不能为客户端将按引用对象传递*到*服务器。</span><span class="sxs-lookup"><span data-stu-id="876e1-362">While it is possible to achieve something like by-reference objects returned *from* the server, it is not possible for a client to pass a by-reference object *to* the server.</span></span> <span data-ttu-id="876e1-363">在 WCF 中使用双工服务可实现需要在客户端和服务器间来回会话的方案。</span><span class="sxs-lookup"><span data-stu-id="876e1-363">A scenario that requires a conversation back and forth between client and server can be achieved in WCF using a duplex service.</span></span> <span data-ttu-id="876e1-364">有关详细信息，请参阅[双工服务](./feature-details/duplex-services.md)。</span><span class="sxs-lookup"><span data-stu-id="876e1-364">For more information, see [Duplex Services](./feature-details/duplex-services.md).</span></span>  
  
## <a name="summary"></a><span data-ttu-id="876e1-365">总结</span><span class="sxs-lookup"><span data-stu-id="876e1-365">Summary</span></span>  
 <span data-ttu-id="876e1-366">.NET 远程处理是一种通信框架，仅用于完全信任的环境中。</span><span class="sxs-lookup"><span data-stu-id="876e1-366">.NET Remoting is a communication framework intended to be used only within fully-trusted environments.</span></span> <span data-ttu-id="876e1-367">它是一项传统技术，仅支持向后兼容性。</span><span class="sxs-lookup"><span data-stu-id="876e1-367">It is a legacy product and supported only for backward compatibility.</span></span> <span data-ttu-id="876e1-368">它不应用于生成新的应用程序。</span><span class="sxs-lookup"><span data-stu-id="876e1-368">It should not be used to build new applications.</span></span> <span data-ttu-id="876e1-369">相反，WCF 融入了安全性，并建议将其用于生成新的和现有的应用程序。</span><span class="sxs-lookup"><span data-stu-id="876e1-369">Conversely, WCF was designed with security in mind and is recommended for new and existing applications.</span></span> <span data-ttu-id="876e1-370">Microsoft 建议将现有的远程处理应用程序迁移到使用 WCF 或 ASP.NET Web API。</span><span class="sxs-lookup"><span data-stu-id="876e1-370">Microsoft recommends that existing Remoting applications be migrated to use WCF or ASP.NET Web API instead.</span></span>