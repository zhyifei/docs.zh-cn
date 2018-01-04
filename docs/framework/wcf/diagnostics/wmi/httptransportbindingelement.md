---
title: HttpTransportBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 088a7bce-6bb2-4839-ad74-f68d4b1aa0f9
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b6370284dbd9c680b29f315c791ea76356e7b36f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="httptransportbindingelement"></a><span data-ttu-id="3e055-102">HttpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="3e055-102">HttpTransportBindingElement</span></span>
<span data-ttu-id="3e055-103">HttpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="3e055-103">HttpTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e055-104">语法</span><span class="sxs-lookup"><span data-stu-id="3e055-104">Syntax</span></span>  
  
```  
class HttpTransportBindingElement : TransportBindingElement  
{  
  boolean AllowCookies;  
  string AuthenticationScheme;  
  boolean BypassProxyOnLocal;  
  string HostNameComparisonMode;  
  boolean KeepAliveEnabled;  
  sint32 MaxBufferSize;  
  string ProxyAddress;  
  string ProxyAuthenticationScheme;  
  string Realm;  
  string TransferMode;  
  boolean UnsafeConnectionNtlmAuthentication;  
  boolean UseDefaultWebProxy;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="3e055-105">方法</span><span class="sxs-lookup"><span data-stu-id="3e055-105">Methods</span></span>  
 <span data-ttu-id="3e055-106">HttpTransportBindingElement 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="3e055-106">The HttpTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="3e055-107">属性</span><span class="sxs-lookup"><span data-stu-id="3e055-107">Properties</span></span>  
 <span data-ttu-id="3e055-108">HttpTransportBindingElement 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="3e055-108">The HttpTransportBindingElement class has the following properties:</span></span>  
  
### <a name="allowcookies"></a><span data-ttu-id="3e055-109">AllowCookies</span><span class="sxs-lookup"><span data-stu-id="3e055-109">AllowCookies</span></span>  
 <span data-ttu-id="3e055-110">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="3e055-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="3e055-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="3e055-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3e055-112">一个值，指示客户端是否接受 cookie 并根据将来的请求对其进行传播。</span><span class="sxs-lookup"><span data-stu-id="3e055-112">A value that indicates whether the client accepts cookies and propagates them on future requests.</span></span>  
  
### <a name="authenticationscheme"></a><span data-ttu-id="3e055-113">AuthenticationScheme</span><span class="sxs-lookup"><span data-stu-id="3e055-113">AuthenticationScheme</span></span>  
 <span data-ttu-id="3e055-114">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="3e055-114">Data type: string</span></span>  
  
 <span data-ttu-id="3e055-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="3e055-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3e055-116">用来验证 HTTP 侦听器正在处理的客户端请求的身份验证方案。</span><span class="sxs-lookup"><span data-stu-id="3e055-116">The authentication scheme used to authenticate client requests being processed by an HTTP listener.</span></span>  
  
### <a name="bypassproxyonlocal"></a><span data-ttu-id="3e055-117">BypassProxyOnLocal</span><span class="sxs-lookup"><span data-stu-id="3e055-117">BypassProxyOnLocal</span></span>  
 <span data-ttu-id="3e055-118">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="3e055-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="3e055-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="3e055-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3e055-120">一个值，指示是否忽略本地地址的代理。</span><span class="sxs-lookup"><span data-stu-id="3e055-120">A value that indicates whether proxies are ignored for local addresses.</span></span>  
  
### <a name="hostnamecomparisonmode"></a><span data-ttu-id="3e055-121">HostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="3e055-121">HostNameComparisonMode</span></span>  
 <span data-ttu-id="3e055-122">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="3e055-122">Data type: string</span></span>  
  
 <span data-ttu-id="3e055-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="3e055-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3e055-124">一个值，指示在对 URI 进行匹配时，是否使用主机名来访问服务。</span><span class="sxs-lookup"><span data-stu-id="3e055-124">A value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>  
  
### <a name="keepaliveenabled"></a><span data-ttu-id="3e055-125">KeepAliveEnabled</span><span class="sxs-lookup"><span data-stu-id="3e055-125">KeepAliveEnabled</span></span>  
 <span data-ttu-id="3e055-126">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="3e055-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="3e055-127">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="3e055-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3e055-128">启用后，HTTP 连接将保持活动状态，无论是什么活动级别。</span><span class="sxs-lookup"><span data-stu-id="3e055-128">When enabled, HTTP connections are kept alive regardless of activity level.</span></span>  
  
### <a name="maxbuffersize"></a><span data-ttu-id="3e055-129">MaxBufferSize</span><span class="sxs-lookup"><span data-stu-id="3e055-129">MaxBufferSize</span></span>  
 <span data-ttu-id="3e055-130">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="3e055-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="3e055-131">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="3e055-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3e055-132">缓冲池的最大大小。</span><span class="sxs-lookup"><span data-stu-id="3e055-132">The maximum size of the buffer pool.</span></span>  
  
### <a name="proxyaddress"></a><span data-ttu-id="3e055-133">ProxyAddress</span><span class="sxs-lookup"><span data-stu-id="3e055-133">ProxyAddress</span></span>  
 <span data-ttu-id="3e055-134">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="3e055-134">Data type: string</span></span>  
  
 <span data-ttu-id="3e055-135">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="3e055-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3e055-136">一个 URI，包含用于 HTTP 请求的代理地址。</span><span class="sxs-lookup"><span data-stu-id="3e055-136">A URI that contains the address of the proxy to use for HTTP requests.</span></span>  
  
### <a name="proxyauthenticationscheme"></a><span data-ttu-id="3e055-137">ProxyAuthenticationScheme</span><span class="sxs-lookup"><span data-stu-id="3e055-137">ProxyAuthenticationScheme</span></span>  
 <span data-ttu-id="3e055-138">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="3e055-138">Data type: string</span></span>  
  
 <span data-ttu-id="3e055-139">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="3e055-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3e055-140">用来验证 HTTP 代理正在处理的客户端请求的身份验证方案。</span><span class="sxs-lookup"><span data-stu-id="3e055-140">The authentication scheme used to authenticate client requests being processed by an HTTP proxy.</span></span>  
  
### <a name="realm"></a><span data-ttu-id="3e055-141">Realm</span><span class="sxs-lookup"><span data-stu-id="3e055-141">Realm</span></span>  
 <span data-ttu-id="3e055-142">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="3e055-142">Data type: string</span></span>  
  
 <span data-ttu-id="3e055-143">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="3e055-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3e055-144">身份验证领域。</span><span class="sxs-lookup"><span data-stu-id="3e055-144">The authentication realm.</span></span>  
  
### <a name="transfermode"></a><span data-ttu-id="3e055-145">TransferMode</span><span class="sxs-lookup"><span data-stu-id="3e055-145">TransferMode</span></span>  
 <span data-ttu-id="3e055-146">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="3e055-146">Data type: string</span></span>  
  
 <span data-ttu-id="3e055-147">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="3e055-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3e055-148">一个值，指定对消息进行缓冲处理还是流式处理，或者指定消息是请求还是响应。</span><span class="sxs-lookup"><span data-stu-id="3e055-148">A value that specifies whether messages are buffered or streamed or a request or response.</span></span>  
  
### <a name="unsafeconnectionntlmauthentication"></a><span data-ttu-id="3e055-149">UnsafeConnectionNtlmAuthentication</span><span class="sxs-lookup"><span data-stu-id="3e055-149">UnsafeConnectionNtlmAuthentication</span></span>  
 <span data-ttu-id="3e055-150">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="3e055-150">Data type: boolean</span></span>  
  
 <span data-ttu-id="3e055-151">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="3e055-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3e055-152">一个值，指示服务器上是否启用了不安全连接共享。</span><span class="sxs-lookup"><span data-stu-id="3e055-152">A value that indicates whether Unsafe Connection Sharing is enabled on the server.</span></span>  
  
### <a name="usedefaultwebproxy"></a><span data-ttu-id="3e055-153">UseDefaultWebProxy</span><span class="sxs-lookup"><span data-stu-id="3e055-153">UseDefaultWebProxy</span></span>  
 <span data-ttu-id="3e055-154">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="3e055-154">Data type: boolean</span></span>  
  
 <span data-ttu-id="3e055-155">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="3e055-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3e055-156">一个值，指示是否使用计算机范围的代理设置，而不使用用户特定的设置。</span><span class="sxs-lookup"><span data-stu-id="3e055-156">A value that indicates whether the machine-wide proxy settings are used rather than the user specific settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e055-157">惠?</span><span class="sxs-lookup"><span data-stu-id="3e055-157">Requirements</span></span>  
  
|<span data-ttu-id="3e055-158">MOF</span><span class="sxs-lookup"><span data-stu-id="3e055-158">MOF</span></span>|<span data-ttu-id="3e055-159">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="3e055-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="3e055-160">命名空间</span><span class="sxs-lookup"><span data-stu-id="3e055-160">Namespace</span></span>|<span data-ttu-id="3e055-161">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="3e055-161">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3e055-162">请参阅</span><span class="sxs-lookup"><span data-stu-id="3e055-162">See Also</span></span>  
 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>
