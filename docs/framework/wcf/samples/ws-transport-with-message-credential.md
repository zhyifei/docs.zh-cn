---
title: 使用消息凭据的 WS 传输
ms.date: 03/30/2017
ms.assetid: 0d092f3a-b309-439b-920b-66d8f46a0e3c
ms.openlocfilehash: 708869f2350f01e75b949f4817fcf8aac35ea018
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2018
---
# <a name="ws-transport-with-message-credential"></a><span data-ttu-id="0df72-102">使用消息凭据的 WS 传输</span><span class="sxs-lookup"><span data-stu-id="0df72-102">WS Transport With Message Credential</span></span>
<span data-ttu-id="0df72-103">此示例演示如何将 SSL 传输安全与消息中传送的客户端凭据结合使用。</span><span class="sxs-lookup"><span data-stu-id="0df72-103">This sample demonstrates the use of SSL transport security in combination with client credential being carried in the message.</span></span> <span data-ttu-id="0df72-104">本示例使用 `wsHttpBinding` 绑定。</span><span class="sxs-lookup"><span data-stu-id="0df72-104">This sample uses the `wsHttpBinding` binding.</span></span>  
  
 <span data-ttu-id="0df72-105">默认情况下，`wsHttpBinding` 绑定提供 HTTP 通信。</span><span class="sxs-lookup"><span data-stu-id="0df72-105">By default, the `wsHttpBinding` binding provides HTTP communication.</span></span> <span data-ttu-id="0df72-106">针对传输安全配置绑定之后，该绑定即支持 HTTPS 通信。</span><span class="sxs-lookup"><span data-stu-id="0df72-106">When configured for transport security, the binding supports HTTPS communication.</span></span> <span data-ttu-id="0df72-107">HTTPS 为通过网络传输的消息提供机密性和完整性保护。</span><span class="sxs-lookup"><span data-stu-id="0df72-107">HTTPS provides confidentiality and integrity protection for the messages that are transmitted over the wire.</span></span> <span data-ttu-id="0df72-108">但是，可用于针对服务对客户端进行身份验证的身份验证机制集仅限于 HTTPS 传输所支持的内容。</span><span class="sxs-lookup"><span data-stu-id="0df72-108">However the set of authentication mechanisms that can be used to authenticate the client to the service is limited to what the HTTPS transport supports.</span></span> <span data-ttu-id="0df72-109">Windows Communication Foundation (WCF) 提供`TransportWithMessageCredential`旨在克服此限制的安全模式。</span><span class="sxs-lookup"><span data-stu-id="0df72-109">Windows Communication Foundation (WCF) offers a `TransportWithMessageCredential` security mode that is designed to overcome this limitation.</span></span> <span data-ttu-id="0df72-110">配置该安全模式之后，使用传输安全为传输的消息提供机密性和完整性，并执行服务身份验证。</span><span class="sxs-lookup"><span data-stu-id="0df72-110">When this security mode is configured, the transport security is used to provide confidentiality and integrity for the transmitted messages and to perform the service authentication.</span></span> <span data-ttu-id="0df72-111">但是，客户端身份验证是通过将客户端凭据放在消息中直接执行。</span><span class="sxs-lookup"><span data-stu-id="0df72-111">However, the client authentication is performed by putting the client credential directly in the message.</span></span> <span data-ttu-id="0df72-112">这样，你可以使用任何凭据类型的支持的客户端身份验证，同时保持传输安全模式下的性能优势的消息安全模式。</span><span class="sxs-lookup"><span data-stu-id="0df72-112">This allows you to use any credential type that is supported by the message security mode for the client authentication while keeping the performance benefit of transport security mode.</span></span>  
  
 <span data-ttu-id="0df72-113">在此示例中，使用 `UserName` 凭据类型向服务对客户端进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="0df72-113">In this sample, a `UserName` credential type is used to authenticate the client to the service.</span></span>  
  
 <span data-ttu-id="0df72-114">此示例基于[入门](../../../../docs/framework/wcf/samples/getting-started-sample.md)实现计算器服务。</span><span class="sxs-lookup"><span data-stu-id="0df72-114">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service.</span></span> <span data-ttu-id="0df72-115">`wsHttpBinding` 绑定在客户端和服务的应用程序配置文件中指定和配置。</span><span class="sxs-lookup"><span data-stu-id="0df72-115">The `wsHttpBinding` binding is specified and configured in the application configuration files for the client and service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0df72-116">本主题的最后介绍了此示例的设置过程和生成说明。</span><span class="sxs-lookup"><span data-stu-id="0df72-116">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="0df72-117">此示例中的程序代码在几乎等同于的[入门](../../../../docs/framework/wcf/samples/getting-started-sample.md)服务。</span><span class="sxs-lookup"><span data-stu-id="0df72-117">The program code in the sample is almost identical to that of the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) service.</span></span> <span data-ttu-id="0df72-118">服务协定还提供了一个附加操作，即 `GetCallerIdentity`。</span><span class="sxs-lookup"><span data-stu-id="0df72-118">There is one additional operation provided by the service contract - `GetCallerIdentity`.</span></span> <span data-ttu-id="0df72-119">该操作向调用方返回调用方标识的名称。</span><span class="sxs-lookup"><span data-stu-id="0df72-119">This operation returns the name of the caller's identity to the caller.</span></span>  

```csharp
public string GetCallerIdentity()  
{  
    // Use ServiceSecurityContext.WindowsIdentity to get the name of the caller.  
    return ServiceSecurityContext.Current.WindowsIdentity.Name;  
}  
```

 <span data-ttu-id="0df72-120">必须在生成和运行示例之前使用 Web 服务器证书向导创建证书并分配此证书。</span><span class="sxs-lookup"><span data-stu-id="0df72-120">You must create a certificate and assign it by using the Web Server Certificate Wizard before building and running the sample.</span></span> <span data-ttu-id="0df72-121">配置文件设置中的终结点定义和绑定定义可启用 `TransportWithMessageCredential` 安全模式，如下面的客户端示例配置所示。</span><span class="sxs-lookup"><span data-stu-id="0df72-121">The endpoint definition and binding definition in the configuration file settings enable `TransportWithMessageCredential` security mode, as shown in the following sample configuration for the client.</span></span>  
  
```xml  
<system.serviceModel>  
  <client>  
    <endpoint name=""  
              address="https://localhost/servicemodelsamples/service.svc"   
              binding="wsHttpBinding"   
              bindingConfiguration="Binding1"   
              contract="Microsoft.ServiceModel.Samples.ICalculator" />  
  </client>  
  
  <bindings>  
    <wsHttpBinding>  
      <!--   
        This configuration defines the security mode as TransportWithMessageCredential.  
        and the clientCredentialType as UserName.  
        -->  
      <binding name="Binding1">  
        <security mode ="TransportWithMessageCredential">  
          <message clientCredentialType="UserName" />  
        </security>  
      </binding>  
    </wsHttpBinding>  
  </bindings>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="0df72-122">指定的地址使用 https:// 方案。</span><span class="sxs-lookup"><span data-stu-id="0df72-122">The address specified uses the https:// scheme.</span></span> <span data-ttu-id="0df72-123">绑定配置将安全模式设置为 `TransportWithMessageCredential`。</span><span class="sxs-lookup"><span data-stu-id="0df72-123">The binding configuration sets the security mode to `TransportWithMessageCredential`.</span></span> <span data-ttu-id="0df72-124">必须在服务的 Web.config 文件中指定相同的安全模式。</span><span class="sxs-lookup"><span data-stu-id="0df72-124">The same security mode must be specified in the service's Web.config file.</span></span>  
  
 <span data-ttu-id="0df72-125">因为此示例中使用的证书是用 Makecert.exe 创建的测试证书，当你尝试访问 https 时显示安全警报： 地址，如https://localhost/servicemodelsamples/service.svc，从你的浏览器。</span><span class="sxs-lookup"><span data-stu-id="0df72-125">Because the certificate used in this sample is a test certificate created with Makecert.exe, a security alert appears when you try to access an https: address, such as https://localhost/servicemodelsamples/service.svc, from your browser.</span></span> <span data-ttu-id="0df72-126">若要允许 WCF 客户端以使用就地测试证书，一些附加代码已添加到客户端以禁用安全警报。</span><span class="sxs-lookup"><span data-stu-id="0df72-126">To allow the WCF client to work with a test certificate in place, some additional code has been added to the client to suppress the security alert.</span></span> <span data-ttu-id="0df72-127">使用生产证书时，不需要此代码和随附的类。</span><span class="sxs-lookup"><span data-stu-id="0df72-127">This code, and the accompanying class, is not required when using production certificates.</span></span>  

```csharp
// WARNING: This code is only needed for test certificates such as those created by makecert. It is   
// not recommended for production code.  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
```
  
 <span data-ttu-id="0df72-128">运行示例时，操作请求和响应将显示在客户端控制台窗口中。</span><span class="sxs-lookup"><span data-stu-id="0df72-128">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="0df72-129">在客户端窗口中按 Enter 可以关闭客户端。</span><span class="sxs-lookup"><span data-stu-id="0df72-129">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
Username authentication required.  
Provide a valid machine or domain account. [domain\\user]  
   Enter username:   
YourDomainName\YourAccountName  
   Enter password:   
********  
YourDomainName\YourAccountName  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="0df72-130">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="0df72-130">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="0df72-131">确保已执行[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="0df72-131">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="0df72-132">确保已执行[Internet 信息服务 (IIS) 服务器证书安装说明](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md)。</span><span class="sxs-lookup"><span data-stu-id="0df72-132">Ensure that you have performed the [Internet Information Services (IIS) Server Certificate Installation Instructions](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md).</span></span>  
  
3.  <span data-ttu-id="0df72-133">若要生成 C# 或 Visual Basic .NET 版本的解决方案，请按照 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="0df72-133">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4.  <span data-ttu-id="0df72-134">若要在单或跨计算机配置上运行示例，请按照中的说明[运行 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/running-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="0df72-134">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0df72-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="0df72-135">See Also</span></span>
