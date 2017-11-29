---
title: "基于消息队列的消息安全性"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 329aea9c-fa80-45c0-b2b9-e37fd7b85b38
caps.latest.revision: "22"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 6e3d87ab31b7a0910b270e81c28985ffe9279d4c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="message-security-over-message-queuing"></a><span data-ttu-id="39190-102">基于消息队列的消息安全性</span><span class="sxs-lookup"><span data-stu-id="39190-102">Message Security over Message Queuing</span></span>
<span data-ttu-id="39190-103">此示例演示如何实现一个应用程序，该应用程序对客户端使用 WS-Security 和 X.509v3 证书身份验证，并要求使用服务器的 X.509v3 证书对 MSMQ 进行服务器身份验证。</span><span class="sxs-lookup"><span data-stu-id="39190-103">This sample demonstrates how to implement an application that uses WS-Security with X.509v3 certificate authentication for the client and requires server authentication using the server's X.509v3 certificate over MSMQ.</span></span> <span data-ttu-id="39190-104">有时候消息安全性更重要，以确保 MSMQ 存储区中的消息始终是加密的，并且应用程序能够对消息执行其自己的身份验证。</span><span class="sxs-lookup"><span data-stu-id="39190-104">Message security is sometimes more desirable to ensure that the messages in the MSMQ store stay encrypted and the application can perform its own authentication of the message.</span></span>  
  
 <span data-ttu-id="39190-105">此示例基于[事务性 MSMQ 绑定](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md)示例。</span><span class="sxs-lookup"><span data-stu-id="39190-105">This sample is based on the [Transacted MSMQ Binding](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md) sample.</span></span> <span data-ttu-id="39190-106">消息已经过加密和签名。</span><span class="sxs-lookup"><span data-stu-id="39190-106">The messages are encrypted and signed.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="39190-107">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="39190-107">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="39190-108">确保已执行[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="39190-108">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="39190-109">如果先运行服务，则它将检查以确保队列存在。</span><span class="sxs-lookup"><span data-stu-id="39190-109">If the service is run first, it will check to ensure that the queue is present.</span></span> <span data-ttu-id="39190-110">如果队列不存在，则服务将创建一个队列。</span><span class="sxs-lookup"><span data-stu-id="39190-110">If the queue is not present, the service will create one.</span></span> <span data-ttu-id="39190-111">可以先运行服务以创建队列或通过 MSMQ 队列管理器创建一个队列。</span><span class="sxs-lookup"><span data-stu-id="39190-111">You can run the service first to create the queue, or you can create one via the MSMQ Queue Manager.</span></span> <span data-ttu-id="39190-112">执行下面的步骤来在 Windows 2008 中创建队列。</span><span class="sxs-lookup"><span data-stu-id="39190-112">Follow these steps to create a queue in Windows 2008.</span></span>  
  
    1.  <span data-ttu-id="39190-113">在 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 中打开服务器管理器。</span><span class="sxs-lookup"><span data-stu-id="39190-113">Open Server Manager in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span></span>  
  
    2.  <span data-ttu-id="39190-114">展开**功能**选项卡。</span><span class="sxs-lookup"><span data-stu-id="39190-114">Expand the **Features** tab.</span></span>  
  
    3.  <span data-ttu-id="39190-115">右键单击**私有消息队列**，然后选择**新建**，**专用队列**。</span><span class="sxs-lookup"><span data-stu-id="39190-115">Right-click **Private Message Queues**, and select **New**, **Private Queue**.</span></span>  
  
    4.  <span data-ttu-id="39190-116">检查**事务**框。</span><span class="sxs-lookup"><span data-stu-id="39190-116">Check the **Transactional** box.</span></span>  
  
    5.  <span data-ttu-id="39190-117">输入`ServiceModelSamplesTransacted`作为新队列的名称。</span><span class="sxs-lookup"><span data-stu-id="39190-117">Enter `ServiceModelSamplesTransacted` as the name of the new queue.</span></span>  
  
3.  <span data-ttu-id="39190-118">若要生成 C# 或 Visual Basic .NET 版本的解决方案，请按照 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="39190-118">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="39190-119">在同一计算机上运行示例</span><span class="sxs-lookup"><span data-stu-id="39190-119">To run the sample on the same computer</span></span>  
  
1.  <span data-ttu-id="39190-120">请确保路径包括 Makecert.exe 和 FindPrivateKey.exe 所在的文件夹。</span><span class="sxs-lookup"><span data-stu-id="39190-120">Ensure that the path includes the folder that contains Makecert.exe and FindPrivateKey.exe.</span></span>  
  
2.  <span data-ttu-id="39190-121">运行示例安装文件夹中的 Setup.bat。</span><span class="sxs-lookup"><span data-stu-id="39190-121">Run Setup.bat from the sample install folder.</span></span> <span data-ttu-id="39190-122">这将安装运行示例所需的所有证书。</span><span class="sxs-lookup"><span data-stu-id="39190-122">This installs all the certificates required for running the sample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="39190-123">请确保在运行完该示例后通过运行 Cleanup.bat 来移除证书。</span><span class="sxs-lookup"><span data-stu-id="39190-123">Ensure that you remove the certificates by running Cleanup.bat when you have finished with the sample.</span></span> <span data-ttu-id="39190-124">其他安全示例使用相同的证书。</span><span class="sxs-lookup"><span data-stu-id="39190-124">Other security samples use the same certificates.</span></span>  
  
3.  <span data-ttu-id="39190-125">启动 \service\bin 中的 Service.exe。</span><span class="sxs-lookup"><span data-stu-id="39190-125">Launch Service.exe from \service\bin.</span></span>  
  
4.  <span data-ttu-id="39190-126">启动 \client\bin 中的 Client.exe。</span><span class="sxs-lookup"><span data-stu-id="39190-126">Launch Client.exe from \client\bin.</span></span> <span data-ttu-id="39190-127">客户端活动将显示在客户端控制台应用程序上。</span><span class="sxs-lookup"><span data-stu-id="39190-127">Client activity is displayed on the client console application.</span></span>  
  
5.  <span data-ttu-id="39190-128">如果客户端与服务无法进行通信，请参见 [Troubleshooting Tips](http://msdn.microsoft.com/en-us/8787c877-5e96-42da-8214-fa737a38f10b)。</span><span class="sxs-lookup"><span data-stu-id="39190-128">If the client and service are not able to communicate, see [Troubleshooting Tips](http://msdn.microsoft.com/en-us/8787c877-5e96-42da-8214-fa737a38f10b).</span></span>  
  
### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="39190-129">跨计算机运行示例</span><span class="sxs-lookup"><span data-stu-id="39190-129">To run the sample across computers</span></span>  
  
1.  <span data-ttu-id="39190-130">将 Setup.bat、Cleanup.bat 和 ImportClientCert.bat 文件复制到服务计算机上。</span><span class="sxs-lookup"><span data-stu-id="39190-130">Copy the Setup.bat, Cleanup.bat, and ImportClientCert.bat files to the service computer.</span></span>  
  
2.  <span data-ttu-id="39190-131">在客户端计算机上为这些客户端二进制文件创建一个目录。</span><span class="sxs-lookup"><span data-stu-id="39190-131">Create a directory on the client computer for the client binaries.</span></span>  
  
3.  <span data-ttu-id="39190-132">将客户端程序文件复制到客户端计算机上的客户端目录中。</span><span class="sxs-lookup"><span data-stu-id="39190-132">Copy the client program files to the client directory on the client computer.</span></span> <span data-ttu-id="39190-133">另外，将 Setup.bat、Cleanup.bat 和 ImportServiceCert.bat 文件复制到客户端上。</span><span class="sxs-lookup"><span data-stu-id="39190-133">Also copy the Setup.bat, Cleanup.bat, and ImportServiceCert.bat files to the client.</span></span>  
  
4.  <span data-ttu-id="39190-134">在服务器上运行 `setup.bat service`。</span><span class="sxs-lookup"><span data-stu-id="39190-134">On the server, run `setup.bat service`.</span></span> <span data-ttu-id="39190-135">运行`setup.bat`与`service`自变量的计算机的完全限定域名创建一个服务证书，并将服务证书导出到名为 Service.cer 的文件。</span><span class="sxs-lookup"><span data-stu-id="39190-135">Running `setup.bat` with the `service` argument creates a service certificate with the fully-qualified domain name of the computer and exports the service certificate to a file named Service.cer.</span></span>  
  
5.  <span data-ttu-id="39190-136">编辑服务的 service.exe.config 以反映新的证书名称 (在`findValue`属性中[ \<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)) 这是计算机的完全限定域名相同。</span><span class="sxs-lookup"><span data-stu-id="39190-136">Edit service's service.exe.config to reflect the new certificate name (in the `findValue` attribute in the [\<serviceCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)) which is the same as the fully-qualified domain name of the computer.</span></span>  
  
6.  <span data-ttu-id="39190-137">将服务目录中的 Service.cer 文件复制到客户端计算机上的客户端目录中。</span><span class="sxs-lookup"><span data-stu-id="39190-137">Copy the Service.cer file from the service directory to the client directory on the client computer.</span></span>  
  
7.  <span data-ttu-id="39190-138">在客户端上，运行 `setup.bat client`。</span><span class="sxs-lookup"><span data-stu-id="39190-138">On the client, run `setup.bat client`.</span></span> <span data-ttu-id="39190-139">如果使用 `setup.bat` 参数运行 `client`，则会创建一个名为 client.com 的客户端证书，并将此客户端证书导出到名为 Client.cer 的文件中。</span><span class="sxs-lookup"><span data-stu-id="39190-139">Running `setup.bat` with the `client` argument creates a client certificate named client.com and exports the client certificate to a file named Client.cer.</span></span>  
  
8.  <span data-ttu-id="39190-140">在客户端计算机上的 Client.exe.config 文件中，更改终结点的地址值，使其与服务的新地址相匹配。</span><span class="sxs-lookup"><span data-stu-id="39190-140">In the Client.exe.config file on the client computer, change the address value of the endpoint to match the new address of your service.</span></span> <span data-ttu-id="39190-141">通过用服务器的完全限定域名替换 localhost 来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="39190-141">Do this by replacing localhost with the fully-qualified domain name of the server.</span></span>  <span data-ttu-id="39190-142">还必须更改服务的证书名称，使其与服务计算机的完全限定域名相同（在 `findValue` 下的 `defaultCertificate` 的 `serviceCertificate` 元素的 `clientCredentials` 属性中）。</span><span class="sxs-lookup"><span data-stu-id="39190-142">You must also change the certificate name of the service to be the same as the fully-qualified domain name of the service computer (in the `findValue` attribute in the `defaultCertificate` element of `serviceCertificate` under `clientCredentials`).</span></span>  
  
9. <span data-ttu-id="39190-143">将客户端目录中的 Client.cer 文件复制到服务器上的服务目录中。</span><span class="sxs-lookup"><span data-stu-id="39190-143">Copy the Client.cer file from the client directory to the service directory on the server.</span></span>  
  
10. <span data-ttu-id="39190-144">在客户端上，运行 `ImportServiceCert.bat`。</span><span class="sxs-lookup"><span data-stu-id="39190-144">On the client, run `ImportServiceCert.bat`.</span></span> <span data-ttu-id="39190-145">这会将 Service.cer 文件中的服务证书导入 CurrentUser – TrustedPeople 存储区。</span><span class="sxs-lookup"><span data-stu-id="39190-145">This imports the service certificate from the Service.cer file into the CurrentUser - TrustedPeople store.</span></span>  
  
11. <span data-ttu-id="39190-146">在服务器上，运行 `ImportClientCert.bat`，这会将 Client.cer 文件中的客户端证书导入 LocalMachine - TrustedPeople 存储区。</span><span class="sxs-lookup"><span data-stu-id="39190-146">On the server, run `ImportClientCert.bat`, This imports the client certificate from the Client.cer file into the LocalMachine - TrustedPeople store.</span></span>  
  
12. <span data-ttu-id="39190-147">在服务计算机上，在命令提示符下启动 Service.exe。</span><span class="sxs-lookup"><span data-stu-id="39190-147">On the service computer, launch Service.exe from the command prompt.</span></span>  
  
13. <span data-ttu-id="39190-148">在客户端计算机上，在命令提示符下启动 Client.exe。</span><span class="sxs-lookup"><span data-stu-id="39190-148">On the client computer, launch Client.exe from the command prompt.</span></span> <span data-ttu-id="39190-149">如果客户端与服务无法进行通信，请参见 [Troubleshooting Tips](http://msdn.microsoft.com/en-us/8787c877-5e96-42da-8214-fa737a38f10b)。</span><span class="sxs-lookup"><span data-stu-id="39190-149">If the client and service are not able to communicate, see [Troubleshooting Tips](http://msdn.microsoft.com/en-us/8787c877-5e96-42da-8214-fa737a38f10b).</span></span>  
  
### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="39190-150">运行示例后进行清理</span><span class="sxs-lookup"><span data-stu-id="39190-150">To clean up after the sample</span></span>  
  
-   <span data-ttu-id="39190-151">运行完示例后运行示例文件夹中的 Cleanup.bat。</span><span class="sxs-lookup"><span data-stu-id="39190-151">Run Cleanup.bat in the samples folder once you have finished running the sample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="39190-152">此脚本不会在跨计算机运行此示例时移除客户端上的服务证书。</span><span class="sxs-lookup"><span data-stu-id="39190-152">This script does not remove service certificates on a client when running this sample across computers.</span></span> <span data-ttu-id="39190-153">如果已运行跨计算机使用证书的 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 示例，请确保清除已安装在 CurrentUser - TrustedPeople 存储中的服务证书。</span><span class="sxs-lookup"><span data-stu-id="39190-153">If you have run [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] samples that use certificates across computers, be sure to clear the service certificates that have been installed in the CurrentUser - TrustedPeople store.</span></span> <span data-ttu-id="39190-154">为此，请使用以下命令：`certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>`，例如：`certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`。</span><span class="sxs-lookup"><span data-stu-id="39190-154">To do this, use the following command: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` For example: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39190-155">要求</span><span class="sxs-lookup"><span data-stu-id="39190-155">Requirements</span></span>  
 <span data-ttu-id="39190-156">此示例要求安装并运行 MSMQ。</span><span class="sxs-lookup"><span data-stu-id="39190-156">This sample requires that MSMQ is installed and running.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="39190-157">演示</span><span class="sxs-lookup"><span data-stu-id="39190-157">Demonstrates</span></span>  
 <span data-ttu-id="39190-158">客户端使用服务的公钥对消息进行加密，并使用其自己的证书对消息进行签名。</span><span class="sxs-lookup"><span data-stu-id="39190-158">The client encrypts the message using the public key of the service and signs the message using its own certificate.</span></span> <span data-ttu-id="39190-159">从队列中读取消息的服务使用其受信任人的存储区中的证书对客户端证书进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="39190-159">The service reading the message from the queue authenticates the client certificate with the certificate in its trusted people store.</span></span> <span data-ttu-id="39190-160">然后它对消息进行解密并将消息调度给服务操作。</span><span class="sxs-lookup"><span data-stu-id="39190-160">It then decrypts the message and dispatches the message to the service operation.</span></span>  
  
 <span data-ttu-id="39190-161">因为 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 消息是作为负载通过 MSMQ 消息的正文携带的，所以正文在 MSMQ 存储区中依然保持加密状态。</span><span class="sxs-lookup"><span data-stu-id="39190-161">Because the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] message is carried as a payload in the body of the MSMQ message, the body remains encrypted in the MSMQ store.</span></span> <span data-ttu-id="39190-162">这样可以保护消息，以防意外泄漏。</span><span class="sxs-lookup"><span data-stu-id="39190-162">This secures the message from unwanted disclosure of the message.</span></span> <span data-ttu-id="39190-163">请注意，MSMQ 本身并不知道它携带的消息是否经过加密。</span><span class="sxs-lookup"><span data-stu-id="39190-163">Note that MSMQ itself is not aware whether the message it is carrying is encrypted.</span></span>  
  
 <span data-ttu-id="39190-164">此示例演示如何在消息级别对 MSMQ 进行相互身份验证。</span><span class="sxs-lookup"><span data-stu-id="39190-164">The sample demonstrates how mutual authentication at the message level can be used with MSMQ.</span></span> <span data-ttu-id="39190-165">证书是在带外交换的。</span><span class="sxs-lookup"><span data-stu-id="39190-165">The certificates are exchanged out-of-band.</span></span> <span data-ttu-id="39190-166">对于排队的应用程序始终是这样，因为服务和客户端不是必须同时处于开启状态并正在运行。</span><span class="sxs-lookup"><span data-stu-id="39190-166">This is always the case with queued application because the service and the client do not have to be up and running at the same time.</span></span>  
  
## <a name="description"></a><span data-ttu-id="39190-167">描述</span><span class="sxs-lookup"><span data-stu-id="39190-167">Description</span></span>  
 <span data-ttu-id="39190-168">示例客户端和服务代码是相同[事务性 MSMQ 绑定](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md)示例有一处不同。</span><span class="sxs-lookup"><span data-stu-id="39190-168">The sample client and service code are the same as the [Transacted MSMQ Binding](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md) sample with one difference.</span></span> <span data-ttu-id="39190-169">操作协定是通过保护级别批注的，这说明消息必须是经过签名和加密的。</span><span class="sxs-lookup"><span data-stu-id="39190-169">The operation contract is annotated with protection level, which suggests that the message must be signed and encrypted.</span></span>  
  
```  
// Define a service contract.   
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface IOrderProcessor  
{  
    [OperationContract(IsOneWay = true, ProtectionLevel=ProtectionLevel.EncryptAndSign)]  
    void SubmitPurchaseOrder(PurchaseOrder po);  
}  
```  
  
 <span data-ttu-id="39190-170">为了确保使用所要求的令牌来标识服务和客户端以保证消息的安全性，App.config 中包含了凭据信息。</span><span class="sxs-lookup"><span data-stu-id="39190-170">To ensure that the message is secured using the required token to identify the service and client, the App.config contains credential information.</span></span>  
  
 <span data-ttu-id="39190-171">客户端配置指定要用来对服务进行身份验证的服务证书。</span><span class="sxs-lookup"><span data-stu-id="39190-171">The client configuration specifies the service certificate to authenticate the service.</span></span> <span data-ttu-id="39190-172">它使用其本地计算机存储区作为受信任的存储区，以依赖服务的有效性。</span><span class="sxs-lookup"><span data-stu-id="39190-172">It uses its LocalMachine store as the trusted store to rely on the validity of the service.</span></span> <span data-ttu-id="39190-173">它还指定消息所附加的用来对客户端进行服务身份验证的客户端证书。</span><span class="sxs-lookup"><span data-stu-id="39190-173">It also specifies the client certificate that is attached with the message for service authentication of the client.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  
  <system.serviceModel>  
  
    <client>  
      <!-- Define NetMsmqEndpoint -->  
      <endpoint address="net.msmq://localhost/private/ServiceModelSamplesMessageSecurity"   
                binding="netMsmqBinding"   
                bindingConfiguration="messageSecurityBinding"  
                contract="Microsoft.ServiceModel.Samples.IOrderProcessor"  
                behaviorConfiguration="ClientCertificateBehavior" />  
    </client>  
  
    <bindings>  
        <netMsmqBinding>  
            <binding name="messageSecurityBinding">  
                <security mode="Message">  
                    <message clientCredentialType="Certificate"/>  
                </security>  
            </binding>  
        </netMsmqBinding>  
    </bindings>  
  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="ClientCertificateBehavior">  
          <!--   
        The clientCredentials behavior allows one to define a certificate to present to a service.  
        A certificate is used by a client to authenticate itself to the service and provide message integrity.  
        This configuration references the "client.com" certificate installed during the setup instructions.  
        -->  
          <clientCredentials>  
            <clientCertificate findValue="client.com" storeLocation="CurrentUser" storeName="My" x509FindType="FindBySubjectName" />  
            <serviceCertificate>  
                <defaultCertificate findValue="localhost" storeLocation="CurrentUser" storeName="TrustedPeople" x509FindType="FindBySubjectName"/>  
              <!--   
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate   
            is in the user's Trusted People store, then it is trusted without performing a  
            validation of the certificate's issuer chain. This setting is used here for convenience so that the   
            sample can be run without having to have certificates issued by a certification authority (CA).  
            This setting is less secure than the default, ChainTrust. The security implications of this   
            setting should be carefully considered before using PeerOrChainTrust in production code.   
            -->  
              <authentication certificateValidationMode="PeerOrChainTrust" />  
            </serviceCertificate>  
          </clientCredentials>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="39190-174">请注意，安全模式设置为“消息”，而 ClientCredentialType 设置为“证书”。</span><span class="sxs-lookup"><span data-stu-id="39190-174">Note that the security mode is set to Message and the ClientCredentialType is set to Certificate.</span></span>  
  
 <span data-ttu-id="39190-175">服务配置中包括一个服务行为，该行为指定客户端对服务进行身份验证时使用的服务的凭据。</span><span class="sxs-lookup"><span data-stu-id="39190-175">The service configuration includes a service behavior that specifies the service's credentials that are used when the client authenticates the service.</span></span> <span data-ttu-id="39190-176">中指定的服务器证书使用者名称`findValue`属性中[ \<serviceCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)。</span><span class="sxs-lookup"><span data-stu-id="39190-176">The server certificate subject name is specified in the `findValue` attribute in the [\<serviceCredentials>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md).</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  
  <appSettings>  
    <!-- Use appSetting to configure MSMQ queue name. -->  
    <add key="queueName" value=".\private$\ServiceModelSamplesMessageSecurity" />  
  </appSettings>  
  
  <system.serviceModel>  
    <services>  
      <service   
          name="Microsoft.ServiceModel.Samples.OrderProcessorService"  
          behaviorConfiguration="PurchaseOrderServiceBehavior">  
        <host>  
          <baseAddresses>  
            <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
          </baseAddresses>  
        </host>  
        <!-- Define NetMsmqEndpoint -->  
        <endpoint address="net.msmq://localhost/private/ServiceModelSamplesMessageSecurity"  
                  binding="netMsmqBinding"  
                  bindingConfiguration="messageSecurityBinding"  
                  contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />  
        <!-- The mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex. -->  
        <endpoint address="mex"  
                  binding="mexHttpBinding"  
                  contract="IMetadataExchange" />  
      </service>  
    </services>  
  
    <bindings>  
        <netMsmqBinding>  
            <binding name="messageSecurityBinding">  
                <security mode="Message">  
                    <message clientCredentialType="Certificate" />  
                </security>  
            </binding>  
        </netMsmqBinding>  
    </bindings>  
  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="PurchaseOrderServiceBehavior">  
          <serviceMetadata httpGetEnabled="True"/>  
          <!--   
               The serviceCredentials behavior allows one to define a service certificate.  
               A service certificate is used by the service to authenticate itself to its clients and to provide message protection.  
               This configuration references the "localhost" certificate installed during the setup instructions.  
          -->  
          <serviceCredentials>  
            <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />  
            <clientCertificate>  
                <certificate findValue="client.com" storeLocation="LocalMachine" storeName="TrustedPeople" x509FindType="FindBySubjectName"/>  
              <!--   
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate   
            is in the user's Trusted People store, then it is trusted without performing a  
            validation of the certificate's issuer chain. This setting is used here for convenience so that the   
            sample can be run without having to have certificates issued by a certification authority (CA).  
            This setting is less secure than the default, ChainTrust. The security implications of this   
            setting should be carefully considered before using PeerOrChainTrust in production code.   
            -->  
              <authentication certificateValidationMode="PeerOrChainTrust" />  
            </clientCertificate>  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  
  </system.serviceModel>  
  
</configuration>  
```  
  
 <span data-ttu-id="39190-177">此示例演示如何使用配置控制身份验证，以及如何从安全上下文中获取调用方的标识，如下面的示例代码所述：</span><span class="sxs-lookup"><span data-stu-id="39190-177">The sample demonstrates controlling authentication using configuration, and how to obtain the caller’s identity from the security context, as shown in the following sample code:</span></span>  
  
```  
    // Service class which implements the service contract.  
    // Added code to write output to the console window.  
    public class OrderProcessorService : IOrderProcessor  
    {  
        private string GetCallerIdentity()  
        {  
            // The client certificate is not mapped to a Windows identity by default.  
            // ServiceSecurityContext.PrimaryIdentity is populated based on the information  
            // in the certificate that the client used to authenticate itself to the service.  
            return ServiceSecurityContext.Current.PrimaryIdentity.Name;  
        }  
  
        [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]  
        public void SubmitPurchaseOrder(PurchaseOrder po)  
        {  
            Console.WriteLine("Client's Identity {0} ", GetCallerIdentity());  
            Orders.Add(po);  
            Console.WriteLine("Processing {0} ", po);  
        }  
  //…  
}  
```  
  
 <span data-ttu-id="39190-178">运行时，服务代码将显示客户端标识。</span><span class="sxs-lookup"><span data-stu-id="39190-178">When run, the service code displays the client identification.</span></span> <span data-ttu-id="39190-179">下面提供了服务代码的示例输出：</span><span class="sxs-lookup"><span data-stu-id="39190-179">The following is a sample output from the service code:</span></span>  
  
```  
The service is ready.  
Press <ENTER> to terminate service.  
  
Client's Identity CN=client.com; ECA6629A3C695D01832D77EEE836E04891DE9D3C  
Processing Purchase Order: 6536e097-da96-4773-9da3-77bab4345b5d  
        Customer: somecustomer.com  
        OrderDetails  
                Order LineItem: 54 of Blue Widget @unit price: $29.99  
                Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $42461.56  
        Order status: Pending  
```  
  
## <a name="comments"></a><span data-ttu-id="39190-180">注释</span><span class="sxs-lookup"><span data-stu-id="39190-180">Comments</span></span>  
  
-   <span data-ttu-id="39190-181">创建客户端证书。</span><span class="sxs-lookup"><span data-stu-id="39190-181">Creating the client certificate.</span></span>  
  
     <span data-ttu-id="39190-182">批处理文件中的以下行用于创建客户端证书。</span><span class="sxs-lookup"><span data-stu-id="39190-182">The following line in the batch file creates the client certificate.</span></span> <span data-ttu-id="39190-183">创建的证书的主题名称中会使用指定的客户端名称。</span><span class="sxs-lookup"><span data-stu-id="39190-183">The client name specified is used in the subject name of the certificate created.</span></span> <span data-ttu-id="39190-184">证书存储在 `My` 存储位置下的 `CurrentUser` 存储区中。</span><span class="sxs-lookup"><span data-stu-id="39190-184">The certificate is stored in `My` store at the `CurrentUser` store location.</span></span>  
  
    ```  
    echo ************  
    echo making client cert  
    echo ************  
    makecert.exe -sr CurrentUser -ss MY -a sha1 -n CN=%CLIENT_NAME% -sky exchange -pe  
    ```  
  
-   <span data-ttu-id="39190-185">将客户端证书安装到服务器的受信任证书存储区中。</span><span class="sxs-lookup"><span data-stu-id="39190-185">Installing the client certificate into server’s trusted certificate store.</span></span>  
  
     <span data-ttu-id="39190-186">批处理文件中的以下行将客户端证书复制到服务器的 TrustedPeople 存储中，以使服务器能够做出相关的信任或不信任决定。</span><span class="sxs-lookup"><span data-stu-id="39190-186">The following line in the batch file copies the client certificate into the server's TrustedPeople store so that the server can make the relevant trust or no-trust decisions.</span></span> <span data-ttu-id="39190-187">为了使 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 服务信任安装在 TrustedPeople 存储区中的证书，必须将客户端证书验证模式设置为 `PeerOrChainTrust` 或 `PeerTrust` 值。</span><span class="sxs-lookup"><span data-stu-id="39190-187">For a certificate installed in the TrustedPeople store to be trusted by a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service, the client certificate validation mode must be set to `PeerOrChainTrust` or `PeerTrust` value.</span></span> <span data-ttu-id="39190-188">请参见前面的服务配置示例，了解如何使用配置文件完成此操作。</span><span class="sxs-lookup"><span data-stu-id="39190-188">See the previous service configuration sample to learn how this can be done using a configuration file.</span></span>  
  
    ```  
    echo ************  
    echo copying client cert to server's LocalMachine store  
    echo ************  
    certmgr.exe -add -r CurrentUser -s My -c -n %CLIENT_NAME% -r LocalMachine -s TrustedPeople  
    ```  
  
-   <span data-ttu-id="39190-189">创建服务器证书。</span><span class="sxs-lookup"><span data-stu-id="39190-189">Creating the server certificate.</span></span>  
  
     <span data-ttu-id="39190-190">Setup.bat 批处理文件中的以下行创建将要使用的服务器证书：</span><span class="sxs-lookup"><span data-stu-id="39190-190">The following lines from the Setup.bat batch file create the server certificate to be used:</span></span>  
  
    ```  
    echo ************  
    echo Server cert setup starting  
    echo %SERVER_NAME%  
    echo ************  
    echo making server cert  
    echo ************  
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe  
    ```  
  
     <span data-ttu-id="39190-191">%SERVER_NAME% 变量指定服务器名称。</span><span class="sxs-lookup"><span data-stu-id="39190-191">The %SERVER_NAME% variable specifies the server name.</span></span> <span data-ttu-id="39190-192">该证书存储在 LocalMachine 存储区中。</span><span class="sxs-lookup"><span data-stu-id="39190-192">The certificate is stored in the LocalMachine store.</span></span> <span data-ttu-id="39190-193">如果用服务自变量运行 setup 批处理文件 (如， `setup.bat service`) %server_name%包含计算机的完全限定域名。否则，它默认为 localhost</span><span class="sxs-lookup"><span data-stu-id="39190-193">If the setup batch file is run with an argument of service (such as, `setup.bat service`) the %SERVER_NAME% contains the fully-qualified domain name of the computer.Otherwise it defaults to localhost</span></span>  
  
-   <span data-ttu-id="39190-194">将服务器证书安装到客户端的受信任证书存储区中。</span><span class="sxs-lookup"><span data-stu-id="39190-194">Installing server certificate into the client’s trusted certificate store.</span></span>  
  
     <span data-ttu-id="39190-195">以下行将服务器证书复制到客户端的受信任人存储中。</span><span class="sxs-lookup"><span data-stu-id="39190-195">The following line copies the server certificate into the client trusted people store.</span></span> <span data-ttu-id="39190-196">因为客户端系统不隐式信任 Makecert.exe 生成的证书，所以需要执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="39190-196">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="39190-197">如果已经拥有一个证书，该证书来源于客户端的受信任根证书（例如由 Microsoft 颁发的证书），则不需要执行使用服务器证书填充客户端证书存储区这一步骤。</span><span class="sxs-lookup"><span data-stu-id="39190-197">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft-issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>  
  
    ```  
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="39190-198">如果您使用的是非美国英文版本的 Microsoft Windows，则必须编辑 Setup.bat 文件，并用与您所在的区域对应的帐户名称替换“NT AUTHORITY\NETWORK SERVICE”帐户名称。</span><span class="sxs-lookup"><span data-stu-id="39190-198">If you are using a non-U.S. English edition of Microsoft Windows you must edit the Setup.bat file and replace the "NT AUTHORITY\NETWORK SERVICE" account name with your regional equivalent.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="39190-199">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="39190-199">The samples may already be installed on your computer.</span></span> <span data-ttu-id="39190-200">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="39190-200">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="39190-201">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="39190-201">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="39190-202">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="39190-202">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\MessageSecurity`  
  
## <a name="see-also"></a><span data-ttu-id="39190-203">另请参阅</span><span class="sxs-lookup"><span data-stu-id="39190-203">See Also</span></span>
