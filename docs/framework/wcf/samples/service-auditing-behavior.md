---
title: 服务审核行为
ms.date: 03/30/2017
ms.assetid: 59bf0cda-e496-4418-a3a1-2f0f6e85f8ce
ms.openlocfilehash: 5fdc213551b5a7b3474321551d7c2cb149ca978d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59151419"
---
# <a name="service-auditing-behavior"></a><span data-ttu-id="13abc-102">服务审核行为</span><span class="sxs-lookup"><span data-stu-id="13abc-102">Service Auditing Behavior</span></span>
<span data-ttu-id="13abc-103">此示例演示如何在服务操作过程中使用 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> 来启用对安全事件的审核。</span><span class="sxs-lookup"><span data-stu-id="13abc-103">This sample demonstrates how to use the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> to enable auditing of security events during service operations.</span></span> <span data-ttu-id="13abc-104">此示例基于[Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="13abc-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span> <span data-ttu-id="13abc-105">服务和客户端已配置使用[ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="13abc-105">The service and client have been configured using the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span></span> <span data-ttu-id="13abc-106">`mode`的属性[\<安全 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)已设置为`Message`并`clientCredentialType`已设置为`Windows`。</span><span class="sxs-lookup"><span data-stu-id="13abc-106">The `mode` attribute of the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) has been set to `Message` and `clientCredentialType` has been set to `Windows`.</span></span> <span data-ttu-id="13abc-107">在此示例中，客户端是一个控制台应用程序 (.exe)，服务是由 Internet 信息服务 (IIS) 承载的。</span><span class="sxs-lookup"><span data-stu-id="13abc-107">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="13abc-108">本主题的最后介绍了此示例的设置过程和生成说明。</span><span class="sxs-lookup"><span data-stu-id="13abc-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="13abc-109">服务配置文件使用 `serviceSecurityAudit` 元素来配置审核。</span><span class="sxs-lookup"><span data-stu-id="13abc-109">The service configuration file uses the `serviceSecurityAudit` element to configure auditing.</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      ...  
<!-- serviceSecurityAudit allows specification of audit location   
     and whether to audit success, failure or both. This service   
     logs success and failure of messageAuthentication   
     to the default location -->  
     <serviceSecurityAudit auditLogLocation ="Default" messageAuthenticationAuditLevel = "SuccessOrFailure" />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 <span data-ttu-id="13abc-110">运行示例时，操作请求和响应将显示在客户端控制台窗口中。</span><span class="sxs-lookup"><span data-stu-id="13abc-110">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="13abc-111">在控制台窗口中按 Enter 可以关闭客户端。</span><span class="sxs-lookup"><span data-stu-id="13abc-111">Press ENTER in the console window to shut down the client.</span></span>  
  
 <span data-ttu-id="13abc-112">通过运行事件查看器可以查看所生成的审核日志。</span><span class="sxs-lookup"><span data-stu-id="13abc-112">The resulting audit logs can be seen by running the Event Viewer.</span></span> <span data-ttu-id="13abc-113">默认情况下，可在 Windows XP 上的应用程序日志中查看审核事件；而在 Windows Server 2003 和 Windows Vista 上，可在安全日志中查看审核事件。</span><span class="sxs-lookup"><span data-stu-id="13abc-113">By default, on Windows XP the audit events can be seen in the Application Log while on Windows Server 2003 and Windows Vista, the audit events can be seen in the Security Log.</span></span> <span data-ttu-id="13abc-114">可在 Windows Server 2008 和 Windows 7 上的应用程序和服务日志中查看审核事件。</span><span class="sxs-lookup"><span data-stu-id="13abc-114">On Windows Server 2008 and Windows 7, the audit events can be seen in the Applications and Services logs.</span></span> <span data-ttu-id="13abc-115">可以通过设置指定审核事件的位置`auditLogLocation`属性为"应用程序"或"安全"。</span><span class="sxs-lookup"><span data-stu-id="13abc-115">The location of audit events can be specified by setting the `auditLogLocation` attribute to "Application" or "Security".</span></span> <span data-ttu-id="13abc-116">有关详细信息，请参阅[如何：审核安全事件](../../../../docs/framework/wcf/feature-details/how-to-audit-wcf-security-events.md)。</span><span class="sxs-lookup"><span data-stu-id="13abc-116">For more information, see [How to: Audit Security Events](../../../../docs/framework/wcf/feature-details/how-to-audit-wcf-security-events.md).</span></span> <span data-ttu-id="13abc-117">如果事件写入安全日志 LocalSecurityPolicy-> 中启用对象访问应设置为"Success"和"失败"。</span><span class="sxs-lookup"><span data-stu-id="13abc-117">If the events are written in the Security Log the LocalSecurityPolicy-> Enable Object Access should be set for "Success" and "Failure".</span></span>  
  
 <span data-ttu-id="13abc-118">在查看事件日志时，审核事件的来源为“ServiceModel Audit 3.0.0.0”。</span><span class="sxs-lookup"><span data-stu-id="13abc-118">When looking at the event log, the source of the audit events is "ServiceModel Audit 3.0.0.0".</span></span> <span data-ttu-id="13abc-119">消息身份验证审核记录具有类别为"MessageAuthentication"，而服务授权审核记录的类别为"ServiceAuthorization"。</span><span class="sxs-lookup"><span data-stu-id="13abc-119">Message authentication audit records have a category of "MessageAuthentication" while service authorization audit records have a category of "ServiceAuthorization".</span></span>  
  
 <span data-ttu-id="13abc-120">消息身份验证审核事件包含消息是否被篡改、消息是否已过期以及客户端是否可以向服务进行身份验证等信息。</span><span class="sxs-lookup"><span data-stu-id="13abc-120">Message authentication audit events cover whether the message was tampered with, whether the message has expired, and whether the client can authenticate to the service.</span></span> <span data-ttu-id="13abc-121">这些事件还提供了有关身份验证是成功还是失败（以及客户端标识）的信息和有关消息所发送到的终结点（以及与消息关联的操作）的信息。</span><span class="sxs-lookup"><span data-stu-id="13abc-121">They provide information about whether the authentication succeeded or failed along with the identity of the client, and the endpoint the message was sent to along with the action associated with the message.</span></span>  
  
 <span data-ttu-id="13abc-122">服务授权审核事件包含服务授权管理器所做出的授权决定。</span><span class="sxs-lookup"><span data-stu-id="13abc-122">Service authorization audit events cover the authorization decision made by a service authorization manager.</span></span> <span data-ttu-id="13abc-123">这些事件提供了有关以下各项的信息：授权是成功还是失败以及客户端标识、消息所发送到的终结点、与消息关联的操作、从传入消息中生成的授权上下文的标识符和做出访问决定的授权管理器的类型。</span><span class="sxs-lookup"><span data-stu-id="13abc-123">They provide information about whether authorization succeeded or failed along with the identity of the client, the endpoint the message was sent to, the action associated with the message, the identifier of the authorization context that was generated from the incoming message, and the type of the authorization manager that made the access decision.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="13abc-124">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="13abc-124">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="13abc-125">请确保您具有执行[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="13abc-125">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="13abc-126">若要生成 C# 或 Visual Basic .NET 版本的解决方案，请按照 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="13abc-126">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="13abc-127">若要在单或跨计算机配置中运行示例，请按照中的说明[运行 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/running-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="13abc-127">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13abc-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="13abc-128">See also</span></span>

- [<span data-ttu-id="13abc-129">审核</span><span class="sxs-lookup"><span data-stu-id="13abc-129">Auditing</span></span>](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)
- [<span data-ttu-id="13abc-130">如何：审核安全事件</span><span class="sxs-lookup"><span data-stu-id="13abc-130">How to: Audit Security Events</span></span>](../../../../docs/framework/wcf/feature-details/how-to-audit-wcf-security-events.md)
