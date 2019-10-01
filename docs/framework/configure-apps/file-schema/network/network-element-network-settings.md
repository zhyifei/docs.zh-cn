---
title: <network> 元素（网络设置）
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#network
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/network
helpviewer_keywords:
- <network> element
- network element
ms.assetid: 2c2c6ad4-ed11-48ab-b28e-2bc0ba9b42c7
ms.openlocfilehash: bac288bb28c4176e52366d0e0b7d8bc7d313cf96
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698010"
---
# <a name="network-element-network-settings"></a><span data-ttu-id="74a71-102">\<network > 元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="74a71-102">\<network> Element (Network Settings)</span></span>
<span data-ttu-id="74a71-103">配置外部简单邮件传输协议（SMTP）服务器的网络选项。</span><span class="sxs-lookup"><span data-stu-id="74a71-103">Configures the network options for an external Simple Mail Transport Protocol (SMTP) server.</span></span>  
  
[<span data-ttu-id="74a71-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="74a71-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="74a71-105">&nbsp; @ no__t[ **\<system >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="74a71-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="74a71-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t[ **\<mailSettings >** ](mailsettings-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="74a71-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)</span></span>  
<span data-ttu-id="74a71-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5[ **\<smtp >** ](smtp-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="74a71-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<smtp>**](smtp-element-network-settings.md)</span></span>  
<span data-ttu-id="74a71-108">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7 **\<network >**</span><span class="sxs-lookup"><span data-stu-id="74a71-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<network>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74a71-109">语法</span><span class="sxs-lookup"><span data-stu-id="74a71-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="74a71-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="74a71-110">Attributes and Elements</span></span>  
 <span data-ttu-id="74a71-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="74a71-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="74a71-112">特性</span><span class="sxs-lookup"><span data-stu-id="74a71-112">Attributes</span></span>  
  
|<span data-ttu-id="74a71-113">特性</span><span class="sxs-lookup"><span data-stu-id="74a71-113">Attribute</span></span>|<span data-ttu-id="74a71-114">描述</span><span class="sxs-lookup"><span data-stu-id="74a71-114">Description</span></span>|  
|---------------|-----------------|  
|`clientDomain`|<span data-ttu-id="74a71-115">指定要在初始 SMTP 协议请求中用来连接到 SMTP 邮件服务器的客户端域名。</span><span class="sxs-lookup"><span data-stu-id="74a71-115">Specifies the client domain name to use in the initial SMTP protocol request to connect to the SMTP mail server.</span></span> <span data-ttu-id="74a71-116">默认值为发送请求的本地计算机的本地主机名。</span><span class="sxs-lookup"><span data-stu-id="74a71-116">The default value is the localhost name of the local computer sending the request.</span></span>|  
|`defaultCredentials`|<span data-ttu-id="74a71-117">指定是否应使用默认用户凭据访问 smtp 邮件服务器以获取 SMTP 事务。</span><span class="sxs-lookup"><span data-stu-id="74a71-117">Specifies whether the default user credentials should be used to access the SMTP mail server for SMTP transactions.</span></span> <span data-ttu-id="74a71-118">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="74a71-118">The default value is `false`.</span></span>|  
|`enableSsl`|<span data-ttu-id="74a71-119">指定是否使用 SSL 访问 SMTP 邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="74a71-119">Specifies whether SSL is used to access an SMTP mail server.</span></span> <span data-ttu-id="74a71-120">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="74a71-120">The default value is `false`.</span></span>|  
|`host`|<span data-ttu-id="74a71-121">指定用于 SMTP 事务的 SMTP 邮件服务器的主机名。</span><span class="sxs-lookup"><span data-stu-id="74a71-121">Specifies the hostname of the SMTP mail server to use for SMTP transactions.</span></span> <span data-ttu-id="74a71-122">此属性没有默认值。</span><span class="sxs-lookup"><span data-stu-id="74a71-122">This attribute has no default value.</span></span>|  
|`password`|<span data-ttu-id="74a71-123">指定对 SMTP 邮件服务器进行身份验证时要使用的密码。</span><span class="sxs-lookup"><span data-stu-id="74a71-123">Specifies the password to use for authentication to the SMTP mail server.</span></span> <span data-ttu-id="74a71-124">此属性没有默认值。</span><span class="sxs-lookup"><span data-stu-id="74a71-124">This attribute has no default value.</span></span>|  
|`port`|<span data-ttu-id="74a71-125">指定用于连接到 SMTP 邮件服务器的端口号。</span><span class="sxs-lookup"><span data-stu-id="74a71-125">Specifies the port number to use to connect to the SMTP mail server.</span></span> <span data-ttu-id="74a71-126">默认值为 25。</span><span class="sxs-lookup"><span data-stu-id="74a71-126">The default value is 25.</span></span>|  
|`targetName`|<span data-ttu-id="74a71-127">指定在对 SMTP 事务使用扩展保护时用于身份验证的服务提供程序名称（SPN）。</span><span class="sxs-lookup"><span data-stu-id="74a71-127">Specifies the Service Provider Name (SPN) to use for authentication when using extended protection for SMTP transactions.</span></span> <span data-ttu-id="74a71-128">此属性没有默认值。</span><span class="sxs-lookup"><span data-stu-id="74a71-128">This attribute has no default value.</span></span>|  
|`userName`|<span data-ttu-id="74a71-129">指定用于对 SMTP 邮件服务器进行身份验证的用户名。</span><span class="sxs-lookup"><span data-stu-id="74a71-129">Specifies the user name to use for authentication to the SMTP mail server.</span></span> <span data-ttu-id="74a71-130">此属性没有默认值。</span><span class="sxs-lookup"><span data-stu-id="74a71-130">This attribute has no default value.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="74a71-131">子元素</span><span class="sxs-lookup"><span data-stu-id="74a71-131">Child Elements</span></span>  
 <span data-ttu-id="74a71-132">无。</span><span class="sxs-lookup"><span data-stu-id="74a71-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="74a71-133">父元素</span><span class="sxs-lookup"><span data-stu-id="74a71-133">Parent Elements</span></span>  
  
|<span data-ttu-id="74a71-134">元素</span><span class="sxs-lookup"><span data-stu-id="74a71-134">Element</span></span>|<span data-ttu-id="74a71-135">描述</span><span class="sxs-lookup"><span data-stu-id="74a71-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="74a71-136">\<smtp > 元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="74a71-136">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="74a71-137">配置简单邮件传输协议（SMTP）邮件发送选项。</span><span class="sxs-lookup"><span data-stu-id="74a71-137">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="74a71-138">备注</span><span class="sxs-lookup"><span data-stu-id="74a71-138">Remarks</span></span>  
 <span data-ttu-id="74a71-139">某些 SMTP 服务器要求在使用之前向服务器进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="74a71-139">Some SMTP servers require that you authenticate yourself to the server before use.</span></span> <span data-ttu-id="74a71-140">如果要使用主机上的默认网络凭据对自己进行身份验证，请将 `defaultCredentials` 特性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="74a71-140">If you want to authenticate yourself using the default network credentials on your host, set the `defaultCredentials` attribute to `true`.</span></span> <span data-ttu-id="74a71-141">@No__t-0 属性可用于从适用的配置文件中获取 @no__t 的属性的当前值。</span><span class="sxs-lookup"><span data-stu-id="74a71-141">The <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType> property can be used to get the current value of the `defaultCredentials` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="74a71-142">你还可以使用基本身份验证（用户名和密码）对 SMTP 服务器进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="74a71-142">You can also use basic authentication (a user name and password) to authenticate yourself to the SMTP server.</span></span> <span data-ttu-id="74a71-143">若要使用此选项，你必须为指定的 SMTP 服务器指定有效的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="74a71-143">To use this option, you must specify a valid user name and password for the specified SMTP server.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="74a71-144">基本身份验证将 @no__t 0 和 `password` 值发送到未加密的服务器。</span><span class="sxs-lookup"><span data-stu-id="74a71-144">Basic authentication sends the `userName` and `password` values to the server unencrypted.</span></span> <span data-ttu-id="74a71-145">监视网络流量的任何人都可以查看凭据并使用它们连接到服务器。</span><span class="sxs-lookup"><span data-stu-id="74a71-145">Anyone monitoring network traffic can view your credentials and use them to connect to the server.</span></span> <span data-ttu-id="74a71-146">你应考虑使用更安全的身份验证机制，如 Kerberos 或 NT LAN Manager （NTLM）。如果 `defaultCredentials` @no__t 为-1，则如果服务器支持这些协议，则将使用 Kerberos 或 NTLM。</span><span class="sxs-lookup"><span data-stu-id="74a71-146">You should consider using a more secure authentication mechanism, such as Kerberos or NT LAN Manager (NTLM.) If `defaultCredentials` is `true`, Kerberos or NTLM will be used if the server supports these protocols.</span></span>  
  
 <span data-ttu-id="74a71-147">基本身份验证和默认网络凭据选项相互排斥;如果将 @no__t 0 设置为 `true` 并指定用户名和密码，则将使用默认网络凭据，并忽略基本身份验证数据。</span><span class="sxs-lookup"><span data-stu-id="74a71-147">The basic authentication and default network credentials options are mutually exclusive; if you set `defaultCredentials` to `true` and specify a user name and password, the default network credential is used, and the basic authentication data is ignored.</span></span>  
  
 <span data-ttu-id="74a71-148">对于 "基本身份验证"，如果指定 `userName`，还应指定一个 @no__t 以自行向邮件服务器进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="74a71-148">For basic authentication if you specify a `userName`, you should also specify a `password` to authentication yourself to the mail server.</span></span>  
  
 <span data-ttu-id="74a71-149">@No__t-0 属性可用于从适用的配置文件中获取 @no__t 的属性的当前值。</span><span class="sxs-lookup"><span data-stu-id="74a71-149">The <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType> property can be used to get the current value of the `userName` attribute from applicable configuration files.</span></span> <span data-ttu-id="74a71-150">@No__t-0 属性可用于从适用的配置文件中获取 @no__t 的属性的当前值。</span><span class="sxs-lookup"><span data-stu-id="74a71-150">The <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType> property can be used to get the current value of the `password` attribute from applicable configuration files.</span></span> <span data-ttu-id="74a71-151">出于安全原因，通常不会将 `password` 特性输入到配置文件中。</span><span class="sxs-lookup"><span data-stu-id="74a71-151">A `password` attribute would not normally be entered in configuration files for security reasons.</span></span>  
  
 <span data-ttu-id="74a71-152">@No__t-0 特性将在初始 SMTP 协议请求中使用的客户端域名更改为 SMTP 服务器。</span><span class="sxs-lookup"><span data-stu-id="74a71-152">The `clientDomain` attribute changes the client domain name used in the initial SMTP protocol request to an SMTP server.</span></span> <span data-ttu-id="74a71-153">@No__t-0 属性可以设置为本地计算机的完全限定域名，而不能设置为默认使用的本地主机名。</span><span class="sxs-lookup"><span data-stu-id="74a71-153">The `clientDomain` attribute can be set to the fully-qualified domain name of the local machine, rather than the localhost name that is used by default.</span></span> <span data-ttu-id="74a71-154">这可以更好地符合 SMTP 协议标准。</span><span class="sxs-lookup"><span data-stu-id="74a71-154">This provides greater compliance with the SMTP protocol standards.</span></span> <span data-ttu-id="74a71-155">默认值为发送请求的本地计算机的本地主机名。</span><span class="sxs-lookup"><span data-stu-id="74a71-155">The default value is the localhost name of the local computer sending the request.</span></span> <span data-ttu-id="74a71-156">@No__t-0 属性可用于从适用的配置文件中获取 @no__t 的属性的当前值。</span><span class="sxs-lookup"><span data-stu-id="74a71-156">The <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType> property can be used to get the current value of the `clientDomain` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="74a71-157">使用扩展保护时，`targetName` 属性用于身份验证。</span><span class="sxs-lookup"><span data-stu-id="74a71-157">The `targetName` attribute is used for authentication when using extended protection.</span></span> <span data-ttu-id="74a71-158">默认值的格式为 "SMTPSVC/\<host >"，其中 \<host > 是 SMTP 邮件服务器的主机名。</span><span class="sxs-lookup"><span data-stu-id="74a71-158">The default value is of the form "SMTPSVC/\<host>" where \<host> is the hostname of the SMTP mail server.</span></span> <span data-ttu-id="74a71-159">@No__t-0 属性可用于从适用的配置文件中获取 @no__t 的属性的当前值。</span><span class="sxs-lookup"><span data-stu-id="74a71-159">The <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType> property can be used to get the current value of the `targetName` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="74a71-160">@No__t-0 属性指定是否使用 SSL 访问 SMTP 邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="74a71-160">The `enableSsl` attribute specifies whether SSL is used to access an SMTP mail server.</span></span> <span data-ttu-id="74a71-161"><xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>类仅支持在 RFC 3207 中定义的基于传输层安全性的安全 smtp 的 smtp 服务扩展。</span><span class="sxs-lookup"><span data-stu-id="74a71-161">The <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType> class only supports the SMTP Service Extension for Secure SMTP over Transport Layer Security as defined in RFC 3207.</span></span> <span data-ttu-id="74a71-162">在此模式下，SMTP 会话在未加密的通道上开始，然后客户端向服务器发出一个 STARTTLS 命令，以使用 SSL 切换到安全通信。</span><span class="sxs-lookup"><span data-stu-id="74a71-162">In this mode, the SMTP session begins on an unencrypted channel, then a STARTTLS command is issued by the client to the server to switch to secure communication using SSL.</span></span> <span data-ttu-id="74a71-163">有关详细信息，请参阅 Internet 工程任务组（IETF）发布的 RFC 3207。</span><span class="sxs-lookup"><span data-stu-id="74a71-163">See RFC 3207 published by the Internet Engineering Task Force (IETF) for more information.</span></span>  
  
 <span data-ttu-id="74a71-164">备用连接方法是在发送任何协议命令之前提前建立 SSL 会话的位置。</span><span class="sxs-lookup"><span data-stu-id="74a71-164">An alternate connection method is where an SSL session is established up front before any protocol commands are sent.</span></span> <span data-ttu-id="74a71-165">此连接方法有时称为 SMTPS，默认情况下使用端口465。</span><span class="sxs-lookup"><span data-stu-id="74a71-165">This connection method is sometimes called SMTPS and by default uses port 465.</span></span> <span data-ttu-id="74a71-166">当前不支持使用 SSL 的替代连接方法。</span><span class="sxs-lookup"><span data-stu-id="74a71-166">This alternate connection method using SSL is not currently supported.</span></span>  
  
 <span data-ttu-id="74a71-167">@No__t-0 属性可用于从适用的配置文件中获取 @no__t 的属性的当前值。</span><span class="sxs-lookup"><span data-stu-id="74a71-167">The <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType> property can be used to get the current value of the `enableSsl` attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="74a71-168">示例</span><span class="sxs-lookup"><span data-stu-id="74a71-168">Example</span></span>  
 <span data-ttu-id="74a71-169">下面的示例指定了使用默认网络凭据发送电子邮件所需的适当 SMTP 参数。</span><span class="sxs-lookup"><span data-stu-id="74a71-169">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="Network">  
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
  
## <a name="see-also"></a><span data-ttu-id="74a71-170">请参阅</span><span class="sxs-lookup"><span data-stu-id="74a71-170">See also</span></span>

- <xref:System.Net.Configuration.SmtpNetworkElement?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- [<span data-ttu-id="74a71-171">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="74a71-171">Network Settings Schema</span></span>](index.md)
