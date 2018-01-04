---
title: WSStreamedHttpBinding
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 97ce4d3d-ca6f-45fa-b33b-2429bb84e65b
caps.latest.revision: "27"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7d6259640bae2b4be4fac73883df8945bf1db7ff
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="wsstreamedhttpbinding"></a><span data-ttu-id="c51b2-102">WSStreamedHttpBinding</span><span class="sxs-lookup"><span data-stu-id="c51b2-102">WSStreamedHttpBinding</span></span>
<span data-ttu-id="c51b2-103">此示例演示如何创建一个绑定，该绑定用于在使用 HTTP 传输时支持流方案。</span><span class="sxs-lookup"><span data-stu-id="c51b2-103">The sample demonstrates how to create a binding that is designed to support streaming scenarios when the HTTP transport is used.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c51b2-104">本主题的最后介绍了此示例的设置过程和生成说明。</span><span class="sxs-lookup"><span data-stu-id="c51b2-104">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c51b2-105">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="c51b2-105">The samples may already be installed on your machine.</span></span> <span data-ttu-id="c51b2-106">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="c51b2-106">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="c51b2-107">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="c51b2-107">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c51b2-108">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="c51b2-108">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Binding\WSStreamedHttpBinding`  
  
 <span data-ttu-id="c51b2-109">下面是创建和配置新的标准绑定时涉及到的步骤。</span><span class="sxs-lookup"><span data-stu-id="c51b2-109">The steps to create and configure a new standard binding are as follows.</span></span>  
  
1.  <span data-ttu-id="c51b2-110">创建新的标准绑定</span><span class="sxs-lookup"><span data-stu-id="c51b2-110">Create a new standard binding</span></span>  
  
     <span data-ttu-id="c51b2-111">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 中的标准绑定（如 basicHttpBinding 和 netTcpBinding）根据具体要求配置基础传输和通道堆栈。</span><span class="sxs-lookup"><span data-stu-id="c51b2-111">The standard bindings in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] such as basicHttpBinding, and netTcpBinding configure the underlying transports and channel stack for specific requirements.</span></span> <span data-ttu-id="c51b2-112">在该示例中，`WSStreamedHttpBinding` 将通道堆栈配置为支持流。</span><span class="sxs-lookup"><span data-stu-id="c51b2-112">In this sample, `WSStreamedHttpBinding` configures the channel stack to support streaming.</span></span> <span data-ttu-id="c51b2-113">默认情况下，不将 WS-Security 和可靠消息传递添加到通道堆栈中，因为流不支持这两个功能。</span><span class="sxs-lookup"><span data-stu-id="c51b2-113">By default, WS-Security and reliable messaging are not added to the channel stack because both features are not supported by streaming.</span></span> <span data-ttu-id="c51b2-114">新绑定是在派生自 `WSStreamedHttpBinding` 的 <xref:System.ServiceModel.Channels.Binding> 类中实现的。</span><span class="sxs-lookup"><span data-stu-id="c51b2-114">The new binding is implemented in the class `WSStreamedHttpBinding` that derives from <xref:System.ServiceModel.Channels.Binding>.</span></span> <span data-ttu-id="c51b2-115">`WSStreamedHttpBinding` 包含下列绑定元素：<xref:System.ServiceModel.Channels.HttpTransportBindingElement>、<xref:System.ServiceModel.Channels.HttpsTransportBindingElement>、<xref:System.ServiceModel.Channels.TransactionFlowBindingElement> 和 <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>。</span><span class="sxs-lookup"><span data-stu-id="c51b2-115">The `WSStreamedHttpBinding` contains the following binding elements: <xref:System.ServiceModel.Channels.HttpTransportBindingElement>, <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>, <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>, and <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>.</span></span> <span data-ttu-id="c51b2-116">该类提供一种 `CreateBindingElements()` 方法来配置所得到的绑定堆栈，如下面的示例代码中所示。</span><span class="sxs-lookup"><span data-stu-id="c51b2-116">The class provides a `CreateBindingElements()` method to configure the resulting binding stack, as shown in the following sample code.</span></span>  
  
    ```  
    public override BindingElementCollection CreateBindingElements()  
    {  
         // return collection of BindingElements  
         BindingElementCollection bindingElements = new BindingElementCollection();  
  
        // the order of binding elements within the collection is important: layered channels are applied in the order included, followed by  
        // the message encoder, and finally the transport at the end  
        if (flowTransactions)  
        {  
            bindingElements.Add(transactionFlow);  
        }  
        bindingElements.Add(textEncoding);  
  
        // add transport (http or https)  
        bindingElements.Add(transport);  
        return bindingElements.Clone();  
    }  
    ```  
  
2.  <span data-ttu-id="c51b2-117">添加配置支持</span><span class="sxs-lookup"><span data-stu-id="c51b2-117">Add configuration support</span></span>  
  
     <span data-ttu-id="c51b2-118">为了通过配置来公开传输，此示例还实现了另外两个类：`WSStreamedHttpBindingConfigurationElement` 和 `WSStreamedHttpBindingSection`。</span><span class="sxs-lookup"><span data-stu-id="c51b2-118">To expose the transport through configuration the sample implements two more classes—`WSStreamedHttpBindingConfigurationElement` and `WSStreamedHttpBindingSection`.</span></span> <span data-ttu-id="c51b2-119">`WSStreamedHttpBindingSection` 类是一个向 <xref:System.ServiceModel.Configuration.StandardBindingCollectionElement%602> 配置系统公开 `WSStreamedHttpBinding` 的 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c51b2-119">The class `WSStreamedHttpBindingSection` is a <xref:System.ServiceModel.Configuration.StandardBindingCollectionElement%602> that exposes `WSStreamedHttpBinding` to the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] configuration system.</span></span> <span data-ttu-id="c51b2-120">批量实现委托给从 `WSStreamedHttpBindingConfigurationElement` 派生的 <xref:System.ServiceModel.Configuration.StandardBindingElement>。</span><span class="sxs-lookup"><span data-stu-id="c51b2-120">The bulk of the implementation is delegated to `WSStreamedHttpBindingConfigurationElement`, which derives from <xref:System.ServiceModel.Configuration.StandardBindingElement>.</span></span> <span data-ttu-id="c51b2-121">`WSStreamedHttpBindingConfigurationElement` 类具有与 `WSStreamedHttpBinding` 的属性相对应的属性，以及用来将每个配置元素映射到绑定的函数。</span><span class="sxs-lookup"><span data-stu-id="c51b2-121">The class `WSStreamedHttpBindingConfigurationElement` has properties that correspond to the properties of `WSStreamedHttpBinding`, and functions to map each configuration element to a binding.</span></span>  
  
     <span data-ttu-id="c51b2-122">可通过将以下节添加到服务的配置文件中来向配置系统注册处理程序。</span><span class="sxs-lookup"><span data-stu-id="c51b2-122">Register the handler with the configuration system, by adding the following section to the service's configuration file.</span></span>  
  
    ```xml  
    <configuration>  
      <system.serviceModel>  
        <extensions>  
          <bindingExtensions>  
            <add name="wsStreamedHttpBinding" type="Microsoft.ServiceModel.Samples.WSStreamedHttpBindingCollectionElement, WSStreamedHttpBinding, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null" />  
          </bindingExtensions>  
        </extensions>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
     <span data-ttu-id="c51b2-123">随后可以从 serviceModel 配置节中引用处理程序。</span><span class="sxs-lookup"><span data-stu-id="c51b2-123">The handler can then be referenced from the serviceModel configuration section.</span></span>  
  
    ```xml  
    <configuration>  
      <system.serviceModel>  
        <client>  
          <endpoint  
                    address="https://localhost/servicemodelsamples/service.svc"  
                    bindingConfiguration="Binding"  
                    binding="wsStreamedHttpBinding"  
                    contract="Microsoft.ServiceModel.Samples.IStreamedEchoService"/>  
        </client>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="c51b2-124">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="c51b2-124">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="c51b2-125">使用以下命令安装 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0。</span><span class="sxs-lookup"><span data-stu-id="c51b2-125">Install [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 using the following command.</span></span>  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2.  <span data-ttu-id="c51b2-126">确保已执行中列出的步骤[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="c51b2-126">Ensure that you have performed the steps listed in [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
3.  <span data-ttu-id="c51b2-127">确保已执行[Internet 信息服务 (IIS) 服务器证书安装说明](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md)。</span><span class="sxs-lookup"><span data-stu-id="c51b2-127">Ensure that you have performed the [Internet Information Services (IIS) Server Certificate Installation Instructions](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md).</span></span>  
  
4.  <span data-ttu-id="c51b2-128">若要生成解决方案，请按照中的说明[生成 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/building-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="c51b2-128">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
5.  <span data-ttu-id="c51b2-129">若要在跨计算机配置上运行示例，请按照中的说明[运行 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/running-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="c51b2-129">To run the sample in a cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
6.  <span data-ttu-id="c51b2-130">在看到客户端窗口时，键入“Sample.txt”。</span><span class="sxs-lookup"><span data-stu-id="c51b2-130">When the client window displays, type "Sample.txt".</span></span> <span data-ttu-id="c51b2-131">应当能够在目录中找到“Copy of Sample.txt”。</span><span class="sxs-lookup"><span data-stu-id="c51b2-131">You should find a "Copy of Sample.txt" in your directory.</span></span>  
  
## <a name="the-wsstreamedhttpbinding-sample-service"></a><span data-ttu-id="c51b2-132">WSStreamedHttpBinding 示例服务</span><span class="sxs-lookup"><span data-stu-id="c51b2-132">The WSStreamedHttpBinding Sample Service</span></span>  
 <span data-ttu-id="c51b2-133">使用 `WSStreamedHttpBinding` 的示例服务位于服务子目录中。</span><span class="sxs-lookup"><span data-stu-id="c51b2-133">The sample service that uses `WSStreamedHttpBinding` is located in the service subdirectory.</span></span> <span data-ttu-id="c51b2-134">所实现的 `OperationContract` 在返回 `MemoryStream` 之前，首先使用 `MemoryStream` 检索传入的流中的所有数据。</span><span class="sxs-lookup"><span data-stu-id="c51b2-134">The implementation of `OperationContract` uses a `MemoryStream` to first retrieve all data from the incoming stream before returning the `MemoryStream`.</span></span> <span data-ttu-id="c51b2-135">此示例服务是由 Internet 信息服务 (IIS) 承载的。</span><span class="sxs-lookup"><span data-stu-id="c51b2-135">The sample service is hosted by Internet Information Services (IIS).</span></span>  
  
```  
[ServiceContract]  
public interface IStreamedEchoService  
{  
    [OperationContract]  
    Stream Echo(Stream data);  
}  
  
public class StreamedEchoService : IStreamedEchoService  
{  
    public Stream Echo(Stream data)  
    {  
        MemoryStream dataStorage = new MemoryStream();  
        byte[] byteArray = new byte[8192];  
        int bytesRead = data.Read(byteArray, 0, 8192);  
        while (bytesRead > 0)  
        {  
            dataStorage.Write(byteArray, 0, bytesRead);  
            bytesRead = data.Read(byteArray, 0, 8192);  
        }  
        data.Close();  
        dataStorage.Seek(0, SeekOrigin.Begin);  
  
        return dataStorage;  
    }  
}  
```  
  
## <a name="the-wsstreamedhttpbinding-sample-client"></a><span data-ttu-id="c51b2-136">WSStreamedHttpBinding 示例客户端</span><span class="sxs-lookup"><span data-stu-id="c51b2-136">The WSStreamedHttpBinding Sample Client</span></span>  
 <span data-ttu-id="c51b2-137">在使用 `WSStreamedHttpBinding` 与服务进行交互时所用的客户端位于客户端子目录中。</span><span class="sxs-lookup"><span data-stu-id="c51b2-137">The client that is used to interact with the service using `WSStreamedHttpBinding` is located in the client subdirectory.</span></span> <span data-ttu-id="c51b2-138">因为此示例中使用的证书是用 Makecert.exe 创建的测试证书，所以，当尝试在浏览器中访问 HTTPS 地址（如 https://localhost/servicemodelsamples/service.svc）时，将显示一个安全警报。</span><span class="sxs-lookup"><span data-stu-id="c51b2-138">Because the certificate used in this sample is a test certificate created with Makecert.exe, a security alert displays when you attempt to access an HTTPS address in your browser such as https://localhost/servicemodelsamples/service.svc.</span></span> <span data-ttu-id="c51b2-139">为了允许 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 客户端就地使用测试证书，已向客户端添加了一些附加代码，以禁用安全警报。</span><span class="sxs-lookup"><span data-stu-id="c51b2-139">To allow the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client to work with a test certificate in place, some additional code has been added to the client to suppress the security alert.</span></span> <span data-ttu-id="c51b2-140">使用生产证书时，不需要此代码和随附的类。</span><span class="sxs-lookup"><span data-stu-id="c51b2-140">The code and the accompanying class are not required when using production certificates.</span></span>  
  
```  
// WARNING: This code is only required for test certificates such as those created by makecert. It is   
// not recommended for production code.  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
```  
  
## <a name="see-also"></a><span data-ttu-id="c51b2-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="c51b2-141">See Also</span></span>
