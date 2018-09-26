---
title: 如何：指定通道安全凭据
ms.date: 03/30/2017
ms.assetid: f8e03f47-9c4f-4dd5-8f85-429e6d876119
author: BrucePerlerMS
ms.openlocfilehash: 8e730e3deaccb581b1722b62ce6282d8fde7180e
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2018
ms.locfileid: "47196170"
---
# <a name="how-to-specify-channel-security-credentials"></a><span data-ttu-id="e9afe-102">如何：指定通道安全凭据</span><span class="sxs-lookup"><span data-stu-id="e9afe-102">How to: Specify Channel Security Credentials</span></span>
<span data-ttu-id="e9afe-103">Windows Communication Foundation (WCF) 服务标记允许 COM 应用程序可以调用 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="e9afe-103">The Windows Communication Foundation (WCF) Service Moniker allows COM applications to call WCF services.</span></span> <span data-ttu-id="e9afe-104">大多数 WCF 服务需要客户端指定要用于身份验证和授权的凭据。</span><span class="sxs-lookup"><span data-stu-id="e9afe-104">Most WCF services require the client to specify credentials for authentication and authorization.</span></span> <span data-ttu-id="e9afe-105">在从 WCF 客户端调用 WCF 服务，可以指定这些凭据，在托管代码或应用程序配置文件中。</span><span class="sxs-lookup"><span data-stu-id="e9afe-105">When calling a WCF service from a WCF client, you can specify these credentials in managed code or in an application configuration file.</span></span> <span data-ttu-id="e9afe-106">在 COM 应用程序中调用 WCF 服务，可以使用<xref:System.ServiceModel.ComIntegration.IChannelCredentials>接口指定凭据。</span><span class="sxs-lookup"><span data-stu-id="e9afe-106">When calling a WCF service from a COM application, you can use the <xref:System.ServiceModel.ComIntegration.IChannelCredentials> interface to specify credentials.</span></span> <span data-ttu-id="e9afe-107">本主题将介绍使用 <xref:System.ServiceModel.ComIntegration.IChannelCredentials> 接口指定凭据的各种方法。</span><span class="sxs-lookup"><span data-stu-id="e9afe-107">This topic will illustrate various ways to specify credentials using the <xref:System.ServiceModel.ComIntegration.IChannelCredentials> interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e9afe-108"><xref:System.ServiceModel.ComIntegration.IChannelCredentials> 是一种基于 IDispatch 的接口，在 Visual Studio 环境中使用它将无法获取 IntelliSense 功能。</span><span class="sxs-lookup"><span data-stu-id="e9afe-108"><xref:System.ServiceModel.ComIntegration.IChannelCredentials> is an IDispatch-based interface and you will not get IntelliSense functionality in the Visual Studio environment.</span></span>  
  
 <span data-ttu-id="e9afe-109">本文将使用 WCF 服务中定义[消息安全示例](../../../../docs/framework/wcf/samples/message-security-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="e9afe-109">This article will use the WCF service defined in the [Message Security Sample](../../../../docs/framework/wcf/samples/message-security-sample.md).</span></span>  
  
### <a name="to-specify-a-client-certificate"></a><span data-ttu-id="e9afe-110">指定客户端证书</span><span class="sxs-lookup"><span data-stu-id="e9afe-110">To specify a client certificate</span></span>  
  
1.  <span data-ttu-id="e9afe-111">在消息安全目录中运行 Setup.bat 文件以创建和安装所需的测试证书。</span><span class="sxs-lookup"><span data-stu-id="e9afe-111">Run the Setup.bat file in the Message Security directory to create and install the required test certificates.</span></span>  
  
2.  <span data-ttu-id="e9afe-112">打开消息安全项目。</span><span class="sxs-lookup"><span data-stu-id="e9afe-112">Open the Message Security project.</span></span>  
  
3.  <span data-ttu-id="e9afe-113">添加`[ServiceBehavior(Namespace=``http://Microsoft.ServiceModel.Samples``)]`到`ICalculator`接口定义。</span><span class="sxs-lookup"><span data-stu-id="e9afe-113">Add `[ServiceBehavior(Namespace=``http://Microsoft.ServiceModel.Samples``)]` to the `ICalculator` interface definition.</span></span>  
  
4.  <span data-ttu-id="e9afe-114">添加`bindingNamespace=``http://Microsoft.ServiceModel.Samples`到服务 App.config 中的终结点标记。</span><span class="sxs-lookup"><span data-stu-id="e9afe-114">Add `bindingNamespace=``http://Microsoft.ServiceModel.Samples` to the endpoint tag in the App.config for the service.</span></span>  
  
5.  <span data-ttu-id="e9afe-115">生成消息安全示例并运行 Service.exe。</span><span class="sxs-lookup"><span data-stu-id="e9afe-115">Build the Message Security Sample and run Service.exe.</span></span> <span data-ttu-id="e9afe-116">使用 Internet Explorer 并浏览到服务的 URI (http://localhost:8000/ServiceModelSamples/Service)以确保服务正在运行。</span><span class="sxs-lookup"><span data-stu-id="e9afe-116">Use Internet Explorer and browse to the service's URI (http://localhost:8000/ServiceModelSamples/Service) to ensure that the service is working.</span></span>  
  
6.  <span data-ttu-id="e9afe-117">打开 Visual Basic 6.0 并创建一个新的 Standard .exe 文件。</span><span class="sxs-lookup"><span data-stu-id="e9afe-117">Open Visual Basic 6.0 and create a new Standard .exe file.</span></span> <span data-ttu-id="e9afe-118">在窗体中添加一个按钮并双击该按钮，以将以下代码添加到 Click 处理程序中：</span><span class="sxs-lookup"><span data-stu-id="e9afe-118">Add a button to the form and double-click the button to add the following code to the Click handler:</span></span>  
  
    ```  
        monString = "service:mexAddress=http://localhost:8000/ServiceModelSamples/Service?wsdl"  
        monString = monString + ", address=http://localhost:8000/ServiceModelSamples/Service"  
        monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
        monString = monString + ", binding=BasicHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
  
        Set monikerProxy = GetObject(monString)  
  
        'Set the Service Certificate.  
     monikerProxy.ChannelCredentials.SetServiceCertificateAuthentication "CurrentUser", "NoCheck", "PeerOrChainTrust"  
    monikerProxy.ChannelCredentials.SetDefaultServiceCertificateFromStore "CurrentUser", "TrustedPeople", "FindBySubjectName", "localhost"  
  
        'Set the Client Certificate.  
        monikerProxy.ChannelCredentials.SetClientCertificateFromStoreByName "CN=client.com", "CurrentUser", "My"  
        MsgBox monikerProxy.Add(3, 4)  
    ```  
  
7.  <span data-ttu-id="e9afe-119">运行 Visual Basic 应用程序并验证结果。</span><span class="sxs-lookup"><span data-stu-id="e9afe-119">Run the Visual Basic application and verify the results.</span></span>  
  
     <span data-ttu-id="e9afe-120">Visual Basic 应用程序将显示一个消息框，其中包含调用 Add(3, 4) 的结果。</span><span class="sxs-lookup"><span data-stu-id="e9afe-120">The Visual Basic application will display a message box with the result from calling Add(3, 4).</span></span> <span data-ttu-id="e9afe-121"><xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromFile%28System.String%2CSystem.String%2CSystem.String%29> 或 <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromStoreByName%28System.String%2CSystem.String%2CSystem.String%29> 也可以用于代替 <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromStore%28System.String%2CSystem.String%2CSystem.String%2CSystem.Object%29> 设置客户端证书：</span><span class="sxs-lookup"><span data-stu-id="e9afe-121"><xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromFile%28System.String%2CSystem.String%2CSystem.String%29> or <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromStoreByName%28System.String%2CSystem.String%2CSystem.String%29> can also be used in place of <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromStore%28System.String%2CSystem.String%2CSystem.String%2CSystem.Object%29> to set the Client Certificate:</span></span>  
  
    ```  
    monikerProxy.ChannelCredentials.SetClientCertificateFromFile "C:\MyClientCert.pfx", "password", "DefaultKeySet"  
    ```  
  
> [!NOTE]
>  <span data-ttu-id="e9afe-122">为使此调用生效，客户端证书在运行该客户端的计算机上应该是受信任的。</span><span class="sxs-lookup"><span data-stu-id="e9afe-122">For this call to work, the client certificate needs to be trusted on the machine the client is running on.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e9afe-123">如果标记格式不正确，或如果服务不可用，则对 `GetObject` 的调用将返回一个错误，指示“语法无效”。</span><span class="sxs-lookup"><span data-stu-id="e9afe-123">If the moniker is malformed or if the service is unavailable, the call to `GetObject` will return an error saying "Invalid Syntax."</span></span> <span data-ttu-id="e9afe-124">如果您收到此错误，请确保所使用的标记正确无误且服务可用。</span><span class="sxs-lookup"><span data-stu-id="e9afe-124">If you receive this error, make sure the moniker you are using is correct and the service is available.</span></span>  
  
### <a name="to-specify-user-name-and-password"></a><span data-ttu-id="e9afe-125">指定用户名和密码</span><span class="sxs-lookup"><span data-stu-id="e9afe-125">To specify user name and password</span></span>  
  
1.  <span data-ttu-id="e9afe-126">修改服务的 App.config 文件以使用 `wsHttpBinding`。</span><span class="sxs-lookup"><span data-stu-id="e9afe-126">Modify the Service App.config file to use the `wsHttpBinding`.</span></span> <span data-ttu-id="e9afe-127">验证用户名和密码时需要如此：</span><span class="sxs-lookup"><span data-stu-id="e9afe-127">This is required for user name and password validation:</span></span>  
  
  
  
2.  <span data-ttu-id="e9afe-128">将 `clientCredentialType` 设置为 UserName：</span><span class="sxs-lookup"><span data-stu-id="e9afe-128">Set the `clientCredentialType` to UserName:</span></span>  
  
  
  
3.  <span data-ttu-id="e9afe-129">打开 Visual Basic 6.0 并创建一个新的 Standard .exe 文件。</span><span class="sxs-lookup"><span data-stu-id="e9afe-129">Open Visual Basic 6.0 and create a new Standard .exe file.</span></span> <span data-ttu-id="e9afe-130">在窗体中添加一个按钮并双击该按钮，以将以下代码添加到 Click 处理程序中：</span><span class="sxs-lookup"><span data-stu-id="e9afe-130">Add a button to the form and double-click the button to add the following code to the Click handler:</span></span>  
  
    ```  
    monString = "service:mexAddress=http://localhost:8000/ServiceModelSamples/Service?wsdl"  
    monString = monString + ", address=http://localhost:8000/ServiceModelSamples/Service"  
    monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", binding=WSHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
  
    Set monikerProxy = GetObject(monString)  
  
    monikerProxy.ChannelCredentials.SetServiceCertificateAuthentication "CurrentUser", "NoCheck", "PeerOrChainTrust"  
    monikerProxy.ChannelCredentials.SetUserNameCredential "username", "password"  
  
    MsgBox monikerProxy.Add(3, 4)  
    ```  
  
4.  <span data-ttu-id="e9afe-131">运行 Visual Basic 应用程序并验证结果。</span><span class="sxs-lookup"><span data-stu-id="e9afe-131">Run the Visual Basic application and verify the results.</span></span> <span data-ttu-id="e9afe-132">Visual Basic 应用程序将显示一个消息框，其中包含调用 Add(3, 4) 的结果。</span><span class="sxs-lookup"><span data-stu-id="e9afe-132">The Visual Basic application will display a message box with the result from calling Add(3, 4).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e9afe-133">在本示例中，服务标记中指定的绑定已更改为 WSHttpBinding_ICalculator。</span><span class="sxs-lookup"><span data-stu-id="e9afe-133">The binding specified in the service moniker in this sample has been changed to WSHttpBinding_ICalculator.</span></span> <span data-ttu-id="e9afe-134">另外请注意，在调用 <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetUserNameCredential%28System.String%2CSystem.String%29> 时，必须提供有效的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="e9afe-134">Also note that you must supply a valid user name and password in the call to <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetUserNameCredential%28System.String%2CSystem.String%29>.</span></span>  
  
### <a name="to-specify-windows-credentials"></a><span data-ttu-id="e9afe-135">指定 Windows 凭据</span><span class="sxs-lookup"><span data-stu-id="e9afe-135">To specify Windows Credentials</span></span>  
  
1.  <span data-ttu-id="e9afe-136">在服务的 App.config 文件中将 `clientCredentialType` 设置为 Windows：</span><span class="sxs-lookup"><span data-stu-id="e9afe-136">Set `clientCredentialType` to Windows in the Service App.config file:</span></span>  
  
  
  
2.  <span data-ttu-id="e9afe-137">打开 Visual Basic 6.0 并创建一个新的 Standard .exe 文件。</span><span class="sxs-lookup"><span data-stu-id="e9afe-137">Open Visual Basic 6.0 and create a new Standard .exe file.</span></span> <span data-ttu-id="e9afe-138">在窗体中添加一个按钮并双击该按钮，以将以下代码添加到 Click 处理程序中：</span><span class="sxs-lookup"><span data-stu-id="e9afe-138">Add a button to the form and double-click the button to add the following code to the Click handler:</span></span>  
  
    ```  
    monString = "service:mexAddress=http://localhost:8000/ServiceModelSamples/Service?wsdl"  
    monString = monString + ", address=http://localhost:8000/ServiceModelSamples/Service"  
    monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", binding=WSHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", upnidentity=domain\userID"  
  
    Set monikerProxy = GetObject(monString)  
     monikerProxy.ChannelCredentials.SetWindowsCredential "domain", "userID", "password", 1, True  
  
    MsgBox monikerProxy.Add(3, 4)  
    ```  
  
3.  <span data-ttu-id="e9afe-139">运行 Visual Basic 应用程序并验证结果。</span><span class="sxs-lookup"><span data-stu-id="e9afe-139">Run the Visual Basic application and verify the results.</span></span> <span data-ttu-id="e9afe-140">Visual Basic 应用程序将显示一个消息框，其中包含调用 Add(3, 4) 的结果。</span><span class="sxs-lookup"><span data-stu-id="e9afe-140">The Visual Basic application will display a message box with the result from calling Add(3, 4).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e9afe-141">您必须使用有效值替换“domain”、“userID”和“password”。</span><span class="sxs-lookup"><span data-stu-id="e9afe-141">You must replace "domain", "userID", and "password" with valid values.</span></span>  
  
### <a name="to-specify-an-issue-token"></a><span data-ttu-id="e9afe-142">指定颁发令牌</span><span class="sxs-lookup"><span data-stu-id="e9afe-142">To specify an issue token</span></span>  
  
1.  <span data-ttu-id="e9afe-143">颁发令牌仅用于使用联合安全的应用程序。</span><span class="sxs-lookup"><span data-stu-id="e9afe-143">Issue tokens are used only for applications using federated security.</span></span> <span data-ttu-id="e9afe-144">有关联合安全的详细信息，请参阅[联合身份验证和颁发令牌](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)并[联合身份验证示例](../../../../docs/framework/wcf/samples/federation-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="e9afe-144">For more information about federated security, see [Federation and Issued Tokens](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md) and [Federation Sample](../../../../docs/framework/wcf/samples/federation-sample.md).</span></span>  
  
     <span data-ttu-id="e9afe-145">下面的 Visual Basic 代码示例演示如何调用 <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetIssuedToken%28System.String%2CSystem.String%2CSystem.String%29> 方法：</span><span class="sxs-lookup"><span data-stu-id="e9afe-145">The following Visual Basic code example illustrates how to call the <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetIssuedToken%28System.String%2CSystem.String%2CSystem.String%29> method:</span></span>  
  
    ```  
        monString = "service:mexAddress=http://localhost:8000/ServiceModelSamples/Service?wsdl"  
        monString = monString + ", address=http://localhost:8000/SomeService/Service"  
        monString = monString + ", contract=ICalculator, contractNamespace=http://SomeService.Samples"  
        monString = monString + ", binding=WSHttpBinding_ISomeContract, bindingNamespace=http://SomeService.Samples"  
  
        Set monikerProxy = GetObject(monString)  
    monikerProxy.SetIssuedToken("http://somemachine/sts", "bindingType", "binding")  
    ```  
  
     <span data-ttu-id="e9afe-146">有关用于此方法的参数的更多信息，请参见 <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetIssuedToken%28System.String%2CSystem.String%2CSystem.String%29>。</span><span class="sxs-lookup"><span data-stu-id="e9afe-146">For more information about the parameters for this method, see <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetIssuedToken%28System.String%2CSystem.String%2CSystem.String%29>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9afe-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="e9afe-147">See Also</span></span>  
 [<span data-ttu-id="e9afe-148">联合</span><span class="sxs-lookup"><span data-stu-id="e9afe-148">Federation</span></span>](../../../../docs/framework/wcf/feature-details/federation.md)  
 [<span data-ttu-id="e9afe-149">如何：在联合身份验证服务上配置凭据</span><span class="sxs-lookup"><span data-stu-id="e9afe-149">How to: Configure Credentials on a Federation Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)  
 [<span data-ttu-id="e9afe-150">如何：创建联合客户端</span><span class="sxs-lookup"><span data-stu-id="e9afe-150">How to: Create a Federated Client</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [<span data-ttu-id="e9afe-151">消息安全性</span><span class="sxs-lookup"><span data-stu-id="e9afe-151">Message Security</span></span>](../../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)  
 [<span data-ttu-id="e9afe-152">绑定与安全</span><span class="sxs-lookup"><span data-stu-id="e9afe-152">Bindings and Security</span></span>](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)
