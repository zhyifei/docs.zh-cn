---
title: 保证客户端的安全
ms.date: 03/30/2017
helpviewer_keywords:
- clients [WCF], security considerations
ms.assetid: 44c8578c-9a5b-4acd-8168-1c30a027c4c5
ms.openlocfilehash: d76b7db8a3c8f2dcdc8bdbc325a1bb14b87229ab
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54721105"
---
# <a name="securing-clients"></a><span data-ttu-id="a41d4-102">保证客户端的安全</span><span class="sxs-lookup"><span data-stu-id="a41d4-102">Securing Clients</span></span>
<span data-ttu-id="a41d4-103">在 Windows Communication Foundation (WCF)，由服务规定客户端的安全要求。</span><span class="sxs-lookup"><span data-stu-id="a41d4-103">In Windows Communication Foundation (WCF), the service dictates the security requirements for clients.</span></span> <span data-ttu-id="a41d4-104">即，由服务指定要使用的安全模式以及客户端是否必须提供凭据。</span><span class="sxs-lookup"><span data-stu-id="a41d4-104">That is, the service specifies what security mode to use, and whether or not the client must provide a credential.</span></span> <span data-ttu-id="a41d4-105">因此，保证客户端安全的过程非常简单：使用从服务那里获得的元数据（如果已发布）来生成客户端。</span><span class="sxs-lookup"><span data-stu-id="a41d4-105">The process of securing a client, therefore, is simple: use the metadata obtained from the service (if it is published) and build a client.</span></span> <span data-ttu-id="a41d4-106">元数据指定如何配置客户端。</span><span class="sxs-lookup"><span data-stu-id="a41d4-106">The metadata specifies how to configure the client.</span></span> <span data-ttu-id="a41d4-107">如果服务要求客户端提供凭据，您必须获得能够满足要求的凭据。</span><span class="sxs-lookup"><span data-stu-id="a41d4-107">If the service requires that the client supply a credential, then you must obtain a credential that fits the requirement.</span></span> <span data-ttu-id="a41d4-108">本主题进一步详细讨论此过程。</span><span class="sxs-lookup"><span data-stu-id="a41d4-108">This topic discusses the process in further detail.</span></span> <span data-ttu-id="a41d4-109">有关创建安全服务的详细信息，请参阅[Securing Services](../../../docs/framework/wcf/securing-services.md)。</span><span class="sxs-lookup"><span data-stu-id="a41d4-109">For more information about creating a secure service, see [Securing Services](../../../docs/framework/wcf/securing-services.md).</span></span>  
  
## <a name="the-service-specifies-security"></a><span data-ttu-id="a41d4-110">服务指定安全性</span><span class="sxs-lookup"><span data-stu-id="a41d4-110">The Service Specifies Security</span></span>  
 <span data-ttu-id="a41d4-111">默认情况下，WCF 绑定已启用的安全功能。</span><span class="sxs-lookup"><span data-stu-id="a41d4-111">By default, WCF bindings have security features enabled.</span></span> <span data-ttu-id="a41d4-112">（<xref:System.ServiceModel.BasicHttpBinding> 是一个例外。）因此，如果服务使用 WCF 创建的是更好地实现安全性，以确保身份验证、 保密性和完整性。</span><span class="sxs-lookup"><span data-stu-id="a41d4-112">(The exception is the <xref:System.ServiceModel.BasicHttpBinding>.) Therefore, if the service was created using WCF, there is a greater chance that it will implement security to ensure authentication, confidentiality, and integrity.</span></span> <span data-ttu-id="a41d4-113">在这种情况下，服务提供的元数据将指示建立安全通信通道需要哪些条件。</span><span class="sxs-lookup"><span data-stu-id="a41d4-113">In that case, the metadata the service provides will indicate what it requires to establish a secure communication channel.</span></span> <span data-ttu-id="a41d4-114">如果服务元数据不包含安全要求，则无法对服务强行实施安全方案，例如 Secure Sockets Layer (SSL) over HTTP。</span><span class="sxs-lookup"><span data-stu-id="a41d4-114">If the service metadata does not include any security requirements, there is no way to impose a security scheme, such as Secure Sockets Layer (SSL) over HTTP, on a service.</span></span> <span data-ttu-id="a41d4-115">但是，如果服务要求客户端提供凭据，则客户端开发人员、部署人员或管理员必须提供客户端用来向该服务证明自己身份的实际凭据。</span><span class="sxs-lookup"><span data-stu-id="a41d4-115">If, however, the service requires the client to supply a credential, then the client developer, deployer, or administrator must supply the actual credential that the client will use to authenticate itself to the service.</span></span>  
  
## <a name="obtaining-metadata"></a><span data-ttu-id="a41d4-116">获取元数据</span><span class="sxs-lookup"><span data-stu-id="a41d4-116">Obtaining Metadata</span></span>  
 <span data-ttu-id="a41d4-117">创建客户端时，第一步是获取客户端将与其通信的服务的元数据。</span><span class="sxs-lookup"><span data-stu-id="a41d4-117">When creating a client, the first step is to obtain the metadata for the service that the client will communicate with.</span></span> <span data-ttu-id="a41d4-118">有两种方法可以做到这一点。</span><span class="sxs-lookup"><span data-stu-id="a41d4-118">This can be done in two ways.</span></span> <span data-ttu-id="a41d4-119">首先，如果该服务发布元数据交换 (MEX) 终结点，或者使其元数据可通过 HTTP 或 HTTPS，则可以下载元数据中使用[ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)，以生成同时客户端，以及配置文件的代码文件。</span><span class="sxs-lookup"><span data-stu-id="a41d4-119">First, if the service publishes a metadata exchange (MEX) endpoint or makes its metadata available over HTTP or HTTPS, you can download the metadata using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md), which generates both code files for a client as well as a configuration file.</span></span> <span data-ttu-id="a41d4-120">(有关使用该工具的详细信息，请参阅[使用 WCF 客户端访问服务](../../../docs/framework/wcf/accessing-services-using-a-wcf-client.md)。)其次，如果服务没有发布 MEX 终结点，也没有使自己的元数据可通过 HTTP 或 HTTPS 获得，您必须与服务创建者联系，以获得描述安全要求和元数据的文档。</span><span class="sxs-lookup"><span data-stu-id="a41d4-120">(For more information about using the tool, see [Accessing Services Using a WCF Client](../../../docs/framework/wcf/accessing-services-using-a-wcf-client.md).) If the service does not publish a MEX endpoint and also does not make its metadata available over HTTP or HTTPS, you must contact the service creator for documentation that describes the security requirements and the metadata.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a41d4-121">建议使用来自受信任的源且未被篡改的元数据。</span><span class="sxs-lookup"><span data-stu-id="a41d4-121">It is recommended that the metadata come from a trusted source and that it not be tampered with.</span></span> <span data-ttu-id="a41d4-122">使用 HTTP 协议检索到的元数据是以明文形式发送的，可能被篡改。</span><span class="sxs-lookup"><span data-stu-id="a41d4-122">Metadata retrieved using the HTTP protocol is sent in clear text and can be tampered with.</span></span> <span data-ttu-id="a41d4-123">如果服务使用 <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> 和 <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetUrl%2A> 属性，请根据服务创建者提供的 URL，使用 HTTPS 协议下载数据。</span><span class="sxs-lookup"><span data-stu-id="a41d4-123">If the service uses the <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> and <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetUrl%2A> properties, use the URL the service creator supplied to download the data using the HTTPS protocol.</span></span>  
  
## <a name="validating-security"></a><span data-ttu-id="a41d4-124">验证安全性</span><span class="sxs-lookup"><span data-stu-id="a41d4-124">Validating Security</span></span>  
 <span data-ttu-id="a41d4-125">元数据源可以分为两大类：受信任的源和不受信任的源。</span><span class="sxs-lookup"><span data-stu-id="a41d4-125">Metadata sources can be divided into two broad categories: trust sources and untrusted sources.</span></span> <span data-ttu-id="a41d4-126">如果信任某个源，并且已从该源的安全 MEX 终结点下载客户端代码和其他元数据，则可以生成客户端，为其提供正确的凭据，然后无所顾忌地运行该客户端。</span><span class="sxs-lookup"><span data-stu-id="a41d4-126">If you trust a source and have downloaded the client code and other metadata from that source's secure MEX endpoint, then you can build the client, supply it with the right credentials, and run it with no other concerns.</span></span>  
  
 <span data-ttu-id="a41d4-127">但是，如果您选择从一个知之甚少的源下载客户端和元数据，请务必验证代码所使用的安全措施。</span><span class="sxs-lookup"><span data-stu-id="a41d4-127">However, if you elect to download a client and metadata from a source that you know little about, be sure to validate the security measures the code uses.</span></span> <span data-ttu-id="a41d4-128">例如，一定不要简单地创建一个向服务发送个人或财务信息的客户端，除非该服务要求保密性和完整性（这是最基本的要求）。</span><span class="sxs-lookup"><span data-stu-id="a41d4-128">For example, you must not simply create a client that sends your personal or financial information to a service unless the service demands confidentiality and integrity (at the very least).</span></span> <span data-ttu-id="a41d4-129">您对服务所有者的信任应达到您愿意向其公开这些信息的程度，因为他或她将能够看到这些信息。</span><span class="sxs-lookup"><span data-stu-id="a41d4-129">You should trust the owner of the service to the extent that you are willing to disclose such information because such information will be visible to him or her.</span></span>  
  
 <span data-ttu-id="a41d4-130">因此，请记住如下规则：在使用来自不受信任的源的代码和元数据时，应检查这些代码和元数据，以确保它们满足你所要求的安全级别。</span><span class="sxs-lookup"><span data-stu-id="a41d4-130">As a rule, therefore, when using code and metadata from an untrusted source, check the code and metadata to ensure that it meets the security level that you require.</span></span>  
  
## <a name="setting-a-client-credential"></a><span data-ttu-id="a41d4-131">设置客户端凭据</span><span class="sxs-lookup"><span data-stu-id="a41d4-131">Setting a Client Credential</span></span>  
 <span data-ttu-id="a41d4-132">在客户端上设置客户端凭据的过程包含两个步骤：</span><span class="sxs-lookup"><span data-stu-id="a41d4-132">Setting a client credential on a client consists of two steps:</span></span>  
  
1.  <span data-ttu-id="a41d4-133">确定*客户端凭据类型*服务要求。</span><span class="sxs-lookup"><span data-stu-id="a41d4-133">Determine the *client credential type* the service requires.</span></span> <span data-ttu-id="a41d4-134">这是通过两种方法之一完成的。</span><span class="sxs-lookup"><span data-stu-id="a41d4-134">This is accomplished by one of two methods.</span></span> <span data-ttu-id="a41d4-135">首先，如果您拥有来自服务创建者的文档，则其中应指定了服务所要求的客户端凭据类型（如果有要求的话）。</span><span class="sxs-lookup"><span data-stu-id="a41d4-135">First, if you have documentation from the service creator, it should specify the client credential type (if any) the service requires.</span></span> <span data-ttu-id="a41d4-136">其次，如果您仅拥有由 Svcutil.exe 工具生成的配置文件，则可以检查各个绑定，以确定要求何种凭据类型。</span><span class="sxs-lookup"><span data-stu-id="a41d4-136">Second, if you have only a configuration file generated by the Svcutil.exe tool, you can examine the individual bindings to determine what credential type is required.</span></span>  
  
2.  <span data-ttu-id="a41d4-137">指定一个实际客户端凭据。</span><span class="sxs-lookup"><span data-stu-id="a41d4-137">Specify an actual client credential.</span></span> <span data-ttu-id="a41d4-138">实际的客户端凭据称为*客户端凭据值*类型区分开来。</span><span class="sxs-lookup"><span data-stu-id="a41d4-138">The actual client credential is called a *client credential value* to distinguish it from the type.</span></span> <span data-ttu-id="a41d4-139">例如，如果客户端凭据类型指定了证书，您必须提供由该服务所信任的证书颁发机构颁发的 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="a41d4-139">For example, if the client credential type specifies a certificate, you must supply an X.509 certificate that is issued by a certification authority the service trusts.</span></span>  
  
### <a name="determining-the-client-credential-type"></a><span data-ttu-id="a41d4-140">确定客户端凭据类型</span><span class="sxs-lookup"><span data-stu-id="a41d4-140">Determining the Client Credential Type</span></span>  
 <span data-ttu-id="a41d4-141">如果有配置文件由 Svcutil.exe 工具生成，请检查[\<绑定 >](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)部分可以确定哪些客户端凭据类型是必需的。</span><span class="sxs-lookup"><span data-stu-id="a41d4-141">If you have the configuration file the Svcutil.exe tool generated, examine the [\<bindings>](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) section to determine what client credential type is required.</span></span> <span data-ttu-id="a41d4-142">该节包含指定安全要求的绑定元素。</span><span class="sxs-lookup"><span data-stu-id="a41d4-142">Within the section are binding elements that specify the security requirements.</span></span> <span data-ttu-id="a41d4-143">具体而言，检查\<安全 > 的每个绑定元素。</span><span class="sxs-lookup"><span data-stu-id="a41d4-143">Specifically, examine the \<security> Element of each binding.</span></span> <span data-ttu-id="a41d4-144">该元素包含 `mode` 属性，该属性可设置为以下三个可能的值之一：`Message`、`Transport` 或 `TransportWithMessageCredential`。</span><span class="sxs-lookup"><span data-stu-id="a41d4-144">That element includes the `mode` attribute, which you can set to one of three possible values (`Message`, `Transport`, or `TransportWithMessageCredential`).</span></span> <span data-ttu-id="a41d4-145">该属性的值确定模式，而模式则确定哪个子元素有效。</span><span class="sxs-lookup"><span data-stu-id="a41d4-145">The value of the attribute determines the mode, and the mode determines which of the child elements is significant.</span></span>  
  
 <span data-ttu-id="a41d4-146">`<security>`元素可以包含`<transport>`或`<message>`元素，或两者。</span><span class="sxs-lookup"><span data-stu-id="a41d4-146">The `<security>` element can contain either a `<transport>` or `<message>` element, or both.</span></span> <span data-ttu-id="a41d4-147">有效元素是指与安全模式匹配的那个元素。</span><span class="sxs-lookup"><span data-stu-id="a41d4-147">The significant element is the one that matches the security mode.</span></span> <span data-ttu-id="a41d4-148">例如，下面的代码指定安全模式为 `"Message"`，`<message>` 元素的客户端凭据类型为 `"Certificate"`。</span><span class="sxs-lookup"><span data-stu-id="a41d4-148">For example, the following code specifies that the security mode is `"Message"`, and the client credential type for the `<message>` element is `"Certificate"`.</span></span> <span data-ttu-id="a41d4-149">在这种情况下，`<transport>` 元素可以忽略。</span><span class="sxs-lookup"><span data-stu-id="a41d4-149">In this case, the `<transport>` element can be ignored.</span></span> <span data-ttu-id="a41d4-150">但是，`<message>` 元素指定必须提供 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="a41d4-150">However, the `<message>` element specifies that an X.509 certificate must be supplied.</span></span>  
  
```xml  
<wsHttpBinding>  
    <binding name="WSHttpBinding_ICalculator">  
       <security mode="Message">  
           <transport clientCredentialType="Windows"   
                      realm="" />  
           <message clientCredentialType="Certificate"   
                    negotiateServiceCredential="true"  
                    algorithmSuite="Default"   
                    establishSecurityContext="true" />  
       </security>  
    </binding>  
</wsHttpBinding>  
```  
  
 <span data-ttu-id="a41d4-151">请注意，如果按照下面的示例所示，将 `clientCredentialType` 属性设置为 `"Windows"`，则无需提供实际凭据值。</span><span class="sxs-lookup"><span data-stu-id="a41d4-151">Note that if the `clientCredentialType` attribute is set to `"Windows"`, as shown in the following example, you do not need to supply an actual credential value.</span></span> <span data-ttu-id="a41d4-152">这是因为，Windows 集成安全性提供了正在运行客户端的用户的实际凭据（一个 Kerberos 令牌）。</span><span class="sxs-lookup"><span data-stu-id="a41d4-152">This is because the Windows integrated security provides the actual credential (a Kerberos token) of the person who is running the client.</span></span>  
  
```xml  
<security mode="Message">  
    <transport clientCredentialType="Windows "   
        realm="" />  
</security>  
```  
  
### <a name="setting-the-client-credential-value"></a><span data-ttu-id="a41d4-153">设置客户端凭据值</span><span class="sxs-lookup"><span data-stu-id="a41d4-153">Setting the Client Credential Value</span></span>  
 <span data-ttu-id="a41d4-154">如果确定客户端必须提供凭据，请使用适当的方法来配置客户端。</span><span class="sxs-lookup"><span data-stu-id="a41d4-154">If it is determined that the client must supply a credential, use the appropriate method to configure the client.</span></span> <span data-ttu-id="a41d4-155">例如，若要设置客户端证书，请使用 <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="a41d4-155">For example, to set a client certificate, use the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> method.</span></span>  
  
 <span data-ttu-id="a41d4-156">一种常见的证书形式是 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="a41d4-156">A common form of credential is the X.509 certificate.</span></span> <span data-ttu-id="a41d4-157">可以通过两种方式来提供凭据：</span><span class="sxs-lookup"><span data-stu-id="a41d4-157">You can supply the credential in two ways:</span></span>  
  
-   <span data-ttu-id="a41d4-158">在客户端代码中对其进行编程（使用 `SetCertificate` 方法）。</span><span class="sxs-lookup"><span data-stu-id="a41d4-158">By programming it in your client code (using the `SetCertificate` method).</span></span>  
  
 <span data-ttu-id="a41d4-159">通过添加[\<行为 >](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)部分中的客户端的配置文件和使用`clientCredentials`元素 （如下所示）。</span><span class="sxs-lookup"><span data-stu-id="a41d4-159">By adding a [\<behaviors>](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) section of the configuration file for the client and using the `clientCredentials` element (shown below).</span></span>  
  
#### <a name="setting-a-clientcredentials-value-in-code"></a><span data-ttu-id="a41d4-160">设置\<clientCredentials > 在代码中的值</span><span class="sxs-lookup"><span data-stu-id="a41d4-160">Setting a \<clientCredentials> Value in Code</span></span>  
 <span data-ttu-id="a41d4-161">若要设置[ \<clientCredentials >](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)值在代码中，你必须访问<xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A>属性<xref:System.ServiceModel.ClientBase%601>类。</span><span class="sxs-lookup"><span data-stu-id="a41d4-161">To set a [\<clientCredentials>](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) value in code, you must access the <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> property of the <xref:System.ServiceModel.ClientBase%601> class.</span></span> <span data-ttu-id="a41d4-162">该属性返回一个 <xref:System.ServiceModel.Description.ClientCredentials> 对象，使用该对象可以访问各种凭据类型，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="a41d4-162">The property returns a <xref:System.ServiceModel.Description.ClientCredentials> object that allows access to various credential types, as shown in the following table.</span></span>  
  
|<span data-ttu-id="a41d4-163">ClientCredential 属性</span><span class="sxs-lookup"><span data-stu-id="a41d4-163">ClientCredential Property</span></span>|<span data-ttu-id="a41d4-164">描述</span><span class="sxs-lookup"><span data-stu-id="a41d4-164">Description</span></span>|<span data-ttu-id="a41d4-165">说明</span><span class="sxs-lookup"><span data-stu-id="a41d4-165">Notes</span></span>|  
|-------------------------------|-----------------|-----------|  
|<xref:System.ServiceModel.Description.ClientCredentials.ClientCertificate%2A>|<span data-ttu-id="a41d4-166">返回一个 <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential></span><span class="sxs-lookup"><span data-stu-id="a41d4-166">Returns an <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential></span></span>|<span data-ttu-id="a41d4-167">表示客户端提供的 X.509 证书，客户端使用该证书向服务器证明自己的身份。</span><span class="sxs-lookup"><span data-stu-id="a41d4-167">Represents an X.509 certificate provided by the client to authenticate itself to the service.</span></span>|  
|<xref:System.ServiceModel.Description.ClientCredentials.HttpDigest%2A>|<span data-ttu-id="a41d4-168">返回一个 <xref:System.ServiceModel.Security.HttpDigestClientCredential></span><span class="sxs-lookup"><span data-stu-id="a41d4-168">Returns an <xref:System.ServiceModel.Security.HttpDigestClientCredential></span></span>|<span data-ttu-id="a41d4-169">表示 HTTP 摘要式凭据。</span><span class="sxs-lookup"><span data-stu-id="a41d4-169">Represents an HTTP digest credential.</span></span> <span data-ttu-id="a41d4-170">该凭据是用户名和密码的哈希。</span><span class="sxs-lookup"><span data-stu-id="a41d4-170">The credential is a hash of the user name and password.</span></span>|  
|<xref:System.ServiceModel.Description.ClientCredentials.IssuedToken%2A>|<span data-ttu-id="a41d4-171">返回一个 <xref:System.ServiceModel.Security.IssuedTokenClientCredential></span><span class="sxs-lookup"><span data-stu-id="a41d4-171">Returns an <xref:System.ServiceModel.Security.IssuedTokenClientCredential></span></span>|<span data-ttu-id="a41d4-172">表示由安全令牌服务颁发的一个自定义安全令牌，通常用在联合方案中。</span><span class="sxs-lookup"><span data-stu-id="a41d4-172">Represents a custom security token issued by a Security Token Service, commonly used in federation scenarios.</span></span>|  
|<xref:System.ServiceModel.Description.ClientCredentials.Peer%2A>|<span data-ttu-id="a41d4-173">返回一个 <xref:System.ServiceModel.Security.PeerCredential></span><span class="sxs-lookup"><span data-stu-id="a41d4-173">Returns a <xref:System.ServiceModel.Security.PeerCredential></span></span>|<span data-ttu-id="a41d4-174">表示一个用于参与 Windows 域上的对等网格的对等凭据。</span><span class="sxs-lookup"><span data-stu-id="a41d4-174">Represents a Peer credential for participation in a Peer mesh on a Windows domain.</span></span>|  
|<xref:System.ServiceModel.Description.ClientCredentials.ServiceCertificate%2A>|<span data-ttu-id="a41d4-175">返回一个 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential></span><span class="sxs-lookup"><span data-stu-id="a41d4-175">Returns an <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential></span></span>|<span data-ttu-id="a41d4-176">表示服务在带外协商中提供的 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="a41d4-176">Represents an X.509 certificate provided by the service in an out-of-band negotiation.</span></span>|  
|<xref:System.ServiceModel.Description.ClientCredentials.UserName%2A>|<span data-ttu-id="a41d4-177">返回一个 <xref:System.ServiceModel.Security.UserNamePasswordClientCredential></span><span class="sxs-lookup"><span data-stu-id="a41d4-177">Returns a <xref:System.ServiceModel.Security.UserNamePasswordClientCredential></span></span>|<span data-ttu-id="a41d4-178">表示一个用户名和密码对。</span><span class="sxs-lookup"><span data-stu-id="a41d4-178">Represents a user name and password pair.</span></span>|  
|<xref:System.ServiceModel.Description.ClientCredentials.Windows%2A>|<span data-ttu-id="a41d4-179">返回一个 <xref:System.ServiceModel.Security.WindowsClientCredential></span><span class="sxs-lookup"><span data-stu-id="a41d4-179">Returns a <xref:System.ServiceModel.Security.WindowsClientCredential></span></span>|<span data-ttu-id="a41d4-180">表示 Windows 客户端凭据（Kerberos 凭据）。</span><span class="sxs-lookup"><span data-stu-id="a41d4-180">Represents a Windows client credential (a Kerberos credential).</span></span> <span data-ttu-id="a41d4-181">该类的属性是只读的。</span><span class="sxs-lookup"><span data-stu-id="a41d4-181">The properties of the class are read-only.</span></span>|  
  
#### <a name="setting-a-clientcredentials-value-in-configuration"></a><span data-ttu-id="a41d4-182">设置\<clientCredentials > 配置中的值</span><span class="sxs-lookup"><span data-stu-id="a41d4-182">Setting a \<clientCredentials> Value in Configuration</span></span>  
 <span data-ttu-id="a41d4-183">凭据值指定为的子元素使用的终结点行为[ \<clientCredentials >](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)元素。</span><span class="sxs-lookup"><span data-stu-id="a41d4-183">Credential values are specified by using an endpoint behavior as child elements of the [\<clientCredentials>](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) element.</span></span> <span data-ttu-id="a41d4-184">所使用的元素取决于客户端凭据类型。</span><span class="sxs-lookup"><span data-stu-id="a41d4-184">The element used depends on the client credential type.</span></span> <span data-ttu-id="a41d4-185">例如，下面的示例演示设置 X.509 证书使用的配置 <[\<clientCertificate >](../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md)。</span><span class="sxs-lookup"><span data-stu-id="a41d4-185">For example, the following example shows the configuration to set an X.509 certificate using the <[\<clientCertificate>](../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md).</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="myEndpointBehavior">  
          <clientCredentials>  
            <clientCertificate findvalue="myMachineName"   
            storeLocation="Current" X509FindType="FindBySubjectName" />  
          </clientCredentials>  
        </behavior>              
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="a41d4-186">若要在配置中设置客户端凭据，添加[ \<endpointBehaviors >](../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md)到配置文件的元素。</span><span class="sxs-lookup"><span data-stu-id="a41d4-186">To set the client credential in configuration, add an [\<endpointBehaviors>](../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md) element to the configuration file.</span></span> <span data-ttu-id="a41d4-187">此外，必须添加的行为元素链接到服务的终结点使用`behaviorConfiguration`的属性[\<终结点 >](https://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017)元素，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="a41d4-187">Additionally, the added behavior element must be linked to the service's endpoint using the `behaviorConfiguration` attribute of the [\<endpoint>](https://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017) element as shown in the following example.</span></span> <span data-ttu-id="a41d4-188">`behaviorConfiguration` 属性的值必须与行为 `name` 属性的值相匹配。</span><span class="sxs-lookup"><span data-stu-id="a41d4-188">The value of the `behaviorConfiguration` attribute must match the value of the behavior `name` attribute.</span></span>  
  
 `<configuration>`  
  
 `<system.serviceModel>`  
  
 `<client>`  
  
 `<endpoint address="http://localhost/servicemodelsamples/service.svc"`  
  
 `binding="wsHttpBinding"`  
  
 `bindingConfiguration="Binding1"`  
  
 `behaviorConfiguration="myEndpointBehavior"`  
  
 `contract="Microsoft.ServiceModel.Samples.ICalculator" />`  
  
 `</client>`  
  
 `</system.serviceModel>`  
  
 `</configuration>`  
  
> [!NOTE]
>  <span data-ttu-id="a41d4-189">有些客户端凭据值无法使用应用程序配置文件来设置，例如，用户名和密码值或 Windows 用户和密码值。</span><span class="sxs-lookup"><span data-stu-id="a41d4-189">Some of the client credential values cannot be set using application configuration files, for example, user name and password, or Windows user and password values.</span></span> <span data-ttu-id="a41d4-190">这种凭据值只能在代码中指定。</span><span class="sxs-lookup"><span data-stu-id="a41d4-190">Such credential values can be specified only in code.</span></span>  
  
 <span data-ttu-id="a41d4-191">有关设置客户端凭据的详细信息，请参阅[如何：指定客户端凭据值](../../../docs/framework/wcf/how-to-specify-client-credential-values.md)。</span><span class="sxs-lookup"><span data-stu-id="a41d4-191">For more information about setting the client credential, see [How to: Specify Client Credential Values](../../../docs/framework/wcf/how-to-specify-client-credential-values.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a41d4-192">当 `ClientCredentialType` 设置为 `SecurityMode` 时，`"TransportWithMessageCredential",` 将被忽略，如下面的示例配置所示。</span><span class="sxs-lookup"><span data-stu-id="a41d4-192">`ClientCredentialType` is ignored when `SecurityMode` is set to `"TransportWithMessageCredential",` as shown in the following sample configuration.</span></span>  
  
```xml  
<wsHttpBinding>  
    <binding name="PingBinding">  
        <security mode="TransportWithMessageCredential"  >  
           <message  clientCredentialType="UserName"   
               establishSecurityContext="false"    
               negotiateServiceCredential="false" />  
           <transport clientCredentialType="Certificate"  />  
         </security>  
    </binding>  
</wsHttpBinding>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a41d4-193">请参阅</span><span class="sxs-lookup"><span data-stu-id="a41d4-193">See also</span></span>
- <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A>
- <xref:System.ServiceModel.ClientBase%601>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A>
- <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetUrl%2A>
- [<span data-ttu-id="a41d4-194">\<bindings></span><span class="sxs-lookup"><span data-stu-id="a41d4-194">\<bindings></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)
- [<span data-ttu-id="a41d4-195">配置编辑器工具 (SvcConfigEditor.exe)</span><span class="sxs-lookup"><span data-stu-id="a41d4-195">Configuration Editor Tool (SvcConfigEditor.exe)</span></span>](../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)
- [<span data-ttu-id="a41d4-196">保护服务</span><span class="sxs-lookup"><span data-stu-id="a41d4-196">Securing Services</span></span>](../../../docs/framework/wcf/securing-services.md)
- [<span data-ttu-id="a41d4-197">使用 WCF 客户端访问服务</span><span class="sxs-lookup"><span data-stu-id="a41d4-197">Accessing Services Using a WCF Client</span></span>](../../../docs/framework/wcf/accessing-services-using-a-wcf-client.md)
- [<span data-ttu-id="a41d4-198">如何：指定客户端凭据值</span><span class="sxs-lookup"><span data-stu-id="a41d4-198">How to: Specify Client Credential Values</span></span>](../../../docs/framework/wcf/how-to-specify-client-credential-values.md)
- [<span data-ttu-id="a41d4-199">ServiceModel 元数据实用工具 (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="a41d4-199">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
- [<span data-ttu-id="a41d4-200">如何：指定客户端凭据类型</span><span class="sxs-lookup"><span data-stu-id="a41d4-200">How to: Specify the Client Credential Type</span></span>](../../../docs/framework/wcf/how-to-specify-the-client-credential-type.md)
