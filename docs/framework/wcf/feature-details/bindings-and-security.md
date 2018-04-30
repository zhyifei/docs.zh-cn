---
title: 绑定与安全
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- bindings [WCF], security
- WCF security
- Windows Communication Foundation, security
- bindings [WCF]
ms.assetid: 4de03dd3-968a-4e65-af43-516e903d7f95
caps.latest.revision: 42
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload:
- dotnet
ms.openlocfilehash: 440bbcf03eef8f32a28073bfc9f5aeeb824a50fd
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2018
---
# <a name="bindings-and-security"></a><span data-ttu-id="9d3fc-102">绑定与安全</span><span class="sxs-lookup"><span data-stu-id="9d3fc-102">Bindings and Security</span></span>
<span data-ttu-id="9d3fc-103">包含在 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 中的系统提供的绑定提供了一种编写 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 应用程序的快捷方法。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-103">The system-provided bindings included with [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] offer a quick way to program [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications.</span></span> <span data-ttu-id="9d3fc-104">但有一个例外，就是所有绑定都启用了默认的安全方案。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-104">With one exception, all the bindings have a default security scheme enabled.</span></span> <span data-ttu-id="9d3fc-105">本主题将帮助你根据安全需要来选择正确的绑定。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-105">This topic helps you select the right binding for your security needs.</span></span>  
  
 <span data-ttu-id="9d3fc-106">有关概述[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]安全，请参阅[安全概述](../../../../docs/framework/wcf/feature-details/security-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-106">For an overview of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] security, see [Security Overview](../../../../docs/framework/wcf/feature-details/security-overview.md).</span></span> <span data-ttu-id="9d3fc-107">有关编程的详细信息[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]使用绑定，请参阅[编程 WCF 安全](../../../../docs/framework/wcf/feature-details/programming-wcf-security.md)。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-107">For more information about programming [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] using bindings, see [Programming WCF Security](../../../../docs/framework/wcf/feature-details/programming-wcf-security.md).</span></span>  
  
 <span data-ttu-id="9d3fc-108">如果你已选择一个绑定，则可以了解有关在中与安全性相关联的运行时行为的详细信息[安全行为](../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-108">If you have already selected a binding, you can find out more about the run-time behaviors that are associated with security in [Security Behaviors](../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md).</span></span>  
  
 <span data-ttu-id="9d3fc-109">部分安全性功能无法用系统提供的绑定进行编程。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-109">Some security functions are not programmable using the system-provided bindings.</span></span> <span data-ttu-id="9d3fc-110">使用自定义绑定的更多控制，请参阅[使用自定义绑定的安全功能](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-110">For more control using a custom binding, see [Security Capabilities with Custom Bindings](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md).</span></span>  
  
## <a name="security-functions-of-bindings"></a><span data-ttu-id="9d3fc-111">绑定的安全功能</span><span class="sxs-lookup"><span data-stu-id="9d3fc-111">Security Functions of Bindings</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9d3fc-112"> 包含许多由系统提供的绑定，这些绑定可以满足大多数需求。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-112"> includes a number of system-provided bindings that meet most needs.</span></span> <span data-ttu-id="9d3fc-113">如果某个特定绑定不能满足要求，你还可以创建自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-113">If a particular binding does not suffice, you can also create a custom binding.</span></span> <span data-ttu-id="9d3fc-114">系统提供的绑定的列表，请参阅[系统提供的绑定](../../../../docs/framework/wcf/system-provided-bindings.md)。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-114">For a list of system-provided bindings, see [System-Provided Bindings](../../../../docs/framework/wcf/system-provided-bindings.md).</span></span> <span data-ttu-id="9d3fc-115">有关自定义绑定的详细信息，请参阅[自定义绑定](../../../../docs/framework/wcf/extending/custom-bindings.md)。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-115">For more information about custom bindings, see [Custom Bindings](../../../../docs/framework/wcf/extending/custom-bindings.md).</span></span>  
  
 <span data-ttu-id="9d3fc-116">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 中的每个绑定都具有两种形式：一种是 API，一种是在配置文件中使用的 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-116">Every binding in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] has two forms: as an API and as an XML element used in a configuration file.</span></span> <span data-ttu-id="9d3fc-117">例如， `WSHttpBinding` (API) 具有一个对应[ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-117">For example, the `WSHttpBinding` (API) has a counterpart in the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span></span>  
  
 <span data-ttu-id="9d3fc-118">下一节列出了每个绑定的两种形式，并概括了安全功能。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-118">The following section lists both forms for each binding and summarizes the security features.</span></span>  
  
### <a name="basichttp"></a><span data-ttu-id="9d3fc-119">BasicHttp</span><span class="sxs-lookup"><span data-stu-id="9d3fc-119">BasicHttp</span></span>  
 <span data-ttu-id="9d3fc-120">在代码中，使用<xref:System.ServiceModel.BasicHttpBinding>类; 在配置中，使用[ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-120">In code, use the <xref:System.ServiceModel.BasicHttpBinding> class; in configuration, use the [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span></span>  
  
 <span data-ttu-id="9d3fc-121">此绑定的目的是与如下一系列现有技术一起使用：</span><span class="sxs-lookup"><span data-stu-id="9d3fc-121">This binding is designed for use with a range of existing technologies, including the following:</span></span>  
  
-   <span data-ttu-id="9d3fc-122">ASP.NET Web 服务 (ASMX) 版本 1。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-122">ASP.NET Web services (ASMX), version 1.</span></span>  
  
-   <span data-ttu-id="9d3fc-123">Web Service Enhancements (WSE) 应用程序。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-123">Web Service Enhancements (WSE) applications.</span></span>  
  
-   <span data-ttu-id="9d3fc-124">基本配置文件定义在 Web 服务互操作性 (WS-我) 规范 ([http://go.microsoft.com/fwlink/?LinkId=38955](http://go.microsoft.com/fwlink/?LinkId=38955))。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-124">Basic Profile as defined in the Web Services Interoperability (WS-I) specification ([http://go.microsoft.com/fwlink/?LinkId=38955](http://go.microsoft.com/fwlink/?LinkId=38955)).</span></span>  
  
-   <span data-ttu-id="9d3fc-125">WS-I 中定义的基本安全配置文件。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-125">Basic security profile as defined in WS-I.</span></span>  
  
 <span data-ttu-id="9d3fc-126">默认情况下，此绑定是不安全的。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-126">By default, this binding is not secure.</span></span> <span data-ttu-id="9d3fc-127">它的目的是与 ASMX 服务进行互操作。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-127">It is designed to interoperate with ASMX services.</span></span> <span data-ttu-id="9d3fc-128">启用安全性后，此绑定可以与 Internet 信息服务 (IIS) 安全机制（例如基本身份验证、摘要和 Windows 集成安全性）进行无缝的互操作。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-128">When security is enabled, the binding is designed for seamless interoperation with Internet Information Services (IIS) security mechanisms, such as basic authentication, digest, and integrated Windows security.</span></span> <span data-ttu-id="9d3fc-129">有关详细信息，请参阅[传输安全概述](../../../../docs/framework/wcf/feature-details/transport-security-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-129">For more information, see [Transport Security Overview](../../../../docs/framework/wcf/feature-details/transport-security-overview.md).</span></span> <span data-ttu-id="9d3fc-130">此绑定支持以下功能：</span><span class="sxs-lookup"><span data-stu-id="9d3fc-130">This binding supports the following:</span></span>  
  
-   <span data-ttu-id="9d3fc-131">HTTPS 传输安全。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-131">HTTPS transport security.</span></span>  
  
-   <span data-ttu-id="9d3fc-132">HTTP 基本身份验证。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-132">HTTP basic authentication.</span></span>  
  
-   <span data-ttu-id="9d3fc-133">WS-Security。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-133">WS-Security.</span></span>  
  
 <span data-ttu-id="9d3fc-134">有关详细信息，请参阅<xref:System.ServiceModel.BasicHttpSecurity>, <xref:System.ServiceModel.BasicHttpMessageSecurity>, <xref:System.ServiceModel.BasicHttpMessageCredentialType>和<xref:System.ServiceModel.BasicHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="9d3fc-134">For more information, see <xref:System.ServiceModel.BasicHttpSecurity>, <xref:System.ServiceModel.BasicHttpMessageSecurity>, <xref:System.ServiceModel.BasicHttpMessageCredentialType>, and <xref:System.ServiceModel.BasicHttpSecurityMode>.</span></span>  
  
### <a name="wshttpbinding"></a><span data-ttu-id="9d3fc-135">WSHttpBinding</span><span class="sxs-lookup"><span data-stu-id="9d3fc-135">WSHttpBinding</span></span>  
 <span data-ttu-id="9d3fc-136">在代码中，使用<xref:System.ServiceModel.WSHttpBinding>类; 在配置中，使用[ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-136">In code, use the <xref:System.ServiceModel.WSHttpBinding> class; in configuration, use the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span></span>  
  
 <span data-ttu-id="9d3fc-137">默认情况下，此绑定实现 WS-Security 规范，并提供与实现 WS-\* 规范的服务的互操作性。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-137">By default, this binding implements the WS-Security specification and provides interoperability with services that implement the WS-\* specifications.</span></span> <span data-ttu-id="9d3fc-138">它支持以下功能：</span><span class="sxs-lookup"><span data-stu-id="9d3fc-138">It supports the following:</span></span>  
  
-   <span data-ttu-id="9d3fc-139">HTTPS 传输安全。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-139">HTTPS transport security.</span></span>  
  
-   <span data-ttu-id="9d3fc-140">WS-Security。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-140">WS-Security.</span></span>  
  
-   <span data-ttu-id="9d3fc-141">使用 SOAP 消息凭据安全对调用方进行身份验证的 HTTPS 传输保护。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-141">HTTPS transport protection with SOAP message credential security for authenticating the caller.</span></span>  
  
 <span data-ttu-id="9d3fc-142">有关详细信息，请参阅<xref:System.ServiceModel.WSHttpSecurity>， <xref:System.ServiceModel.MessageSecurityOverHttp>， <xref:System.ServiceModel.MessageCredentialType>， <xref:System.ServiceModel.SecurityMode>， <xref:System.ServiceModel.HttpTransportSecurity>， <xref:System.ServiceModel.HttpClientCredentialType>，和<xref:System.ServiceModel.HttpProxyCredentialType>。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-142">For more information, see <xref:System.ServiceModel.WSHttpSecurity>, <xref:System.ServiceModel.MessageSecurityOverHttp>, <xref:System.ServiceModel.MessageCredentialType>, <xref:System.ServiceModel.SecurityMode>, <xref:System.ServiceModel.HttpTransportSecurity>, <xref:System.ServiceModel.HttpClientCredentialType>, and <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>  
  
### <a name="wsdualhttpbinding"></a><span data-ttu-id="9d3fc-143">WSDualHttpBinding</span><span class="sxs-lookup"><span data-stu-id="9d3fc-143">WSDualHttpBinding</span></span>  
 <span data-ttu-id="9d3fc-144">在代码中，使用<xref:System.ServiceModel.WSDualHttpBinding>类; 在配置中，使用[ \<wsDualHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-144">In code, use the <xref:System.ServiceModel.WSDualHttpBinding> class; in configuration, use the [\<wsDualHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>  
  
 <span data-ttu-id="9d3fc-145">此绑定的目的是启用双工服务应用程序。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-145">This binding is designed to enable duplex service applications.</span></span> <span data-ttu-id="9d3fc-146">此绑定实现了 WS-Security 规范，以便获得基于消息的传送安全。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-146">This binding implements the WS-Security specification for message-based transfer security.</span></span> <span data-ttu-id="9d3fc-147">传输安全不可用。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-147">Transport security is not available.</span></span> <span data-ttu-id="9d3fc-148">默认情况下，它提供下列功能：</span><span class="sxs-lookup"><span data-stu-id="9d3fc-148">By default, it provides the following features:</span></span>  
  
-   <span data-ttu-id="9d3fc-149">实现 WS-Reliable Messaging 以保证可靠性。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-149">Implements WS-Reliable Messaging for reliability.</span></span>  
  
-   <span data-ttu-id="9d3fc-150">实现 WS-Security 以保证传送安全和身份验证。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-150">Implements WS-Security for transfer security and authentication.</span></span>  
  
-   <span data-ttu-id="9d3fc-151">使用 HTTP 进行消息传递。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-151">Uses HTTP for message delivery.</span></span>  
  
-   <span data-ttu-id="9d3fc-152">使用文本/XML 消息编码。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-152">Uses text/XML message encoding.</span></span>  
  
 <span data-ttu-id="9d3fc-153">使用 WS-Security（消息层安全性），可通过此绑定配置下列参数：</span><span class="sxs-lookup"><span data-stu-id="9d3fc-153">Using WS-Security (message-layer security), the binding allows you to configure the following parameters:</span></span>  
  
-   <span data-ttu-id="9d3fc-154">用来确定加密算法的安全算法组。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-154">The security algorithm suite to determine the cryptographic algorithm.</span></span>  
  
-   <span data-ttu-id="9d3fc-155">下列功能的绑定选项：</span><span class="sxs-lookup"><span data-stu-id="9d3fc-155">Binding options for the following:</span></span>  
  
    -   <span data-ttu-id="9d3fc-156">提供可在客户端带外使用的服务凭据。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-156">Providing service credentials available out-of-band at the client.</span></span>  
  
    -   <span data-ttu-id="9d3fc-157">提供从服务协商的服务凭据作为通道设置的一部分。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-157">Providing service credentials negotiated from the service as part of channel setup.</span></span>  
  
 <span data-ttu-id="9d3fc-158">有关详细信息，请参阅 <xref:System.ServiceModel.WSDualHttpSecurity> 和 <xref:System.ServiceModel.WSDualHttpSecurityMode>。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-158">For more information, see <xref:System.ServiceModel.WSDualHttpSecurity> and <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span></span>  
  
### <a name="nettcpbinding"></a><span data-ttu-id="9d3fc-159">NetTcpBinding</span><span class="sxs-lookup"><span data-stu-id="9d3fc-159">NetTcpBinding</span></span>  
 <span data-ttu-id="9d3fc-160">在代码中，使用<xref:System.ServiceModel.NetTcpBinding>类; 在配置中，使用[ \<netTcpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-160">In code, use the <xref:System.ServiceModel.NetTcpBinding> class; in configuration, use the [\<netTcpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).</span></span>  
  
 <span data-ttu-id="9d3fc-161">此绑定针对计算机之间的通信进行了优化。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-161">This binding is optimized for cross-machine communication.</span></span> <span data-ttu-id="9d3fc-162">默认情况下，它具有以下特征：</span><span class="sxs-lookup"><span data-stu-id="9d3fc-162">By default, it has the following characteristics:</span></span>  
  
-   <span data-ttu-id="9d3fc-163">实现传输层安全性。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-163">Implements transport-layer security.</span></span>  
  
-   <span data-ttu-id="9d3fc-164">利用 Windows 安全性来实现传送安全性和身份验证。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-164">Leverages Windows security for transfer security and authentication.</span></span>  
  
-   <span data-ttu-id="9d3fc-165">使用 TCP 进行传输。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-165">Uses TCP for transport.</span></span>  
  
-   <span data-ttu-id="9d3fc-166">实现二进制消息编码。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-166">Implements binary message encoding.</span></span>  
  
-   <span data-ttu-id="9d3fc-167">实现 WS-Reliable Messaging。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-167">Implements WS-Reliable Messaging.</span></span>  
  
 <span data-ttu-id="9d3fc-168">此绑定具有下列选项：</span><span class="sxs-lookup"><span data-stu-id="9d3fc-168">Options include the following:</span></span>  
  
-   <span data-ttu-id="9d3fc-169">消息层安全性（使用 WS-Security）。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-169">Message-layer security (using WS-Security).</span></span>  
  
-   <span data-ttu-id="9d3fc-170">使用消息凭据实现传输安全性：保密性和完整性由 Transport Layer Security (TLS) over TCP 提供，授权凭据由 WS-Security 提供。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-170">Transport security with message credential—confidentiality and integrity provided by Transport Layer Security (TLS) over TCP, and credentials for authorization provided by WS-Security.</span></span>  
  
 <span data-ttu-id="9d3fc-171">有关详细信息，请参阅<xref:System.ServiceModel.NetTcpSecurity>， <xref:System.ServiceModel.TcpTransportSecurity>， <xref:System.ServiceModel.TcpClientCredentialType>， <xref:System.ServiceModel.MessageSecurityOverTcp>，和<xref:System.ServiceModel.MessageCredentialType>。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-171">For more information, see <xref:System.ServiceModel.NetTcpSecurity>, <xref:System.ServiceModel.TcpTransportSecurity>, <xref:System.ServiceModel.TcpClientCredentialType>, <xref:System.ServiceModel.MessageSecurityOverTcp>, and <xref:System.ServiceModel.MessageCredentialType>.</span></span>  
  
### <a name="netnamedpipebinding"></a><span data-ttu-id="9d3fc-172">NetNamedPipeBinding</span><span class="sxs-lookup"><span data-stu-id="9d3fc-172">NetNamedPipeBinding</span></span>  
 <span data-ttu-id="9d3fc-173">在代码中，使用<xref:System.ServiceModel.NetNamedPipeBinding>类; 在配置中，使用[ \<netNamedPipeBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/netnamedpipebinding.md)。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-173">In code, use the <xref:System.ServiceModel.NetNamedPipeBinding> class; in configuration, use the [\<netNamedPipeBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/netnamedpipebinding.md).</span></span>  
  
 <span data-ttu-id="9d3fc-174">此绑定针对进程之间的通信（通常在同一台计算机上）进行了优化。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-174">This binding is optimized for cross-process communication (usually on the same machine).</span></span> <span data-ttu-id="9d3fc-175">默认情况下，此绑定具有以下特征：</span><span class="sxs-lookup"><span data-stu-id="9d3fc-175">By default, this binding has the following characteristics:</span></span>  
  
-   <span data-ttu-id="9d3fc-176">使用传输安全性来实现消息传输和身份验证。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-176">Uses transport security for message transfer and authentication.</span></span>  
  
-   <span data-ttu-id="9d3fc-177">使用命名管道进行消息传递。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-177">Uses named pipes for message delivery.</span></span>  
  
-   <span data-ttu-id="9d3fc-178">实现二进制消息编码。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-178">Implements binary message encoding.</span></span>  
  
-   <span data-ttu-id="9d3fc-179">加密和消息签名。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-179">Encryption and message signing.</span></span>  
  
 <span data-ttu-id="9d3fc-180">此绑定具有下列选项：</span><span class="sxs-lookup"><span data-stu-id="9d3fc-180">Options include the following:</span></span>  
  
-   <span data-ttu-id="9d3fc-181">使用 Windows 安全性进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-181">Authentication using Windows security.</span></span>  
  
 <span data-ttu-id="9d3fc-182">有关详细信息，请参阅<xref:System.ServiceModel.NetNamedPipeSecurity>、<xref:System.ServiceModel.NetNamedPipeSecurityMode>和<xref:System.ServiceModel.NamedPipeTransportSecurity>。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-182">For more information, see <xref:System.ServiceModel.NetNamedPipeSecurity>, <xref:System.ServiceModel.NetNamedPipeSecurityMode>, and <xref:System.ServiceModel.NamedPipeTransportSecurity>.</span></span>  
  
### <a name="msmqintegrationbinding"></a><span data-ttu-id="9d3fc-183">MsmqIntegrationBinding</span><span class="sxs-lookup"><span data-stu-id="9d3fc-183">MsmqIntegrationBinding</span></span>  
 <span data-ttu-id="9d3fc-184">在代码中，使用<xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>类; 在配置中，使用[ \<msmqIntegrationBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-184">In code, use the <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> class; in configuration, use the [\<msmqIntegrationBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md).</span></span>  
  
 <span data-ttu-id="9d3fc-185">此绑定最适合于创建与非 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Microsoft 消息队列 (MSMQ) 终结点进行互操作的 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 客户端和服务。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-185">This binding is optimized for creating [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] clients and services that interoperate with non-[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Microsoft Message Queuing (MSMQ) endpoints.</span></span>  
  
 <span data-ttu-id="9d3fc-186">默认情况下，此绑定使用传输安全性并提供下列安全特征：</span><span class="sxs-lookup"><span data-stu-id="9d3fc-186">By default, this binding uses transport security and provides the following security characteristics:</span></span>  
  
-   <span data-ttu-id="9d3fc-187">可以禁用安全性 (None)。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-187">Security can be disabled (None).</span></span>  
  
-   <span data-ttu-id="9d3fc-188">MSMQ 传输安全性 (Transport)。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-188">MSMQ transport security (Transport).</span></span>  
  
 <span data-ttu-id="9d3fc-189">有关详细信息，请参阅 <xref:System.ServiceModel.NetMsmqSecurity> 和 <xref:System.ServiceModel.NetMsmqSecurityMode>。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-189">For more information, see <xref:System.ServiceModel.NetMsmqSecurity> and <xref:System.ServiceModel.NetMsmqSecurityMode>.</span></span>  
  
### <a name="netmsmqbinding"></a><span data-ttu-id="9d3fc-190">NetMsmqBinding</span><span class="sxs-lookup"><span data-stu-id="9d3fc-190">NetMsmqBinding</span></span>  
 <span data-ttu-id="9d3fc-191">在代码中，使用<xref:System.ServiceModel.NetMsmqBinding>类; 在配置中，使用[ \<netMsmqBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-191">In code, use the <xref:System.ServiceModel.NetMsmqBinding> class; in configuration, use the [\<netMsmqBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md).</span></span>  
  
 <span data-ttu-id="9d3fc-192">此绑定适合在创建需要 MSMQ 排队消息支持的 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务时使用。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-192">This binding is intended for use when creating [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services that require MSMQ queued message support.</span></span>  
  
 <span data-ttu-id="9d3fc-193">默认情况下，此绑定使用传输安全性并提供下列安全特征：</span><span class="sxs-lookup"><span data-stu-id="9d3fc-193">By default, this binding uses transport security and provides the following security characteristics:</span></span>  
  
-   <span data-ttu-id="9d3fc-194">可以禁用安全性 (None)。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-194">Security can be disabled (None).</span></span>  
  
-   <span data-ttu-id="9d3fc-195">MSMQ 传输安全性 (Transport)。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-195">MSMQ transport security (Transport).</span></span>  
  
-   <span data-ttu-id="9d3fc-196">基于 SOAP 的消息安全性 (Message)。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-196">SOAP-based message security (Message).</span></span>  
  
-   <span data-ttu-id="9d3fc-197">同时启用传输安全性和消息安全性 (Both)。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-197">Simultaneous Transport and Message security (Both).</span></span>  
  
-   <span data-ttu-id="9d3fc-198">支持的客户端凭据类型：None、Windows、UserName、Certificate、IssuedToken。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-198">Client Credential Types supported: None, Windows, UserName, Certificate, IssuedToken.</span></span>  
  
 <span data-ttu-id="9d3fc-199">仅当安全模式设置为 <xref:System.ServiceModel.MessageCredentialType.Certificate> 或 <xref:System.ServiceModel.NetMsmqSecurityMode.Both> 时，才支持 <xref:System.ServiceModel.NetMsmqSecurityMode.Message> 凭据。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-199">The <xref:System.ServiceModel.MessageCredentialType.Certificate> credential is supported only when the security mode is set to either <xref:System.ServiceModel.NetMsmqSecurityMode.Both> or <xref:System.ServiceModel.NetMsmqSecurityMode.Message>.</span></span>  
  
 <span data-ttu-id="9d3fc-200">有关详细信息，请参阅 <xref:System.ServiceModel.MessageSecurityOverMsmq> 和 <xref:System.ServiceModel.MsmqTransportSecurity>。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-200">For more information, see <xref:System.ServiceModel.MessageSecurityOverMsmq> and <xref:System.ServiceModel.MsmqTransportSecurity>.</span></span>  
  
### <a name="wsfederationhttpbinding"></a><span data-ttu-id="9d3fc-201">WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="9d3fc-201">WSFederationHttpBinding</span></span>  
 <span data-ttu-id="9d3fc-202">在代码中，使用<xref:System.ServiceModel.WSFederationHttpBinding>类; 在配置中，使用[ \<wsFederationHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-202">In code, use the <xref:System.ServiceModel.WSFederationHttpBinding> class; in configuration, use the [\<wsFederationHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span></span>  
  
 <span data-ttu-id="9d3fc-203">默认情况下，此绑定使用 WS-Security（消息层安全性）。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-203">By default, this binding uses WS-Security (message-layer security).</span></span>  
  
 <span data-ttu-id="9d3fc-204">有关详细信息，请参阅[联合身份验证](../../../../docs/framework/wcf/feature-details/federation.md)， <xref:System.ServiceModel.WSFederationHttpSecurity>，和<xref:System.ServiceModel.WSFederationHttpSecurityMode>。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-204">For more information, see [Federation](../../../../docs/framework/wcf/feature-details/federation.md), <xref:System.ServiceModel.WSFederationHttpSecurity>, and <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>  
  
## <a name="custom-bindings"></a><span data-ttu-id="9d3fc-205">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="9d3fc-205">Custom Bindings</span></span>  
 <span data-ttu-id="9d3fc-206">如果系统提供的绑定都不能满足您的需求，则可以使用自定义安全绑定元素来创建自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-206">If none of the system-provided bindings meets you requirements, you can create a custom binding with a custom security binding element.</span></span> <span data-ttu-id="9d3fc-207">有关详细信息，请参阅[使用自定义绑定的安全功能](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-207">For more information, see [Security Capabilities with Custom Bindings](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md).</span></span>  
  
## <a name="binding-choices"></a><span data-ttu-id="9d3fc-208">绑定选择</span><span class="sxs-lookup"><span data-stu-id="9d3fc-208">Binding Choices</span></span>  
 <span data-ttu-id="9d3fc-209">下表概括了安全模式设置中提供的功能，也就是说，它列出了当安全模式设置为 `Transport`、`Message` 或 `TransportWithMessageCredential` 时可以使用的功能。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-209">The following table summarizes the features offered in the security mode setting, that is, it lists the features available when the security mode is set to `Transport`, `Message`, or `TransportWithMessageCredential`.</span></span> <span data-ttu-id="9d3fc-210">使用此表可帮助您找到应用程序所需的安全功能。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-210">Use this table to help you find the security features your application requires.</span></span>  
  
|<span data-ttu-id="9d3fc-211">设置</span><span class="sxs-lookup"><span data-stu-id="9d3fc-211">Setting</span></span>|<span data-ttu-id="9d3fc-212">功能</span><span class="sxs-lookup"><span data-stu-id="9d3fc-212">Features</span></span>|  
|-------------|--------------|  
|<span data-ttu-id="9d3fc-213">传输</span><span class="sxs-lookup"><span data-stu-id="9d3fc-213">Transport</span></span>|<span data-ttu-id="9d3fc-214">服务器身份验证</span><span class="sxs-lookup"><span data-stu-id="9d3fc-214">Server authentication</span></span><br /><br /> <span data-ttu-id="9d3fc-215">客户端身份验证</span><span class="sxs-lookup"><span data-stu-id="9d3fc-215">Client authentication</span></span><br /><br /> <span data-ttu-id="9d3fc-216">点对点安全性</span><span class="sxs-lookup"><span data-stu-id="9d3fc-216">Point-to-point security</span></span><br /><br /> <span data-ttu-id="9d3fc-217">互操作性</span><span class="sxs-lookup"><span data-stu-id="9d3fc-217">Interoperability</span></span><br /><br /> <span data-ttu-id="9d3fc-218">硬件加速</span><span class="sxs-lookup"><span data-stu-id="9d3fc-218">Hardware acceleration</span></span><br /><br /> <span data-ttu-id="9d3fc-219">高吞吐量</span><span class="sxs-lookup"><span data-stu-id="9d3fc-219">High throughput</span></span><br /><br /> <span data-ttu-id="9d3fc-220">安全防火墙</span><span class="sxs-lookup"><span data-stu-id="9d3fc-220">Secure firewall</span></span><br /><br /> <span data-ttu-id="9d3fc-221">高延迟应用程序</span><span class="sxs-lookup"><span data-stu-id="9d3fc-221">High-latency applications</span></span><br /><br /> <span data-ttu-id="9d3fc-222">跨越多个跃点重新加密</span><span class="sxs-lookup"><span data-stu-id="9d3fc-222">Re-encryption across multiple hops</span></span>|  
|<span data-ttu-id="9d3fc-223">消息</span><span class="sxs-lookup"><span data-stu-id="9d3fc-223">Message</span></span>|<span data-ttu-id="9d3fc-224">服务器身份验证</span><span class="sxs-lookup"><span data-stu-id="9d3fc-224">Server authentication</span></span><br /><br /> <span data-ttu-id="9d3fc-225">客户端身份验证</span><span class="sxs-lookup"><span data-stu-id="9d3fc-225">Client authentication</span></span><br /><br /> <span data-ttu-id="9d3fc-226">端对端安全性</span><span class="sxs-lookup"><span data-stu-id="9d3fc-226">End-to-end security</span></span><br /><br /> <span data-ttu-id="9d3fc-227">互操作性</span><span class="sxs-lookup"><span data-stu-id="9d3fc-227">Interoperability</span></span><br /><br /> <span data-ttu-id="9d3fc-228">丰富的声明</span><span class="sxs-lookup"><span data-stu-id="9d3fc-228">Rich claims</span></span><br /><br /> <span data-ttu-id="9d3fc-229">联合</span><span class="sxs-lookup"><span data-stu-id="9d3fc-229">Federation</span></span><br /><br /> <span data-ttu-id="9d3fc-230">多因素身份验证</span><span class="sxs-lookup"><span data-stu-id="9d3fc-230">Multifactor authentication</span></span><br /><br /> <span data-ttu-id="9d3fc-231">自定义令牌</span><span class="sxs-lookup"><span data-stu-id="9d3fc-231">Custom tokens</span></span><br /><br /> <span data-ttu-id="9d3fc-232">公证人/时间戳服务</span><span class="sxs-lookup"><span data-stu-id="9d3fc-232">Notary/timestamp service</span></span><br /><br /> <span data-ttu-id="9d3fc-233">高延迟应用程序</span><span class="sxs-lookup"><span data-stu-id="9d3fc-233">High-latency applications</span></span><br /><br /> <span data-ttu-id="9d3fc-234">消息签名的持久性</span><span class="sxs-lookup"><span data-stu-id="9d3fc-234">Persistence of message signatures</span></span>|  
|<span data-ttu-id="9d3fc-235">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="9d3fc-235">TransportWithMessageCredential</span></span>|<span data-ttu-id="9d3fc-236">服务器身份验证</span><span class="sxs-lookup"><span data-stu-id="9d3fc-236">Server authentication</span></span><br /><br /> <span data-ttu-id="9d3fc-237">客户端身份验证</span><span class="sxs-lookup"><span data-stu-id="9d3fc-237">Client authentication</span></span><br /><br /> <span data-ttu-id="9d3fc-238">点对点安全性</span><span class="sxs-lookup"><span data-stu-id="9d3fc-238">Point-to-point security</span></span><br /><br /> <span data-ttu-id="9d3fc-239">互操作性</span><span class="sxs-lookup"><span data-stu-id="9d3fc-239">Interoperability</span></span><br /><br /> <span data-ttu-id="9d3fc-240">硬件加速</span><span class="sxs-lookup"><span data-stu-id="9d3fc-240">Hardware acceleration</span></span><br /><br /> <span data-ttu-id="9d3fc-241">高吞吐量</span><span class="sxs-lookup"><span data-stu-id="9d3fc-241">High throughput</span></span><br /><br /> <span data-ttu-id="9d3fc-242">丰富的客户端声明</span><span class="sxs-lookup"><span data-stu-id="9d3fc-242">Rich client claims</span></span><br /><br /> <span data-ttu-id="9d3fc-243">联合</span><span class="sxs-lookup"><span data-stu-id="9d3fc-243">Federation</span></span><br /><br /> <span data-ttu-id="9d3fc-244">多因素身份验证</span><span class="sxs-lookup"><span data-stu-id="9d3fc-244">Multifactor authentication</span></span><br /><br /> <span data-ttu-id="9d3fc-245">自定义令牌</span><span class="sxs-lookup"><span data-stu-id="9d3fc-245">Custom tokens</span></span><br /><br /> <span data-ttu-id="9d3fc-246">安全防火墙</span><span class="sxs-lookup"><span data-stu-id="9d3fc-246">Secure firewall</span></span><br /><br /> <span data-ttu-id="9d3fc-247">高延迟应用程序</span><span class="sxs-lookup"><span data-stu-id="9d3fc-247">High-latency applications</span></span><br /><br /> <span data-ttu-id="9d3fc-248">跨越多个跃点重新加密</span><span class="sxs-lookup"><span data-stu-id="9d3fc-248">Re-encryption across multiple hops</span></span>|  
  
 <span data-ttu-id="9d3fc-249">下表列出了支持各种模式设置的绑定。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-249">The following table lists the bindings that support the various mode settings.</span></span> <span data-ttu-id="9d3fc-250">请从该表中选择用来创建服务终结点的绑定。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-250">Select a binding from the table to use to create your service endpoint.</span></span>  
  
|<span data-ttu-id="9d3fc-251">绑定</span><span class="sxs-lookup"><span data-stu-id="9d3fc-251">Binding</span></span>|<span data-ttu-id="9d3fc-252">是否支持 Transport 模式</span><span class="sxs-lookup"><span data-stu-id="9d3fc-252">Transport mode support</span></span>|<span data-ttu-id="9d3fc-253">是否支持 Message 模式</span><span class="sxs-lookup"><span data-stu-id="9d3fc-253">Message mode support</span></span>|<span data-ttu-id="9d3fc-254">是否支持 TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="9d3fc-254">TransportWithMessageCredential support</span></span>|  
|-------------|----------------------------|--------------------------|--------------------------------------------|  
|`BasicHttpBinding`|<span data-ttu-id="9d3fc-255">是</span><span class="sxs-lookup"><span data-stu-id="9d3fc-255">Yes</span></span>|<span data-ttu-id="9d3fc-256">是</span><span class="sxs-lookup"><span data-stu-id="9d3fc-256">Yes</span></span>|<span data-ttu-id="9d3fc-257">是</span><span class="sxs-lookup"><span data-stu-id="9d3fc-257">Yes</span></span>|  
|`WSHttpBinding`|<span data-ttu-id="9d3fc-258">是</span><span class="sxs-lookup"><span data-stu-id="9d3fc-258">Yes</span></span>|<span data-ttu-id="9d3fc-259">是</span><span class="sxs-lookup"><span data-stu-id="9d3fc-259">Yes</span></span>|<span data-ttu-id="9d3fc-260">是</span><span class="sxs-lookup"><span data-stu-id="9d3fc-260">Yes</span></span>|  
|`WSDualHttpBinding`|<span data-ttu-id="9d3fc-261">No</span><span class="sxs-lookup"><span data-stu-id="9d3fc-261">No</span></span>|<span data-ttu-id="9d3fc-262">是</span><span class="sxs-lookup"><span data-stu-id="9d3fc-262">Yes</span></span>|<span data-ttu-id="9d3fc-263">No</span><span class="sxs-lookup"><span data-stu-id="9d3fc-263">No</span></span>|  
|`NetTcpBinding`|<span data-ttu-id="9d3fc-264">是</span><span class="sxs-lookup"><span data-stu-id="9d3fc-264">Yes</span></span>|<span data-ttu-id="9d3fc-265">是</span><span class="sxs-lookup"><span data-stu-id="9d3fc-265">Yes</span></span>|<span data-ttu-id="9d3fc-266">是</span><span class="sxs-lookup"><span data-stu-id="9d3fc-266">Yes</span></span>|  
|`NetNamedPipeBinding`|<span data-ttu-id="9d3fc-267">是</span><span class="sxs-lookup"><span data-stu-id="9d3fc-267">Yes</span></span>|<span data-ttu-id="9d3fc-268">No</span><span class="sxs-lookup"><span data-stu-id="9d3fc-268">No</span></span>|<span data-ttu-id="9d3fc-269">否</span><span class="sxs-lookup"><span data-stu-id="9d3fc-269">No</span></span>|  
|`NetMsmqBinding`|<span data-ttu-id="9d3fc-270">是</span><span class="sxs-lookup"><span data-stu-id="9d3fc-270">Yes</span></span>|<span data-ttu-id="9d3fc-271">是</span><span class="sxs-lookup"><span data-stu-id="9d3fc-271">Yes</span></span>|<span data-ttu-id="9d3fc-272">No</span><span class="sxs-lookup"><span data-stu-id="9d3fc-272">No</span></span>|  
|`MsmqIntegrationBinding`|<span data-ttu-id="9d3fc-273">是</span><span class="sxs-lookup"><span data-stu-id="9d3fc-273">Yes</span></span>|<span data-ttu-id="9d3fc-274">No</span><span class="sxs-lookup"><span data-stu-id="9d3fc-274">No</span></span>|<span data-ttu-id="9d3fc-275">否</span><span class="sxs-lookup"><span data-stu-id="9d3fc-275">No</span></span>|  
|`wsFederationHttpBinding`|<span data-ttu-id="9d3fc-276">否</span><span class="sxs-lookup"><span data-stu-id="9d3fc-276">No</span></span>|<span data-ttu-id="9d3fc-277">是</span><span class="sxs-lookup"><span data-stu-id="9d3fc-277">Yes</span></span>|<span data-ttu-id="9d3fc-278">是</span><span class="sxs-lookup"><span data-stu-id="9d3fc-278">Yes</span></span>|  
  
## <a name="transport-credentials-in-bindings"></a><span data-ttu-id="9d3fc-279">绑定中的传输凭据</span><span class="sxs-lookup"><span data-stu-id="9d3fc-279">Transport Credentials in Bindings</span></span>  
 <span data-ttu-id="9d3fc-280">下表列出了在传输安全模式下使用 `BasicHttpBinding` 或 `WSHttpBinding` 时可用的客户端凭据类型。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-280">The following table lists the client credential types available when using either `BasicHttpBinding` or `WSHttpBinding` in transport security mode.</span></span>  
  
|<span data-ttu-id="9d3fc-281">类型</span><span class="sxs-lookup"><span data-stu-id="9d3fc-281">Type</span></span>|<span data-ttu-id="9d3fc-282">描述</span><span class="sxs-lookup"><span data-stu-id="9d3fc-282">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="9d3fc-283">无</span><span class="sxs-lookup"><span data-stu-id="9d3fc-283">None</span></span>|<span data-ttu-id="9d3fc-284">指定客户端不需要提供任何凭据。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-284">Specifies that the client does not need to present any credential.</span></span> <span data-ttu-id="9d3fc-285">这相当于匿名客户端。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-285">This translates to an anonymous client.</span></span>|  
|<span data-ttu-id="9d3fc-286">Basic</span><span class="sxs-lookup"><span data-stu-id="9d3fc-286">Basic</span></span>|<span data-ttu-id="9d3fc-287">基本身份验证</span><span class="sxs-lookup"><span data-stu-id="9d3fc-287">Basic authentication.</span></span> <span data-ttu-id="9d3fc-288">有关详细信息，请参阅 RFC 2617 – HTTP 身份验证： 基本和摘要式身份验证，在[ http://go.microsoft.com/fwlink/?LinkId=84023 ](http://go.microsoft.com/fwlink/?LinkId=84023)。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-288">For more information, see RFC 2617 – HTTP Authentication: Basic and Digest Authentication, available at [http://go.microsoft.com/fwlink/?LinkId=84023](http://go.microsoft.com/fwlink/?LinkId=84023).</span></span>|  
|<span data-ttu-id="9d3fc-289">摘要</span><span class="sxs-lookup"><span data-stu-id="9d3fc-289">Digest</span></span>|<span data-ttu-id="9d3fc-290">摘要式身份验证。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-290">Digest authentication.</span></span> <span data-ttu-id="9d3fc-291">有关详细信息，请参阅 RFC 2617 – HTTP 身份验证： 基本和摘要式身份验证，在[ http://go.microsoft.com/fwlink/?LinkId=84023 ](http://go.microsoft.com/fwlink/?LinkId=84023)。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-291">For more information, see RFC 2617 – HTTP Authentication: Basic and Digest Authentication, available at [http://go.microsoft.com/fwlink/?LinkId=84023](http://go.microsoft.com/fwlink/?LinkId=84023).</span></span>|  
|<span data-ttu-id="9d3fc-292">NTLM</span><span class="sxs-lookup"><span data-stu-id="9d3fc-292">NTLM</span></span>|<span data-ttu-id="9d3fc-293">NT LAN Manager (NTLM) 身份验证。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-293">NT LAN Manager (NTLM) authentication.</span></span>|  
|<span data-ttu-id="9d3fc-294">Windows</span><span class="sxs-lookup"><span data-stu-id="9d3fc-294">Windows</span></span>|<span data-ttu-id="9d3fc-295">Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-295">Windows authentication.</span></span>|  
|<span data-ttu-id="9d3fc-296">证书</span><span class="sxs-lookup"><span data-stu-id="9d3fc-296">Certificate</span></span>|<span data-ttu-id="9d3fc-297">使用证书执行的身份验证。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-297">Authentication performed using a certificate.</span></span>|  
|<span data-ttu-id="9d3fc-298">IssuedToken</span><span class="sxs-lookup"><span data-stu-id="9d3fc-298">IssuedToken</span></span>|<span data-ttu-id="9d3fc-299">允许服务要求使用由安全令牌服务或 [!INCLUDE[infocard](../../../../includes/infocard-md.md)] 颁发的令牌对客户端进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-299">Allows the service to require that the client be authenticated using a token issued by a security token service or by [!INCLUDE[infocard](../../../../includes/infocard-md.md)].</span></span> <span data-ttu-id="9d3fc-300">有关详细信息，请参阅[联合身份验证和颁发令牌](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-300">For more information, see [Federation and Issued Tokens](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span></span>|  
  
### <a name="message-client-credentials-in-bindings"></a><span data-ttu-id="9d3fc-301">绑定中的消息客户端凭据</span><span class="sxs-lookup"><span data-stu-id="9d3fc-301">Message Client Credentials in Bindings</span></span>  
 <span data-ttu-id="9d3fc-302">下表列出在 Message 安全模式下使用绑定时可用的客户端凭据类型。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-302">The following table lists the client credential types available when using a binding in Message security mode.</span></span>  
  
|<span data-ttu-id="9d3fc-303">类型</span><span class="sxs-lookup"><span data-stu-id="9d3fc-303">Type</span></span>|<span data-ttu-id="9d3fc-304">描述</span><span class="sxs-lookup"><span data-stu-id="9d3fc-304">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="9d3fc-305">无</span><span class="sxs-lookup"><span data-stu-id="9d3fc-305">None</span></span>|<span data-ttu-id="9d3fc-306">允许服务与匿名客户端交互。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-306">Allows the service to interact with anonymous clients.</span></span>|  
|<span data-ttu-id="9d3fc-307">Windows</span><span class="sxs-lookup"><span data-stu-id="9d3fc-307">Windows</span></span>|<span data-ttu-id="9d3fc-308">允许在 Windows 凭据的已通过身份验证的上下文中执行 SOAP 消息交换。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-308">Allows SOAP message exchanges to be made under the authenticated context of a Windows credential.</span></span>|  
|<span data-ttu-id="9d3fc-309">UserName</span><span class="sxs-lookup"><span data-stu-id="9d3fc-309">UserName</span></span>|<span data-ttu-id="9d3fc-310">允许服务要求使用用户名凭据对客户端进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-310">Allows the service to require that the client be authenticated using a user name credential.</span></span> <span data-ttu-id="9d3fc-311">请注意，当安全模式设置为 `TransportWithMessageCredential` 时，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 不支持发送密码摘要，也不支持使用密码派生密钥并将这样的密钥用于 Message 模式安全。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-311">Note that when the security mode is set to `TransportWithMessageCredential`, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not support sending a password digest or deriving keys using password and using such keys for Message mode security.</span></span> <span data-ttu-id="9d3fc-312">因此，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 强制要求在使用用户名凭据时确保传输的安全性。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-312">As such, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] enforces that the transport is secured when using user name credentials.</span></span>|  
|<span data-ttu-id="9d3fc-313">证书</span><span class="sxs-lookup"><span data-stu-id="9d3fc-313">Certificate</span></span>|<span data-ttu-id="9d3fc-314">允许服务要求使用证书对客户端进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-314">Allows the service to require that the client be authenticated using a certificate.</span></span>|  
|<span data-ttu-id="9d3fc-315">IssuedToken</span><span class="sxs-lookup"><span data-stu-id="9d3fc-315">IssuedToken</span></span>|<span data-ttu-id="9d3fc-316">允许服务使用安全令牌服务来提供自定义令牌。</span><span class="sxs-lookup"><span data-stu-id="9d3fc-316">Allows the service to use a security token service to supply a custom token.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9d3fc-317">请参阅</span><span class="sxs-lookup"><span data-stu-id="9d3fc-317">See Also</span></span>  
 [<span data-ttu-id="9d3fc-318">安全性概述</span><span class="sxs-lookup"><span data-stu-id="9d3fc-318">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="9d3fc-319">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="9d3fc-319">Securing Services and Clients</span></span>](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="9d3fc-320">选择凭据类型</span><span class="sxs-lookup"><span data-stu-id="9d3fc-320">Selecting a Credential Type</span></span>](../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="9d3fc-321">使用自定义绑定的安全功能</span><span class="sxs-lookup"><span data-stu-id="9d3fc-321">Security Capabilities with Custom Bindings</span></span>](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="9d3fc-322">安全行为</span><span class="sxs-lookup"><span data-stu-id="9d3fc-322">Security Behaviors</span></span>](../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="9d3fc-323">Windows Server App Fabric 的安全模型</span><span class="sxs-lookup"><span data-stu-id="9d3fc-323">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
