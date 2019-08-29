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
ms.openlocfilehash: ee60b990bc749dbb9c5d0e7426c57e9392ddf9d4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920973"
---
# <a name="network-element-network-settings"></a>\<network > 元素 (网络设置)
配置外部简单邮件传输协议 (SMTP) 服务器的网络选项。  
  
 \<configuration>  
\<system.net>  
\<mailSettings>  
\<smtp>  
\<network>  
  
## <a name="syntax"></a>语法  
  
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
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|`clientDomain`|指定要在初始 SMTP 协议请求中用来连接到 SMTP 邮件服务器的客户端域名。 默认值为发送请求的本地计算机的本地主机名。|  
|`defaultCredentials`|指定是否应使用默认用户凭据访问 smtp 邮件服务器以获取 SMTP 事务。 默认值为 `false`。|  
|`enableSsl`|指定是否使用 SSL 访问 SMTP 邮件服务器。 默认值为 `false`。|  
|`host`|指定用于 SMTP 事务的 SMTP 邮件服务器的主机名。 此属性没有默认值。|  
|`password`|指定对 SMTP 邮件服务器进行身份验证时要使用的密码。 此属性没有默认值。|  
|`port`|指定用于连接到 SMTP 邮件服务器的端口号。 默认值为 25。|  
|`targetName`|指定在对 SMTP 事务使用扩展保护时用于身份验证的服务提供程序名称 (SPN)。 此属性没有默认值。|  
|`userName`|指定用于对 SMTP 邮件服务器进行身份验证的用户名。 此属性没有默认值。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<smtp > 元素 (网络设置)](smtp-element-network-settings.md)|配置简单邮件传输协议 (SMTP) 邮件发送选项。|  
  
## <a name="remarks"></a>备注  
 某些 SMTP 服务器要求在使用之前向服务器进行身份验证。 如果要使用主机上的默认网络凭据对自己进行身份验证, 请将`defaultCredentials`属性设置`true`为。 属性可用于从适用的配置文件中获取`defaultCredentials`特性的当前值。 <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType>  
  
 你还可以使用基本身份验证 (用户名和密码) 对 SMTP 服务器进行身份验证。 若要使用此选项, 你必须为指定的 SMTP 服务器指定有效的用户名和密码。  
  
> [!NOTE]
> 基本身份验证将`userName`和`password`值发送到未加密的服务器。 监视网络流量的任何人都可以查看凭据并使用它们连接到服务器。 你应考虑使用更安全的身份验证机制, 如 Kerberos 或 NT LAN Manager (NTLM)。如果`defaultCredentials` 为`true`, 则如果服务器支持这些协议, 则将使用 Kerberos 或 NTLM。  
  
 基本身份验证和默认网络凭据选项相互排斥;如果将设置`defaultCredentials`为`true`并指定用户名和密码, 则将使用默认网络凭据, 并忽略基本身份验证数据。  
  
 对于基本身份验证`userName`, 如果指定, 则还应`password`指定, 以便自行向邮件服务器进行身份验证。  
  
 属性可用于从适用的配置文件中获取`userName`特性的当前值。 <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType> 属性可用于从适用的配置文件中获取`password`特性的当前值。 <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType> 出于`password`安全原因, 通常不会将属性输入到配置文件中。  
  
 `clientDomain`属性将在初始 smtp 协议请求中使用的客户端域名更改为 SMTP 服务器。 `clientDomain`属性可以设置为本地计算机的完全限定域名, 而不能设置为默认使用的 localhost 名称。 这可以更好地符合 SMTP 协议标准。 默认值为发送请求的本地计算机的本地主机名。 属性可用于从适用的配置文件中获取`clientDomain`特性的当前值。 <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType>  
  
 使用`targetName`扩展保护时, 此属性用于身份验证。 默认值的格式为 "SMTPSVC/\<host >", 其中\<host > 是 SMTP 邮件服务器的主机名。 属性可用于从适用的配置文件中获取`targetName`特性的当前值。 <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType>  
  
 `enableSsl`特性指定是否使用 SSL 访问 SMTP 邮件服务器。 <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>类仅支持在 RFC 3207 中定义的基于传输层安全性的安全 smtp 的 smtp 服务扩展。 在此模式下, SMTP 会话在未加密的通道上开始, 然后客户端向服务器发出一个 STARTTLS 命令, 以使用 SSL 切换到安全通信。 有关详细信息, 请参阅 Internet 工程任务组 (IETF) 发布的 RFC 3207。  
  
 备用连接方法是在发送任何协议命令之前提前建立 SSL 会话的位置。 此连接方法有时称为 SMTPS, 默认情况下使用端口465。 当前不支持使用 SSL 的替代连接方法。  
  
 属性可用于从适用的配置文件中获取`enableSsl`特性的当前值。 <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType>  
  
## <a name="example"></a>示例  
 下面的示例指定了使用默认网络凭据发送电子邮件所需的适当 SMTP 参数。  
  
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
  
## <a name="see-also"></a>请参阅

- <xref:System.Net.Configuration.SmtpNetworkElement?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- [网络设置架构](index.md)
