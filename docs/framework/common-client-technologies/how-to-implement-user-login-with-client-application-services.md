---
title: "如何：使用客户端应用程序服务来实现用户登录"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- validating users [client application services]
- validation [.NET Framework], client application services
- client application services, authenticate users
ms.assetid: 5431a671-eb02-4e18-a651-24764fccec9a
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 909fbaa4e7dc1d384b5085d71cec346bde44cf14
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-user-login-with-client-application-services"></a><span data-ttu-id="9fa6f-102">如何：使用客户端应用程序服务来实现用户登录</span><span class="sxs-lookup"><span data-stu-id="9fa6f-102">How to: Implement User Login with Client Application Services</span></span>
<span data-ttu-id="9fa6f-103">可以通过现有 [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)] 配置文件服务，使用客户端应用程序服务来验证用户。</span><span class="sxs-lookup"><span data-stu-id="9fa6f-103">You can use client application services to validate users through an existing [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)] profile service.</span></span> <span data-ttu-id="9fa6f-104">有关如何设置 [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)] 配置文件服务的信息，请参阅[将 Forms 身份验证用于 Microsoft Ajax](http://msdn.microsoft.com/library/c50f7dc5-323c-4c63-b4f3-96edfc1e815e)。</span><span class="sxs-lookup"><span data-stu-id="9fa6f-104">For information about how to set up the [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)] profile service, see [Using Forms Authentication with Microsoft Ajax](http://msdn.microsoft.com/library/c50f7dc5-323c-4c63-b4f3-96edfc1e815e).</span></span>  
  
 <span data-ttu-id="9fa6f-105">以下过程介绍如何在应用程序配置为使用客户端身份验证服务提供程序之一时，通过身份验证服务验证用户。</span><span class="sxs-lookup"><span data-stu-id="9fa6f-105">The following procedures describe how to validate users through the authentication service when your application is configured to use one of the client authentication service providers.</span></span> <span data-ttu-id="9fa6f-106">有关更多信息，请参见 [How to: Configure Client Application Services](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md)。</span><span class="sxs-lookup"><span data-stu-id="9fa6f-106">For more information, see [How to: Configure Client Application Services](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md).</span></span>  
  
 <span data-ttu-id="9fa6f-107">通常，可通过 `static` <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=nameWithType> 方法执行所有验证。</span><span class="sxs-lookup"><span data-stu-id="9fa6f-107">You will typically perform all validation through the `static` <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="9fa6f-108">此方法通过配置的身份验证提供程序管理与身份验证服务进行的交互。</span><span class="sxs-lookup"><span data-stu-id="9fa6f-108">This method manages the interaction with the authentication service through the configured authentication provider.</span></span> <span data-ttu-id="9fa6f-109">有关详细信息，请参阅[客户端应用程序服务概述](../../../docs/framework/common-client-technologies/client-application-services-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="9fa6f-109">For more information, see [Client Application Services Overview](../../../docs/framework/common-client-technologies/client-application-services-overview.md).</span></span>  
  
 <span data-ttu-id="9fa6f-110">Forms 身份验证过程需要访问正在运行的 [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)] 身份验证服务。</span><span class="sxs-lookup"><span data-stu-id="9fa6f-110">The forms authentication procedures require access to a running [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)] authentication service.</span></span> <span data-ttu-id="9fa6f-111">有关客户端应用程序服务功能端到端测试的指南，请参阅[演练：使用客户端应用程序服务](../../../docs/framework/common-client-technologies/walkthrough-using-client-application-services.md)。</span><span class="sxs-lookup"><span data-stu-id="9fa6f-111">For guidance on end-to-end testing of client application services features, see [Walkthrough: Using Client Application Services](../../../docs/framework/common-client-technologies/walkthrough-using-client-application-services.md).</span></span>  
  
### <a name="to-authenticate-a-user-with-forms-authentication-using-a-membership-credentials-provider"></a><span data-ttu-id="9fa6f-112">使用成员资格凭据提供程序通过 Forms 身份验证对用户进行身份验证</span><span class="sxs-lookup"><span data-stu-id="9fa6f-112">To authenticate a user with forms authentication using a membership credentials provider</span></span>  
  
1.  <span data-ttu-id="9fa6f-113">实现 <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider> 接口。</span><span class="sxs-lookup"><span data-stu-id="9fa6f-113">Implement the <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider> interface.</span></span> <span data-ttu-id="9fa6f-114">下面的代码示例演示从 <xref:System.Windows.Forms.Form?displayProperty=nameWithType> 派生的登录对话框类的 <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A?displayProperty=nameWithType> 实现。</span><span class="sxs-lookup"><span data-stu-id="9fa6f-114">The following code example shows a <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A?displayProperty=nameWithType> implementation for a login dialog box class derived from  <xref:System.Windows.Forms.Form?displayProperty=nameWithType>.</span></span> <span data-ttu-id="9fa6f-115">此对话框中具有用于输入用户名和密码的文本框，以及一个“记住我”复选框。</span><span class="sxs-lookup"><span data-stu-id="9fa6f-115">This dialog box has text boxes for user name and password and a "remember me" check box.</span></span> <span data-ttu-id="9fa6f-116">客户端身份验证提供程序调用 <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A> 方法时，会显示窗体。</span><span class="sxs-lookup"><span data-stu-id="9fa6f-116">When the client authentication provider calls the <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A> method, the form is displayed.</span></span> <span data-ttu-id="9fa6f-117">用户在登录对话框中填写信息并单击“确定”时，会在新 <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationCredentials> 对象中返回指定值。</span><span class="sxs-lookup"><span data-stu-id="9fa6f-117">When the user fills in the information in the login dialog box and clicks OK, the specified values are returned in a new <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationCredentials> object.</span></span>  
  
     [!code-csharp[ClientApplicationServices#210](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Login.cs#210)]
     [!code-vb[ClientApplicationServices#210](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Login.vb#210)]  
  
2.  <span data-ttu-id="9fa6f-118">调用 `static` <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=nameWithType> 方法并传入空字符串作为参数值。</span><span class="sxs-lookup"><span data-stu-id="9fa6f-118">Call the `static` <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=nameWithType> method and pass in empty strings as the parameter values.</span></span> <span data-ttu-id="9fa6f-119">指定空字符串时，此方法针对为应用程序配置的凭据提供程序在内部调用 <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="9fa6f-119">When you specify empty strings, this method internally calls the <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A> method for the credentials provider configured for your application.</span></span> <span data-ttu-id="9fa6f-120">下面的代码示例调用此方法以限制对整个 Windows 窗体应用程序的访问。</span><span class="sxs-lookup"><span data-stu-id="9fa6f-120">The following code example calls this method to restrict access to an entire Windows Forms application.</span></span> <span data-ttu-id="9fa6f-121">可以将此代码添加到 <xref:System.Windows.Forms.Form.Load?displayProperty=nameWithType> 处理程序。</span><span class="sxs-lookup"><span data-stu-id="9fa6f-121">You can add this code to a <xref:System.Windows.Forms.Form.Load?displayProperty=nameWithType> handler.</span></span>  
  
     [!code-csharp[ClientApplicationServices#317](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Class1.cs#317)]
     [!code-vb[ClientApplicationServices#317](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Class1.vb#317)]  
  
### <a name="to-authenticate-a-user-with-forms-authentication-without-using-a-membership-credentials-provider"></a><span data-ttu-id="9fa6f-122">在不使用成员资格凭据提供程序的情况下通过 Forms 身份验证对用户进行身份验证</span><span class="sxs-lookup"><span data-stu-id="9fa6f-122">To authenticate a user with forms authentication without using a membership credentials provider</span></span>  
  
-   <span data-ttu-id="9fa6f-123">调用 `static` <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=nameWithType> 方法并传入从用户检索的用户名和密码值。</span><span class="sxs-lookup"><span data-stu-id="9fa6f-123">Call the `static` <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=nameWithType> method and pass in user name and password values retrieved from the user.</span></span>  
  
     [!code-csharp[ClientApplicationServices#318](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Class1.cs#318)]
     [!code-vb[ClientApplicationServices#318](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Class1.vb#318)]  
  
### <a name="to-authenticate-a-user-with-windows-authentication"></a><span data-ttu-id="9fa6f-124">使用 Windows 身份验证对用户进行身份验证</span><span class="sxs-lookup"><span data-stu-id="9fa6f-124">To authenticate a user with Windows authentication</span></span>  
  
-   <span data-ttu-id="9fa6f-125">调用 `static` <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=nameWithType> 方法并传递空字符串用作参数。</span><span class="sxs-lookup"><span data-stu-id="9fa6f-125">Call the `static` <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=nameWithType> method and pass empty strings for the parameters.</span></span> <span data-ttu-id="9fa6f-126">此方法调用将始终返回 `true`，并会将 cookie 添加到包含 Windows 标识的用户 cookie 缓存。</span><span class="sxs-lookup"><span data-stu-id="9fa6f-126">This method call will always return `true` and will add a cookie to the user's cookie cache that contains the Windows identity.</span></span>  
  
     [!code-csharp[ClientApplicationServices#319](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Class1.cs#319)]
     [!code-vb[ClientApplicationServices#319](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Class1.vb#319)]  
  
## <a name="robust-programming"></a><span data-ttu-id="9fa6f-127">可靠编程</span><span class="sxs-lookup"><span data-stu-id="9fa6f-127">Robust Programming</span></span>  
 <span data-ttu-id="9fa6f-128">本主题中的代码示例演示 Windows 客户端应用程序中的身份验证的最简单用法。</span><span class="sxs-lookup"><span data-stu-id="9fa6f-128">The example code in this topic demonstrates the simplest usages of authentication in a Windows client application.</span></span> <span data-ttu-id="9fa6f-129">但是，对客户端应用程序服务和窗体身份验证调用 `static` <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=nameWithType> 方法时，代码可能会引发 <xref:System.Net.WebException>。</span><span class="sxs-lookup"><span data-stu-id="9fa6f-129">When you call the `static` <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=nameWithType> method with client application services and forms authentication, however, your code can throw a <xref:System.Net.WebException>.</span></span> <span data-ttu-id="9fa6f-130">这指示身份验证服务不可用。</span><span class="sxs-lookup"><span data-stu-id="9fa6f-130">This indicates that the authentication service is unavailable.</span></span> <span data-ttu-id="9fa6f-131">有关如何处理此异常的示例，请参阅[演练：使用客户端应用程序服务](../../../docs/framework/common-client-technologies/walkthrough-using-client-application-services.md)。</span><span class="sxs-lookup"><span data-stu-id="9fa6f-131">For an example of how to handle this exception, see [Walkthrough: Using Client Application Services](../../../docs/framework/common-client-technologies/walkthrough-using-client-application-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fa6f-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9fa6f-132">See Also</span></span>  
 [<span data-ttu-id="9fa6f-133">客户端应用程序服务</span><span class="sxs-lookup"><span data-stu-id="9fa6f-133">Client Application Services</span></span>](../../../docs/framework/common-client-technologies/client-application-services.md)  
 [<span data-ttu-id="9fa6f-134">客户端应用程序服务概述</span><span class="sxs-lookup"><span data-stu-id="9fa6f-134">Client Application Services Overview</span></span>](../../../docs/framework/common-client-technologies/client-application-services-overview.md)  
 [<span data-ttu-id="9fa6f-135">如何：配置客户端应用程序服务</span><span class="sxs-lookup"><span data-stu-id="9fa6f-135">How to: Configure Client Application Services</span></span>](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md)  
 [<span data-ttu-id="9fa6f-136">演练：使用客户端应用程序服务</span><span class="sxs-lookup"><span data-stu-id="9fa6f-136">Walkthrough: Using Client Application Services</span></span>](../../../docs/framework/common-client-technologies/walkthrough-using-client-application-services.md)  
 [<span data-ttu-id="9fa6f-137">将 Forms 身份验证用于 Microsoft Ajax</span><span class="sxs-lookup"><span data-stu-id="9fa6f-137">Using Forms Authentication with Microsoft Ajax</span></span>](http://msdn.microsoft.com/library/c50f7dc5-323c-4c63-b4f3-96edfc1e815e)
