---
title: SendMail 自定义活动
ms.date: 03/30/2017
ms.assetid: 947a9ae6-379c-43a3-9cd5-87f573a5739f
ms.openlocfilehash: e7cc64e68c3d78b9ee7ec813700e96a52c239141
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182785"
---
# <a name="sendmail-custom-activity"></a>SendMail 自定义活动
本示例演示如何创建派生自 <xref:System.Activities.AsyncCodeActivity> 的自定义活动，以使用 SMTP 发送邮件供在工作流应用程序内使用。 自定义活动使用以<xref:System.Net.Mail.SmtpClient>异步方式发送电子邮件和通过身份验证发送邮件的功能。 它还提供一些最终用户功能，例如测试模式、标记替换、文件模板和测试放置路径。  
  
 下表详细描述了 `SendMail` 活动的自变量。  
  
|名称|类型|说明|  
|-|-|-|  
|主机|String|SMTP 服务器主机的地址。|  
|端口|String|主机中 SMTP 服务的端口。|  
|EnableSsl|bool|指定 <xref:System.Net.Mail.SmtpClient> 是否使用安全套接字层 (SSL) 来对连接进行加密。|  
|UserName|String|设置用于验证发件人 <xref:System.Net.Mail.SmtpClient.Credentials%2A> 属性的凭据的用户名。|  
|密码|String|设置用于验证发件人 <xref:System.Net.Mail.SmtpClient.Credentials%2A> 属性的凭据的密码。|  
|主题|<xref:System.Activities.InArgument%601>\<字符串>|邮件主题。|  
|Body|<xref:System.Activities.InArgument%601>\<字符串>|邮件正文。|  
|Attachments|<xref:System.Activities.InArgument%601>\<字符串>|用于存储附加到此电子邮件的数据的附件集合。|  
|源|<xref:System.Net.Mail.MailAddress>|此电子邮件的地址。|  
|目标|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|包含此电子邮件收件人的地址集合。|  
|CC|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|包含此电子邮件的抄送 （CC） 收件人的地址集合。|  
|BCC|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|包含此电子邮件的盲拷贝 （BCC） 收件人的地址集合。|  
|令牌|<xref:System.Activities.InArgument%601><I\<字典字符串，字符串>>|会在正文中进行替换的标记。 此功能允许用户在正文中指定一些值，这些值稍后可由使用此属性提供的标记进行替换。|  
|BodyTemplateFilePath|String|正文模板的路径。 `SendMail` 活动将此文件的内容复制到其 body 属性中。<br /><br /> 此模板可包含由 tokens 属性的内容替换的标记。|  
|TestMailTo|<xref:System.Net.Mail.MailAddress>|设置此属性后，所有电子邮件都发送到其中指定的地址。<br /><br /> 此属性应在测试工作流时使用。 例如，当您希望确保所有电子邮件都发送而不发送给实际收件人时。|  
|TestDropPath|String|设置此属性后，所有电子邮件也会保存在指定的文件中。<br /><br /> 此属性用于在测试或调试工作流时使用，以确保传出电子邮件的格式和内容是合适的。|  
  
## <a name="solution-contents"></a>解决方案内容  
 解决方案包含两个项目。  
  
|Project|说明|重要文件|  
|-------------|-----------------|---------------------|  
|SendMail|SendMail 活动|1. SendMail.cs：主要活动的实施<br />2. 发送邮件设计器.xaml 和SendMailDesigner.xaml.cs：发送邮件活动的设计师<br />3. MailTemplateBody.htm：要发送的电子邮件的模板。|  
|SendMailTestClient|测试 SendMail 活动的客户端。  此项目演示两种调用 SendMail 活动的方式：声明方式和编程方式。|1. 序列1.xaml：调用发送邮件活动的工作流。<br />2. Program.cs：调用 Sequence1，并以编程方式创建使用 SendMail 的工作流。|  
  
## <a name="further-configuration-of-the-sendmail-activity"></a>SendMail 活动的进一步配置  
 虽然在此示例中未显示，但用户可以执行 SendMail 活动的其他配置。 以下三部分演示如何完成此操作。  
  
### <a name="sending-an-email-using-tokens-specified-in-the-body"></a>使用正文中指定的标记发送电子邮件。  
 此代码段演示如何使用正文中的标记发送电子邮件。 注意在 body 属性中提供标记的方式。 将以下标记的值提供给 tokens 属性。  
  
```csharp  
IDictionary<string, string> tokens = new Dictionary<string, string>();  
tokens.Add("@name", "John Doe");  
tokens.Add("@date", DateTime.Now.ToString());  
tokens.Add("@server", "localhost");  
  
new SendMail  
{  
    From = new LambdaValue<MailAddress>(ctx => new MailAddress("john.doe@contoso.com")),  
    To = new LambdaValue<MailAddressCollection>(  
                    ctx => new MailAddressCollection() { new MailAddress("someone@microsoft.com") }),  
    Subject = "Test email",  
    Body = "Hello @name. This is a test email sent from @server. Current date is @date",  
    Host = "localhost",  
    Port = 25,  
    Tokens = new LambdaValue<IDictionary<string, string>>(ctx => tokens)  
};  
```  
  
### <a name="sending-an-email-using-a-template"></a>使用模板发送电子邮件  
 此代码段演示如何使用正文中的模板标记发送电子邮件。 请注意，设置 `BodyTemplateFilePath` 属性时，不需要提供 Body 属性的值（模板文件的内容将复制到正文）。  
  
```csharp  
new SendMail  
{
    From = new LambdaValue<MailAddress>(ctx => new MailAddress("john.doe@contoso.com")),  
    To = new LambdaValue<MailAddressCollection>(  
                    ctx => new MailAddressCollection() { new MailAddress("someone@microsoft.com") }),  
    Subject = "Test email",  
    Host = "localhost",  
    Port = 25,  
    Tokens = new LambdaValue<IDictionary<string, string>>(ctx => tokens),  
    BodyTemplateFilePath = @"..\..\..\SendMail\Templates\MailTemplateBody.htm",
};  
```  
  
### <a name="sending-mails-in-testing-mode"></a>在测试模式下发送电子邮件  
 此代码段演示如何设置两个测试属性：通过设置`TestMailTo`到将发送到的所有消息`john.doe@contoso.con`（不考虑 To、Cc、密件抄送的值）。 通过设置 TestDropPath，所有传出电子邮件还将记录在提供的路径中。 可单独设置这些属性（它们不相关）。  
  
```csharp  
new SendMail  
{
   From = new LambdaValue<MailAddress>(ctx => new MailAddress("john.doe@contoso.com")),  
   To = new LambdaValue<MailAddressCollection>(  
                    ctx => new MailAddressCollection() { new MailAddress("someone@microsoft.com") }),  
   Subject = "Test email",  
   Host = "localhost",  
   Port = 25,  
   Tokens = new LambdaValue<IDictionary<string, string>>(ctx => tokens),  
   BodyTemplateFilePath = @"..\..\..\SendMail\Templates\MailTemplateBody.htm",  
   TestMailTo= new LambdaValue<MailAddress>(ctx => new MailAddress("john.doe@contoso.com")),  
   TestDropPath = @"c:\Samples\SendMail\TestDropPath\",  
};  
```  
  
## <a name="set-up-instructions"></a>设置说明  
 此示例要求具有对 SMTP 服务器的访问权限。  
  
 有关设置 SMTP 服务器的详细信息，请参阅以下链接。  
  
- [配置 SMTP 服务 (IIS 6.0)](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc784968(v=ws.10))  
  
- [IIS 7.0：配置 SMTP 电子邮件](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772058(v=ws.10))  
  
- [如何安装 SMTP 服务](https://docs.microsoft.com/previous-versions/tn-archive/aa997480(v=exchg.65))  
  
 可下载第三方提供的 SMTP 模拟器。  
  
##### <a name="to-run-this-sample"></a>运行本示例的步骤  
  
1. 使用 Visual Studio 2010，打开 SendMail.sln 解决方案文件。  
  
2. 确保您具有对有效 SMTP 服务器的访问权限。 查看设置说明。  
  
3. 使用服务器地址和"从"和"收件人"电子邮件地址配置程序。  
  
     要正确运行此示例，您可能需要在 Program.cs 和 Sequence.xaml 中配置"收件人"和"收件人"电子邮件地址的值以及 SMTP 服务器的地址。 您将需要更改这两个位置中的地址，因为程序用两种不同的方式发送邮件。  
  
4. 要生成解决方案，按 Ctrl+Shift+B。  
  
5. 若要运行解决方案，请按 Ctrl+F5。  
  
> [!IMPORTANT]
> 您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> 如果此目录不存在，请转到[Windows 通信基础 （WCF） 和 Windows 工作流基础 （WF） 示例 .NET 框架 4](https://www.microsoft.com/download/details.aspx?id=21459)以下载[!INCLUDE[wf1](../../../../includes/wf1-md.md)]所有 Windows 通信基础 （WCF） 和示例。 此示例位于以下目录：  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\SendMail`
