---
title: 配置和元数据支持
ms.date: 03/30/2017
ms.assetid: 27c240cb-8cab-472c-87f8-c864f4978758
ms.openlocfilehash: 74dab4528ae11b60fc930a826962b71595073a7f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64587729"
---
# <a name="configuration-and-metadata-support"></a><span data-ttu-id="f38bc-102">配置和元数据支持</span><span class="sxs-lookup"><span data-stu-id="f38bc-102">Configuration and Metadata Support</span></span>
<span data-ttu-id="f38bc-103">本主题说明如何启用配置和元数据对绑定和绑定元素的支持。</span><span class="sxs-lookup"><span data-stu-id="f38bc-103">This topic describes how to enable configuration and metadata support for bindings and binding elements.</span></span>  
  
## <a name="overview-of-configuration-and-metadata"></a><span data-ttu-id="f38bc-104">配置和元数据概述</span><span class="sxs-lookup"><span data-stu-id="f38bc-104">Overview of Configuration and Metadata</span></span>  
 <span data-ttu-id="f38bc-105">本主题讨论下列任务，是可选项 1、 2 和 4 中[开发通道](../../../../docs/framework/wcf/extending/developing-channels.md)任务列表。</span><span class="sxs-lookup"><span data-stu-id="f38bc-105">This topic discusses the following tasks, which are optional items 1, 2, and 4 in the [Developing Channels](../../../../docs/framework/wcf/extending/developing-channels.md) task list.</span></span>  
  
- <span data-ttu-id="f38bc-106">启用配置文件对绑定元素的支持。</span><span class="sxs-lookup"><span data-stu-id="f38bc-106">Enabling configuration file support for a binding element.</span></span>  
  
- <span data-ttu-id="f38bc-107">启用配置文件对绑定的支持。</span><span class="sxs-lookup"><span data-stu-id="f38bc-107">Enabling configuration file support for a binding.</span></span>  
  
- <span data-ttu-id="f38bc-108">导出绑定元素的 WSDL 和策略断言。</span><span class="sxs-lookup"><span data-stu-id="f38bc-108">Exporting WSDL and policy assertions for a binding element.</span></span>  
  
- <span data-ttu-id="f38bc-109">标识 WSDL 和策略断言以插入或配置你的绑定或绑定元素。</span><span class="sxs-lookup"><span data-stu-id="f38bc-109">Identifying WSDL and policy assertions to insert and configure your binding or binding element.</span></span>  
  
 <span data-ttu-id="f38bc-110">有关创建用户定义的绑定和绑定元素的信息，请参阅[创建用户定义绑定](../../../../docs/framework/wcf/extending/creating-user-defined-bindings.md)并[创建 BindingElement](../../../../docs/framework/wcf/extending/creating-a-bindingelement.md)分别。</span><span class="sxs-lookup"><span data-stu-id="f38bc-110">For information about creating user-defined bindings and binding elements, see [Creating User-Defined Bindings](../../../../docs/framework/wcf/extending/creating-user-defined-bindings.md) and [Creating a BindingElement](../../../../docs/framework/wcf/extending/creating-a-bindingelement.md), respectively.</span></span>  
  
## <a name="adding-configuration-support"></a><span data-ttu-id="f38bc-111">添加配置支持</span><span class="sxs-lookup"><span data-stu-id="f38bc-111">Adding Configuration Support</span></span>  
 <span data-ttu-id="f38bc-112">若要启用配置文件对通道的支持，必须实现两个配置节：<xref:System.ServiceModel.Configuration.BindingElementExtensionElement?displayProperty=nameWithType>（启用配置对绑定元素的支持）以及 <xref:System.ServiceModel.Configuration.StandardBindingElement?displayProperty=nameWithType> 和 <xref:System.ServiceModel.Configuration.StandardBindingCollectionElement%602?displayProperty=nameWithType>（启用配置对绑定的支持）。</span><span class="sxs-lookup"><span data-stu-id="f38bc-112">To enable configuration file support for a channel, you must implement two configuration sections, <xref:System.ServiceModel.Configuration.BindingElementExtensionElement?displayProperty=nameWithType>, which enables configuration support for binding elements, and the <xref:System.ServiceModel.Configuration.StandardBindingElement?displayProperty=nameWithType> and <xref:System.ServiceModel.Configuration.StandardBindingCollectionElement%602?displayProperty=nameWithType>, which enable configuration support for bindings.</span></span>  
  
 <span data-ttu-id="f38bc-113">执行此操作的更简单方法是使用[ConfigurationCodeGenerator](../../../../docs/framework/wcf/samples/configurationcodegenerator.md)示例工具，用于生成绑定和绑定元素的配置代码。</span><span class="sxs-lookup"><span data-stu-id="f38bc-113">An easier way to do this is to use the [ConfigurationCodeGenerator](../../../../docs/framework/wcf/samples/configurationcodegenerator.md) sample tool to generate configuration code for your bindings and binding elements.</span></span>  
  
### <a name="extending-bindingelementextensionelement"></a><span data-ttu-id="f38bc-114">扩展 BindingElementExtensionElement</span><span class="sxs-lookup"><span data-stu-id="f38bc-114">Extending BindingElementExtensionElement</span></span>  
 <span data-ttu-id="f38bc-115">下面的代码示例摘自[传输：UDP](../../../../docs/framework/wcf/samples/transport-udp.md)示例。</span><span class="sxs-lookup"><span data-stu-id="f38bc-115">The following example code is taken from the [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) sample.</span></span> <span data-ttu-id="f38bc-116">`UdpTransportElement` 是一个 <xref:System.ServiceModel.Configuration.BindingElementExtensionElement>，它向配置系统公开 `UdpTransportBindingElement`。</span><span class="sxs-lookup"><span data-stu-id="f38bc-116">The `UdpTransportElement` is a <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> that exposes `UdpTransportBindingElement` to the configuration system.</span></span> <span data-ttu-id="f38bc-117">通过若干基本重写，此示例定义配置节名称、绑定元素的类型以及如何创建绑定元素。</span><span class="sxs-lookup"><span data-stu-id="f38bc-117">With a few basic overrides, the sample defines the configuration section name, the type of the binding element and how to create the binding element.</span></span> <span data-ttu-id="f38bc-118">然后，用户可以按如下方式注册配置文件中的扩展节。</span><span class="sxs-lookup"><span data-stu-id="f38bc-118">Users can then register the extension section in a configuration file as follows.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <extensions>  
      <bindingElementExtensions>  
      <add name="udpTransport" type="Microsoft.ServiceModel.Samples.UdpTransportElement, UdpTransport />  
      </bindingElementExtensions>  
    </extensions>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="f38bc-119">可以从自定义绑定来引用该扩展以将 UDP 用作传输协议。</span><span class="sxs-lookup"><span data-stu-id="f38bc-119">The extension can be referenced from custom bindings to use UDP as the transport.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <customBinding>  
       <binding configurationName="UdpCustomBinding">  
         <udpTransport/>  
       </binding>  
      </customBinding>  
    </bindings>  
  </system.serviceModel>  
</configuration>  
```  
  
### <a name="adding-configuration-for-a-binding"></a><span data-ttu-id="f38bc-120">为绑定添加配置</span><span class="sxs-lookup"><span data-stu-id="f38bc-120">Adding Configuration for a Binding</span></span>  
 <span data-ttu-id="f38bc-121">`SampleProfileUdpBindingCollectionElement` 节是一个 <xref:System.ServiceModel.Configuration.StandardBindingCollectionElement%602>，它向配置系统公开 `SampleProfileUdpBinding`。</span><span class="sxs-lookup"><span data-stu-id="f38bc-121">The section `SampleProfileUdpBindingCollectionElement` is a <xref:System.ServiceModel.Configuration.StandardBindingCollectionElement%602> that exposes `SampleProfileUdpBinding` to the configuration system.</span></span> <span data-ttu-id="f38bc-122">批量实现委派给从 `SampleProfileUdpBindingConfigurationElement` 派生的 <xref:System.ServiceModel.Configuration.StandardBindingElement>。</span><span class="sxs-lookup"><span data-stu-id="f38bc-122">The bulk of the implementation is delegated to the `SampleProfileUdpBindingConfigurationElement`, which derives from <xref:System.ServiceModel.Configuration.StandardBindingElement>.</span></span> <span data-ttu-id="f38bc-123">`SampleProfileUdpBindingConfigurationElement`属性相对应的属性上`SampleProfileUdpBinding`，并从映射的函数`ConfigurationElement`绑定。</span><span class="sxs-lookup"><span data-stu-id="f38bc-123">The `SampleProfileUdpBindingConfigurationElement` has properties that correspond to the properties on `SampleProfileUdpBinding`, and functions to map from the `ConfigurationElement` binding.</span></span> <span data-ttu-id="f38bc-124">最后，在 `OnApplyConfiguration` 中重写 `SampleProfileUdpBinding` 方法，如下面的代码示例中所示。</span><span class="sxs-lookup"><span data-stu-id="f38bc-124">Finally, the `OnApplyConfiguration` method is overridden in the `SampleProfileUdpBinding`, as shown in the following sample code.</span></span>  
  
```csharp 
protected override void OnApplyConfiguration(string configurationName)  
{  
            if (binding == null)  
                throw new ArgumentNullException("binding");  
  
            if (binding.GetType() != typeof(SampleProfileUdpBinding))  
            {  
                throw new ArgumentException(string.Format(CultureInfo.CurrentCulture,  
                    "Invalid type for binding. Expected type: {0}. Type passed in: {1}.",  
                    typeof(SampleProfileUdpBinding).AssemblyQualifiedName,  
                    binding.GetType().AssemblyQualifiedName));  
            }  
            SampleProfileUdpBinding udpBinding = (SampleProfileUdpBinding)binding;  
  
            udpBinding.OrderedSession = this.OrderedSession;  
            udpBinding.ReliableSessionEnabled = this.ReliableSessionEnabled;  
            udpBinding.SessionInactivityTimeout = this.SessionInactivityTimeout;  
            if (this.ClientBaseAddress != null)  
                   udpBinding.ClientBaseAddress = ClientBaseAddress;  
}  
```  
  
 <span data-ttu-id="f38bc-125">若要使用配置系统注册此处理程序，请将下一节添加到相关的配置文件中。</span><span class="sxs-lookup"><span data-stu-id="f38bc-125">To register this handler with the configuration system, add the following section to the relevant configuration file.</span></span>  
  
```xml  
<configuration>  
  <configSections>  
     <sectionGroup name="system.serviceModel">  
         <sectionGroup name="bindings">  
                 <section name="sampleProfileUdpBinding" type="Microsoft.ServiceModel.Samples.SampleProfileUdpBindingCollectionElement, UdpTransport />  
         </sectionGroup>  
     </sectionGroup>  
  </configSections>  
</configuration>  
```  
  
 <span data-ttu-id="f38bc-126">然后从引用[ \<system.serviceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)配置节。</span><span class="sxs-lookup"><span data-stu-id="f38bc-126">It can then be referenced from the [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) configuration section.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <client>  
      <endpoint configurationName="calculator"  
                address="soap.udp://localhost:8001/"   
                bindingConfiguration="CalculatorServer"  
                binding="sampleProfileUdpBinding"   
                contract= "Microsoft.ServiceModel.Samples.ICalculatorContract">  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="adding-metadata-support-for-a-binding-element"></a><span data-ttu-id="f38bc-127">为绑定元素添加元数据支持</span><span class="sxs-lookup"><span data-stu-id="f38bc-127">Adding Metadata Support for a Binding Element</span></span>  
 <span data-ttu-id="f38bc-128">若要将通道集成到元数据系统中，系统必须支持策略的导入和导出。</span><span class="sxs-lookup"><span data-stu-id="f38bc-128">To integrate a channel into the metadata system, it must support both the import and export of policy.</span></span> <span data-ttu-id="f38bc-129">这允许工具，如[ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)生成客户端的绑定元素。</span><span class="sxs-lookup"><span data-stu-id="f38bc-129">This allows tools such as [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to generate clients of the binding element.</span></span>  
  
### <a name="adding-wsdl-support"></a><span data-ttu-id="f38bc-130">添加 WSDL 支持</span><span class="sxs-lookup"><span data-stu-id="f38bc-130">Adding WSDL Support</span></span>  
 <span data-ttu-id="f38bc-131">绑定中的传输绑定元素负责导出和导入元数据中的寻址信息。</span><span class="sxs-lookup"><span data-stu-id="f38bc-131">The transport binding element in a binding is responsible for exporting and importing addressing information in metadata.</span></span> <span data-ttu-id="f38bc-132">当使用 SOAP 绑定时，传输绑定元素还应在元数据中导出正确的传输 URI。</span><span class="sxs-lookup"><span data-stu-id="f38bc-132">When using a SOAP binding, the transport binding element should also export a correct transport URI in metadata.</span></span> <span data-ttu-id="f38bc-133">下面的代码示例摘自[传输：UDP](../../../../docs/framework/wcf/samples/transport-udp.md)示例。</span><span class="sxs-lookup"><span data-stu-id="f38bc-133">The following example code is taken from the [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) sample.</span></span>  
  
#### <a name="wsdl-export"></a><span data-ttu-id="f38bc-134">WSDL 导出</span><span class="sxs-lookup"><span data-stu-id="f38bc-134">WSDL Export</span></span>  
 <span data-ttu-id="f38bc-135">若要导出寻址信息`UdpTransportBindingElement`实现<xref:System.ServiceModel.Description.IWsdlExportExtension?displayProperty=nameWithType>接口。</span><span class="sxs-lookup"><span data-stu-id="f38bc-135">To export addressing information, the `UdpTransportBindingElement` implements the <xref:System.ServiceModel.Description.IWsdlExportExtension?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="f38bc-136"><xref:System.ServiceModel.Description.IWsdlExportExtension.ExportEndpoint%2A?displayProperty=nameWithType> 方法将正确的寻址信息添加到 WSDL 端口中。</span><span class="sxs-lookup"><span data-stu-id="f38bc-136">The <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportEndpoint%2A?displayProperty=nameWithType> method adds the correct addressing information to the WSDL port.</span></span>  
  
```csharp  
if (context.WsdlPort != null)  
{  
    AddAddressToWsdlPort(context.WsdlPort, context.Endpoint.Address, encodingBindingElement.MessageVersion.Addressing);  
}  
```  
  
 <span data-ttu-id="f38bc-137">当终结点使用 SOAP 绑定时，`UdpTransportBindingElement` 方法的 <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportEndpoint%2A> 实现也会导出传输 URI：</span><span class="sxs-lookup"><span data-stu-id="f38bc-137">The `UdpTransportBindingElement` implementation of the <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportEndpoint%2A> method also exports a transport URI when the endpoint uses a SOAP binding:</span></span>  
  
```csharp  
WsdlNS.SoapBinding soapBinding = GetSoapBinding(context, exporter);  
if (soapBinding != null)  
{  
    soapBinding.Transport = UdpPolicyStrings.UdpNamespace;  
}  
```  
  
#### <a name="wsdl-import"></a><span data-ttu-id="f38bc-138">WSDL 导入</span><span class="sxs-lookup"><span data-stu-id="f38bc-138">WSDL Import</span></span>  
 <span data-ttu-id="f38bc-139">若要扩展 WSDL 导入系统以处理导入地址，请将以下配置添加到 Svcutil.exe 的配置文件，如 Svcutil.exe.config 文件所示：</span><span class="sxs-lookup"><span data-stu-id="f38bc-139">To extend the WSDL import system to handle importing the addresses, add the following configuration to the configuration file for Svcutil.exe as shown in the Svcutil.exe.config file:</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <client>  
      <metadata>  
        <wsdlImporters>  
          <extension type=" Microsoft.ServiceModel.Samples.UdpBindingElementImporter, UdpTransport" />  
        </policyImporters>  
      </metadata>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="f38bc-140">当运行 Svcutil.exe 时，有两个选项可用来获取 Svcutil.exe 以加载 WSDL 导入扩展：</span><span class="sxs-lookup"><span data-stu-id="f38bc-140">When running Svcutil.exe, there are two options for getting Svcutil.exe to load the WSDL import extensions:</span></span>  
  
1. <span data-ttu-id="f38bc-141">Svcutil.exe 指向配置文件使用 /SvcutilConfig:\<文件 >。</span><span class="sxs-lookup"><span data-stu-id="f38bc-141">Point Svcutil.exe to the configuration file using the /SvcutilConfig:\<file>.</span></span>  
  
2. <span data-ttu-id="f38bc-142">将配置节添加到与 Svcutil.exe 处于同一目录的 Svcutil.exe.config 中。</span><span class="sxs-lookup"><span data-stu-id="f38bc-142">Add the configuration section to Svcutil.exe.config in the same directory as Svcutil.exe.</span></span>  
  
 <span data-ttu-id="f38bc-143">`UdpBindingElementImporter` 类型实现 <xref:System.ServiceModel.Description.IWsdlImportExtension?displayProperty=nameWithType> 接口。</span><span class="sxs-lookup"><span data-stu-id="f38bc-143">The `UdpBindingElementImporter` type implements the <xref:System.ServiceModel.Description.IWsdlImportExtension?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="f38bc-144">`ImportEndpoint` 方法从 WSDL 端口导入地址：</span><span class="sxs-lookup"><span data-stu-id="f38bc-144">The `ImportEndpoint` method imports the address from the WSDL port:</span></span>  
  
```csharp  
BindingElementCollection bindingElements = context.Endpoint.Binding.CreateBindingElements();  
TransportBindingElement transportBindingElement = bindingElements.Find<TransportBindingElement>();  
if (transportBindingElement is UdpTransportBindingElement)  
{  
    ImportAddress(context);  
}  
```  
  
### <a name="adding-policy-support"></a><span data-ttu-id="f38bc-145">添加策略支持</span><span class="sxs-lookup"><span data-stu-id="f38bc-145">Adding Policy Support</span></span>  
 <span data-ttu-id="f38bc-146">自定义绑定元素可以在 WSDL 绑定中为服务终结点导出策略断言以表示该绑定元素的功能。</span><span class="sxs-lookup"><span data-stu-id="f38bc-146">The custom binding element can export policy assertions in the WSDL binding for a service endpoint to express the capabilities of that binding element.</span></span> <span data-ttu-id="f38bc-147">下面的代码示例摘自[传输：UDP](../../../../docs/framework/wcf/samples/transport-udp.md)示例。</span><span class="sxs-lookup"><span data-stu-id="f38bc-147">The following example code is taken from the [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) sample.</span></span>  
  
#### <a name="policy-export"></a><span data-ttu-id="f38bc-148">策略导出</span><span class="sxs-lookup"><span data-stu-id="f38bc-148">Policy Export</span></span>  
 <span data-ttu-id="f38bc-149">`UdpTransportBindingElement`类型实现<xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType>以添加对导出策略的支持。</span><span class="sxs-lookup"><span data-stu-id="f38bc-149">The `UdpTransportBindingElement` type implements <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> to add support for exporting policy.</span></span> <span data-ttu-id="f38bc-150">因此，<xref:System.ServiceModel.Description.MetadataExporter?displayProperty=nameWithType> 在为任何包含它的绑定而生成策略时都包含 `UdpTransportBindingElement`。</span><span class="sxs-lookup"><span data-stu-id="f38bc-150">As a result, <xref:System.ServiceModel.Description.MetadataExporter?displayProperty=nameWithType> includes `UdpTransportBindingElement` in the generation of policy for any binding that includes it.</span></span>  
  
 <span data-ttu-id="f38bc-151">在 <xref:System.ServiceModel.Description.IPolicyExportExtension.ExportPolicy%2A?displayProperty=nameWithType> 中，如果通道处于多路广播模式，添加 UDP 的断言和其他断言。</span><span class="sxs-lookup"><span data-stu-id="f38bc-151">In <xref:System.ServiceModel.Description.IPolicyExportExtension.ExportPolicy%2A?displayProperty=nameWithType>, add an assertion for UDP and another assertion if the channel is in multicast mode.</span></span> <span data-ttu-id="f38bc-152">这是因为，多路广播模式影响通信堆栈的构造方式，因此必须在两端之间进行协调。</span><span class="sxs-lookup"><span data-stu-id="f38bc-152">This is because multicast mode affects how the communication stack is constructed, and thus must be coordinated between both sides.</span></span>  
  
```csharp  
ICollection<XmlElement> bindingAssertions = context.GetBindingAssertions();  
XmlDocument xmlDocument = new XmlDocument();  
bindingAssertions.Add(xmlDocument.CreateElement(  
UdpPolicyStrings.Prefix, UdpPolicyStrings.TransportAssertion, UdpPolicyStrings.UdpNamespace));  
if (Multicast)  
{  
    bindingAssertions.Add(xmlDocument.CreateElement(  
UdpPolicyStrings.Prefix, UdpPolicyStrings.MulticastAssertion,     UdpPolicyStrings.UdpNamespace));  
}  
```  
  
 <span data-ttu-id="f38bc-153">因为自定义传输绑定元素负责处理寻址，所以 <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> 上的 `UdpTransportBindingElement` 实现还必须处理导出相应的 WS-Addressing 策略断言以指示正在使用的 WS-Addressing 的版本。</span><span class="sxs-lookup"><span data-stu-id="f38bc-153">Because custom transport binding elements are responsible for handling addressing, the <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> implementation on the `UdpTransportBindingElement` must also handle exporting the appropriate WS-Addressing policy assertions to indicate the version of WS-Addressing being used.</span></span>  
  
```csharp  
AddWSAddressingAssertion(context, encodingBindingElement.MessageVersion.Addressing);  
```  
  
#### <a name="policy-import"></a><span data-ttu-id="f38bc-154">策略导入</span><span class="sxs-lookup"><span data-stu-id="f38bc-154">Policy Import</span></span>  
 <span data-ttu-id="f38bc-155">若要扩展策略导入系统，请将以下配置添加到 Svcutil.exe 的配置文件，如 Svcutil.exe.config 文件所示：</span><span class="sxs-lookup"><span data-stu-id="f38bc-155">To extend the policy import system, add the following configuration to the configuration file for Svcutil.exe as shown in the Svcutil.exe.config file:</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <client>  
      <metadata>  
        <policyImporters>  
          <extension type=" Microsoft.ServiceModel.Samples.UdpBindingElementImporter, UdpTransport" />  
        </policyImporters>  
      </metadata>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="f38bc-156">然后从已注册的类 (<xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType>) 中实现 `UdpBindingElementImporter`。</span><span class="sxs-lookup"><span data-stu-id="f38bc-156">Then we implement <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> from our registered class (`UdpBindingElementImporter`).</span></span> <span data-ttu-id="f38bc-157">在 <xref:System.ServiceModel.Description.IPolicyImportExtension.ImportPolicy%2A?displayProperty=nameWithType> 中，检查适当命名空间中的断言并处理那些生成传输和检查它是否为多路广播的断言。</span><span class="sxs-lookup"><span data-stu-id="f38bc-157">In <xref:System.ServiceModel.Description.IPolicyImportExtension.ImportPolicy%2A?displayProperty=nameWithType>, examine the assertions in the appropriate namespace and process the ones for generating the transport and checking if it is multicast.</span></span> <span data-ttu-id="f38bc-158">此外，从绑定断言列表中删除导入程序处理的断言。</span><span class="sxs-lookup"><span data-stu-id="f38bc-158">In addition, remove the assertions that the importer handles from the list of binding assertions.</span></span> <span data-ttu-id="f38bc-159">同样，当运行 Svcutil.exe 时，有两个用于集成的选项：</span><span class="sxs-lookup"><span data-stu-id="f38bc-159">Again, when running Svcutil.exe, there are two options for integration:</span></span>  
  
1. <span data-ttu-id="f38bc-160">Svcutil.exe 指向配置文件使用 /SvcutilConfig:\<文件 >。</span><span class="sxs-lookup"><span data-stu-id="f38bc-160">Point Svcutil.exe to our configuration file using the /SvcutilConfig:\<file>.</span></span>  
  
2. <span data-ttu-id="f38bc-161">将配置节添加到与 Svcutil.exe 处于同一目录的 Svcutil.exe.config 中。</span><span class="sxs-lookup"><span data-stu-id="f38bc-161">Add the configuration section to Svcutil.exe.config in the same directory as Svcutil.exe.</span></span>  
  
### <a name="adding-a-custom-standard-binding-importer"></a><span data-ttu-id="f38bc-162">添加自定义标准绑定导入程序</span><span class="sxs-lookup"><span data-stu-id="f38bc-162">Adding a Custom Standard Binding Importer</span></span>  
 <span data-ttu-id="f38bc-163">默认情况下，Svcutil.exe 和 <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType> 类型识别并导入系统提供的绑定。</span><span class="sxs-lookup"><span data-stu-id="f38bc-163">Svcutil.exe and the <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType> type, by default, recognize and import system-provided bindings.</span></span> <span data-ttu-id="f38bc-164">否则，绑定将作为 <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType> 实例而导入。</span><span class="sxs-lookup"><span data-stu-id="f38bc-164">Otherwise, the binding gets imported as a <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType> instance.</span></span> <span data-ttu-id="f38bc-165">若要启用 Svcutil.exe 和 <xref:System.ServiceModel.Description.WsdlImporter> 以导入 `SampleProfileUdpBinding`，`UdpBindingElementImporter` 还需充当自定义标准绑定导入程序。</span><span class="sxs-lookup"><span data-stu-id="f38bc-165">To enable Svcutil.exe and the <xref:System.ServiceModel.Description.WsdlImporter> to import the `SampleProfileUdpBinding` the `UdpBindingElementImporter` also acts as a custom standard binding importer.</span></span>  
  
 <span data-ttu-id="f38bc-166">自定义标准绑定导入程序实现`ImportEndpoint`方法<xref:System.ServiceModel.Description.IWsdlImportExtension?displayProperty=nameWithType>接口以检查<xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType>从元数据以查看它是否可以具有已由生成特定的标准绑定导入的实例。</span><span class="sxs-lookup"><span data-stu-id="f38bc-166">A custom standard binding importer implements the `ImportEndpoint` method on the <xref:System.ServiceModel.Description.IWsdlImportExtension?displayProperty=nameWithType> interface to examine the <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType> instance imported from metadata to see if it could have been generated by specific standard binding.</span></span>  
  
```csharp  
if (context.Endpoint.Binding is CustomBinding)  
{  
    Binding binding;  
    if (transportBindingElement is UdpTransportBindingElement)  
    {  
        //if TryCreate is true, the CustomBinding will be replace by a SampleProfileUdpBinding in the  
        //generated config file for better typed generation.  
        if (SampleProfileUdpBinding.TryCreate(bindingElements, out binding))  
        {  
            binding.Name = context.Endpoint.Binding.Name;  
            binding.Namespace = context.Endpoint.Binding.Namespace;  
            context.Endpoint.Binding = binding;  
        }  
    }  
}  
```  
  
 <span data-ttu-id="f38bc-167">通常，实现自定义标准绑定导入程序包括检查导入的绑定元素的属性以验证是否仅更改了标准绑定可以设置的属性，而所有其他属性都是各自的默认值。</span><span class="sxs-lookup"><span data-stu-id="f38bc-167">Generally, implementing a custom standard binding importer involves checking the properties of the imported binding elements to verify that only properties that could have been set by the standard binding have changed and all other properties are their defaults.</span></span> <span data-ttu-id="f38bc-168">用于实现标准绑定导入程序的基本策略是创建标准绑定的实例，将绑定元素中的属性传播到标准绑定支持的标准绑定实例中，然后将标准绑定中的绑定元素与导入的绑定元素进行比较。</span><span class="sxs-lookup"><span data-stu-id="f38bc-168">A basic strategy for implementing a standard binding importer is to create an instance of the standard binding, propagate the properties from the binding elements to the standard binding instance that the standard binding supports, and the compare the binding elements from the standard binding with the imported binding elements.</span></span>
