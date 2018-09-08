---
title: SendMail 自定义活动
ms.date: 03/30/2017
ms.assetid: 947a9ae6-379c-43a3-9cd5-87f573a5739f
ms.openlocfilehash: e9d27711754c3aa8ff7f68c23f528c9f5c4356f7
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44189960"
---
# <a name="sendmail-custom-activity"></a>SendMail 自定义活动
本示例演示如何创建派生自 <xref:System.Activities.AsyncCodeActivity> 的自定义活动，以使用 SMTP 发送邮件供在工作流应用程序内使用。 自定义活动使用的功能的<xref:System.Net.Mail.SmtpClient>以异步方式发送电子邮件以及发送身份验证的邮件。 它还提供一些最终用户功能，例如测试模式、标记替换、文件模板和测试放置路径。  
  
 下表详细描述了 `SendMail` 活动的参数。  
  
|名称|类型|描述|  
|-|-|-|  
|Host|String|SMTP 服务器主机的地址。|  
|端口|String|主机中 SMTP 服务的端口。|  
|EnableSsl|bool|指定 <xref:System.Net.Mail.SmtpClient> 是否使用安全套接字层 (SSL) 来对连接进行加密。|  
|UserName|String|设置用于验证发件人 <xref:System.Net.Mail.SmtpClient.Credentials%2A> 属性的凭据的用户名。|  
|密码|String|设置用于验证发件人 <xref:System.Net.Mail.SmtpClient.Credentials%2A> 属性的凭据的密码。|  
|Subject|<xref:System.Activities.InArgument%601>\<string>|邮件主题。|  
|正文|<xref:System.Activities.InArgument%601>\<string>|邮件正文。|  
|附件|<xref:System.Activities.InArgument%601>\<string>|用于存储数据附加到此电子邮件的附件集合。|  
|From|<xref:System.Net.Mail.MailAddress>|来自此电子邮件地址。|  
|到|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|包含此电子邮件的收件人的地址集合。|  
|CC|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|地址包含此电子邮件的抄送 (CC) 收件人的集合。|  
|BCC|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|包含此电子邮件的密件抄送 (BCC) 收件人的地址集合。|  
|标记|<xref:System.Activities.InArgument%601>< IDictionary\<字符串、 字符串 >>|会在正文中进行替换的标记。 此功能允许用户在正文中指定一些值，这些值稍后可由使用此属性提供的标记进行替换。|  
|BodyTemplateFilePath|String|正文模板的路径。 `SendMail` 活动将此文件的内容复制到其 body 属性中。<br /><br /> 此模板可包含由 tokens 属性的内容替换的标记。|  
|TestMailTo|<xref:System.Net.Mail.MailAddress>|当设置此属性时，所有电子邮件发送到在其中指定的地址。<br /><br /> 此属性应在测试工作流时使用。 例如，如果想要确保不将它们发送到实际收件人的情况下发送所有电子邮件。|  
|TestDropPath|String|如果设置此属性，还会在指定的文件中保存所有电子邮件。<br /><br /> 此属性应在测试或调试工作流，以确保为相应的格式和内容的传出电子邮件时使用。|  
  
## <a name="solution-contents"></a>解决方案内容  
 解决方案包含两个项目。  
  
|Project|描述|重要文件|  
|-------------|-----------------|---------------------|  
|SendMail|SendMail 活动|1.SendMail.cs：主要活动的实现<br />2.SendMailDesigner.xaml 和 SendMailDesigner.xaml.cs：SendMail 活动的设计器<br />3.MailTemplateBody.htm：要发出的电子邮件的模板。|  
|SendMailTestClient|测试 SendMail 活动的客户端。  此项目演示两种调用 SendMail 活动的方式：声明方式和编程方式。|1.Sequence1.xaml：调用 SendMail 活动的工作流。<br />2.Program.cs：调用 Sequence1，并以编程方式创建使用 SendMail 的工作流。|  
  
## <a name="further-configuration-of-the-sendmail-activity"></a>SendMail 活动的进一步配置  
 虽然在此示例中未显示，但用户可以执行 SendMail 活动的其他配置。 以下三部分演示如何完成此操作。  
  
### <a name="sending-an-email-using-tokens-specified-in-the-body"></a>使用正文中指定的标记发送电子邮件。  
 此代码段演示如何使用正文中的标记发送电子邮件。 注意在 body 属性中提供标记的方式。 将以下标记的值提供给 tokens 属性。  
  
```html  
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
  
```  
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
 此代码片段演示如何设置两个测试属性： 通过设置`TestMailTo`到所有消息将发送到john.doe@contoso.con（而无需考虑的值的收件人、 抄送、 密件抄送）。 通过设置 TestDropPath，所有传出电子邮件还将记录在提供的路径中。 可单独设置这些属性（它们不相关）。  
  
```  
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
  
-   [Microsoft Technet](https://go.microsoft.com/fwlink/?LinkId=166060)  
  
-   [配置 SMTP 服务 (IIS 6.0)](https://go.microsoft.com/fwlink/?LinkId=150456)  
  
-   [IIS 7.0： 配置 SMTP 电子邮件](https://go.microsoft.com/fwlink/?LinkId=150457)  
  
-   [如何安装 SMTP 服务](https://go.microsoft.com/fwlink/?LinkId=150458)  
  
 可下载第三方提供的 SMTP 模拟器。  
  
##### <a name="to-run-this-sample"></a>运行此示例  
  
1.  使用 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 打开 SendMail.sln 解决方案文件。  
  
2.  确保您具有对有效 SMTP 服务器的访问权限。 查看设置说明。  
  
3.  使用你的服务器地址，并从 / 向电子邮件地址，请配置该程序。  
  
     若要正确运行此示例，可能需要在 Program.cs 中和 Sequence.xaml 中配置从 / 向电子邮件地址和 SMTP 服务器的地址的值。 您将需要更改这两个位置中的地址，因为程序用两种不同的方式发送邮件。  
  
4.  要生成解决方案，按 Ctrl+Shift+B。  
  
5.  若要运行解决方案，请按 Ctrl+F5。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\SendMail`