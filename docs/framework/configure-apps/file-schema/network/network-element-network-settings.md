---
title: '&lt;网络&gt;元素 （网络设置）'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#network
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/network
helpviewer_keywords:
- <network> element
- network element
ms.assetid: 2c2c6ad4-ed11-48ab-b28e-2bc0ba9b42c7
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: e53d39f15a01f751a93c5531b3079d77bf0040e4
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltnetworkgt-element-network-settings"></a>&lt;网络&gt;元素 （网络设置）
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
|`clientDomain`|指定要在初始 SMTP 协议请求中用于连接到 SMTP 邮件服务器的客户端域名。 默认值为本地计算机发送请求的 localhost 名称。|  
|`defaultCredentials`|指定是否应使用默认用户凭据来访问 SMTP 事务的 SMTP 邮件服务器。 默认值为 `false`。|  
|`enableSsl`|指定是否使用 SSL 来访问 SMTP 邮件服务器。 默认值为 `false`。|  
|`host`|指定要使用的 SMTP 事务的 SMTP 邮件服务器的主机名。 此属性包含没有默认值。|  
|`password`|指定要用于对 SMTP 邮件服务器的身份验证的密码。 此属性包含没有默认值。|  
|`port`|指定要用于连接到 SMTP 邮件服务器的端口号。 默认值为 25。|  
|`targetName`|指定的 SMTP 事务使用扩展的保护时，用于进行身份验证服务提供程序名称 (SPN)。 此属性包含没有默认值。|  
|`userName`|指定要用于对 SMTP 邮件服务器的身份验证的用户名。 此属性包含没有默认值。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<smtp > 元素 （网络设置）](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|配置简单邮件传输协议 (SMTP) 邮件发送选项。|  
  
## <a name="remarks"></a>备注  
 有些 SMTP 服务器要求，你的身份验证在使用之前的服务器。 如果你想要在主机上使用的默认网络凭据自行进行身份验证，请将设置`defaultCredentials`属性设为`true`。 <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType>属性可以用于获取的当前值`defaultCredentials`从适用的配置文件的属性。  
  
 你还可以使用基本身份验证 （用户名和密码） 进行身份验证到 SMTP 服务器。 若要使用此选项，必须指定有效的用户名称和指定的 SMTP 服务器的密码。  
  
> [!NOTE]
>  基本身份验证发送`userName`和`password`到服务器以未加密状态的值。 监视网络流量的任何人都可以查看你的凭据和使用它们来连接到服务器。 你应考虑使用更安全的身份验证机制，例如 Kerberos 或 NT LAN Manager (NTLM)。如果`defaultCredentials`是`true`，将使用 Kerberos 或 NTLM，如果服务器支持这些协议。  
  
 基本身份验证和默认网络凭据选项是互斥;如果你设置`defaultCredentials`到`true`并指定用户名和密码，使用的默认网络凭据，并且忽略基本身份验证数据。  
  
 如果你指定的基本身份验证的`userName`，还应指定`password`到身份验证自己到邮件服务器。  
  
 <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType>属性可以用于获取的当前值`userName`从适用的配置文件的属性。 <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType>属性可以用于获取的当前值`password`从适用的配置文件的属性。 A`password`属性将不正常情况下输入在出于安全原因的配置文件中。  
  
 `clientDomain`属性将更改对 SMTP 服务器的初始 SMTP 协议请求中使用的客户端域名称。 `clientDomain`属性可以设置为本地计算机的完全限定域名，而不是默认情况下使用 localhost 名称。 这提供了更好地遵守 SMTP 协议标准。 默认值为本地计算机发送请求的 localhost 名称。 <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType>属性可以用于获取的当前值`clientDomain`从适用的配置文件的属性。  
  
 `targetName`使用扩展的保护时，属性用于身份验证。 默认值是窗体"SMTPSVC /\<主机 >"其中\<主机 > 是 SMTP 邮件服务器的主机名。 <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType>属性可以用于获取的当前值`targetName`从适用的配置文件的属性。  
  
 `enableSsl`属性指定是否使用 SSL 来访问 SMTP 邮件服务器。 <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>类只支持 SMTP 服务扩展安全 SMTP 通过传输层安全性 RFC 3207 中定义。 在此模式下，SMTP 会话从开始时未加密通道，然后执行 STARTTLS 命令颁发客户端到服务器以切换到使用 SSL 的安全通信。 请参阅 RFC 3207 发布通过 Internet 工程任务组 (IETF) 有关详细信息。  
  
 备用连接另一方法是其中任何协议命令发送之前预先建立 SSL 会话。 此连接方法有时被称为 SMTPS 和默认使用端口 465。 当前不支持使用 SSL 此备用连接方法。  
  
 <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType>属性可以用于获取的当前值`enableSsl`从适用的配置文件的属性。  
  
## <a name="example"></a>示例  
 下面的示例指定适当的 SMTP 参数，以使用默认网络凭据发送电子邮件。  
  
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
  
## <a name="see-also"></a>请参阅  
 <xref:System.Net.Configuration.SmtpNetworkElement?displayProperty=nameWithType>  
 <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>  
 <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>  
 [网络设置架构](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
