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
# <a name="network-element-network-settings"></a>\<网络>元素（网络设置）
配置外部简单邮件传输协议 （SMTP） 服务器的网络选项。  

[**\<配置>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<邮件设置>**](mailsettings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<斯姆特普>**](smtp-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<网络>**

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
  
### <a name="attributes"></a>属性  
  
|Attribute|说明|  
|---------------|-----------------|  
|`clientDomain`|指定要在初始 SMTP 协议请求中用于连接到 SMTP 邮件服务器的客户端域名。 默认值是发送请求的本地计算机的本地主机名称。|  
|`defaultCredentials`|指定是否应使用默认用户凭据访问 SMTP 事务中的 SMTP 邮件服务器。 默认值是 `false`。|  
|`enableSsl`|指定是否使用 SSL 访问 SMTP 邮件服务器。 默认值是 `false`。|  
|`host`|指定用于 SMTP 事务的 SMTP 邮件服务器的主机名。 此属性没有默认值。|  
|`password`|指定用于对 SMTP 邮件服务器进行身份验证的密码。 此属性没有默认值。|  
|`port`|指定用于连接到 SMTP 邮件服务器的端口号。 默认值为 25。|  
|`targetName`|指定用于对 SMTP 事务使用扩展保护的服务提供商名称 （SPN）。 此属性没有默认值。|  
|`userName`|指定用于对 SMTP 邮件服务器进行身份验证的用户名。 此属性没有默认值。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|说明|  
|-------------|-----------------|  
|[\<smtp>元素（网络设置）](smtp-element-network-settings.md)|配置简单的邮件传输协议 （SMTP） 邮件发送选项。|  
  
## <a name="remarks"></a>备注  
 某些 SMTP 服务器要求您在使用前向服务器进行身份验证。 如果要使用主机上的默认网络凭据进行身份验证，请将`defaultCredentials`属性设置为`true`。 该<xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType>属性可用于从适用的配置文件获取属性的`defaultCredentials`当前值。  
  
 您还可以使用基本身份验证（用户名和密码）对 SMTP 服务器进行身份验证。 要使用此选项，必须为指定的 SMTP 服务器指定有效的用户名和密码。  
  
> [!NOTE]
> 基本身份验证将`userName`和`password`值发送到未加密的服务器。 监视网络流量的任何人都可以查看您的凭据，并使用它们连接到服务器。 应考虑使用更安全的身份验证机制，如 Kerberos 或 NT LAN 管理器 （NTLM）。如果是`defaultCredentials``true`，如果服务器支持这些协议，将使用 Kerberos 或 NTLM。  
  
 基本身份验证和默认网络凭据选项是互斥的;如果设置为`defaultCredentials``true`并指定用户名和密码，则使用默认网络凭据，并忽略基本身份验证数据。  
  
 对于基本身份验证，如果指定`userName`了 ，则还应指定`password`以自行对邮件服务器进行身份验证。  
  
 该<xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType>属性可用于从适用的配置文件获取属性的`userName`当前值。 该<xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType>属性可用于从适用的配置文件获取属性的`password`当前值。 出于`password`安全原因，通常不会在配置文件中输入属性。  
  
 该`clientDomain`属性将初始 SMTP 协议请求中使用的客户端域名更改为 SMTP 服务器。 该`clientDomain`属性可以设置为本地计算机的完全限定域名，而不是默认情况下使用的本地主机名称。 这提高了 SMTP 协议标准的合规性。 默认值是发送请求的本地计算机的本地主机名称。 该<xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType>属性可用于从适用的配置文件获取属性的`clientDomain`当前值。  
  
 使用`targetName`扩展保护时，该属性用于身份验证。 默认值为"SMTPSVC/\<主机>"的形式，其中\<主机>是 SMTP 邮件服务器的主机名。 该<xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType>属性可用于从适用的配置文件获取属性的`targetName`当前值。  
  
 该`enableSsl`属性指定是否使用 SSL 访问 SMTP 邮件服务器。 该<xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>类仅支持 RFC 3207 中定义的通过传输层安全性实现安全 SMTP 的 SMTP 服务扩展。 在此模式下，SMTP 会话从未加密的通道开始，然后客户端向服务器发出 STARTTLS 命令，以便使用 SSL 切换到安全通信。 有关详细信息，请参阅互联网工程工作组 （IETF） 发布的 RFC 3207。  
  
 备用连接方法是在发送任何协议命令之前预先建立 SSL 会话。 此连接方法有时称为 SMTPS，默认情况下使用端口 465。 当前不支持使用此 SSL 的替代连接方法。  
  
 该<xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType>属性可用于从适用的配置文件获取属性的`enableSsl`当前值。  
  
## <a name="example"></a>示例  
 下面的示例指定使用默认网络凭据发送电子邮件的相应 SMTP 参数。  
  
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
  
## <a name="see-also"></a>另请参阅

- <xref:System.Net.Configuration.SmtpNetworkElement?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- [网络设置架构](index.md)
