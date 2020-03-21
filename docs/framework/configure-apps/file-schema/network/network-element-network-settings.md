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
ms.openlocfilehash: f7cfcc3b9d5a717c23175cd15aa48ae97c828e57
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154811"
---
# <a name="network-element-network-settings"></a><span data-ttu-id="75809-102">\<网络>元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="75809-102">\<network> Element (Network Settings)</span></span>
<span data-ttu-id="75809-103">配置外部简单邮件传输协议 （SMTP） 服务器的网络选项。</span><span class="sxs-lookup"><span data-stu-id="75809-103">Configures the network options for an external Simple Mail Transport Protocol (SMTP) server.</span></span>  

<span data-ttu-id="75809-104">[**\<配置>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="75809-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="75809-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="75809-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="75809-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<邮件设置>**](mailsettings-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="75809-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)</span></span>\
<span data-ttu-id="75809-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<斯姆特普>**](smtp-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="75809-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<smtp>**](smtp-element-network-settings.md)</span></span>\
<span data-ttu-id="75809-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<网络>**</span><span class="sxs-lookup"><span data-stu-id="75809-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<network>**</span></span>

## <a name="syntax"></a><span data-ttu-id="75809-109">语法</span><span class="sxs-lookup"><span data-stu-id="75809-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="75809-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="75809-110">Attributes and Elements</span></span>  
 <span data-ttu-id="75809-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="75809-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="75809-112">属性</span><span class="sxs-lookup"><span data-stu-id="75809-112">Attributes</span></span>  
  
|<span data-ttu-id="75809-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="75809-113">Attribute</span></span>|<span data-ttu-id="75809-114">说明</span><span class="sxs-lookup"><span data-stu-id="75809-114">Description</span></span>|  
|---------------|-----------------|  
|`clientDomain`|<span data-ttu-id="75809-115">指定要在初始 SMTP 协议请求中用于连接到 SMTP 邮件服务器的客户端域名。</span><span class="sxs-lookup"><span data-stu-id="75809-115">Specifies the client domain name to use in the initial SMTP protocol request to connect to the SMTP mail server.</span></span> <span data-ttu-id="75809-116">默认值是发送请求的本地计算机的本地主机名称。</span><span class="sxs-lookup"><span data-stu-id="75809-116">The default value is the localhost name of the local computer sending the request.</span></span>|  
|`defaultCredentials`|<span data-ttu-id="75809-117">指定是否应使用默认用户凭据访问 SMTP 事务中的 SMTP 邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="75809-117">Specifies whether the default user credentials should be used to access the SMTP mail server for SMTP transactions.</span></span> <span data-ttu-id="75809-118">默认值是 `false`。</span><span class="sxs-lookup"><span data-stu-id="75809-118">The default value is `false`.</span></span>|  
|`enableSsl`|<span data-ttu-id="75809-119">指定是否使用 SSL 访问 SMTP 邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="75809-119">Specifies whether SSL is used to access an SMTP mail server.</span></span> <span data-ttu-id="75809-120">默认值是 `false`。</span><span class="sxs-lookup"><span data-stu-id="75809-120">The default value is `false`.</span></span>|  
|`host`|<span data-ttu-id="75809-121">指定用于 SMTP 事务的 SMTP 邮件服务器的主机名。</span><span class="sxs-lookup"><span data-stu-id="75809-121">Specifies the hostname of the SMTP mail server to use for SMTP transactions.</span></span> <span data-ttu-id="75809-122">此属性没有默认值。</span><span class="sxs-lookup"><span data-stu-id="75809-122">This attribute has no default value.</span></span>|  
|`password`|<span data-ttu-id="75809-123">指定用于对 SMTP 邮件服务器进行身份验证的密码。</span><span class="sxs-lookup"><span data-stu-id="75809-123">Specifies the password to use for authentication to the SMTP mail server.</span></span> <span data-ttu-id="75809-124">此属性没有默认值。</span><span class="sxs-lookup"><span data-stu-id="75809-124">This attribute has no default value.</span></span>|  
|`port`|<span data-ttu-id="75809-125">指定用于连接到 SMTP 邮件服务器的端口号。</span><span class="sxs-lookup"><span data-stu-id="75809-125">Specifies the port number to use to connect to the SMTP mail server.</span></span> <span data-ttu-id="75809-126">默认值为 25。</span><span class="sxs-lookup"><span data-stu-id="75809-126">The default value is 25.</span></span>|  
|`targetName`|<span data-ttu-id="75809-127">指定用于对 SMTP 事务使用扩展保护的服务提供商名称 （SPN）。</span><span class="sxs-lookup"><span data-stu-id="75809-127">Specifies the Service Provider Name (SPN) to use for authentication when using extended protection for SMTP transactions.</span></span> <span data-ttu-id="75809-128">此属性没有默认值。</span><span class="sxs-lookup"><span data-stu-id="75809-128">This attribute has no default value.</span></span>|  
|`userName`|<span data-ttu-id="75809-129">指定用于对 SMTP 邮件服务器进行身份验证的用户名。</span><span class="sxs-lookup"><span data-stu-id="75809-129">Specifies the user name to use for authentication to the SMTP mail server.</span></span> <span data-ttu-id="75809-130">此属性没有默认值。</span><span class="sxs-lookup"><span data-stu-id="75809-130">This attribute has no default value.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="75809-131">子元素</span><span class="sxs-lookup"><span data-stu-id="75809-131">Child Elements</span></span>  
 <span data-ttu-id="75809-132">无。</span><span class="sxs-lookup"><span data-stu-id="75809-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="75809-133">父元素</span><span class="sxs-lookup"><span data-stu-id="75809-133">Parent Elements</span></span>  
  
|<span data-ttu-id="75809-134">元素</span><span class="sxs-lookup"><span data-stu-id="75809-134">Element</span></span>|<span data-ttu-id="75809-135">说明</span><span class="sxs-lookup"><span data-stu-id="75809-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="75809-136">\<smtp>元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="75809-136">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="75809-137">配置简单的邮件传输协议 （SMTP） 邮件发送选项。</span><span class="sxs-lookup"><span data-stu-id="75809-137">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="75809-138">备注</span><span class="sxs-lookup"><span data-stu-id="75809-138">Remarks</span></span>  
 <span data-ttu-id="75809-139">某些 SMTP 服务器要求您在使用前向服务器进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="75809-139">Some SMTP servers require that you authenticate yourself to the server before use.</span></span> <span data-ttu-id="75809-140">如果要使用主机上的默认网络凭据进行身份验证，请将`defaultCredentials`属性设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="75809-140">If you want to authenticate yourself using the default network credentials on your host, set the `defaultCredentials` attribute to `true`.</span></span> <span data-ttu-id="75809-141">该<xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType>属性可用于从适用的配置文件获取属性的`defaultCredentials`当前值。</span><span class="sxs-lookup"><span data-stu-id="75809-141">The <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType> property can be used to get the current value of the `defaultCredentials` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="75809-142">您还可以使用基本身份验证（用户名和密码）对 SMTP 服务器进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="75809-142">You can also use basic authentication (a user name and password) to authenticate yourself to the SMTP server.</span></span> <span data-ttu-id="75809-143">要使用此选项，必须为指定的 SMTP 服务器指定有效的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="75809-143">To use this option, you must specify a valid user name and password for the specified SMTP server.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="75809-144">基本身份验证将`userName`和`password`值发送到未加密的服务器。</span><span class="sxs-lookup"><span data-stu-id="75809-144">Basic authentication sends the `userName` and `password` values to the server unencrypted.</span></span> <span data-ttu-id="75809-145">监视网络流量的任何人都可以查看您的凭据，并使用它们连接到服务器。</span><span class="sxs-lookup"><span data-stu-id="75809-145">Anyone monitoring network traffic can view your credentials and use them to connect to the server.</span></span> <span data-ttu-id="75809-146">应考虑使用更安全的身份验证机制，如 Kerberos 或 NT LAN 管理器 （NTLM）。如果是`defaultCredentials``true`，如果服务器支持这些协议，将使用 Kerberos 或 NTLM。</span><span class="sxs-lookup"><span data-stu-id="75809-146">You should consider using a more secure authentication mechanism, such as Kerberos or NT LAN Manager (NTLM.) If `defaultCredentials` is `true`, Kerberos or NTLM will be used if the server supports these protocols.</span></span>  
  
 <span data-ttu-id="75809-147">基本身份验证和默认网络凭据选项是互斥的;如果设置为`defaultCredentials``true`并指定用户名和密码，则使用默认网络凭据，并忽略基本身份验证数据。</span><span class="sxs-lookup"><span data-stu-id="75809-147">The basic authentication and default network credentials options are mutually exclusive; if you set `defaultCredentials` to `true` and specify a user name and password, the default network credential is used, and the basic authentication data is ignored.</span></span>  
  
 <span data-ttu-id="75809-148">对于基本身份验证，如果指定`userName`了 ，则还应指定`password`以自行对邮件服务器进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="75809-148">For basic authentication if you specify a `userName`, you should also specify a `password` to authentication yourself to the mail server.</span></span>  
  
 <span data-ttu-id="75809-149">该<xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType>属性可用于从适用的配置文件获取属性的`userName`当前值。</span><span class="sxs-lookup"><span data-stu-id="75809-149">The <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType> property can be used to get the current value of the `userName` attribute from applicable configuration files.</span></span> <span data-ttu-id="75809-150">该<xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType>属性可用于从适用的配置文件获取属性的`password`当前值。</span><span class="sxs-lookup"><span data-stu-id="75809-150">The <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType> property can be used to get the current value of the `password` attribute from applicable configuration files.</span></span> <span data-ttu-id="75809-151">出于`password`安全原因，通常不会在配置文件中输入属性。</span><span class="sxs-lookup"><span data-stu-id="75809-151">A `password` attribute would not normally be entered in configuration files for security reasons.</span></span>  
  
 <span data-ttu-id="75809-152">该`clientDomain`属性将初始 SMTP 协议请求中使用的客户端域名更改为 SMTP 服务器。</span><span class="sxs-lookup"><span data-stu-id="75809-152">The `clientDomain` attribute changes the client domain name used in the initial SMTP protocol request to an SMTP server.</span></span> <span data-ttu-id="75809-153">该`clientDomain`属性可以设置为本地计算机的完全限定域名，而不是默认情况下使用的本地主机名称。</span><span class="sxs-lookup"><span data-stu-id="75809-153">The `clientDomain` attribute can be set to the fully-qualified domain name of the local machine, rather than the localhost name that is used by default.</span></span> <span data-ttu-id="75809-154">这提高了 SMTP 协议标准的合规性。</span><span class="sxs-lookup"><span data-stu-id="75809-154">This provides greater compliance with the SMTP protocol standards.</span></span> <span data-ttu-id="75809-155">默认值是发送请求的本地计算机的本地主机名称。</span><span class="sxs-lookup"><span data-stu-id="75809-155">The default value is the localhost name of the local computer sending the request.</span></span> <span data-ttu-id="75809-156">该<xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType>属性可用于从适用的配置文件获取属性的`clientDomain`当前值。</span><span class="sxs-lookup"><span data-stu-id="75809-156">The <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType> property can be used to get the current value of the `clientDomain` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="75809-157">使用`targetName`扩展保护时，该属性用于身份验证。</span><span class="sxs-lookup"><span data-stu-id="75809-157">The `targetName` attribute is used for authentication when using extended protection.</span></span> <span data-ttu-id="75809-158">默认值为"SMTPSVC/\<主机>"的形式，其中\<主机>是 SMTP 邮件服务器的主机名。</span><span class="sxs-lookup"><span data-stu-id="75809-158">The default value is of the form "SMTPSVC/\<host>" where \<host> is the hostname of the SMTP mail server.</span></span> <span data-ttu-id="75809-159">该<xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType>属性可用于从适用的配置文件获取属性的`targetName`当前值。</span><span class="sxs-lookup"><span data-stu-id="75809-159">The <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType> property can be used to get the current value of the `targetName` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="75809-160">该`enableSsl`属性指定是否使用 SSL 访问 SMTP 邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="75809-160">The `enableSsl` attribute specifies whether SSL is used to access an SMTP mail server.</span></span> <span data-ttu-id="75809-161">该<xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>类仅支持 RFC 3207 中定义的通过传输层安全性实现安全 SMTP 的 SMTP 服务扩展。</span><span class="sxs-lookup"><span data-stu-id="75809-161">The <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType> class only supports the SMTP Service Extension for Secure SMTP over Transport Layer Security as defined in RFC 3207.</span></span> <span data-ttu-id="75809-162">在此模式下，SMTP 会话从未加密的通道开始，然后客户端向服务器发出 STARTTLS 命令，以便使用 SSL 切换到安全通信。</span><span class="sxs-lookup"><span data-stu-id="75809-162">In this mode, the SMTP session begins on an unencrypted channel, then a STARTTLS command is issued by the client to the server to switch to secure communication using SSL.</span></span> <span data-ttu-id="75809-163">有关详细信息，请参阅互联网工程工作组 （IETF） 发布的 RFC 3207。</span><span class="sxs-lookup"><span data-stu-id="75809-163">See RFC 3207 published by the Internet Engineering Task Force (IETF) for more information.</span></span>  
  
 <span data-ttu-id="75809-164">备用连接方法是在发送任何协议命令之前预先建立 SSL 会话。</span><span class="sxs-lookup"><span data-stu-id="75809-164">An alternate connection method is where an SSL session is established up front before any protocol commands are sent.</span></span> <span data-ttu-id="75809-165">此连接方法有时称为 SMTPS，默认情况下使用端口 465。</span><span class="sxs-lookup"><span data-stu-id="75809-165">This connection method is sometimes called SMTPS and by default uses port 465.</span></span> <span data-ttu-id="75809-166">当前不支持使用此 SSL 的替代连接方法。</span><span class="sxs-lookup"><span data-stu-id="75809-166">This alternate connection method using SSL is not currently supported.</span></span>  
  
 <span data-ttu-id="75809-167">该<xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType>属性可用于从适用的配置文件获取属性的`enableSsl`当前值。</span><span class="sxs-lookup"><span data-stu-id="75809-167">The <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType> property can be used to get the current value of the `enableSsl` attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="75809-168">示例</span><span class="sxs-lookup"><span data-stu-id="75809-168">Example</span></span>  
 <span data-ttu-id="75809-169">下面的示例指定使用默认网络凭据发送电子邮件的相应 SMTP 参数。</span><span class="sxs-lookup"><span data-stu-id="75809-169">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="75809-170">另请参阅</span><span class="sxs-lookup"><span data-stu-id="75809-170">See also</span></span>

- <xref:System.Net.Configuration.SmtpNetworkElement?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- [<span data-ttu-id="75809-171">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="75809-171">Network Settings Schema</span></span>](index.md)
