---
title: "保证客户端应用程序的安全"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6239592e-fa7d-4dea-9f00-d296d0048b01
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 100def5fdf531527705fb0c1aebdc20674e0ce60
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="secure-client-applications"></a><span data-ttu-id="c393e-102">保证客户端应用程序的安全</span><span class="sxs-lookup"><span data-stu-id="c393e-102">Secure Client Applications</span></span>
<span data-ttu-id="c393e-103">应用程序通常由多个部件组成，所有这些部件均不能包含漏洞，否则可能导致数据丢失或以其他方式危害系统。</span><span class="sxs-lookup"><span data-stu-id="c393e-103">Applications typically consist of many parts that must all be protected from vulnerabilities that could result in data loss or otherwise compromise the system.</span></span> <span data-ttu-id="c393e-104">在攻击者可访问数据或系统资源之前将其阻止，以此可创建安全的用户界面来防止出现许多问题。</span><span class="sxs-lookup"><span data-stu-id="c393e-104">Creating secure user interfaces can prevent many problems by blocking attackers before they can access data or system resources.</span></span>  
  
## <a name="validate-user-input"></a><span data-ttu-id="c393e-105">验证用户输入</span><span class="sxs-lookup"><span data-stu-id="c393e-105">Validate User Input</span></span>  
 <span data-ttu-id="c393e-106">在构建访问数据的应用程序时，除非能够证明其不为恶意输入，否则您应该假定所有用户输入均为恶意输入。</span><span class="sxs-lookup"><span data-stu-id="c393e-106">When constructing an application that accesses data, you should assume that all user input is malicious until proven otherwise.</span></span> <span data-ttu-id="c393e-107">如果未能实现此目的，则可能会使您的应用程序易于受到攻击。</span><span class="sxs-lookup"><span data-stu-id="c393e-107">Failure to do so can leave your application vulnerable to attack.</span></span> <span data-ttu-id="c393e-108">.NET Framework 包含的类可帮助您约束输入控件的值的域，如限制可输入字符的数目。</span><span class="sxs-lookup"><span data-stu-id="c393e-108">The .NET Framework contains classes to help you enforce a domain of values for input controls, such as limiting the number of characters that can be entered.</span></span> <span data-ttu-id="c393e-109">使用事件挂钩，您可以编写用于检查值的有效性的程序。</span><span class="sxs-lookup"><span data-stu-id="c393e-109">Event hooks allow you to write procedures to check the validity of values.</span></span> <span data-ttu-id="c393e-110">可验证和强类型化用户输入数据，从而限制应用程序对脚本和 SQL 注入攻击的公开程度。</span><span class="sxs-lookup"><span data-stu-id="c393e-110">User input data can be validated and strongly typed, limiting an application's exposure to script and SQL injection exploits.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c393e-111">您还必须验证数据源和客户端应用程序中的用户输入。</span><span class="sxs-lookup"><span data-stu-id="c393e-111">You must also validate user input at the data source as well as in the client application.</span></span> <span data-ttu-id="c393e-112">因为攻击者可能选择避开应用程序，而直接攻击数据源。</span><span class="sxs-lookup"><span data-stu-id="c393e-112">An attacker may choose to circumvent your application and attack the data source directly.</span></span>  
  
 [<span data-ttu-id="c393e-113">安全性和用户输入</span><span class="sxs-lookup"><span data-stu-id="c393e-113">Security and User Input</span></span>](../../../../docs/standard/security/security-and-user-input.md)  
 <span data-ttu-id="c393e-114">描述如何处理与用户输入相关的细微和潜在危险缺陷。</span><span class="sxs-lookup"><span data-stu-id="c393e-114">Describes how to handle subtle and potentially dangerous bugs involving user input.</span></span>  
  
 [<span data-ttu-id="c393e-115">在 ASP.NET 网页验证用户输入</span><span class="sxs-lookup"><span data-stu-id="c393e-115">Validating User Input in ASP.NET Web Pages</span></span>](http://msdn.microsoft.com/library/4ad3dacb-89e0-4cee-89ac-40a3f2a85461)  
 <span data-ttu-id="c393e-116">概述如何使用 ASP.NET 验证控件验证用户输入。</span><span class="sxs-lookup"><span data-stu-id="c393e-116">Overview of validating user input using ASP.NET validation controls.</span></span>  
  
 [<span data-ttu-id="c393e-117">Windows 窗体中的用户输入</span><span class="sxs-lookup"><span data-stu-id="c393e-117">User Input in Windows Forms</span></span>](../../../../docs/framework/winforms/user-input-in-windows-forms.md)  
 <span data-ttu-id="c393e-118">提供用于验证 Windows 窗体应用程序中鼠标和键盘输入的链接和信息。</span><span class="sxs-lookup"><span data-stu-id="c393e-118">Provides links and information for validating mouse and keyboard input in a Windows Forms application.</span></span>  
  
 [<span data-ttu-id="c393e-119">.NET Framework 正则表达式</span><span class="sxs-lookup"><span data-stu-id="c393e-119">.NET Framework Regular Expressions</span></span>](../../../../docs/standard/base-types/regular-expressions.md)  
 <span data-ttu-id="c393e-120">描述如何使用 <xref:System.Text.RegularExpressions.Regex> 类检查用户输入的有效性。</span><span class="sxs-lookup"><span data-stu-id="c393e-120">Describes how to use the <xref:System.Text.RegularExpressions.Regex> class to check the validity of user input.</span></span>  
  
## <a name="windows-applications"></a><span data-ttu-id="c393e-121">Windows 应用程序</span><span class="sxs-lookup"><span data-stu-id="c393e-121">Windows Applications</span></span>  
 <span data-ttu-id="c393e-122">过去，Windows 应用程序通常使用完全权限运行。</span><span class="sxs-lookup"><span data-stu-id="c393e-122">In the past, Windows applications generally ran with full permissions.</span></span> <span data-ttu-id="c393e-123">通过使用代码启用安全性 (CAS)，.NET Framework 可提供限制在 Windows 应用程序中执行代码的基础结构。</span><span class="sxs-lookup"><span data-stu-id="c393e-123">The .NET Framework provides the infrastructure to restrict code executing in a Windows application by using code access security (CAS).</span></span> <span data-ttu-id="c393e-124">但是，仅使用 CAS 是不足以保护应用程序的。</span><span class="sxs-lookup"><span data-stu-id="c393e-124">However, CAS alone is not enough to protect your application.</span></span>  
  
 [<span data-ttu-id="c393e-125">Windows 窗体安全</span><span class="sxs-lookup"><span data-stu-id="c393e-125">Windows Forms Security</span></span>](../../../../docs/framework/winforms/windows-forms-security.md)  
 <span data-ttu-id="c393e-126">讨论如何保证 Windows 窗体应用程序的安全并提供相关主题的链接。</span><span class="sxs-lookup"><span data-stu-id="c393e-126">Discusses how to secure Windows Forms applications and provides links to related topics.</span></span>  
  
 [<span data-ttu-id="c393e-127">Windows 窗体和非托管应用程序</span><span class="sxs-lookup"><span data-stu-id="c393e-127">Windows Forms and Unmanaged Applications</span></span>](../../../../docs/framework/winforms/advanced/windows-forms-and-unmanaged-applications.md)  
 <span data-ttu-id="c393e-128">描述如何与 Windows 窗体应用程序中的非托管应用程序进行交互。</span><span class="sxs-lookup"><span data-stu-id="c393e-128">Describes how to interact with unmanaged applications in a Windows Forms application.</span></span>  
  
 [<span data-ttu-id="c393e-129">ClickOnce 部署适用于 Windows 窗体应用程序</span><span class="sxs-lookup"><span data-stu-id="c393e-129">ClickOnce Deployment for Windows Forms Applications</span></span>](http://msdn.microsoft.com/library/34d8c770-48f2-460c-8d67-4ea5684511df)  
 <span data-ttu-id="c393e-130">描述如何在 Windows 窗体应用程序中使用 `ClickOnce` 部署，并讨论安全含义。</span><span class="sxs-lookup"><span data-stu-id="c393e-130">Describes how to use `ClickOnce` deployment in a Windows Forms application and discusses the security implications.</span></span>  
  
## <a name="aspnet-and-xml-web-services"></a><span data-ttu-id="c393e-131">ASP.NET 和 XML Web services</span><span class="sxs-lookup"><span data-stu-id="c393e-131">ASP.NET and XML Web Services</span></span>  
 <span data-ttu-id="c393e-132">ASP.NET 应用程序通常需要限制对 Web 站点某些部分的访问，并提供其他数据保护机制和站点安全机制。</span><span class="sxs-lookup"><span data-stu-id="c393e-132">ASP.NET applications generally need to restrict access to some portions of the Web site and provide other mechanisms for data protection and site security.</span></span> <span data-ttu-id="c393e-133">这些链接可提供用于保护 ASP.NET 应用程序的有用信息。</span><span class="sxs-lookup"><span data-stu-id="c393e-133">These links provide useful information for securing your ASP.NET application.</span></span>  
  
 <span data-ttu-id="c393e-134">XML Web services 能够提供可由 ASP.NET 应用程序、Windows 窗体应用程序或其他 Web 服务使用的数据。</span><span class="sxs-lookup"><span data-stu-id="c393e-134">An XML Web service provides data that can be consumed by an ASP.NET application, a Windows Forms application, or another Web service.</span></span> <span data-ttu-id="c393e-135">您需要管理 Web 服务自身的安全性以及客户端应用程序的安全性。</span><span class="sxs-lookup"><span data-stu-id="c393e-135">You need to manage security for the Web service itself as well as security for the client application.</span></span>  
  
 <span data-ttu-id="c393e-136">有关更多信息，请参见以下资源。</span><span class="sxs-lookup"><span data-stu-id="c393e-136">For more information, see the following resources.</span></span>  
  
|<span data-ttu-id="c393e-137">资源</span><span class="sxs-lookup"><span data-stu-id="c393e-137">Resource</span></span>|<span data-ttu-id="c393e-138">描述</span><span class="sxs-lookup"><span data-stu-id="c393e-138">Description</span></span>|  
|--------------|-----------------|  
|[<span data-ttu-id="c393e-139">NIB: ASP.NET 安全</span><span class="sxs-lookup"><span data-stu-id="c393e-139">NIB: ASP.NET Security</span></span>](http://msdn.microsoft.com/library/04b37532-18d9-40b4-8e5f-ee09a70b311d)|<span data-ttu-id="c393e-140">讨论如何保证 ASP.NET 应用程序的安全。</span><span class="sxs-lookup"><span data-stu-id="c393e-140">Discusses how to secure ASP.NET applications.</span></span>|  
|[<span data-ttu-id="c393e-141">保护使用 ASP.NET 创建的 XML Web 服务</span><span class="sxs-lookup"><span data-stu-id="c393e-141">Securing XML Web Services Created Using ASP.NET</span></span>](http://msdn.microsoft.com/library/354b2ab1-2782-4542-b32a-dc560178b90c)|<span data-ttu-id="c393e-142">讨论如何实现 ASP.NET Web 服务的安全性。</span><span class="sxs-lookup"><span data-stu-id="c393e-142">Discusses how to implement security for an ASP.NET Web Service.</span></span>|  
|[<span data-ttu-id="c393e-143">脚本攻击概述</span><span class="sxs-lookup"><span data-stu-id="c393e-143">Script Exploits Overview</span></span>](http://msdn.microsoft.com/library/772c7312-211a-4eb3-8d6e-eec0aa1dcc07)|<span data-ttu-id="c393e-144">讨论如何抵御脚本攻击，该攻击会尝试将恶意字符插入网页。</span><span class="sxs-lookup"><span data-stu-id="c393e-144">Discusses how to guard against a script exploit attack, which attempts to insert malicious characters into a Web page.</span></span>|  
|[<span data-ttu-id="c393e-145">NIB： 基本的 ASP.NET Web 应用程序的安全方案</span><span class="sxs-lookup"><span data-stu-id="c393e-145">NIB:Basic Security Practices for ASP.NET Web Applications</span></span>](http://msdn.microsoft.com/library/94a52ab8-731d-417e-b997-721baf43df38)|<span data-ttu-id="c393e-146">常规安全信息和指向更多讨论的链接，</span><span class="sxs-lookup"><span data-stu-id="c393e-146">General security information and links to further discussion,</span></span>|  
  
## <a name="remoting"></a><span data-ttu-id="c393e-147">远程处理</span><span class="sxs-lookup"><span data-stu-id="c393e-147">Remoting</span></span>  
 <span data-ttu-id="c393e-148">利用 .NET 远程处理，可以方便地生成广泛分布的应用程序，而不论应用程序组件是全部集中在一台计算机上，还是分布在世界各地。</span><span class="sxs-lookup"><span data-stu-id="c393e-148">.NET remoting enables you to build widely distributed applications easily, whether the application components are all on one computer or spread out across the entire world.</span></span> <span data-ttu-id="c393e-149">生成的客户端应用程序可以使用同一台计算机（或可通过其网络连接到的任何其他计算机）上其他进程中的对象。</span><span class="sxs-lookup"><span data-stu-id="c393e-149">You can build client applications that use objects in other processes on the same computer or on any other computer that is reachable over its network.</span></span> <span data-ttu-id="c393e-150">您还可以在同一进程中使用 .NET 远程处理与其他应用程序域进行通信。</span><span class="sxs-lookup"><span data-stu-id="c393e-150">You can also use .NET remoting to communicate with other application domains in the same process.</span></span>  
  
|<span data-ttu-id="c393e-151">资源</span><span class="sxs-lookup"><span data-stu-id="c393e-151">Resource</span></span>|<span data-ttu-id="c393e-152">描述</span><span class="sxs-lookup"><span data-stu-id="c393e-152">Description</span></span>|  
|--------------|-----------------|  
|[<span data-ttu-id="c393e-153">远程应用程序配置</span><span class="sxs-lookup"><span data-stu-id="c393e-153">Configuration of Remote Applications</span></span>](http://msdn.microsoft.com/library/92c0c097-d984-4315-835b-7490ecdf1097)|<span data-ttu-id="c393e-154">讨论如何配置远程处理应用程序以避免出现常见问题。</span><span class="sxs-lookup"><span data-stu-id="c393e-154">Discusses how to configure remoting applications in order to avoid common problems.</span></span>|  
|[<span data-ttu-id="c393e-155">远程处理中的安全</span><span class="sxs-lookup"><span data-stu-id="c393e-155">Security in Remoting</span></span>](http://msdn.microsoft.com/library/9574262c-d4b1-41c5-8600-24ff147c0add)|<span data-ttu-id="c393e-156">描述身份验证和加密以及与远程处理相关的其他安全主题。</span><span class="sxs-lookup"><span data-stu-id="c393e-156">Describes authentication and encryption as well as additional security topics relevant to remoting.</span></span>|  
|[<span data-ttu-id="c393e-157">安全和远程处理注意事项</span><span class="sxs-lookup"><span data-stu-id="c393e-157">Security and Remoting Considerations</span></span>](../../../../docs/framework/misc/security-and-remoting-considerations.md)|<span data-ttu-id="c393e-158">描述与受保护对象和应用程序域交叉相关的安全问题。</span><span class="sxs-lookup"><span data-stu-id="c393e-158">Describes security issues with protected objects and application domain crossing.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c393e-159">请参阅</span><span class="sxs-lookup"><span data-stu-id="c393e-159">See Also</span></span>  
 [<span data-ttu-id="c393e-160">保证 ADO.NET 应用程序的安全</span><span class="sxs-lookup"><span data-stu-id="c393e-160">Securing ADO.NET Applications</span></span>](../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [<span data-ttu-id="c393e-161">数据访问策略的建议</span><span class="sxs-lookup"><span data-stu-id="c393e-161">Recommendations for Data Access Strategies</span></span>](http://msdn.microsoft.com/library/72411f32-d12a-4de8-b961-e54fca7faaf5)  
 [<span data-ttu-id="c393e-162">保护应用程序</span><span class="sxs-lookup"><span data-stu-id="c393e-162">Securing Applications</span></span>](/visualstudio/ide/securing-applications)  
 [<span data-ttu-id="c393e-163">保护连接信息</span><span class="sxs-lookup"><span data-stu-id="c393e-163">Protecting Connection Information</span></span>](../../../../docs/framework/data/adonet/protecting-connection-information.md)  
 [<span data-ttu-id="c393e-164">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="c393e-164">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
