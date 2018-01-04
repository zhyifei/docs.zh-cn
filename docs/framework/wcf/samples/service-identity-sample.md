---
title: "服务标识示例"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 79fa8c1c-85bb-4b67-bc67-bfaf721303f8
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bc2e179109a8015a16684c20e3a1ef46b781b8f0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="service-identity-sample"></a><span data-ttu-id="1a143-102">服务标识示例</span><span class="sxs-lookup"><span data-stu-id="1a143-102">Service Identity Sample</span></span>
<span data-ttu-id="1a143-103">此服务标识示例演示如何为服务设置标识。</span><span class="sxs-lookup"><span data-stu-id="1a143-103">This service identity sample demonstrates how to set the identity for a service.</span></span> <span data-ttu-id="1a143-104">客户端可以在设计时使用服务的元数据来检索标识，然后在运行时对服务的标识进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="1a143-104">At design time, a client can retrieve the identity using the service's metadata and then at runtime the client can authenticate the service's identity.</span></span> <span data-ttu-id="1a143-105">服务标识的概念是允许客户端在调用服务的任何操作之前对服务进行身份验证，从而保护客户端，防止进行未经身份验证的调用。</span><span class="sxs-lookup"><span data-stu-id="1a143-105">The concept of service identity is to allow a client to authenticate a service before calling any of its operations, thereby protecting the client from unauthenticated calls.</span></span> <span data-ttu-id="1a143-106">在安全连接中，服务还在允许客户端访问其之前对客户端的凭据进行身份验证，但这不是此示例要介绍的重点。</span><span class="sxs-lookup"><span data-stu-id="1a143-106">On a secure connection the service also authenticates a client's credentials before allowing it access, but this is not the focus of this sample.</span></span> <span data-ttu-id="1a143-107">请参阅中的示例[客户端](../../../../docs/framework/wcf/samples/client.md)显示服务器身份验证。</span><span class="sxs-lookup"><span data-stu-id="1a143-107">See the samples in [Client](../../../../docs/framework/wcf/samples/client.md) that show server authentication.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1a143-108">本主题的最后介绍了此示例的设置过程和生成说明。</span><span class="sxs-lookup"><span data-stu-id="1a143-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="1a143-109">此示例介绍以下功能：</span><span class="sxs-lookup"><span data-stu-id="1a143-109">This sample illustrates the following features:</span></span>  
  
-   <span data-ttu-id="1a143-110">如何在服务的不同终结点上设置不同类型的标识。</span><span class="sxs-lookup"><span data-stu-id="1a143-110">How to set the different types of identity on different endpoints for a service.</span></span> <span data-ttu-id="1a143-111">每种标识具有不同的功能。</span><span class="sxs-lookup"><span data-stu-id="1a143-111">Each type of identity has different capabilities.</span></span> <span data-ttu-id="1a143-112">要使用哪种标识取决于终结点绑定中使用的安全凭据的类型。</span><span class="sxs-lookup"><span data-stu-id="1a143-112">The type of identity to use is dependent on the type of security credentials used on the endpoint's binding.</span></span>  
  
-   <span data-ttu-id="1a143-113">可以在配置中通过声明方式设置标识，也可以在代码中强制设置标识。</span><span class="sxs-lookup"><span data-stu-id="1a143-113">Identity can either be set declaratively in configuration or imperatively in code.</span></span> <span data-ttu-id="1a143-114">通常，对于客户端和服务，应使用配置来设置标识。</span><span class="sxs-lookup"><span data-stu-id="1a143-114">Typically for both the client and the service you should use configuration to set the identity.</span></span>  
  
-   <span data-ttu-id="1a143-115">如何在客户端设置自定义标识。</span><span class="sxs-lookup"><span data-stu-id="1a143-115">How to set a custom identity on the client.</span></span> <span data-ttu-id="1a143-116">自定义标识通常是对现有标识类型的自定义，客户端可以通过它检查服务凭据中提供的其他声明信息，以便在调用服务之前做出身份验证决策。</span><span class="sxs-lookup"><span data-stu-id="1a143-116">A custom identity is typically a customization of an existing type of identity that enables the client to examine other claim information provided in the service's credentials to make authorization decisions before calling the service.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1a143-117">此示例检查称为 identity.com 的特定证书的标识以及此证书中包含的 RSA 密钥。</span><span class="sxs-lookup"><span data-stu-id="1a143-117">This sample checks the identity of a specific certificate called identity.com and the RSA key contained within this certificate.</span></span> <span data-ttu-id="1a143-118">在客户端上的配置中使用证书和 RSA 标识类型时，获取这些值的简便方法是检查在其中序列化这些值的服务的 WSDL。</span><span class="sxs-lookup"><span data-stu-id="1a143-118">When using the Certificate and RSA identity types in configuration on the client, an easy way to get these values is to inspect the WSDL for the service where these values are serialized.</span></span>  
  
 <span data-ttu-id="1a143-119">下面的示例代码演示如何使用 WSHttpBinding 向证书的域名服务器 (DNS) 配置服务终结点的标识。</span><span class="sxs-lookup"><span data-stu-id="1a143-119">The following sample code shows how to configure the identity of a service endpoint with the Domain Name Server (DNS) of a certificate using a WSHttpBinding.</span></span>  
  
```  
//Create a service endpoint and set its identity to the certificate's DNS                 
WSHttpBinding wsAnonbinding = new WSHttpBinding (SecurityMode.Message);  
// Client are Anonymous to the service  
wsAnonbinding.Security.Message.ClientCredentialType = MessageCredentialType.None;  
WServiceEndpoint ep = serviceHost.AddServiceEndpoint(typeof(ICalculator),wsAnonbinding, String.Empty);  
EndpointAddress epa = new EndpointAddress(dnsrelativeAddress,EndpointIdentity.CreateDnsIdentity("identity.com"));  
ep.Address = epa;  
```  
  
 <span data-ttu-id="1a143-120">还可以在 App.config 文件的配置中指定标识。</span><span class="sxs-lookup"><span data-stu-id="1a143-120">The identity can also be specified in configuration in the App.config file.</span></span> <span data-ttu-id="1a143-121">下面的示例演示如何为服务终结点设置 UPN（用户主要名称）标识。</span><span class="sxs-lookup"><span data-stu-id="1a143-121">The following example shows how to set the UPN (User Principal Name) identity for a service endpoint.</span></span>  
  
```xml  
<endpoint address="upnidentity"  
        behaviorConfiguration=""  
        binding="wsHttpBinding"  
        bindingConfiguration="WSHttpBinding_Windows"  
        name="WSHttpBinding_ICalculator_Windows"  
        contract="Microsoft.ServiceModel.Samples.ICalculator">  
  <!-- Set the UPN identity for this endpoint -->  
  <identity>  
      <userPrincipalName value="host\myservice.com" />  
  </identity >  
</endpoint>  
```  
  
 <span data-ttu-id="1a143-122">通过从 <xref:System.ServiceModel.EndpointIdentity> 和 <xref:System.ServiceModel.Security.IdentityVerifier> 类派生，可以在客户端设置自定义标识。</span><span class="sxs-lookup"><span data-stu-id="1a143-122">A custom identity can be set on the client by deriving from the <xref:System.ServiceModel.EndpointIdentity> and the <xref:System.ServiceModel.Security.IdentityVerifier> classes.</span></span> <span data-ttu-id="1a143-123">从概念上讲，可以将 <xref:System.ServiceModel.Security.IdentityVerifier> 类视为服务的 `AuthorizationManager` 类的客户端等效类。</span><span class="sxs-lookup"><span data-stu-id="1a143-123">Conceptually the <xref:System.ServiceModel.Security.IdentityVerifier> class can be considered to be the client equivalent of the service's `AuthorizationManager` class.</span></span> <span data-ttu-id="1a143-124">下面的代码示例演示了 `OrgEndpointIdentity` 的实现，它用于存储组织名称，以便与服务器证书的主题名称相匹配。</span><span class="sxs-lookup"><span data-stu-id="1a143-124">The following code example shows an implementation of `OrgEndpointIdentity`, which stores an organization name to match in the subject name of the server's certificate.</span></span> <span data-ttu-id="1a143-125">对该组织名称的授权检查发生在 `CheckAccess` 类的 `CustomIdentityVerifier` 方法上。</span><span class="sxs-lookup"><span data-stu-id="1a143-125">The authorization check for the organization name occurs in the `CheckAccess` method on the `CustomIdentityVerifier` class.</span></span>  
  
```  
// This custom EndpointIdentity stores an organization name   
public class OrgEndpointIdentity : EndpointIdentity  
{  
    private string orgClaim;  
    public OrgEndpointIdentity(string orgName)  
    {  
        orgClaim = orgName;  
    }  
    public string OrganizationClaim  
    {  
        get { return orgClaim; }  
        set { orgClaim = value; }  
    }  
}  
  
//This custom IdentityVerifier uses the supplied OrgEndpointIdentity to  
//check that X.509 certificate's distinguished name claim contains  
//the organization name e.g. the string value "O=Contoso"   
class CustomIdentityVerifier : IdentityVerifier  
{  
    public override bool CheckAccess(EndpointIdentity identity, AuthorizationContext authContext)  
    {  
        bool returnvalue = false;  
        foreach (ClaimSet claimset in authContext.ClaimSets)  
        {  
            foreach (Claim claim in claimset)  
            {  
                if (claim.ClaimType == "http://schemas.microsoft.com/ws/2005/05/identity/claims/x500distinguishedname")  
                {  
                    X500DistinguishedName name = (X500DistinguishedName)claim.Resource;  
                    if (name.Name.Contains(((OrgEndpointIdentity)identity).OrganizationClaim))  
                    {  
                        Console.WriteLine("Claim Type: {0}",claim.ClaimType);  
                        Console.WriteLine("Right: {0}", claim.Right);  
                        Console.WriteLine("Resource: {0}",claim.Resource);  
                        Console.WriteLine();  
                        returnvalue = true;  
                    }  
                }  
            }  
        }  
        return returnvalue;  
    }  
}  
```  
  
 <span data-ttu-id="1a143-126">此示例使用称为 identity.com 的证书，此证书位于特定于语言的 Identity 解决方案文件夹中。</span><span class="sxs-lookup"><span data-stu-id="1a143-126">This sample uses a certificate called identity.com which is in the language-specific Identity solution folder.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="1a143-127">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="1a143-127">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="1a143-128">确保已执行[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="1a143-128">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="1a143-129">若要生成 C# 或 Visual Basic .NET 版本的解决方案，请按照 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="1a143-129">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="1a143-130">若要在单或跨计算机配置上运行示例，请按照中的说明[运行 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/running-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="1a143-130">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="1a143-131">在同一计算机上运行示例</span><span class="sxs-lookup"><span data-stu-id="1a143-131">To run the sample on the same computer</span></span>  
  
1.  <span data-ttu-id="1a143-132">在 [!INCLUDE[wxp](../../../../includes/wxp-md.md)] 或 [!INCLUDE[wv](../../../../includes/wv-md.md)] 上，使用 MMC 管理单元工具将 Identity 解决方案文件夹中的 Identity.pfx 证书文件导入 LocalMachine/My（个人）证书存储区中。</span><span class="sxs-lookup"><span data-stu-id="1a143-132">On [!INCLUDE[wxp](../../../../includes/wxp-md.md)] or [!INCLUDE[wv](../../../../includes/wv-md.md)], import the Identity.pfx certificate file in the Identity solution folder into the LocalMachine/My (Personal) certificate store using the MMC snap-in tool.</span></span> <span data-ttu-id="1a143-133">此文件受密码保护。</span><span class="sxs-lookup"><span data-stu-id="1a143-133">This file is password protected.</span></span> <span data-ttu-id="1a143-134">在导入过程中，将提示您输入密码。</span><span class="sxs-lookup"><span data-stu-id="1a143-134">During the import you are asked for a password.</span></span> <span data-ttu-id="1a143-135">类型`xyz`在密码框中。</span><span class="sxs-lookup"><span data-stu-id="1a143-135">Type `xyz` into the password box.</span></span> <span data-ttu-id="1a143-136">有关详细信息，请参阅[如何： 使用 mmc 管理单元查看证书](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md)主题。</span><span class="sxs-lookup"><span data-stu-id="1a143-136">For more information, see the [How to: View Certificates with the MMC Snap-in](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md) topic.</span></span> <span data-ttu-id="1a143-137">完成此操作后，使用管理员特权在 Visual Studio 命令提示中运行 Setup.bat，将此证书复制到 CurrentUser/Trusted People 存储中以便在客户端上使用。</span><span class="sxs-lookup"><span data-stu-id="1a143-137">Once this is done, run Setup.bat in a Visual Studio command prompt with administrator privileges, which copies this certificate to the CurrentUser/Trusted People store for use on the client.</span></span>  
  
2.  <span data-ttu-id="1a143-138">在 [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] 上，使用管理员特权在 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 命令提示中运行示例安装文件夹中的 Setup.bat。</span><span class="sxs-lookup"><span data-stu-id="1a143-138">On [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], run Setup.bat from the sample install folder inside a [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] command prompt with administrator privileges.</span></span> <span data-ttu-id="1a143-139">这将安装运行示例所需的所有证书。</span><span class="sxs-lookup"><span data-stu-id="1a143-139">This installs all the certificates required for running the sample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1a143-140">Setup.bat 批处理文件设计为通过 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 命令提示运行。</span><span class="sxs-lookup"><span data-stu-id="1a143-140">The Setup.bat batch file is designed to be run from a [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] Command Prompt.</span></span> <span data-ttu-id="1a143-141">[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 命令提示中设置的 PATH 环境变量指向包含 Setup.bat 脚本所需的可执行文件的目录。</span><span class="sxs-lookup"><span data-stu-id="1a143-141">The PATH environment variable set within the [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] Command Prompt points to the directory that contains executables required by the Setup.bat script.</span></span> <span data-ttu-id="1a143-142">请确保在运行完该示例后通过运行 Cleanup.bat 来移除证书。</span><span class="sxs-lookup"><span data-stu-id="1a143-142">Ensure that you remove the certificates by running Cleanup.bat when you have finished with the sample.</span></span> <span data-ttu-id="1a143-143">其他安全示例使用相同的证书。</span><span class="sxs-lookup"><span data-stu-id="1a143-143">Other security samples use the same certificates.</span></span>  
  
3.  <span data-ttu-id="1a143-144">启动 \service\bin 目录中的 Service.exe。</span><span class="sxs-lookup"><span data-stu-id="1a143-144">Launch Service.exe from the \service\bin directory.</span></span> <span data-ttu-id="1a143-145">确保该服务指示它已就绪并按显示一条提示\<Enter > 以终止服务。</span><span class="sxs-lookup"><span data-stu-id="1a143-145">Ensure that the service indicates that it is ready and displays a prompt to Press \<Enter> to terminate the service.</span></span>  
  
4.  <span data-ttu-id="1a143-146">启动 \client\bin 目录中的 Client.exe，或在 Visual Studio 中按 F5 以生成并运行。</span><span class="sxs-lookup"><span data-stu-id="1a143-146">Launch Client.exe from \client\bin directory or by pressing F5 in Visual Studio to build and run.</span></span> <span data-ttu-id="1a143-147">客户端活动将显示在客户端控制台应用程序上。</span><span class="sxs-lookup"><span data-stu-id="1a143-147">Client activity is displayed on the client console application.</span></span>  
  
5.  <span data-ttu-id="1a143-148">如果客户端与服务无法进行通信，请参见 [Troubleshooting Tips](http://msdn.microsoft.com/en-us/8787c877-5e96-42da-8214-fa737a38f10b)。</span><span class="sxs-lookup"><span data-stu-id="1a143-148">If the client and service are not able to communicate, see [Troubleshooting Tips](http://msdn.microsoft.com/en-us/8787c877-5e96-42da-8214-fa737a38f10b).</span></span>  
  
### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="1a143-149">跨计算机运行示例</span><span class="sxs-lookup"><span data-stu-id="1a143-149">To run the sample across computers</span></span>  
  
1.  <span data-ttu-id="1a143-150">在生成该示例的客户端部分之前，请确保在 `CallServiceCustomClientIdentity` 方法中更改 Client.cs 文件中的服务终结点地址值。</span><span class="sxs-lookup"><span data-stu-id="1a143-150">Before building the client part of the sample, be sure to change the value for the service's endpoint address in the Client.cs file in the `CallServiceCustomClientIdentity` method.</span></span> <span data-ttu-id="1a143-151">然后生成该示例。</span><span class="sxs-lookup"><span data-stu-id="1a143-151">Then build the sample.</span></span>  
  
2.  <span data-ttu-id="1a143-152">在服务计算机上创建目录。</span><span class="sxs-lookup"><span data-stu-id="1a143-152">Create a directory on the service computer.</span></span>  
  
3.  <span data-ttu-id="1a143-153">将 service\bin 中的服务程序文件复制到服务计算机上的目录中。</span><span class="sxs-lookup"><span data-stu-id="1a143-153">Copy the service program files from service\bin to the directory on the service computer.</span></span> <span data-ttu-id="1a143-154">另外，将 Setup.bat 和 Cleanup.bat 文件复制到服务计算机上。</span><span class="sxs-lookup"><span data-stu-id="1a143-154">Also copy the Setup.bat and Cleanup.bat files to the service computer.</span></span>  
  
4.  <span data-ttu-id="1a143-155">在客户端计算机上为这些客户端二进制文件创建一个目录。</span><span class="sxs-lookup"><span data-stu-id="1a143-155">Create a directory on the client computer for the client binaries.</span></span>  
  
5.  <span data-ttu-id="1a143-156">将客户端程序文件复制到客户端计算机上的客户端目录中。</span><span class="sxs-lookup"><span data-stu-id="1a143-156">Copy the client program files to the client directory on the client computer.</span></span> <span data-ttu-id="1a143-157">另外，将 Setup.bat、Cleanup.bat 和 ImportServiceCert.bat 文件复制到客户端上。</span><span class="sxs-lookup"><span data-stu-id="1a143-157">Also copy the Setup.bat, Cleanup.bat, and ImportServiceCert.bat files to the client.</span></span>  
  
6.  <span data-ttu-id="1a143-158">在服务上，在使用管理员特权打开的 Visual Studio 命令提示中运行 `setup.bat service`。</span><span class="sxs-lookup"><span data-stu-id="1a143-158">On the service, run `setup.bat service` in a Visual Studio command prompt opened with administrator privileges.</span></span> <span data-ttu-id="1a143-159">运行`setup.bat`与`service`自变量的计算机的完全限定域名创建一个服务证书，并将服务证书导出到名为 Service.cer 的文件。</span><span class="sxs-lookup"><span data-stu-id="1a143-159">Running `setup.bat` with the `service` argument creates a service certificate with the fully-qualified domain name of the computer and exports the service certificate to a file named Service.cer.</span></span>  
  
7.  <span data-ttu-id="1a143-160">将服务目录中的 Service.cer 文件复制到客户端计算机上的客户端目录中。</span><span class="sxs-lookup"><span data-stu-id="1a143-160">Copy the Service.cer file from the service directory to the client directory on the client computer.</span></span>  
  
8.  <span data-ttu-id="1a143-161">在客户端计算机上的 Client.exe.config 文件中，更改终结点的地址值，使其与服务的新地址相匹配。</span><span class="sxs-lookup"><span data-stu-id="1a143-161">In the Client.exe.config file on the client computer, change the address value of the endpoint to match the new address of your service.</span></span> <span data-ttu-id="1a143-162">必须更改多个实例。</span><span class="sxs-lookup"><span data-stu-id="1a143-162">There are multiple instances that must be changed.</span></span>  
  
9. <span data-ttu-id="1a143-163">在客户端上，在使用管理员特权打开的 Visual Studio 命令提示中运行 ImportServiceCert.bat。</span><span class="sxs-lookup"><span data-stu-id="1a143-163">On the client, run ImportServiceCert.bat in a Visual Studio command prompt opened with administrator privileges.</span></span> <span data-ttu-id="1a143-164">这会将 Service.cer 文件中的服务证书导入 CurrentUser – TrustedPeople 存储区。</span><span class="sxs-lookup"><span data-stu-id="1a143-164">This imports the service certificate from the Service.cer file into the CurrentUser - TrustedPeople store.</span></span>  
  
10. <span data-ttu-id="1a143-165">在服务计算机上，在命令提示符下启动 Service.exe。</span><span class="sxs-lookup"><span data-stu-id="1a143-165">On the service computer, launch the Service.exe from the command prompt.</span></span>  
  
11. <span data-ttu-id="1a143-166">在客户端计算机上，在命令提示符下启动 Client.exe。</span><span class="sxs-lookup"><span data-stu-id="1a143-166">On the client computer, launch Client.exe from a command prompt.</span></span> <span data-ttu-id="1a143-167">如果客户端与服务无法进行通信，请参见 [Troubleshooting Tips](http://msdn.microsoft.com/en-us/8787c877-5e96-42da-8214-fa737a38f10b)。</span><span class="sxs-lookup"><span data-stu-id="1a143-167">If the client and service are not able to communicate, see [Troubleshooting Tips](http://msdn.microsoft.com/en-us/8787c877-5e96-42da-8214-fa737a38f10b).</span></span>  
  
### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="1a143-168">运行示例后进行清理</span><span class="sxs-lookup"><span data-stu-id="1a143-168">To clean up after the sample</span></span>  
  
-   <span data-ttu-id="1a143-169">运行完示例后运行示例文件夹中的 Cleanup.bat。</span><span class="sxs-lookup"><span data-stu-id="1a143-169">Run Cleanup.bat in the samples folder once you have finished running the sample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1a143-170">此脚本不会在跨计算机运行此示例时移除客户端上的服务证书。</span><span class="sxs-lookup"><span data-stu-id="1a143-170">This script does not remove service certificates on a client when running this sample across computers.</span></span> <span data-ttu-id="1a143-171">如果已运行跨计算机使用证书的 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 示例，请确保清除已安装在 CurrentUser - TrustedPeople 存储中的服务证书。</span><span class="sxs-lookup"><span data-stu-id="1a143-171">If you have run [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] samples that use certificates across computers, be sure to clear the service certificates that have been installed in the CurrentUser - TrustedPeople store.</span></span> <span data-ttu-id="1a143-172">为此，请使用以下命令：`certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>`，例如：`certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`。</span><span class="sxs-lookup"><span data-stu-id="1a143-172">To do this, use the following command: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` For example: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a143-173">请参阅</span><span class="sxs-lookup"><span data-stu-id="1a143-173">See Also</span></span>
