---
title: "如何：使用用户名和密码进行身份验证"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: authentication [WCF], user name and password
ms.assetid: a5415be2-0ef3-464c-9f76-c255cb8165a4
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 31e05709465e429445a2ebdafae719c24d316c8e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-authenticate-with-a-user-name-and-password"></a><span data-ttu-id="16058-102">如何：使用用户名和密码进行身份验证</span><span class="sxs-lookup"><span data-stu-id="16058-102">How to: Authenticate with a User Name and Password</span></span>
<span data-ttu-id="16058-103">本主题演示如何让 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 服务使用 Windows 域用户名和密码来对客户端进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="16058-103">This topic demonstrates how to enable a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service to authenticate a client with a Windows domain username and password.</span></span> <span data-ttu-id="16058-104">它假定您有一个正在工作的自承载 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="16058-104">It assumes you have a working, self-hosted WCF service.</span></span> <span data-ttu-id="16058-105">有关创建基本自承载的 WCF 服务，请参阅示例[入门教程](../../../../docs/framework/wcf/getting-started-tutorial.md)。</span><span class="sxs-lookup"><span data-stu-id="16058-105">For an example of creating a basic self-hosted WCF service see, [Getting Started Tutorial](../../../../docs/framework/wcf/getting-started-tutorial.md).</span></span> <span data-ttu-id="16058-106">本主题假定在代码中配置服务。</span><span class="sxs-lookup"><span data-stu-id="16058-106">This topic assumes the service is configured in code.</span></span> <span data-ttu-id="16058-107">如果你想要查看配置使用配置文件的类似服务的示例请参阅[消息安全用户名称](../../../../docs/framework/wcf/samples/message-security-user-name.md)</span><span class="sxs-lookup"><span data-stu-id="16058-107">If you would like to see an example of configuring a similar service using a configuration file see [Message Security User Name](../../../../docs/framework/wcf/samples/message-security-user-name.md)</span></span>  
  
 <span data-ttu-id="16058-108">若要配置服务以使用 Windows 域用户名和密码使用其客户端身份验证 <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> 并设置其`Security.Mode`属性`Message`。</span><span class="sxs-lookup"><span data-stu-id="16058-108">To configure a service to authenticate its clients using Windows Domain username and passwords use the <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> and set its `Security.Mode` property to `Message`.</span></span> <span data-ttu-id="16058-109">此外，您必须指定 X509 证书，该证书用于在将用户名和密码从客户端发送到服务时对它们进行加密。</span><span class="sxs-lookup"><span data-stu-id="16058-109">In addition you must specify an X509 certificate that will be used to encrypt the username and password as they are sent from the client to the service.</span></span>  
  
 <span data-ttu-id="16058-110">在客户端上，您必须提示用户输入用户名和密码，并指定用户在 WCF 客户端代理上的凭据。</span><span class="sxs-lookup"><span data-stu-id="16058-110">On the client, you must prompt the user for the username and password and specify the user’s credentials on the WCF client proxy.</span></span>  
  
### <a name="to-configure-a-wcf-service-to-authenticate-using-windows-domain-username-and-password"></a><span data-ttu-id="16058-111">配置 WCF 服务以便使用 Windows 域用户名和密码进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="16058-111">To configure a WCF service to authenticate using Windows domain username and password.</span></span>  
  
1.  <span data-ttu-id="16058-112">创建的实例 <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`>，将绑定到的安全模式设置`SecurityMode.Message`，将其设置`ClientCredentialType`绑定到的`MessageCredentialType.UserName`，并添加服务终结点使用的服务主机所配置的绑定，如所示在下面的代码：</span><span class="sxs-lookup"><span data-stu-id="16058-112">Create an instance of the <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`>, set the security mode of the binding to `SecurityMode.Message`, set the `ClientCredentialType` of the binding to `MessageCredentialType.UserName`, and add a service endpoint using the configured binding to the service host as shown in the following code:</span></span>  
  
    ```  
    // ...  
    WSHttpBinding userNameBinding = new WSHttpBinding();  
    userNameBinding.Security.Mode = SecurityMode.Message;  
    userNameBinding.Security.Message.ClientCredentialType = MessageCredentialType.UserName;  
    svcHost.AddServiceEndpoint(typeof(IService1), userNameBinding, "");  
    // ...  
    ```  
  
2.  <span data-ttu-id="16058-113">指定用于对通过网络发送的用户名和密码信息进行加密的服务器证书。</span><span class="sxs-lookup"><span data-stu-id="16058-113">Specify the server certificate used to encrypt the username and password information sent over the wire.</span></span> <span data-ttu-id="16058-114">此代码应紧跟在上面的代码之后。</span><span class="sxs-lookup"><span data-stu-id="16058-114">This code should immediately follow the code above.</span></span> <span data-ttu-id="16058-115">下面的示例使用创建的证书由 setup.bat 文件从[消息安全用户名称](../../../../docs/framework/wcf/samples/message-security-user-name.md)示例：</span><span class="sxs-lookup"><span data-stu-id="16058-115">The following example uses the certificate that is created by the setup.bat file from the [Message Security User Name](../../../../docs/framework/wcf/samples/message-security-user-name.md) sample:</span></span>  
  
    ```  
    // ...  
    svcHost.Credentials.ServiceCertificate.SetCertificate(StoreLocation.LocalMachine, StoreName.My, X509FindType.FindBySubjectName, "localhost");  
    // ...  
    ```  
  
     <span data-ttu-id="16058-116">你可以使用你自己的证书，只需修改代码以引用你的证书。</span><span class="sxs-lookup"><span data-stu-id="16058-116">You can use your own certificate, just modify the code to refer to your certificate.</span></span> <span data-ttu-id="16058-117">有关创建和使用证书的详细信息请参阅[使用证书](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)。</span><span class="sxs-lookup"><span data-stu-id="16058-117">For more information about creating and using certificates see [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span> <span data-ttu-id="16058-118">确保证书在本地计算机的受信任人证书存储区中。</span><span class="sxs-lookup"><span data-stu-id="16058-118">Make sure the certificate is in the Trusted People certificate store for the Local Machine.</span></span> <span data-ttu-id="16058-119">你可以执行此操作通过运行 mmc.exe 并选择**文件**，**添加/删除管理单元中...**菜单项。</span><span class="sxs-lookup"><span data-stu-id="16058-119">You can do this by running mmc.exe and selecting the **File**, **Add/Remove Snap-in...** menu item.</span></span> <span data-ttu-id="16058-120">在**添加或删除管理单元**对话框中，选择**证书管理单元**单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="16058-120">In the **Add or Remove Snap-ins** dialog, select the **Certificates snap-in** and click **Add**.</span></span> <span data-ttu-id="16058-121">在证书管理单元在对话框中选择**计算机帐户**。</span><span class="sxs-lookup"><span data-stu-id="16058-121">In the Certificates Snap-in dialog select **Computer account**.</span></span> <span data-ttu-id="16058-122">默认情况下，从消息安全用户名称示例生成的证书将位于个人/证书文件夹中。</span><span class="sxs-lookup"><span data-stu-id="16058-122">By default the certificate generated from the Message Security User name sample will be located in the Personal/Certificates folder.</span></span>  <span data-ttu-id="16058-123">它将列出为"localhost"颁发给在 MMC 窗口中的列下。</span><span class="sxs-lookup"><span data-stu-id="16058-123">It will be listed as "localhost" under the Issued to column in the MMC window.</span></span> <span data-ttu-id="16058-124">拖放到证书**受信任人**文件夹。</span><span class="sxs-lookup"><span data-stu-id="16058-124">Drag and drop the certificate into the **Trusted People** folder.</span></span> <span data-ttu-id="16058-125">这将允许 WCF 在执行身份验证时，将证书视为受信任的证书。</span><span class="sxs-lookup"><span data-stu-id="16058-125">This will allow WCF to treat the certificate as a trusted certificate when performing authentication.</span></span>  
  
### <a name="to-call-the-service-passing-username-and-password"></a><span data-ttu-id="16058-126">调用服务传递用户名和密码</span><span class="sxs-lookup"><span data-stu-id="16058-126">To call the service passing username and password</span></span>  
  
1.  <span data-ttu-id="16058-127">客户端应用程序必须提示用户输入其用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="16058-127">The client application must prompt the user for their username and password.</span></span> <span data-ttu-id="16058-128">下面的代码要求用户输入用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="16058-128">The following code asks the user for username and password.</span></span>  
  
    > [!WARNING]
    >  <span data-ttu-id="16058-129">此代码不应在生产中使用，因为密码在输入时将显示出来。</span><span class="sxs-lookup"><span data-stu-id="16058-129">This code should not be used in production as the password is displayed while being entered.</span></span>  
  
    ```  
    public static void GetPassword(out string username, out string password)  
            {  
                Console.WriteLine("Provide a valid machine or domain account. [domain\\user]");  
                Console.WriteLine("   Enter username:");  
                username = Console.ReadLine();  
                Console.WriteLine("   Enter password:");  
                password = Console.ReadLine();             
                return;  
            }  
    ```  
  
2.  <span data-ttu-id="16058-130">创建客户端代理的一个实例，用于指定客户端的证书，如下面的代码所示：</span><span class="sxs-lookup"><span data-stu-id="16058-130">Create an instance of the client proxy specifying the client’s credentials as shown in the following code:</span></span>  
  
    ```  
    string username;  
    string password;  
  
    // Instantiate the proxy  
    Service1Client proxy = new Service1Client();  
  
    // Prompt the user for username & password  
    GetPassword(out username, out password);  
  
    // Set the user’s credentials on the proxy  
    proxy.ClientCredentials.UserName.UserName = username;  
    proxy.ClientCredentials.UserName.Password = password;  
  
    // Treat the test certificate as trusted  
    proxy.ClientCredentials.ServiceCertificate.Authentication.CertificateValidationMode = System.ServiceModel.Security.X509CertificateValidationMode.PeerOrChainTrust;  
    // Call the service operation using the proxy  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="16058-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="16058-131">See Also</span></span>  
 <span data-ttu-id="16058-132"><<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`></span><span class="sxs-lookup"><span data-stu-id="16058-132"><<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`></span></span>  
 <xref:System.ServiceModel.WSHttpSecurity>  
 <xref:System.ServiceModel.SecurityMode>  
 <xref:System.ServiceModel.Security.UserNamePasswordClientCredential.UserName%2A>  
 <xref:System.ServiceModel.Security.UserNamePasswordClientCredential.Password%2A>  
 <xref:System.ServiceModel.Security.UserNamePasswordClientCredential>  
 <xref:System.ServiceModel.WSHttpSecurity.Mode%2A>  
 <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A>  
 [<span data-ttu-id="16058-133">使用基本身份验证的传输安全性</span><span class="sxs-lookup"><span data-stu-id="16058-133">Transport Security with Basic Authentication</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-with-basic-authentication.md)  
 [<span data-ttu-id="16058-134">分布式应用程序安全性</span><span class="sxs-lookup"><span data-stu-id="16058-134">Distributed Application Security</span></span>](../../../../docs/framework/wcf/feature-details/distributed-application-security.md)  
 [<span data-ttu-id="16058-135">\<wsHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="16058-135">\<wsHttpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)
