---
title: WS 传输安全
ms.date: 03/30/2017
ms.assetid: 33a20358-5e1b-458a-a6a9-15753bc7b99b
ms.openlocfilehash: 221bf2e0d304e93242bb5fea6854c1c9bb72aec2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79143455"
---
# <a name="ws-transport-security"></a><span data-ttu-id="20867-102">WS 传输安全</span><span class="sxs-lookup"><span data-stu-id="20867-102">WS Transport Security</span></span>
<span data-ttu-id="20867-103">此示例演示如何对 <xref:System.ServiceModel.WSHttpBinding> 绑定使用 SSL 传输安全。</span><span class="sxs-lookup"><span data-stu-id="20867-103">This sample demonstrates the use of SSL transport security with the <xref:System.ServiceModel.WSHttpBinding> binding.</span></span> <span data-ttu-id="20867-104">默认情况下，`wsHttpBinding` 绑定提供 HTTP 通信。</span><span class="sxs-lookup"><span data-stu-id="20867-104">By default, the `wsHttpBinding` binding provides HTTP communication.</span></span> <span data-ttu-id="20867-105">针对传输安全配置绑定之后，该绑定即支持 HTTPS 通信。</span><span class="sxs-lookup"><span data-stu-id="20867-105">When configured for transport security, the binding supports HTTPS communication.</span></span> <span data-ttu-id="20867-106">此示例基于实现计算器服务的[入门](../../../../docs/framework/wcf/samples/getting-started-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="20867-106">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service.</span></span> <span data-ttu-id="20867-107">`wsHttpBinding` 是在客户端和服务的应用程序配置文件中指定和配置的。</span><span class="sxs-lookup"><span data-stu-id="20867-107">The `wsHttpBinding` is specified and configured in the application configuration files for the client and service.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="20867-108">本主题的最后介绍了此示例的设置过程和生成说明。</span><span class="sxs-lookup"><span data-stu-id="20867-108">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="20867-109">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="20867-109">The samples may already be installed on your machine.</span></span> <span data-ttu-id="20867-110">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="20867-110">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="20867-111">如果此目录不存在，请转到[Windows 通信基础 （WCF） 和 Windows 工作流基础 （WF） 示例 .NET 框架 4](https://www.microsoft.com/download/details.aspx?id=21459)以下载[!INCLUDE[wf1](../../../../includes/wf1-md.md)]所有 Windows 通信基础 （WCF） 和示例。</span><span class="sxs-lookup"><span data-stu-id="20867-111">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="20867-112">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="20867-112">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\wsTransportSecurity`  
  
 <span data-ttu-id="20867-113">示例中的程序代码与[入门](../../../../docs/framework/wcf/samples/getting-started-sample.md)服务的代码相同。</span><span class="sxs-lookup"><span data-stu-id="20867-113">The program code in the sample is identical to that of the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) service.</span></span> <span data-ttu-id="20867-114">必须在生成和运行示例之前使用 Web 服务器证书向导创建证书并分配此证书。</span><span class="sxs-lookup"><span data-stu-id="20867-114">You must create a certificate and assign it by using the Web Server Certificate Wizard before building and running the sample.</span></span> <span data-ttu-id="20867-115">配置文件设置中的终结点定义和绑定定义可启用 `Transport` 安全模式，如下面的客户端示例配置所示。</span><span class="sxs-lookup"><span data-stu-id="20867-115">The endpoint definition and binding definition in the configuration file settings enable `Transport` security mode, as shown in the following sample configuration for the client.</span></span>  
  
```xml  
<system.serviceModel>  
  
    <client>  
      <!-- this endpoint has an https: address -->  
      <endpoint address="https://localhost/servicemodelsamples/service.svc" binding="wsHttpBinding" bindingConfiguration="Binding1" contract="Microsoft.Samples.TransportSecurity.ICalculator"/>  
    </client>  
  
    <bindings>  
      <wsHttpBinding>  
        <!-- configure wsHttpbinding with Transport security mode  
                   and clientCredentialType as None -->  
        <binding name="Binding1">  
          <security mode="Transport">  
            <transport clientCredentialType="None"/>  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
  
  </system.serviceModel>  
```  
  
 <span data-ttu-id="20867-116">指定的地址使用 https:// 方案。</span><span class="sxs-lookup"><span data-stu-id="20867-116">The address specified uses the https:// scheme.</span></span> <span data-ttu-id="20867-117">绑定配置将安全模式设置为 `Transport`。</span><span class="sxs-lookup"><span data-stu-id="20867-117">The binding configuration sets the security mode to `Transport`.</span></span> <span data-ttu-id="20867-118">必须在服务的 Web.config 文件中指定相同的安全模式。</span><span class="sxs-lookup"><span data-stu-id="20867-118">The same security mode must be specified in the service's Web.config file.</span></span>  
  
 <span data-ttu-id="20867-119">由于此示例中使用的证书是使用 Makecert.exe 创建的测试证书，因此当您尝试从浏览器访问 https： 地址（如https://localhost/servicemodelsamples/service.svc）时，会显示安全警报。</span><span class="sxs-lookup"><span data-stu-id="20867-119">Because the certificate used in this sample is a test certificate created with Makecert.exe, a security alert appears when you try to access an https: address, such as https://localhost/servicemodelsamples/service.svc, from your browser.</span></span> <span data-ttu-id="20867-120">为了允许 Windows 通信基础 （WCF） 客户端使用就地使用测试证书，已经向客户端添加了一些附加代码以禁止安全警报。</span><span class="sxs-lookup"><span data-stu-id="20867-120">To allow the Windows Communication Foundation (WCF) client to work with a test certificate in place, some additional code has been added to the client to suppress the security alert.</span></span> <span data-ttu-id="20867-121">使用生产证书时，不需要此代码和随附的类。</span><span class="sxs-lookup"><span data-stu-id="20867-121">This code, and the accompanying class, is not required when using production certificates.</span></span>  

```csharp
// This code is required only for test certificates like those created by Makecert.exe.  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
```

 <span data-ttu-id="20867-122">运行示例时，操作请求和响应将显示在客户端控制台窗口中。</span><span class="sxs-lookup"><span data-stu-id="20867-122">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="20867-123">在客户端窗口中按 Enter 可以关闭客户端。</span><span class="sxs-lookup"><span data-stu-id="20867-123">Press ENTER in the client window to shut down the client.</span></span>  
  
```console  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="20867-124">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="20867-124">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="20867-125">使用以下命令安装ASP.NET 4.0。</span><span class="sxs-lookup"><span data-stu-id="20867-125">Install ASP.NET 4.0 using the following command.</span></span>  
  
    ```console  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2. <span data-ttu-id="20867-126">确保已为 Windows[通信基础示例执行一次性设置过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="20867-126">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
3. <span data-ttu-id="20867-127">确保您已执行[互联网信息服务 （IIS） 服务器证书安装说明](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md)。</span><span class="sxs-lookup"><span data-stu-id="20867-127">Ensure that you have performed the [Internet Information Services (IIS) Server Certificate Installation Instructions](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md).</span></span>  
  
4. <span data-ttu-id="20867-128">若要生成 C# 或 Visual Basic .NET 版本的解决方案，请按照 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="20867-128">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
5. <span data-ttu-id="20867-129">要在单机或跨计算机配置中运行示例，请按照[运行 Windows 通信基础示例中的](../../../../docs/framework/wcf/samples/running-the-samples.md)说明操作。</span><span class="sxs-lookup"><span data-stu-id="20867-129">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
