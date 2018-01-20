---
title: "消息安全证书"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: WS Security
ms.assetid: 909333b3-35ec-48f0-baff-9a50161896f6
caps.latest.revision: "51"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 9339258c4f5df606db9126c8b4b886b0a26029a6
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="message-security-certificate"></a><span data-ttu-id="65d37-102">消息安全证书</span><span class="sxs-lookup"><span data-stu-id="65d37-102">Message Security Certificate</span></span>
<span data-ttu-id="65d37-103">此示例演示如何实现一个应用程序，该应用程序对客户端使用 WS 安全性和 X.509 v3 证书身份验证，并要求使用服务器的 X.509 v3 证书进行服务器身份验证。</span><span class="sxs-lookup"><span data-stu-id="65d37-103">This sample demonstrates how to implement an application that uses WS-Security with X.509 v3 certificate authentication for the client and requires server authentication using the server's X.509 v3 certificate.</span></span> <span data-ttu-id="65d37-104">此示例使用默认设置，以便客户端和服务器之间的所有应用程序消息都经过签名和加密。</span><span class="sxs-lookup"><span data-stu-id="65d37-104">This sample uses default settings such that all application messages between the client and server are signed and encrypted.</span></span> <span data-ttu-id="65d37-105">此示例基于[WSHttpBinding](../../../../docs/framework/wcf/samples/wshttpbinding.md)和客户端控制台程序和由 Internet 信息服务 (IIS) 承载的服务库组成。</span><span class="sxs-lookup"><span data-stu-id="65d37-105">This sample is based on the [WSHttpBinding](../../../../docs/framework/wcf/samples/wshttpbinding.md) and consists of a client console program and a service library hosted by Internet Information Services (IIS).</span></span> <span data-ttu-id="65d37-106">该服务实现定义“请求-答复”通信模式的协定。</span><span class="sxs-lookup"><span data-stu-id="65d37-106">The service implements a contract that defines a request-reply communication pattern.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="65d37-107">本主题的最后介绍了此示例的设置过程和生成说明。</span><span class="sxs-lookup"><span data-stu-id="65d37-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="65d37-108">此示例演示如何使用配置来控制身份验证，以及如何从安全上下文中获取调用方的标识，如下面的示例代码所述。</span><span class="sxs-lookup"><span data-stu-id="65d37-108">The sample demonstrates controlling authentication by using configuration and how to obtain the caller’s identity from the security context, as shown in the following sample code.</span></span>  
  
```  
public class CalculatorService : ICalculator  
{  
    public string GetCallerIdentity()  
    {  
        // The client certificate is not mapped to a Windows identity by default.  
        // ServiceSecurityContext.PrimaryIdentity is populated based on the information  
        // in the certificate that the client used to authenticate itself to the service.  
        return ServiceSecurityContext.Current.PrimaryIdentity.Name;  
    }  
    ...  
}  
```  
  
 <span data-ttu-id="65d37-109">服务公开两个终结点，一个用来与使用配置文件 (Web.config) 定义的服务进行通信，另一个用来使用 WS-MetadataExchange 协议来公开服务的 WSDL 文档。</span><span class="sxs-lookup"><span data-stu-id="65d37-109">The service exposes one endpoint for communicating with the service and one endpoint for exposing the service's WSDL document using the WS-MetadataExchange protocol, defined by using the configuration file (Web.config).</span></span> <span data-ttu-id="65d37-110">终结点由地址、绑定和协定组成。</span><span class="sxs-lookup"><span data-stu-id="65d37-110">The endpoint consists of an address, a binding, and a contract.</span></span> <span data-ttu-id="65d37-111">绑定配置的标准[ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)元素，它默认为使用消息安全。</span><span class="sxs-lookup"><span data-stu-id="65d37-111">The binding is configured with a standard [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) element, which defaults to using message security.</span></span> <span data-ttu-id="65d37-112">此示例将 `clientCredentialType` 属性设置为 Certificate 以要求进行客户端身份验证。</span><span class="sxs-lookup"><span data-stu-id="65d37-112">This sample sets the `clientCredentialType` attribute to Certificate to require client authentication.</span></span>  
  
```xml  
<system.serviceModel>  
    <protocolMapping>  
      <add scheme="http" binding="wsHttpBinding"/>  
    </protocolMapping>  
    <bindings>  
      <wsHttpBinding>  
        <!--   
        This configuration defines the security mode as Message and   
        the clientCredentialType as Certificate.  
        -->  
        <binding>  
          <security mode ="Message">  
            <message clientCredentialType="Certificate" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceDebug includeExceptionDetailInFaults="False" />  
          <!--   
        The serviceCredentials behavior allows one to define a service certificate.  
        A service certificate is used by the service to authenticate itself to its clients and to provide message protection.  
        This configuration references the "localhost" certificate installed during the setup instructions.  
        -->  
          <serviceCredentials>  
            <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />  
            <clientCertificate>  
              <!--   
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate   
            is in the user's Trusted People store, then it will be trusted without performing a  
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
```  
  
 <span data-ttu-id="65d37-113">此行为指定在客户端向服务进行身份验证时使用服务凭据。</span><span class="sxs-lookup"><span data-stu-id="65d37-113">The behavior specifies the service's credentials that are used when the client authenticates the service.</span></span> <span data-ttu-id="65d37-114">中指定的服务器证书使用者名称`findValue`属性中[ \<serviceCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)元素。</span><span class="sxs-lookup"><span data-stu-id="65d37-114">The server certificate subject name is specified in the `findValue` attribute in the [\<serviceCredentials>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) element.</span></span>  
  
```xml  
<!--For debugging purposes, set the includeExceptionDetailInFaults attribute to true.-->  
<behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceDebug includeExceptionDetailInFaults="False" />  
          <!--   
        The serviceCredentials behavior allows one to define a service certificate.  
        A service certificate is used by the service to authenticate itself to its clients and to provide message protection.  
        This configuration references the "localhost" certificate installed during the setup instructions.  
        -->  
          <serviceCredentials>  
            <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />  
            <clientCertificate>  
              <!--   
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate   
            is in the user's Trusted People store, then it will be trusted without performing a  
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
```  
  
 <span data-ttu-id="65d37-115">客户端终结点配置由服务终结点的绝对地址、绑定和协定组成。</span><span class="sxs-lookup"><span data-stu-id="65d37-115">The client endpoint configuration consists of an absolute address for the service endpoint, the binding, and the contract.</span></span> <span data-ttu-id="65d37-116">客户端绑定是用相应的安全模式和身份验证模式配置的。</span><span class="sxs-lookup"><span data-stu-id="65d37-116">The client binding is configured with the appropriate security mode and authentication mode.</span></span> <span data-ttu-id="65d37-117">在跨计算机方案中运行时，请确保相应地更改服务终结点地址。</span><span class="sxs-lookup"><span data-stu-id="65d37-117">When running in a cross-computer scenario, ensure that the service endpoint address is changed accordingly.</span></span>  
  
```xml  
<system.serviceModel>  
    <client>  
      <!-- Use a behavior to configure the client certificate to present to the service. -->  
      <endpoint address="http://localhost/servicemodelsamples/service.svc" binding="wsHttpBinding" bindingConfiguration="Binding1" behaviorConfiguration="ClientCertificateBehavior" contract="Microsoft.Samples.Certificate.ICalculator"/>  
    </client>  
  
    <bindings>  
      <wsHttpBinding>  
        <!--   
        This configuration defines the security mode as Message and   
        the clientCredentialType as Certificate.  
        -->  
        <binding name="Binding1">  
          <security mode="Message">  
            <message clientCredentialType="Certificate"/>  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
...  
</system.serviceModel>  
```  
  
 <span data-ttu-id="65d37-118">客户端实现可以通过配置文件或通过代码来设置要使用的证书。</span><span class="sxs-lookup"><span data-stu-id="65d37-118">The client implementation can set the certificate to use, either through the configuration file or through code.</span></span> <span data-ttu-id="65d37-119">下面的示例演示如何设置要在配置文件中使用的证书。</span><span class="sxs-lookup"><span data-stu-id="65d37-119">The following sample shows how to set the certificate to use in the configuration file.</span></span>  
  
```xml  
<system.serviceModel>  
  ...  
  
<behaviors>  
      <endpointBehaviors>  
        <behavior name="ClientCertificateBehavior">  
          <!--   
        The clientCredentials behavior allows one to define a certificate to present to a service.  
        A certificate is used by a client to authenticate itself to the service and provide message integrity.  
        This configuration references the "client.com" certificate installed during the setup instructions.  
        -->  
          <clientCredentials>  
            <clientCertificate findValue="client.com" storeLocation="CurrentUser" storeName="My" x509FindType="FindBySubjectName"/>  
            <serviceCertificate>  
              <!--   
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate   
            is in the user's Trusted People store, then it will be trusted without performing a  
            validation of the certificate's issuer chain. This setting is used here for convenience so that the   
            sample can be run without having to have certificates issued by a certificate authority (CA).  
            This setting is less secure than the default, ChainTrust. The security implications of this   
            setting should be carefully considered before using PeerOrChainTrust in production code.   
            -->  
              <authentication certificateValidationMode="PeerOrChainTrust"/>  
            </serviceCertificate>  
          </clientCredentials>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
  
</system.serviceModel>  
```  
  
 <span data-ttu-id="65d37-120">下面的示例演示如何在程序中调用服务。</span><span class="sxs-lookup"><span data-stu-id="65d37-120">The following sample shows how to call the service in your program.</span></span>  
  
```  
// Create a client.  
CalculatorClient client = new CalculatorClient();  
  
// Call the GetCallerIdentity service operation.  
Console.WriteLine(client.GetCallerIdentity());  
...  
//Closing the client gracefully closes the connection and cleans up resources.  
client.Close();  
```  
  
 <span data-ttu-id="65d37-121">运行示例时，操作请求和响应将显示在客户端控制台窗口中。</span><span class="sxs-lookup"><span data-stu-id="65d37-121">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="65d37-122">在客户端窗口中按 Enter 可以关闭客户端。</span><span class="sxs-lookup"><span data-stu-id="65d37-122">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
CN=client.com  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="65d37-123">通过运行消息安全示例随附的 Setup.bat 批处理文件，可以用相关的证书将客户端和服务器配置为运行承载应用程序，该应用程序需要基于证书的安全性。</span><span class="sxs-lookup"><span data-stu-id="65d37-123">The Setup.bat batch file included with the Message Security samples enables you to configure the client and server with relevant certificates to run a hosted application that requires certificate-based security.</span></span> <span data-ttu-id="65d37-124">该批处理文件可以在三个模式下运行。</span><span class="sxs-lookup"><span data-stu-id="65d37-124">The batch file can be run in three modes.</span></span> <span data-ttu-id="65d37-125">若要在单计算机模式下类型中运行**setup.bat**在 Visual Studio 命令提示符; 服务模式类型**setup.bat service**; 以及客户端模式类型**setup.bat client**.</span><span class="sxs-lookup"><span data-stu-id="65d37-125">To run in single-computer mode type **setup.bat** in a Visual Studio Command Prompt ; for service mode type **setup.bat service**; and for client mode type **setup.bat client**.</span></span> <span data-ttu-id="65d37-126">在跨计算机运行示例时，可以使用客户端模式和服务器模式。</span><span class="sxs-lookup"><span data-stu-id="65d37-126">Use the client and server mode when running the sample across computers.</span></span> <span data-ttu-id="65d37-127">有关详细信息，请参见本主题末尾的设置过程。</span><span class="sxs-lookup"><span data-stu-id="65d37-127">See the setup procedure at the end of this topic for details.</span></span> <span data-ttu-id="65d37-128">下面提供了批处理文件不同节的简要概述，您可以修改这些批处理文件，使其能够在相应的配置中运行：</span><span class="sxs-lookup"><span data-stu-id="65d37-128">The following provides a brief overview of the different sections of the batch files so that they can be modified to run in appropriate configuration:</span></span>  
  
-   <span data-ttu-id="65d37-129">创建客户端证书。</span><span class="sxs-lookup"><span data-stu-id="65d37-129">Creating the client certificate.</span></span>  
  
     <span data-ttu-id="65d37-130">批处理文件中的以下行用于创建客户端证书。</span><span class="sxs-lookup"><span data-stu-id="65d37-130">The following line in the batch file creates the client certificate.</span></span> <span data-ttu-id="65d37-131">创建的证书的主题名称中会使用指定的客户端名称。</span><span class="sxs-lookup"><span data-stu-id="65d37-131">The client name specified is used in the subject name of the certificate created.</span></span> <span data-ttu-id="65d37-132">证书存储在 `My` 存储位置下的 `CurrentUser` 存储区中。</span><span class="sxs-lookup"><span data-stu-id="65d37-132">The certificate is stored in `My` store at the `CurrentUser` store location.</span></span>  
  
    ```  
    echo ************  
    echo making client cert  
    echo ************  
    makecert.exe -sr CurrentUser -ss MY -a sha1 -n CN=%CLIENT_NAME% -sky exchange -pe  
    ```  
  
-   <span data-ttu-id="65d37-133">将客户端证书安装到服务器的受信任证书存储区中。</span><span class="sxs-lookup"><span data-stu-id="65d37-133">Installing the client certificate into the server’s trusted certificate store.</span></span>  
  
     <span data-ttu-id="65d37-134">批处理文件中的以下行将客户端证书复制到服务器的 TrustedPeople 存储中，以使服务器能够做出相关的信任或不信任决定。</span><span class="sxs-lookup"><span data-stu-id="65d37-134">The following line in the batch file copies the client certificate into the server's TrustedPeople store so that the server can make the relevant trust or no-trust decisions.</span></span> <span data-ttu-id="65d37-135">为了使安装在 TrustedPeople 存储中的证书能够被 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 服务信任，必须将客户端证书验证模式设置为 `PeerOrChainTrust` 或 `PeerTrust`。</span><span class="sxs-lookup"><span data-stu-id="65d37-135">In order for a certificate installed in the TrustedPeople store to be trusted by a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service, the client certificate validation mode must be set to `PeerOrChainTrust` or `PeerTrust`.</span></span> <span data-ttu-id="65d37-136">请参见前面的服务配置示例，了解如何使用配置文件完成此操作。</span><span class="sxs-lookup"><span data-stu-id="65d37-136">See the previous service configuration sample to learn how this can be done by using a configuration file.</span></span>  
  
    ```  
    echo ************  
    echo copying client cert to server's LocalMachine store  
    echo ************  
    certmgr.exe -add -r CurrentUser -s My -c -n %CLIENT_NAME% -r LocalMachine -s TrustedPeople   
    ```  
  
-   <span data-ttu-id="65d37-137">创建服务器证书。</span><span class="sxs-lookup"><span data-stu-id="65d37-137">Creating the server certificate.</span></span>  
  
     <span data-ttu-id="65d37-138">Setup.bat 批处理文件中的以下行创建将要使用的服务器证书。</span><span class="sxs-lookup"><span data-stu-id="65d37-138">The following lines from the Setup.bat batch file create the server certificate to be used.</span></span>  
  
    ```  
    echo ************  
    echo Server cert setup starting  
    echo %SERVER_NAME%  
    echo ************  
    echo making server cert  
    echo ************  
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe  
    ```  
  
     <span data-ttu-id="65d37-139">%SERVER_NAME% 变量指定服务器名称。</span><span class="sxs-lookup"><span data-stu-id="65d37-139">The %SERVER_NAME% variable specifies the server name.</span></span> <span data-ttu-id="65d37-140">该证书存储在 LocalMachine 存储区中。</span><span class="sxs-lookup"><span data-stu-id="65d37-140">The certificate is stored in the LocalMachine store.</span></span> <span data-ttu-id="65d37-141">如果用服务自变量运行 Setup.bat 批处理文件 (如， **setup.bat service**) %server_name%包含计算机的完全限定域名。</span><span class="sxs-lookup"><span data-stu-id="65d37-141">If the Setup.bat batch file is run with an argument of service (such as, **setup.bat service**) the %SERVER_NAME% contains the fully-qualified domain name of the computer.</span></span> <span data-ttu-id="65d37-142">否则，它默认为 localhost。</span><span class="sxs-lookup"><span data-stu-id="65d37-142">Otherwise it defaults to localhost.</span></span>  
  
-   <span data-ttu-id="65d37-143">将服务器证书安装到客户端的受信任证书存储区中。</span><span class="sxs-lookup"><span data-stu-id="65d37-143">Installing the server certificate into the client’s trusted certificate store.</span></span>  
  
     <span data-ttu-id="65d37-144">以下行将服务器证书复制到客户端的受信任人存储中。</span><span class="sxs-lookup"><span data-stu-id="65d37-144">The following line copies the server certificate into the client trusted people store.</span></span> <span data-ttu-id="65d37-145">因为客户端系统不隐式信任 Makecert.exe 生成的证书，所以需要执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="65d37-145">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="65d37-146">如果已经拥有一个证书，该证书来源于客户端的受信任根证书（例如由 Microsoft 颁发的证书），则不需要执行使用服务器证书填充客户端证书存储区这一步骤。</span><span class="sxs-lookup"><span data-stu-id="65d37-146">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft-issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>  
  
    ```  
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople  
    ```  
  
-   <span data-ttu-id="65d37-147">授予对证书私钥的权限。</span><span class="sxs-lookup"><span data-stu-id="65d37-147">Granting permissions on the certificate's private key.</span></span>  
  
     <span data-ttu-id="65d37-148">Setup.bat 文件中的以下行使存储在 LocalMachine 存储中的服务器证书可以供 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 工作进程帐户访问。</span><span class="sxs-lookup"><span data-stu-id="65d37-148">The following lines in the Setup.bat file make the server certificate stored in the LocalMachine store accessible to the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] worker process account.</span></span>  
  
    ```  
    echo ************  
    echo setting privileges on server certificates  
    echo ************  
    for /F "delims=" %%i in ('"%ProgramFiles%\ServiceModelSampleTools\FindPrivateKey.exe" My LocalMachine -n CN^=%SERVER_NAME% -a') do set PRIVATE_KEY_FILE=%%i  
    set WP_ACCOUNT=NT AUTHORITY\NETWORK SERVICE  
    (ver | findstr /C:"5.1") && set WP_ACCOUNT=%COMPUTERNAME%\ASPNET  
    echo Y|cacls.exe "%PRIVATE_KEY_FILE%" /E /G "%WP_ACCOUNT%":R  
    iisreset  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="65d37-149">如果您使用的是非美国英文版本的 Windows，则必须编辑 Setup.bat 文件，并用与您所在的区域对应的帐户名称替换“NT AUTHORITY\NETWORK SERVICE”帐户名称。</span><span class="sxs-lookup"><span data-stu-id="65d37-149">If you are using a non-U.S. English edition of Windows, you must edit the Setup.bat file and replace the "NT AUTHORITY\NETWORK SERVICE" account name with your regional equivalent.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="65d37-150">该批处理文件中使用的工具位于 C:\Program Files\Microsoft Visual Studio 8\Common7\tools 或 C:\Program Files\Microsoft SDKs\Windows\v6.0\bin 中。</span><span class="sxs-lookup"><span data-stu-id="65d37-150">The tools used in this batch file are located in either C:\Program Files\Microsoft Visual Studio 8\Common7\tools or C:\Program Files\Microsoft SDKs\Windows\v6.0\bin.</span></span> <span data-ttu-id="65d37-151">这两个目录中必须有一个位于系统路径中。</span><span class="sxs-lookup"><span data-stu-id="65d37-151">One of these directories must be in your system path.</span></span> <span data-ttu-id="65d37-152">如果您安装了 Visual Studio，则在您的路径中进入该目录的最简便方法就是打开 Visual Studio 命令提示。</span><span class="sxs-lookup"><span data-stu-id="65d37-152">If you have Visual Studio installed, the easiest way to get this directory in your path is to open the Visual Studio Command Prompt.</span></span> <span data-ttu-id="65d37-153">单击**启动**，然后选择**所有程序**， **Visual Studio 2012**，**工具**。</span><span class="sxs-lookup"><span data-stu-id="65d37-153">Click **Start**, and then select **All Programs**, **Visual Studio 2012**, **Tools**.</span></span> <span data-ttu-id="65d37-154">此命令提示中已经配置了相应的路径。</span><span class="sxs-lookup"><span data-stu-id="65d37-154">This command prompt has the appropriate paths already configured.</span></span> <span data-ttu-id="65d37-155">否则，您必须向路径中手动添加相应的目录。</span><span class="sxs-lookup"><span data-stu-id="65d37-155">Otherwise you must add the appropriate directory to your path manually.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="65d37-156">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="65d37-156">The samples may already be installed on your computer.</span></span> <span data-ttu-id="65d37-157">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="65d37-157">Check for the following (default) directory before continuing:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="65d37-158">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="65d37-158">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="65d37-159">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="65d37-159">This sample is located in the following directory:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\MessageSecurity`  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="65d37-160">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="65d37-160">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="65d37-161">确保已执行[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="65d37-161">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="65d37-162">若要生成 C# 或 Visual Basic .NET 版本的解决方案，请按照 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="65d37-162">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="65d37-163">在同一计算机上运行示例</span><span class="sxs-lookup"><span data-stu-id="65d37-163">To run the sample on the same computer</span></span>  
  
1.  <span data-ttu-id="65d37-164">使用管理员权限打开 Visual Studio 命令提示符，并从示例安装文件夹运行 Setup.bat。</span><span class="sxs-lookup"><span data-stu-id="65d37-164">Open a Visual Studio Command Prompt  with administrator privileges and run Setup.bat from the sample install folder.</span></span> <span data-ttu-id="65d37-165">这将安装运行示例所需的所有证书。</span><span class="sxs-lookup"><span data-stu-id="65d37-165">This installs all the certificates required for running the sample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="65d37-166">Setup.bat 批处理文件设计为通过 Visual Studio 命令提示符运行。</span><span class="sxs-lookup"><span data-stu-id="65d37-166">The Setup.bat batch file is designed to be run from a Visual Studio Command Prompt .</span></span> <span data-ttu-id="65d37-167">这要求路径环境变量指向 SDK 的安装目录。</span><span class="sxs-lookup"><span data-stu-id="65d37-167">It requires that the path environment variable point to the directory where the SDK is installed.</span></span> <span data-ttu-id="65d37-168">将在 Visual Studio 命令提示符 (2010) 中自动设置此环境变量。</span><span class="sxs-lookup"><span data-stu-id="65d37-168">This environment variable is automatically set within a Visual Studio Command Prompt (2010).</span></span>  
  
2.  <span data-ttu-id="65d37-169">验证是否可以通过输入地址使用浏览器的服务访问`http://localhost/servicemodelsamples/service.svc`。</span><span class="sxs-lookup"><span data-stu-id="65d37-169">Verify access to the service using a browser by entering the address `http://localhost/servicemodelsamples/service.svc`.</span></span>  
  
3.  <span data-ttu-id="65d37-170">启动 \client\bin 中的 Client.exe。</span><span class="sxs-lookup"><span data-stu-id="65d37-170">Launch Client.exe from \client\bin.</span></span> <span data-ttu-id="65d37-171">客户端活动将显示在客户端控制台应用程序上。</span><span class="sxs-lookup"><span data-stu-id="65d37-171">Client activity is displayed on the client console application.</span></span>  
  
4.  <span data-ttu-id="65d37-172">如果客户端和服务不能够进行通信，请参阅[疑难解答提示](http://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b)。</span><span class="sxs-lookup"><span data-stu-id="65d37-172">If the client and service are not able to communicate, see [Troubleshooting Tips](http://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b).</span></span>  
  
### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="65d37-173">跨计算机运行示例</span><span class="sxs-lookup"><span data-stu-id="65d37-173">To run the sample across computers</span></span>  
  
1.  <span data-ttu-id="65d37-174">在服务计算机上创建目录。</span><span class="sxs-lookup"><span data-stu-id="65d37-174">Create a directory on the service computer.</span></span> <span data-ttu-id="65d37-175">使用 Internet Information Services (IIS) 管理工具为此目录创建名为 servicemodelsamples 的虚拟应用程序。</span><span class="sxs-lookup"><span data-stu-id="65d37-175">Create a virtual application named servicemodelsamples for this directory by using the Internet Information Services (IIS) management tool.</span></span>  
  
2.  <span data-ttu-id="65d37-176">将服务程序文件从 \inetpub\wwwroot\servicemodelsamples 复制到服务计算机上的虚拟目录中。</span><span class="sxs-lookup"><span data-stu-id="65d37-176">Copy the service program files from \inetpub\wwwroot\servicemodelsamples to the virtual directory on the service computer.</span></span> <span data-ttu-id="65d37-177">确保复制 \bin 子目录中的文件。</span><span class="sxs-lookup"><span data-stu-id="65d37-177">Ensure that you copy the files in the \bin subdirectory.</span></span> <span data-ttu-id="65d37-178">另外，将 Setup.bat、Cleanup.bat 和 ImportClientCert.bat 文件复制到服务计算机上。</span><span class="sxs-lookup"><span data-stu-id="65d37-178">Also copy the Setup.bat, Cleanup.bat, and ImportClientCert.bat files to the service computer.</span></span>  
  
3.  <span data-ttu-id="65d37-179">在客户端计算机上为这些客户端二进制文件创建一个目录。</span><span class="sxs-lookup"><span data-stu-id="65d37-179">Create a directory on the client computer for the client binaries.</span></span>  
  
4.  <span data-ttu-id="65d37-180">将客户端程序文件复制到客户端计算机上的客户端目录中。</span><span class="sxs-lookup"><span data-stu-id="65d37-180">Copy the client program files to the client directory on the client computer.</span></span> <span data-ttu-id="65d37-181">另外，将 Setup.bat、Cleanup.bat 和 ImportServiceCert.bat 文件复制到客户端上。</span><span class="sxs-lookup"><span data-stu-id="65d37-181">Also copy the Setup.bat, Cleanup.bat, and ImportServiceCert.bat files to the client.</span></span>  
  
5.  <span data-ttu-id="65d37-182">在服务器上，运行**setup.bat service**使用管理员特权的 Visual Studio 命令提示中。</span><span class="sxs-lookup"><span data-stu-id="65d37-182">On the server, run **setup.bat service** in a Visual Studio command prompt with administrator privileges.</span></span> <span data-ttu-id="65d37-183">运行**setup.bat**与**服务**自变量的计算机的完全限定域名创建一个服务证书，并将服务证书导出到名为 Service.cer 的文件。</span><span class="sxs-lookup"><span data-stu-id="65d37-183">Running **setup.bat** with the **service** argument creates a service certificate with the fully-qualified domain name of the computer and exports the service certificate to a file named Service.cer.</span></span>  
  
6.  <span data-ttu-id="65d37-184">编辑 Web.config 以反映新的证书名称 (在`findValue`属性中[ \<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)) 这是计算机的完全限定域名相同。</span><span class="sxs-lookup"><span data-stu-id="65d37-184">Edit Web.config to reflect the new certificate name (in the `findValue` attribute in the [\<serviceCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)) which is the same as the fully-qualified domain name of the computer.</span></span>  
  
7.  <span data-ttu-id="65d37-185">将服务目录中的 Service.cer 文件复制到客户端计算机上的客户端目录中。</span><span class="sxs-lookup"><span data-stu-id="65d37-185">Copy the Service.cer file from the service directory to the client directory on the client computer.</span></span>  
  
8.  <span data-ttu-id="65d37-186">在客户端上运行**setup.bat client**使用管理员特权的 Visual Studio 命令提示中。</span><span class="sxs-lookup"><span data-stu-id="65d37-186">On the client, run **setup.bat client** in a Visual Studio command prompt with administrator privileges.</span></span> <span data-ttu-id="65d37-187">运行**setup.bat**与**客户端**参数创建一个名为 client.com 的客户端证书，并将客户端证书导出到名为 Client.cer 的文件。</span><span class="sxs-lookup"><span data-stu-id="65d37-187">Running **setup.bat** with the **client** argument creates a client certificate named client.com and exports the client certificate to a file named Client.cer.</span></span>  
  
9. <span data-ttu-id="65d37-188">在客户端计算机上的 Client.exe.config 文件中，更改终结点的地址值，使其与服务的新地址相匹配。</span><span class="sxs-lookup"><span data-stu-id="65d37-188">In the Client.exe.config file on the client computer, change the address value of the endpoint to match the new address of your service.</span></span> <span data-ttu-id="65d37-189">通过用服务器的完全限定域名替换 localhost 来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="65d37-189">Do this by replacing localhost with the fully-qualified domain name of the server.</span></span>  
  
10. <span data-ttu-id="65d37-190">将客户端目录中的 Client.cer 文件复制到服务器上的服务目录中。</span><span class="sxs-lookup"><span data-stu-id="65d37-190">Copy the Client.cer file from the client directory to the service directory on the server.</span></span>  
  
11. <span data-ttu-id="65d37-191">在客户端上，使用管理特权在 Visual Studio 命令提示中运行 ImportServiceCert.bat。</span><span class="sxs-lookup"><span data-stu-id="65d37-191">On the client, run ImportServiceCert.bat in a Visual Studio command prompt with administrative privileges.</span></span> <span data-ttu-id="65d37-192">这会将 Service.cer 文件中的服务证书导入 CurrentUser – TrustedPeople 存储区。</span><span class="sxs-lookup"><span data-stu-id="65d37-192">This imports the service certificate from the Service.cer file into the CurrentUser - TrustedPeople store.</span></span>  
  
12. <span data-ttu-id="65d37-193">在服务器上，使用管理特权在 Visual Studio 命令提示中运行 ImportClientCert.bat。</span><span class="sxs-lookup"><span data-stu-id="65d37-193">On the server, run ImportClientCert.bat in a Visual Studio command prompt with administrative privileges.</span></span> <span data-ttu-id="65d37-194">这会将 Client.cer 文件中的客户端证书导入 LocalMachine - TrustedPeople 存储区。</span><span class="sxs-lookup"><span data-stu-id="65d37-194">This imports the client certificate from the Client.cer file into the LocalMachine - TrustedPeople store.</span></span>  
  
13. <span data-ttu-id="65d37-195">在客户端计算机上，从命令提示窗口中启动 Client.exe。</span><span class="sxs-lookup"><span data-stu-id="65d37-195">On the client computer, launch Client.exe from a command prompt window.</span></span> <span data-ttu-id="65d37-196">如果客户端和服务不能够进行通信，请参阅[疑难解答提示](http://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b)。</span><span class="sxs-lookup"><span data-stu-id="65d37-196">If the client and service are not able to communicate, see [Troubleshooting Tips](http://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b).</span></span>  
  
### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="65d37-197">运行示例后进行清理</span><span class="sxs-lookup"><span data-stu-id="65d37-197">To clean up after the sample</span></span>  
  
-   <span data-ttu-id="65d37-198">运行完示例后运行示例文件夹中的 Cleanup.bat。</span><span class="sxs-lookup"><span data-stu-id="65d37-198">Run Cleanup.bat in the samples folder after you have finished running the sample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="65d37-199">此脚本不会在跨计算机运行此示例时移除客户端上的服务证书。</span><span class="sxs-lookup"><span data-stu-id="65d37-199">This script does not remove service certificates on a client when running this sample across computers.</span></span> <span data-ttu-id="65d37-200">如果已运行跨计算机使用证书的 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 示例，请确保清除已安装在 CurrentUser - TrustedPeople 存储中的服务证书。</span><span class="sxs-lookup"><span data-stu-id="65d37-200">If you have run [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] samples that use certificates across computers, be sure to clear the service certificates that have been installed in the CurrentUser - TrustedPeople store.</span></span> <span data-ttu-id="65d37-201">为此，请使用以下命令：`certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>`，例如：`certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`。</span><span class="sxs-lookup"><span data-stu-id="65d37-201">To do this, use the following command: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` For example: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65d37-202">请参阅</span><span class="sxs-lookup"><span data-stu-id="65d37-202">See Also</span></span>
