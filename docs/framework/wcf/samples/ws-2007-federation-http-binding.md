---
title: "WS 2007 联合 HTTP 绑定"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 91c1b477-a96e-4bf5-9330-5e9312113371
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3cdba8b43c109b8fbd0a5892bfa4c4c15e1caabf
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="ws-2007-federation-http-binding"></a><span data-ttu-id="bfb28-102">WS 2007 联合 HTTP 绑定</span><span class="sxs-lookup"><span data-stu-id="bfb28-102">WS 2007 Federation HTTP Binding</span></span>
<span data-ttu-id="bfb28-103">此示例演示 <xref:System.ServiceModel.WS2007FederationHttpBinding> 的用法，它是一个标准绑定，可用来生成支持 1.3 版 WS-Trust 规范的联合方案。</span><span class="sxs-lookup"><span data-stu-id="bfb28-103">This sample demonstrates the use of <xref:System.ServiceModel.WS2007FederationHttpBinding>, a standard binding that you can use to build federated scenarios that support version 1.3 of the WS-Trust specification.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bfb28-104">本主题的最后介绍了此示例的设置过程和生成说明。</span><span class="sxs-lookup"><span data-stu-id="bfb28-104">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="bfb28-105">此示例由基于控制台的客户端程序 (Client.exe)、基于控制台的安全令牌服务程序 (Securitytokenservice.exe) 和基于控制台的服务程序 (Service.exe) 组成。</span><span class="sxs-lookup"><span data-stu-id="bfb28-105">The sample consists of a console-based client program (Client.exe), a console-based security token service program (Securitytokenservice.exe), and a console-based service program (Service.exe).</span></span> <span data-ttu-id="bfb28-106">服务实现用来定义“请求/答复”通信模式的协定。</span><span class="sxs-lookup"><span data-stu-id="bfb28-106">The service implements a contract that defines a request/reply communication pattern.</span></span> <span data-ttu-id="bfb28-107">该协定由 `ICalculator` 接口定义，此接口公开数学运算（`Add`、`Subtract`、`Multiply` 和 `Divide`）。</span><span class="sxs-lookup"><span data-stu-id="bfb28-107">The contract is defined by the `ICalculator` interface, which exposes math operations (`Add`, `Subtract`, `Multiply`, and `Divide`).</span></span> <span data-ttu-id="bfb28-108">客户端从安全令牌服务 (STS) 获取安全令牌，向服务发出同步请求，以进行给定数学运算。</span><span class="sxs-lookup"><span data-stu-id="bfb28-108">The client obtains a security token from the Security Token Service (STS) and makes synchronous requests to the service for a given math operation.</span></span> <span data-ttu-id="bfb28-109">服务使用结果进行回复。</span><span class="sxs-lookup"><span data-stu-id="bfb28-109">The service then replies with the result.</span></span> <span data-ttu-id="bfb28-110">客户端活动显示在控制台窗口中。</span><span class="sxs-lookup"><span data-stu-id="bfb28-110">Client activity is visible in the console window.</span></span>  
  
 <span data-ttu-id="bfb28-111">此示例使用 `ICalculator` 元素提供 `ws2007FederationHttpBinding` 协定。</span><span class="sxs-lookup"><span data-stu-id="bfb28-111">The sample makes the `ICalculator` contract available using the `ws2007FederationHttpBinding` element.</span></span> <span data-ttu-id="bfb28-112">下面的代码演示了此绑定在客户端上的配置。</span><span class="sxs-lookup"><span data-stu-id="bfb28-112">The configuration of this binding on the client is shown in the following code.</span></span>  
  
```xml  
<bindings>  
  <ws2007FederationHttpBinding>  
    <binding name="ServiceFed" >  
      <security mode ="Message">  
        <message issuedKeyType ="SymmetricKey"  
                 issuedTokenType ="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1" >  
          <!-- Endpoint address and binding for Security Token Service -->  
          <issuer address ="http://localhost:8000/sts/windows"   
                  binding ="ws2007HttpBinding" />                
        </message>  
      </security>  
    </binding>  
  </ws2007FederationHttpBinding>  
</bindings>  
```  
  
 <span data-ttu-id="bfb28-113">上[\<安全 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md)、`security`值指定应使用的安全模式。</span><span class="sxs-lookup"><span data-stu-id="bfb28-113">On the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md), the `security` value specifies which security mode should be used.</span></span> <span data-ttu-id="bfb28-114">在此示例中，`message`使用安全性，这就是为什么[\<消息 >](../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md)内指定[\<安全 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="bfb28-114">In this sample, `message` security is used, which is why the [\<message>](../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) is specified inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md).</span></span> <span data-ttu-id="bfb28-115">[\<颁发者 >](../../../../docs/framework/configure-apps/file-schema/wcf/issuer.md)内的元素[\<消息 >](../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md)指定的地址和绑定 sts，以便客户端可以向客户端颁发安全令牌对进行身份验证`ICalculator`服务。</span><span class="sxs-lookup"><span data-stu-id="bfb28-115">The [\<issuer>](../../../../docs/framework/configure-apps/file-schema/wcf/issuer.md) element inside the [\<message>](../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) specifies the address and binding for the STS that issues a security token to the client so that the client can authenticate to the `ICalculator` service.</span></span>  
  
 <span data-ttu-id="bfb28-116">下面的代码演示了此绑定在服务上的配置。</span><span class="sxs-lookup"><span data-stu-id="bfb28-116">The configuration of this binding on the service is shown in the following code.</span></span>  
  
```xml  
<bindings>  
  <ws2007FederationHttpBinding>  
    <binding name="ServiceFed" >  
      <security mode ="Message">  
        <message issuedKeyType ="SymmetricKey"  
                 issuedTokenType ="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1" >  
          <!-- Metadata address for Security Token Service -->  
          <issuerMetadata address ="http://localhost:8000/sts/mex" >  
            <identity>  
              <certificateReference storeLocation ="CurrentUser"   
                                    storeName="TrustedPeople"   
                                    x509FindType ="FindBySubjectDistinguishedName"   
                                    findValue ="CN=STS" />  
            </identity>  
          </issuerMetadata>  
        </message>  
      </security>  
    </binding>  
  </ws2007FederationHttpBinding>  
</bindings>  
```  
  
 <span data-ttu-id="bfb28-117">上[\<安全 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md)、`security`值指定应使用的安全模式。</span><span class="sxs-lookup"><span data-stu-id="bfb28-117">On the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md), the `security` value specifies which security mode should be used.</span></span> <span data-ttu-id="bfb28-118">在此示例中，`message`使用安全性，这就是为什么[\<消息 >](../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md)内指定[\<安全 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="bfb28-118">In this sample, `message` security is used, which is why the [\<message>](../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) is specified inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md).</span></span> <span data-ttu-id="bfb28-119">[ \<IssuerMetadata >](../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata.md)元素`ws2007FederationHttpBinding`内[\<消息 >](../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md)指定地址和用于检索终结点标识STS 元数据。</span><span class="sxs-lookup"><span data-stu-id="bfb28-119">The [\<issuerMetadata>](../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata.md) element of `ws2007FederationHttpBinding` inside the [\<message>](../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) specifies the address and identity for an endpoint that can be used to retrieve metadata for the STS.</span></span>  
  
 <span data-ttu-id="bfb28-120">下面的代码演示了该服务的行为。</span><span class="sxs-lookup"><span data-stu-id="bfb28-120">The behavior for the service is shown in the following code.</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior name ="ServiceBehaviour" >  
      <serviceDebug includeExceptionDetailInFaults ="true"/>  
      <serviceMetadata httpGetEnabled ="true"/>  
      <serviceCredentials>  
        <issuedTokenAuthentication>  
          <knownCertificates>  
            <add storeLocation ="LocalMachine"  
                 storeName="TrustedPeople"  
                 x509FindType="FindBySubjectDistinguishedName"  
                 findValue="CN=STS" />  
          </knownCertificates>  
        </issuedTokenAuthentication>  
        <serviceCertificate storeLocation ="LocalMachine"  
                            storeName ="My"  
                            x509FindType ="FindBySubjectDistinguishedName"  
                            findValue ="CN=localhost"/>  
      </serviceCredentials>  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 <span data-ttu-id="bfb28-121">[ \<IssuedTokenAuthentication >](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)> 允许服务指定它允许客户端身份验证期间提供的令牌上的约束。</span><span class="sxs-lookup"><span data-stu-id="bfb28-121">The [\<issuedTokenAuthentication>](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)> allows the service to specify constraints on the tokens it allows clients to present during authentication.</span></span> <span data-ttu-id="bfb28-122">此配置指定该服务接受由主题名称为 CN=STS 的证书签名的令牌。</span><span class="sxs-lookup"><span data-stu-id="bfb28-122">This configuration specifies that tokens signed by a certificate whose subject name is CN=STS are accepted by the service.</span></span>  
  
 <span data-ttu-id="bfb28-123">STS 使用标准的 <xref:System.ServiceModel.WS2007HttpBinding> 提供单个终结点。</span><span class="sxs-lookup"><span data-stu-id="bfb28-123">STS makes a single endpoint available using the standard <xref:System.ServiceModel.WS2007HttpBinding>.</span></span> <span data-ttu-id="bfb28-124">服务响应客户端对令牌的请求。</span><span class="sxs-lookup"><span data-stu-id="bfb28-124">The service responds to requests from clients for tokens.</span></span> <span data-ttu-id="bfb28-125">如果客户端使用 Windows 帐户进行身份验证，则服务将颁发一个令牌，该令牌以声明的形式包含客户端的用户名。</span><span class="sxs-lookup"><span data-stu-id="bfb28-125">If the client is authenticated using a Windows account, the service issues a token that contains the client's user name as a claim.</span></span> <span data-ttu-id="bfb28-126">在创建令牌的过程中，STS 使用与 CN=STS 证书关联的私钥对令牌进行签名。</span><span class="sxs-lookup"><span data-stu-id="bfb28-126">As part of creating the token, STS signs the token using the private key associated with the CN=STS certificate.</span></span> <span data-ttu-id="bfb28-127">另外，它还创建对称密钥并使用与 CN=localhost 证书关联的公钥对该密钥进行加密。</span><span class="sxs-lookup"><span data-stu-id="bfb28-127">In addition, it creates a symmetric key and encrypts it using the public key associated with the CN=localhost certificate.</span></span> <span data-ttu-id="bfb28-128">在向客户端返回令牌的过程中，STS 还返回对称密钥。</span><span class="sxs-lookup"><span data-stu-id="bfb28-128">In returning the token to the client, STS also returns the symmetric key.</span></span> <span data-ttu-id="bfb28-129">客户端向 `ICalculator` 服务出示所颁发的令牌，并通过使用密钥对消息进行签名来证明客户端知道该对称密钥。</span><span class="sxs-lookup"><span data-stu-id="bfb28-129">The client presents the issued token to the `ICalculator` service and proves that it knows the symmetric key by signing the message with that key.</span></span>  
  
 <span data-ttu-id="bfb28-130">运行示例时，对安全令牌的请求显示在 STS 控制台窗口中。</span><span class="sxs-lookup"><span data-stu-id="bfb28-130">When you run the sample, the request for the security token is shown in the STS console window.</span></span> <span data-ttu-id="bfb28-131">操作请求和响应显示在客户端和服务控制台窗口中。</span><span class="sxs-lookup"><span data-stu-id="bfb28-131">The operation's requests and responses are displayed in the client and service console windows.</span></span> <span data-ttu-id="bfb28-132">在任何一个控制台窗口中按 Enter 可以关闭应用程序。</span><span class="sxs-lookup"><span data-stu-id="bfb28-132">Press ENTER in any of the console windows to shut down the application.</span></span>  
  
 `Add(100,15.99) = 115.99`  
  
 `Subtract(145,76.54) = 68.46`  
  
 `Multiply(9,81.25) = 731.25`  
  
 `Divide(22,7) = 3.14285714285714`  
  
 `Press <ENTER> to terminate client.`  
  
 <span data-ttu-id="bfb28-133">通过运行此示例随附的 Setup.bat 文件，可以用相关的证书将服务器和 STS 配置为运行自承载应用程序。</span><span class="sxs-lookup"><span data-stu-id="bfb28-133">The Setup.bat file included with this sample allows you to configure the server and STS with the relevant certificates to run a self-hosted application.</span></span> <span data-ttu-id="bfb28-134">该批处理文件在 LocalMachine/TrustedPeople 证书存储区中创建两个证书。</span><span class="sxs-lookup"><span data-stu-id="bfb28-134">The batch file creates two certificates in the LocalMachine/TrustedPeople certificate store.</span></span> <span data-ttu-id="bfb28-135">第一个证书的主题名称为 CN=STS，STS 使用该证书对颁发给客户端的安全令牌进行签名。</span><span class="sxs-lookup"><span data-stu-id="bfb28-135">The first certificate has a subject name of CN=STS and is used by STS to sign the security tokens that it issues to the client.</span></span> <span data-ttu-id="bfb28-136">第二个证书的主题名称为 CN=localhost，STS 使用该证书，按照服务能够解密的方式对密钥进行加密。</span><span class="sxs-lookup"><span data-stu-id="bfb28-136">The second certificate has a subject name of CN=localhost and is used by STS to encrypt a key in a way that the service can decrypt.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="bfb28-137">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="bfb28-137">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="bfb28-138">确保已执行[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="bfb28-138">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="bfb28-139">使用管理员特权打开 Visual Studio 命令提示并运行 Setup.bat 文件以创建所需的证书。</span><span class="sxs-lookup"><span data-stu-id="bfb28-139">Open a Visual Studio command prompt with administrator privileges and run the Setup.bat file to create the required certificates.</span></span>  
  
 <span data-ttu-id="bfb28-140">该批处理文件使用随 Windows SDK 分发的 Certmgr.exe 和 Makecert.exe。</span><span class="sxs-lookup"><span data-stu-id="bfb28-140">This batch file uses Certmgr.exe and Makecert.exe, which are distributed with the Windows SDK.</span></span> <span data-ttu-id="bfb28-141">但是，您必须在 Visual Studio 命令提示中运行 Setup.bat，脚本才能找到这些工具。</span><span class="sxs-lookup"><span data-stu-id="bfb28-141">However, you must run Setup.bat from within a Visual Studio  command prompt to enable the script to find these tools.</span></span>  
  
1.  <span data-ttu-id="bfb28-142">若要生成 C# 或 Visual Basic .NET 版本的解决方案，请按照 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="bfb28-142">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2.  <span data-ttu-id="bfb28-143">若要在单或跨计算机配置上运行示例，请按照中的说明[运行 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/running-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="bfb28-143">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span> <span data-ttu-id="bfb28-144">如果你使用[!INCLUDE[windowsver](../../../../includes/windowsver-md.md)]、 必须运行 Service.exe、 Client.exe 和 SecurityTokenService.exe 使用提升的权限 (右键单击文件，然后单击**以管理员身份运行**)。</span><span class="sxs-lookup"><span data-stu-id="bfb28-144">If you are using [!INCLUDE[windowsver](../../../../includes/windowsver-md.md)], you must run Service.exe, Client.exe, and SecurityTokenService.exe with elevated privileges (right-click the files and then click **Run as administrator**).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="bfb28-145">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="bfb28-145">The samples may already be installed on your computer.</span></span> <span data-ttu-id="bfb28-146">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="bfb28-146">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="bfb28-147">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="bfb28-147">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="bfb28-148">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="bfb28-148">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\WS2007FederationHttp`  
  
## <a name="see-also"></a><span data-ttu-id="bfb28-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bfb28-149">See Also</span></span>
