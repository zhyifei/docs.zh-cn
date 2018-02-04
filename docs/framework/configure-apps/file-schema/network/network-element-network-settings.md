---
title: "&lt;网络&gt;元素 （网络设置）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#network
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/network
helpviewer_keywords:
- <network> element
- network element
ms.assetid: 2c2c6ad4-ed11-48ab-b28e-2bc0ba9b42c7
caps.latest.revision: 
author: mcleblanc
ms.author: markl
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: 913765a4d8ac12d25dff446439f6a7510e6067ae
ms.sourcegitcommit: cf22b29db780e532e1090c6e755aa52d28273fa6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/01/2018
---
# <a name="ltnetworkgt-element-network-settings"></a><span data-ttu-id="cef12-102">&lt;网络&gt;元素 （网络设置）</span><span class="sxs-lookup"><span data-stu-id="cef12-102">&lt;network&gt; Element (Network Settings)</span></span>
<span data-ttu-id="cef12-103">配置外部简单邮件传输协议 (SMTP) 服务器的网络选项。</span><span class="sxs-lookup"><span data-stu-id="cef12-103">Configures the network options for an external Simple Mail Transport Protocol (SMTP) server.</span></span>  
  
 <span data-ttu-id="cef12-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="cef12-104">\<configuration></span></span>  
<span data-ttu-id="cef12-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="cef12-105">\<system.net></span></span>  
<span data-ttu-id="cef12-106">\<mailSettings></span><span class="sxs-lookup"><span data-stu-id="cef12-106">\<mailSettings></span></span>  
<span data-ttu-id="cef12-107">\<smtp></span><span class="sxs-lookup"><span data-stu-id="cef12-107">\<smtp></span></span>  
<span data-ttu-id="cef12-108">\<network></span><span class="sxs-lookup"><span data-stu-id="cef12-108">\<network></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cef12-109">语法</span><span class="sxs-lookup"><span data-stu-id="cef12-109">Syntax</span></span>  
  
```xml  
<network  
  clientDomain="string"   
  defaultCredentials="true|false"  
  enableSsl="true|false"  
  host="string"   
  password="string"  
  port="integer"   
  targetName="string"  
  userName="string"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cef12-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="cef12-110">Attributes and Elements</span></span>  
 <span data-ttu-id="cef12-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="cef12-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cef12-112">特性</span><span class="sxs-lookup"><span data-stu-id="cef12-112">Attributes</span></span>  
  
|<span data-ttu-id="cef12-113">特性</span><span class="sxs-lookup"><span data-stu-id="cef12-113">Attribute</span></span>|<span data-ttu-id="cef12-114">描述</span><span class="sxs-lookup"><span data-stu-id="cef12-114">Description</span></span>|  
|---------------|-----------------|  
|`clientDomain`|<span data-ttu-id="cef12-115">指定要在初始 SMTP 协议请求中用于连接到 SMTP 邮件服务器的客户端域名。</span><span class="sxs-lookup"><span data-stu-id="cef12-115">Specifies the client domain name to use in the initial SMTP protocol request to connect to the SMTP mail server.</span></span> <span data-ttu-id="cef12-116">默认值为本地计算机发送请求的 localhost 名称。</span><span class="sxs-lookup"><span data-stu-id="cef12-116">The default value is the localhost name of the local computer sending the request.</span></span>|  
|`defaultCredentials`|<span data-ttu-id="cef12-117">指定是否应使用默认用户凭据来访问 SMTP 事务的 SMTP 邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="cef12-117">Specifies whether the default user credentials should be used to access the SMTP mail server for SMTP transactions.</span></span> <span data-ttu-id="cef12-118">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="cef12-118">The default value is `false`.</span></span>|  
|`enableSsl`|<span data-ttu-id="cef12-119">指定是否使用 SSL 来访问 SMTP 邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="cef12-119">Specifies whether SSL is used to access an SMTP mail server.</span></span> <span data-ttu-id="cef12-120">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="cef12-120">The default value is `false`.</span></span>|  
|`host`|<span data-ttu-id="cef12-121">指定要使用的 SMTP 事务的 SMTP 邮件服务器的主机名。</span><span class="sxs-lookup"><span data-stu-id="cef12-121">Specifies the hostname of the SMTP mail server to use for SMTP transactions.</span></span> <span data-ttu-id="cef12-122">此属性包含没有默认值。</span><span class="sxs-lookup"><span data-stu-id="cef12-122">This attribute has no default value.</span></span>|  
|`password`|<span data-ttu-id="cef12-123">指定要用于对 SMTP 邮件服务器的身份验证的密码。</span><span class="sxs-lookup"><span data-stu-id="cef12-123">Specifies the password to use for authentication to the SMTP mail server.</span></span> <span data-ttu-id="cef12-124">此属性包含没有默认值。</span><span class="sxs-lookup"><span data-stu-id="cef12-124">This attribute has no default value.</span></span>|  
|`port`|<span data-ttu-id="cef12-125">指定要用于连接到 SMTP 邮件服务器的端口号。</span><span class="sxs-lookup"><span data-stu-id="cef12-125">Specifies the port number to use to connect to the SMTP mail server.</span></span> <span data-ttu-id="cef12-126">默认值为 25。</span><span class="sxs-lookup"><span data-stu-id="cef12-126">The default value is 25.</span></span>|  
|`targetName`|<span data-ttu-id="cef12-127">指定的 SMTP 事务使用扩展的保护时，用于进行身份验证服务提供程序名称 (SPN)。</span><span class="sxs-lookup"><span data-stu-id="cef12-127">Specifies the Service Provider Name (SPN) to use for authentication when using extended protection for SMTP transactions.</span></span> <span data-ttu-id="cef12-128">此属性包含没有默认值。</span><span class="sxs-lookup"><span data-stu-id="cef12-128">This attribute has no default value.</span></span>|  
|`userName`|<span data-ttu-id="cef12-129">指定要用于对 SMTP 邮件服务器的身份验证的用户名。</span><span class="sxs-lookup"><span data-stu-id="cef12-129">Specifies the user name to use for authentication to the SMTP mail server.</span></span> <span data-ttu-id="cef12-130">此属性包含没有默认值。</span><span class="sxs-lookup"><span data-stu-id="cef12-130">This attribute has no default value.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cef12-131">子元素</span><span class="sxs-lookup"><span data-stu-id="cef12-131">Child Elements</span></span>  
 <span data-ttu-id="cef12-132">无。</span><span class="sxs-lookup"><span data-stu-id="cef12-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cef12-133">父元素</span><span class="sxs-lookup"><span data-stu-id="cef12-133">Parent Elements</span></span>  
  
|<span data-ttu-id="cef12-134">元素</span><span class="sxs-lookup"><span data-stu-id="cef12-134">Element</span></span>|<span data-ttu-id="cef12-135">描述</span><span class="sxs-lookup"><span data-stu-id="cef12-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cef12-136">\<smtp > 元素 （网络设置）</span><span class="sxs-lookup"><span data-stu-id="cef12-136">\<smtp> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|<span data-ttu-id="cef12-137">配置简单邮件传输协议 (SMTP) 邮件发送选项。</span><span class="sxs-lookup"><span data-stu-id="cef12-137">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cef12-138">备注</span><span class="sxs-lookup"><span data-stu-id="cef12-138">Remarks</span></span>  
 <span data-ttu-id="cef12-139">有些 SMTP 服务器要求，你的身份验证在使用之前的服务器。</span><span class="sxs-lookup"><span data-stu-id="cef12-139">Some SMTP servers require that you authenticate yourself to the server before use.</span></span> <span data-ttu-id="cef12-140">如果你想要在主机上使用的默认网络凭据自行进行身份验证，请将设置`defaultCredentials`属性设为`true`。</span><span class="sxs-lookup"><span data-stu-id="cef12-140">If you want to authenticate yourself using the default network credentials on your host, set the `defaultCredentials` attribute to `true`.</span></span> <span data-ttu-id="cef12-141"><xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType>属性可以用于获取的当前值`defaultCredentials`从适用的配置文件的属性。</span><span class="sxs-lookup"><span data-stu-id="cef12-141">The <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType> property can be used to get the current value of the `defaultCredentials` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="cef12-142">你还可以使用基本身份验证 （用户名和密码） 进行身份验证到 SMTP 服务器。</span><span class="sxs-lookup"><span data-stu-id="cef12-142">You can also use basic authentication (a user name and password) to authenticate yourself to the SMTP server.</span></span> <span data-ttu-id="cef12-143">若要使用此选项，必须指定有效的用户名称和指定的 SMTP 服务器的密码。</span><span class="sxs-lookup"><span data-stu-id="cef12-143">To use this option, you must specify a valid user name and password for the specified SMTP server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cef12-144">基本身份验证发送`userName`和`password`到服务器以未加密状态的值。</span><span class="sxs-lookup"><span data-stu-id="cef12-144">Basic authentication sends the `userName` and `password` values to the server unencrypted.</span></span> <span data-ttu-id="cef12-145">监视网络流量的任何人都可以查看你的凭据和使用它们来连接到服务器。</span><span class="sxs-lookup"><span data-stu-id="cef12-145">Anyone monitoring network traffic can view your credentials and use them to connect to the server.</span></span> <span data-ttu-id="cef12-146">你应考虑使用更安全的身份验证机制，例如 Kerberos 或 NT LAN Manager (NTLM)。如果`defaultCredentials`是`true`，将使用 Kerberos 或 NTLM，如果服务器支持这些协议。</span><span class="sxs-lookup"><span data-stu-id="cef12-146">You should consider using a more secure authentication mechanism, such as Kerberos or NT LAN Manager (NTLM.) If `defaultCredentials` is `true`, Kerberos or NTLM will be used if the server supports these protocols.</span></span>  
  
 <span data-ttu-id="cef12-147">基本身份验证和默认网络凭据选项是互斥;如果你设置`defaultCredentials`到`true`并指定用户名和密码，使用的默认网络凭据，并且忽略基本身份验证数据。</span><span class="sxs-lookup"><span data-stu-id="cef12-147">The basic authentication and default network credentials options are mutually exclusive; if you set `defaultCredentials` to `true` and specify a user name and password, the default network credential is used, and the basic authentication data is ignored.</span></span>  
  
 <span data-ttu-id="cef12-148">如果你指定的基本身份验证的`userName`，还应指定`password`到身份验证自己到邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="cef12-148">For basic authentication if you specify a `userName`, you should also specify a `password` to authentication yourself to the mail server.</span></span>  
  
 <span data-ttu-id="cef12-149"><xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType>属性可以用于获取的当前值`userName`从适用的配置文件的属性。</span><span class="sxs-lookup"><span data-stu-id="cef12-149">The <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType> property can be used to get the current value of the `userName` attribute from applicable configuration files.</span></span> <span data-ttu-id="cef12-150"><xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType>属性可以用于获取的当前值`password`从适用的配置文件的属性。</span><span class="sxs-lookup"><span data-stu-id="cef12-150">The <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType> property can be used to get the current value of the `password` attribute from applicable configuration files.</span></span> <span data-ttu-id="cef12-151">A`password`属性将不正常情况下输入在出于安全原因的配置文件中。</span><span class="sxs-lookup"><span data-stu-id="cef12-151">A `password` attribute would not normally be entered in configuration files for security reasons.</span></span>  
  
 <span data-ttu-id="cef12-152">`clientDomain`属性将更改对 SMTP 服务器的初始 SMTP 协议请求中使用的客户端域名称。</span><span class="sxs-lookup"><span data-stu-id="cef12-152">The `clientDomain` attribute changes the client domain name used in the initial SMTP protocol request to an SMTP server.</span></span> <span data-ttu-id="cef12-153">`clientDomain`属性可以设置为本地计算机的完全限定域名，而不是默认情况下使用 localhost 名称。</span><span class="sxs-lookup"><span data-stu-id="cef12-153">The `clientDomain` attribute can be set to the fully-qualified domain name of the local machine, rather than the localhost name that is used by default.</span></span> <span data-ttu-id="cef12-154">这提供了更好地遵守 SMTP 协议标准。</span><span class="sxs-lookup"><span data-stu-id="cef12-154">This provides greater compliance with the SMTP protocol standards.</span></span> <span data-ttu-id="cef12-155">默认值为本地计算机发送请求的 localhost 名称。</span><span class="sxs-lookup"><span data-stu-id="cef12-155">The default value is the localhost name of the local computer sending the request.</span></span> <span data-ttu-id="cef12-156"><xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType>属性可以用于获取的当前值`clientDomain`从适用的配置文件的属性。</span><span class="sxs-lookup"><span data-stu-id="cef12-156">The <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType> property can be used to get the current value of the `clientDomain` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="cef12-157">`targetName`使用扩展的保护时，属性用于身份验证。</span><span class="sxs-lookup"><span data-stu-id="cef12-157">The `targetName` attribute is used for authentication when using extended protection.</span></span> <span data-ttu-id="cef12-158">默认值是窗体"SMTPSVC /\<主机 >"其中\<主机 > 是 SMTP 邮件服务器的主机名。</span><span class="sxs-lookup"><span data-stu-id="cef12-158">The default value is of the form "SMTPSVC/\<host>" where \<host> is the hostname of the SMTP mail server.</span></span> <span data-ttu-id="cef12-159"><xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType>属性可以用于获取的当前值`targetName`从适用的配置文件的属性。</span><span class="sxs-lookup"><span data-stu-id="cef12-159">The <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType> property can be used to get the current value of the `targetName` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="cef12-160">`enableSsl`属性指定是否使用 SSL 来访问 SMTP 邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="cef12-160">The `enableSsl` attribute specifies whether SSL is used to access an SMTP mail server.</span></span> <span data-ttu-id="cef12-161"><xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>类只支持 SMTP 服务扩展安全 SMTP 通过传输层安全性 RFC 3207 中定义。</span><span class="sxs-lookup"><span data-stu-id="cef12-161">The <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType> class only supports the SMTP Service Extension for Secure SMTP over Transport Layer Security as defined in RFC 3207.</span></span> <span data-ttu-id="cef12-162">在此模式下，SMTP 会话从开始时未加密通道，然后执行 STARTTLS 命令颁发客户端到服务器以切换到使用 SSL 的安全通信。</span><span class="sxs-lookup"><span data-stu-id="cef12-162">In this mode, the SMTP session begins on an unencrypted channel, then a STARTTLS command is issued by the client to the server to switch to secure communication using SSL.</span></span> <span data-ttu-id="cef12-163">请参阅 RFC 3207 发布通过 Internet 工程任务组 (IETF) 有关详细信息。</span><span class="sxs-lookup"><span data-stu-id="cef12-163">See RFC 3207 published by the Internet Engineering Task Force (IETF) for more information.</span></span>  
  
 <span data-ttu-id="cef12-164">备用连接另一方法是其中任何协议命令发送之前预先建立 SSL 会话。</span><span class="sxs-lookup"><span data-stu-id="cef12-164">An alternate connection method is where an SSL session is established up front before any protocol commands are sent.</span></span> <span data-ttu-id="cef12-165">此连接方法有时被称为 SMTPS 和默认使用端口 465。</span><span class="sxs-lookup"><span data-stu-id="cef12-165">This connection method is sometimes called SMTPS and by default uses port 465.</span></span> <span data-ttu-id="cef12-166">当前不支持使用 SSL 此备用连接方法。</span><span class="sxs-lookup"><span data-stu-id="cef12-166">This alternate connection method using SSL is not currently supported.</span></span>  
  
 <span data-ttu-id="cef12-167"><xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType>属性可以用于获取的当前值`enableSsl`从适用的配置文件的属性。</span><span class="sxs-lookup"><span data-stu-id="cef12-167">The <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType> property can be used to get the current value of the `enableSsl` attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cef12-168">示例</span><span class="sxs-lookup"><span data-stu-id="cef12-168">Example</span></span>  
 <span data-ttu-id="cef12-169">下面的示例指定适当的 SMTP 参数，以使用默认网络凭据发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="cef12-169">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="network">  
        <network  
          clientDomain="www.contoso.com"  
          defaultCredentials="true"  
          enableSsl="false"  
          host="mail.contoso.com"  
          port="25"  
        />  
      </smtp>  
    </mailSettings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cef12-170">请参阅</span><span class="sxs-lookup"><span data-stu-id="cef12-170">See Also</span></span>  
 <xref:System.Net.Configuration.SmtpNetworkElement?displayProperty=nameWithType>  
 <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>  
 <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>  
 [<span data-ttu-id="cef12-171">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="cef12-171">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
