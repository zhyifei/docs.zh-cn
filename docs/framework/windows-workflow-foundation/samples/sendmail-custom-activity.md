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
# <a name="sendmail-custom-activity"></a><span data-ttu-id="71d33-102">SendMail 自定义活动</span><span class="sxs-lookup"><span data-stu-id="71d33-102">SendMail Custom Activity</span></span>
<span data-ttu-id="71d33-103">本示例演示如何创建派生自 <xref:System.Activities.AsyncCodeActivity> 的自定义活动，以使用 SMTP 发送邮件供在工作流应用程序内使用。</span><span class="sxs-lookup"><span data-stu-id="71d33-103">This sample demonstrates how to create a custom activity that derives from <xref:System.Activities.AsyncCodeActivity> to send mail using SMTP for use within a workflow application.</span></span> <span data-ttu-id="71d33-104">自定义活动使用以<xref:System.Net.Mail.SmtpClient>异步方式发送电子邮件和通过身份验证发送邮件的功能。</span><span class="sxs-lookup"><span data-stu-id="71d33-104">The custom activity uses the capabilities of <xref:System.Net.Mail.SmtpClient> to send email asynchronously and to send mail with authentication.</span></span> <span data-ttu-id="71d33-105">它还提供一些最终用户功能，例如测试模式、标记替换、文件模板和测试放置路径。</span><span class="sxs-lookup"><span data-stu-id="71d33-105">It also provides some end-user features like test mode, token replacement, file templates, and test drop path.</span></span>  
  
 <span data-ttu-id="71d33-106">下表详细描述了 `SendMail` 活动的自变量。</span><span class="sxs-lookup"><span data-stu-id="71d33-106">The following table details the arguments for the `SendMail` activity.</span></span>  
  
|<span data-ttu-id="71d33-107">名称</span><span class="sxs-lookup"><span data-stu-id="71d33-107">Name</span></span>|<span data-ttu-id="71d33-108">类型</span><span class="sxs-lookup"><span data-stu-id="71d33-108">Type</span></span>|<span data-ttu-id="71d33-109">说明</span><span class="sxs-lookup"><span data-stu-id="71d33-109">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="71d33-110">主机</span><span class="sxs-lookup"><span data-stu-id="71d33-110">Host</span></span>|<span data-ttu-id="71d33-111">String</span><span class="sxs-lookup"><span data-stu-id="71d33-111">String</span></span>|<span data-ttu-id="71d33-112">SMTP 服务器主机的地址。</span><span class="sxs-lookup"><span data-stu-id="71d33-112">Address of the SMTP server host.</span></span>|  
|<span data-ttu-id="71d33-113">端口</span><span class="sxs-lookup"><span data-stu-id="71d33-113">Port</span></span>|<span data-ttu-id="71d33-114">String</span><span class="sxs-lookup"><span data-stu-id="71d33-114">String</span></span>|<span data-ttu-id="71d33-115">主机中 SMTP 服务的端口。</span><span class="sxs-lookup"><span data-stu-id="71d33-115">Port of the SMTP service in the host.</span></span>|  
|<span data-ttu-id="71d33-116">EnableSsl</span><span class="sxs-lookup"><span data-stu-id="71d33-116">EnableSsl</span></span>|<span data-ttu-id="71d33-117">bool</span><span class="sxs-lookup"><span data-stu-id="71d33-117">bool</span></span>|<span data-ttu-id="71d33-118">指定 <xref:System.Net.Mail.SmtpClient> 是否使用安全套接字层 (SSL) 来对连接进行加密。</span><span class="sxs-lookup"><span data-stu-id="71d33-118">Specifies whether the <xref:System.Net.Mail.SmtpClient> uses Secure Sockets Layer (SSL) to encrypt the connection.</span></span>|  
|<span data-ttu-id="71d33-119">UserName</span><span class="sxs-lookup"><span data-stu-id="71d33-119">UserName</span></span>|<span data-ttu-id="71d33-120">String</span><span class="sxs-lookup"><span data-stu-id="71d33-120">String</span></span>|<span data-ttu-id="71d33-121">设置用于验证发件人 <xref:System.Net.Mail.SmtpClient.Credentials%2A> 属性的凭据的用户名。</span><span class="sxs-lookup"><span data-stu-id="71d33-121">Username to set up the credentials to authenticate the sender <xref:System.Net.Mail.SmtpClient.Credentials%2A> property.</span></span>|  
|<span data-ttu-id="71d33-122">密码</span><span class="sxs-lookup"><span data-stu-id="71d33-122">Password</span></span>|<span data-ttu-id="71d33-123">String</span><span class="sxs-lookup"><span data-stu-id="71d33-123">String</span></span>|<span data-ttu-id="71d33-124">设置用于验证发件人 <xref:System.Net.Mail.SmtpClient.Credentials%2A> 属性的凭据的密码。</span><span class="sxs-lookup"><span data-stu-id="71d33-124">Password to set up the credentials to authenticate the sender <xref:System.Net.Mail.SmtpClient.Credentials%2A> property.</span></span>|  
|<span data-ttu-id="71d33-125">主题</span><span class="sxs-lookup"><span data-stu-id="71d33-125">Subject</span></span>|<span data-ttu-id="71d33-126"><xref:System.Activities.InArgument%601>\<字符串></span><span class="sxs-lookup"><span data-stu-id="71d33-126"><xref:System.Activities.InArgument%601>\<string></span></span>|<span data-ttu-id="71d33-127">邮件主题。</span><span class="sxs-lookup"><span data-stu-id="71d33-127">Subject of the message.</span></span>|  
|<span data-ttu-id="71d33-128">Body</span><span class="sxs-lookup"><span data-stu-id="71d33-128">Body</span></span>|<span data-ttu-id="71d33-129"><xref:System.Activities.InArgument%601>\<字符串></span><span class="sxs-lookup"><span data-stu-id="71d33-129"><xref:System.Activities.InArgument%601>\<string></span></span>|<span data-ttu-id="71d33-130">邮件正文。</span><span class="sxs-lookup"><span data-stu-id="71d33-130">Body of the message.</span></span>|  
|<span data-ttu-id="71d33-131">Attachments</span><span class="sxs-lookup"><span data-stu-id="71d33-131">Attachments</span></span>|<span data-ttu-id="71d33-132"><xref:System.Activities.InArgument%601>\<字符串></span><span class="sxs-lookup"><span data-stu-id="71d33-132"><xref:System.Activities.InArgument%601>\<string></span></span>|<span data-ttu-id="71d33-133">用于存储附加到此电子邮件的数据的附件集合。</span><span class="sxs-lookup"><span data-stu-id="71d33-133">Attachment collection used to store data attached to this email message.</span></span>|  
|<span data-ttu-id="71d33-134">源</span><span class="sxs-lookup"><span data-stu-id="71d33-134">From</span></span>|<xref:System.Net.Mail.MailAddress>|<span data-ttu-id="71d33-135">此电子邮件的地址。</span><span class="sxs-lookup"><span data-stu-id="71d33-135">From address for this email message.</span></span>|  
|<span data-ttu-id="71d33-136">目标</span><span class="sxs-lookup"><span data-stu-id="71d33-136">To</span></span>|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|<span data-ttu-id="71d33-137">包含此电子邮件收件人的地址集合。</span><span class="sxs-lookup"><span data-stu-id="71d33-137">Address collection that contains the recipients of this email message.</span></span>|  
|<span data-ttu-id="71d33-138">CC</span><span class="sxs-lookup"><span data-stu-id="71d33-138">CC</span></span>|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|<span data-ttu-id="71d33-139">包含此电子邮件的抄送 （CC） 收件人的地址集合。</span><span class="sxs-lookup"><span data-stu-id="71d33-139">Address collection that contains the carbon copy (CC) recipients for this email message.</span></span>|  
|<span data-ttu-id="71d33-140">BCC</span><span class="sxs-lookup"><span data-stu-id="71d33-140">BCC</span></span>|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|<span data-ttu-id="71d33-141">包含此电子邮件的盲拷贝 （BCC） 收件人的地址集合。</span><span class="sxs-lookup"><span data-stu-id="71d33-141">Address collection that contains the blind carbon copy (BCC) recipients for this email message.</span></span>|  
|<span data-ttu-id="71d33-142">令牌</span><span class="sxs-lookup"><span data-stu-id="71d33-142">Tokens</span></span>|<span data-ttu-id="71d33-143"><xref:System.Activities.InArgument%601><I\<字典字符串，字符串>></span><span class="sxs-lookup"><span data-stu-id="71d33-143"><xref:System.Activities.InArgument%601><IDictionary\<string, string>></span></span>|<span data-ttu-id="71d33-144">会在正文中进行替换的标记。</span><span class="sxs-lookup"><span data-stu-id="71d33-144">Tokens to replace in the body.</span></span> <span data-ttu-id="71d33-145">此功能允许用户在正文中指定一些值，这些值稍后可由使用此属性提供的标记进行替换。</span><span class="sxs-lookup"><span data-stu-id="71d33-145">This feature allows users to specify some values in the body than can be replaced later by the tokens provided using this property.</span></span>|  
|<span data-ttu-id="71d33-146">BodyTemplateFilePath</span><span class="sxs-lookup"><span data-stu-id="71d33-146">BodyTemplateFilePath</span></span>|<span data-ttu-id="71d33-147">String</span><span class="sxs-lookup"><span data-stu-id="71d33-147">String</span></span>|<span data-ttu-id="71d33-148">正文模板的路径。</span><span class="sxs-lookup"><span data-stu-id="71d33-148">Path of a template for the body.</span></span> <span data-ttu-id="71d33-149">`SendMail` 活动将此文件的内容复制到其 body 属性中。</span><span class="sxs-lookup"><span data-stu-id="71d33-149">The `SendMail` activity copies the contents of this file to its body property.</span></span><br /><br /> <span data-ttu-id="71d33-150">此模板可包含由 tokens 属性的内容替换的标记。</span><span class="sxs-lookup"><span data-stu-id="71d33-150">The template can contain tokens that are replaced by the contents of the tokens property.</span></span>|  
|<span data-ttu-id="71d33-151">TestMailTo</span><span class="sxs-lookup"><span data-stu-id="71d33-151">TestMailTo</span></span>|<xref:System.Net.Mail.MailAddress>|<span data-ttu-id="71d33-152">设置此属性后，所有电子邮件都发送到其中指定的地址。</span><span class="sxs-lookup"><span data-stu-id="71d33-152">When this property is set, all emails are sent to the address specified in it.</span></span><br /><br /> <span data-ttu-id="71d33-153">此属性应在测试工作流时使用。</span><span class="sxs-lookup"><span data-stu-id="71d33-153">This property is intended to be used when testing workflows.</span></span> <span data-ttu-id="71d33-154">例如，当您希望确保所有电子邮件都发送而不发送给实际收件人时。</span><span class="sxs-lookup"><span data-stu-id="71d33-154">For example, when you want to make sure that all emails are sent without sending them to the actual recipients.</span></span>|  
|<span data-ttu-id="71d33-155">TestDropPath</span><span class="sxs-lookup"><span data-stu-id="71d33-155">TestDropPath</span></span>|<span data-ttu-id="71d33-156">String</span><span class="sxs-lookup"><span data-stu-id="71d33-156">String</span></span>|<span data-ttu-id="71d33-157">设置此属性后，所有电子邮件也会保存在指定的文件中。</span><span class="sxs-lookup"><span data-stu-id="71d33-157">When this property is set, all emails are also saved in the specified file.</span></span><br /><br /> <span data-ttu-id="71d33-158">此属性用于在测试或调试工作流时使用，以确保传出电子邮件的格式和内容是合适的。</span><span class="sxs-lookup"><span data-stu-id="71d33-158">This property is intended to be used when you are testing or debugging workflows, to make sure that the format and contents of the outgoing emails is appropriate.</span></span>|  
  
## <a name="solution-contents"></a><span data-ttu-id="71d33-159">解决方案内容</span><span class="sxs-lookup"><span data-stu-id="71d33-159">Solution Contents</span></span>  
 <span data-ttu-id="71d33-160">解决方案包含两个项目。</span><span class="sxs-lookup"><span data-stu-id="71d33-160">The solution contains two projects.</span></span>  
  
|<span data-ttu-id="71d33-161">Project</span><span class="sxs-lookup"><span data-stu-id="71d33-161">Project</span></span>|<span data-ttu-id="71d33-162">说明</span><span class="sxs-lookup"><span data-stu-id="71d33-162">Description</span></span>|<span data-ttu-id="71d33-163">重要文件</span><span class="sxs-lookup"><span data-stu-id="71d33-163">Important Files</span></span>|  
|-------------|-----------------|---------------------|  
|<span data-ttu-id="71d33-164">SendMail</span><span class="sxs-lookup"><span data-stu-id="71d33-164">SendMail</span></span>|<span data-ttu-id="71d33-165">SendMail 活动</span><span class="sxs-lookup"><span data-stu-id="71d33-165">The SendMail activity</span></span>|<span data-ttu-id="71d33-166">1. SendMail.cs：主要活动的实施</span><span class="sxs-lookup"><span data-stu-id="71d33-166">1.  SendMail.cs: implementation for the main activity</span></span><br /><span data-ttu-id="71d33-167">2. 发送邮件设计器.xaml 和SendMailDesigner.xaml.cs：发送邮件活动的设计师</span><span class="sxs-lookup"><span data-stu-id="71d33-167">2.  SendMailDesigner.xaml and SendMailDesigner.xaml.cs: designer for the SendMail activity</span></span><br /><span data-ttu-id="71d33-168">3. MailTemplateBody.htm：要发送的电子邮件的模板。</span><span class="sxs-lookup"><span data-stu-id="71d33-168">3.  MailTemplateBody.htm: template for the email to be sent out.</span></span>|  
|<span data-ttu-id="71d33-169">SendMailTestClient</span><span class="sxs-lookup"><span data-stu-id="71d33-169">SendMailTestClient</span></span>|<span data-ttu-id="71d33-170">测试 SendMail 活动的客户端。</span><span class="sxs-lookup"><span data-stu-id="71d33-170">Client to test the SendMail activity.</span></span>  <span data-ttu-id="71d33-171">此项目演示两种调用 SendMail 活动的方式：声明方式和编程方式。</span><span class="sxs-lookup"><span data-stu-id="71d33-171">This project demonstrates two ways of invoking the SendMail activity: declaratively, and programmatically.</span></span>|<span data-ttu-id="71d33-172">1. 序列1.xaml：调用发送邮件活动的工作流。</span><span class="sxs-lookup"><span data-stu-id="71d33-172">1.  Sequence1.xaml: workflow that invokes the SendMail activity.</span></span><br /><span data-ttu-id="71d33-173">2. Program.cs：调用 Sequence1，并以编程方式创建使用 SendMail 的工作流。</span><span class="sxs-lookup"><span data-stu-id="71d33-173">2.  Program.cs: invokes Sequence1 and also creates a workflow programmatically that uses SendMail.</span></span>|  
  
## <a name="further-configuration-of-the-sendmail-activity"></a><span data-ttu-id="71d33-174">SendMail 活动的进一步配置</span><span class="sxs-lookup"><span data-stu-id="71d33-174">Further configuration of the SendMail activity</span></span>  
 <span data-ttu-id="71d33-175">虽然在此示例中未显示，但用户可以执行 SendMail 活动的其他配置。</span><span class="sxs-lookup"><span data-stu-id="71d33-175">Although not shown in the sample, users can perform addition configuration of the SendMail activity.</span></span> <span data-ttu-id="71d33-176">以下三部分演示如何完成此操作。</span><span class="sxs-lookup"><span data-stu-id="71d33-176">The next three sections demonstrate how this is done.</span></span>  
  
### <a name="sending-an-email-using-tokens-specified-in-the-body"></a><span data-ttu-id="71d33-177">使用正文中指定的标记发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="71d33-177">Sending an email using tokens specified in the body</span></span>  
 <span data-ttu-id="71d33-178">此代码段演示如何使用正文中的标记发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="71d33-178">This code snippet demonstrates how you can send email with tokens in the body.</span></span> <span data-ttu-id="71d33-179">注意在 body 属性中提供标记的方式。</span><span class="sxs-lookup"><span data-stu-id="71d33-179">Notice how the tokens are provided in the body property.</span></span> <span data-ttu-id="71d33-180">将以下标记的值提供给 tokens 属性。</span><span class="sxs-lookup"><span data-stu-id="71d33-180">Values for those tokens are provided to the tokens property.</span></span>  
  
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
  
### <a name="sending-an-email-using-a-template"></a><span data-ttu-id="71d33-181">使用模板发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="71d33-181">Sending an email using a template</span></span>  
 <span data-ttu-id="71d33-182">此代码段演示如何使用正文中的模板标记发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="71d33-182">This snippet shows how to send an email using a template tokens in the body.</span></span> <span data-ttu-id="71d33-183">请注意，设置 `BodyTemplateFilePath` 属性时，不需要提供 Body 属性的值（模板文件的内容将复制到正文）。</span><span class="sxs-lookup"><span data-stu-id="71d33-183">Notice that when setting the `BodyTemplateFilePath` property we don’t need to provide the value for Body property (the contents of the template file will be copied to the body).</span></span>  
  
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
  
### <a name="sending-mails-in-testing-mode"></a><span data-ttu-id="71d33-184">在测试模式下发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="71d33-184">Sending Mails in Testing Mode</span></span>  
 <span data-ttu-id="71d33-185">此代码段演示如何设置两个测试属性：通过设置`TestMailTo`到将发送到的所有消息`john.doe@contoso.con`（不考虑 To、Cc、密件抄送的值）。</span><span class="sxs-lookup"><span data-stu-id="71d33-185">This code snippet shows how to set the two testing properties: by setting `TestMailTo` to all messages will be sent to `john.doe@contoso.con` (without regard of the values of To, Cc, Bcc).</span></span> <span data-ttu-id="71d33-186">通过设置 TestDropPath，所有传出电子邮件还将记录在提供的路径中。</span><span class="sxs-lookup"><span data-stu-id="71d33-186">By setting TestDropPath all outgoing emails will be also recorded in the provided path.</span></span> <span data-ttu-id="71d33-187">可单独设置这些属性（它们不相关）。</span><span class="sxs-lookup"><span data-stu-id="71d33-187">These properties can be set independently (they are not related).</span></span>  
  
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
  
## <a name="set-up-instructions"></a><span data-ttu-id="71d33-188">设置说明</span><span class="sxs-lookup"><span data-stu-id="71d33-188">Set-Up Instructions</span></span>  
 <span data-ttu-id="71d33-189">此示例要求具有对 SMTP 服务器的访问权限。</span><span class="sxs-lookup"><span data-stu-id="71d33-189">Access to a SMTP server is required for this sample.</span></span>  
  
 <span data-ttu-id="71d33-190">有关设置 SMTP 服务器的详细信息，请参阅以下链接。</span><span class="sxs-lookup"><span data-stu-id="71d33-190">For more information about setting up a SMTP server, see the following links.</span></span>  
  
- <span data-ttu-id="71d33-191">[配置 SMTP 服务 (IIS 6.0)](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc784968(v=ws.10))</span><span class="sxs-lookup"><span data-stu-id="71d33-191">[Configuring the SMTP Service (IIS 6.0)](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc784968(v=ws.10))</span></span>  
  
- <span data-ttu-id="71d33-192">[IIS 7.0：配置 SMTP 电子邮件](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772058(v=ws.10))</span><span class="sxs-lookup"><span data-stu-id="71d33-192">[IIS 7.0: Configure SMTP E-Mail](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772058(v=ws.10))</span></span>  
  
- <span data-ttu-id="71d33-193">[如何安装 SMTP 服务](https://docs.microsoft.com/previous-versions/tn-archive/aa997480(v=exchg.65))</span><span class="sxs-lookup"><span data-stu-id="71d33-193">[How to Install the SMTP Service](https://docs.microsoft.com/previous-versions/tn-archive/aa997480(v=exchg.65))</span></span>  
  
 <span data-ttu-id="71d33-194">可下载第三方提供的 SMTP 模拟器。</span><span class="sxs-lookup"><span data-stu-id="71d33-194">SMTP emulators provided by third parties are available for download.</span></span>  
  
##### <a name="to-run-this-sample"></a><span data-ttu-id="71d33-195">运行本示例的步骤</span><span class="sxs-lookup"><span data-stu-id="71d33-195">To run this sample</span></span>  
  
1. <span data-ttu-id="71d33-196">使用 Visual Studio 2010，打开 SendMail.sln 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="71d33-196">Using Visual Studio 2010, open the SendMail.sln solution file.</span></span>  
  
2. <span data-ttu-id="71d33-197">确保您具有对有效 SMTP 服务器的访问权限。</span><span class="sxs-lookup"><span data-stu-id="71d33-197">Ensure that you have access to a valid SMTP server.</span></span> <span data-ttu-id="71d33-198">查看设置说明。</span><span class="sxs-lookup"><span data-stu-id="71d33-198">See the set-up instructions.</span></span>  
  
3. <span data-ttu-id="71d33-199">使用服务器地址和"从"和"收件人"电子邮件地址配置程序。</span><span class="sxs-lookup"><span data-stu-id="71d33-199">Configure the program with your server address, and From and To email addresses.</span></span>  
  
     <span data-ttu-id="71d33-200">要正确运行此示例，您可能需要在 Program.cs 和 Sequence.xaml 中配置"收件人"和"收件人"电子邮件地址的值以及 SMTP 服务器的地址。</span><span class="sxs-lookup"><span data-stu-id="71d33-200">To correctly run this sample, you may need to configure the value of From and To email addresses and the address of the SMTP server in  Program.cs and in Sequence.xaml.</span></span> <span data-ttu-id="71d33-201">您将需要更改这两个位置中的地址，因为程序用两种不同的方式发送邮件。</span><span class="sxs-lookup"><span data-stu-id="71d33-201">You will need to change the address in both locations since the program sends mail in two different ways</span></span>  
  
4. <span data-ttu-id="71d33-202">要生成解决方案，按 Ctrl+Shift+B。</span><span class="sxs-lookup"><span data-stu-id="71d33-202">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
5. <span data-ttu-id="71d33-203">若要运行解决方案，请按 Ctrl+F5。</span><span class="sxs-lookup"><span data-stu-id="71d33-203">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="71d33-204">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="71d33-204">The samples may already be installed on your machine.</span></span> <span data-ttu-id="71d33-205">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="71d33-205">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="71d33-206">如果此目录不存在，请转到[Windows 通信基础 （WCF） 和 Windows 工作流基础 （WF） 示例 .NET 框架 4](https://www.microsoft.com/download/details.aspx?id=21459)以下载[!INCLUDE[wf1](../../../../includes/wf1-md.md)]所有 Windows 通信基础 （WCF） 和示例。</span><span class="sxs-lookup"><span data-stu-id="71d33-206">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="71d33-207">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="71d33-207">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\SendMail`
