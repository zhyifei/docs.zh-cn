---
title: HttpTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 088a7bce-6bb2-4839-ad74-f68d4b1aa0f9
ms.openlocfilehash: 2376a0ec25539b97a37b1827e3e4c148eb8d5838
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54610768"
---
# <a name="httptransportbindingelement"></a><span data-ttu-id="0e39f-102">HttpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="0e39f-102">HttpTransportBindingElement</span></span>
<span data-ttu-id="0e39f-103">HttpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="0e39f-103">HttpTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e39f-104">语法</span><span class="sxs-lookup"><span data-stu-id="0e39f-104">Syntax</span></span>  
  
```csharp
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
  
## <a name="methods"></a><span data-ttu-id="0e39f-105">方法</span><span class="sxs-lookup"><span data-stu-id="0e39f-105">Methods</span></span>  
 <span data-ttu-id="0e39f-106">HttpTransportBindingElement 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="0e39f-106">The HttpTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="0e39f-107">Properties</span><span class="sxs-lookup"><span data-stu-id="0e39f-107">Properties</span></span>  
 <span data-ttu-id="0e39f-108">HttpTransportBindingElement 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="0e39f-108">The HttpTransportBindingElement class has the following properties:</span></span>  
  
### <a name="allowcookies"></a><span data-ttu-id="0e39f-109">AllowCookies</span><span class="sxs-lookup"><span data-stu-id="0e39f-109">AllowCookies</span></span>  
 <span data-ttu-id="0e39f-110">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="0e39f-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="0e39f-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="0e39f-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0e39f-112">一个值，指示客户端是否接受 cookie 并根据将来的请求对其进行传播。</span><span class="sxs-lookup"><span data-stu-id="0e39f-112">A value that indicates whether the client accepts cookies and propagates them on future requests.</span></span>  
  
### <a name="authenticationscheme"></a><span data-ttu-id="0e39f-113">AuthenticationScheme</span><span class="sxs-lookup"><span data-stu-id="0e39f-113">AuthenticationScheme</span></span>  
 <span data-ttu-id="0e39f-114">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="0e39f-114">Data type: string</span></span>  
  
 <span data-ttu-id="0e39f-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="0e39f-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0e39f-116">用来验证 HTTP 侦听器正在处理的客户端请求的身份验证方案。</span><span class="sxs-lookup"><span data-stu-id="0e39f-116">The authentication scheme used to authenticate client requests being processed by an HTTP listener.</span></span>  
  
### <a name="bypassproxyonlocal"></a><span data-ttu-id="0e39f-117">BypassProxyOnLocal</span><span class="sxs-lookup"><span data-stu-id="0e39f-117">BypassProxyOnLocal</span></span>  
 <span data-ttu-id="0e39f-118">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="0e39f-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="0e39f-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="0e39f-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0e39f-120">一个值，指示是否忽略本地地址的代理。</span><span class="sxs-lookup"><span data-stu-id="0e39f-120">A value that indicates whether proxies are ignored for local addresses.</span></span>  
  
### <a name="hostnamecomparisonmode"></a><span data-ttu-id="0e39f-121">HostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="0e39f-121">HostNameComparisonMode</span></span>  
 <span data-ttu-id="0e39f-122">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="0e39f-122">Data type: string</span></span>  
  
 <span data-ttu-id="0e39f-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="0e39f-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0e39f-124">一个值，指示在对 URI 进行匹配时，是否使用主机名来访问服务。</span><span class="sxs-lookup"><span data-stu-id="0e39f-124">A value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>  
  
### <a name="keepaliveenabled"></a><span data-ttu-id="0e39f-125">KeepAliveEnabled</span><span class="sxs-lookup"><span data-stu-id="0e39f-125">KeepAliveEnabled</span></span>  
 <span data-ttu-id="0e39f-126">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="0e39f-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="0e39f-127">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="0e39f-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0e39f-128">启用后，HTTP 连接将保持活动状态，无论是什么活动级别。</span><span class="sxs-lookup"><span data-stu-id="0e39f-128">When enabled, HTTP connections are kept alive regardless of activity level.</span></span>  
  
### <a name="maxbuffersize"></a><span data-ttu-id="0e39f-129">MaxBufferSize</span><span class="sxs-lookup"><span data-stu-id="0e39f-129">MaxBufferSize</span></span>  
 <span data-ttu-id="0e39f-130">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="0e39f-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="0e39f-131">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="0e39f-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0e39f-132">缓冲池的最大大小。</span><span class="sxs-lookup"><span data-stu-id="0e39f-132">The maximum size of the buffer pool.</span></span>  
  
### <a name="proxyaddress"></a><span data-ttu-id="0e39f-133">ProxyAddress</span><span class="sxs-lookup"><span data-stu-id="0e39f-133">ProxyAddress</span></span>  
 <span data-ttu-id="0e39f-134">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="0e39f-134">Data type: string</span></span>  
  
 <span data-ttu-id="0e39f-135">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="0e39f-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0e39f-136">一个 URI，包含用于 HTTP 请求的代理地址。</span><span class="sxs-lookup"><span data-stu-id="0e39f-136">A URI that contains the address of the proxy to use for HTTP requests.</span></span>  
  
### <a name="proxyauthenticationscheme"></a><span data-ttu-id="0e39f-137">ProxyAuthenticationScheme</span><span class="sxs-lookup"><span data-stu-id="0e39f-137">ProxyAuthenticationScheme</span></span>  
 <span data-ttu-id="0e39f-138">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="0e39f-138">Data type: string</span></span>  
  
 <span data-ttu-id="0e39f-139">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="0e39f-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0e39f-140">用来验证 HTTP 代理正在处理的客户端请求的身份验证方案。</span><span class="sxs-lookup"><span data-stu-id="0e39f-140">The authentication scheme used to authenticate client requests being processed by an HTTP proxy.</span></span>  
  
### <a name="realm"></a><span data-ttu-id="0e39f-141">Realm</span><span class="sxs-lookup"><span data-stu-id="0e39f-141">Realm</span></span>  
 <span data-ttu-id="0e39f-142">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="0e39f-142">Data type: string</span></span>  
  
 <span data-ttu-id="0e39f-143">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="0e39f-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0e39f-144">身份验证领域。</span><span class="sxs-lookup"><span data-stu-id="0e39f-144">The authentication realm.</span></span>  
  
### <a name="transfermode"></a><span data-ttu-id="0e39f-145">TransferMode</span><span class="sxs-lookup"><span data-stu-id="0e39f-145">TransferMode</span></span>  
 <span data-ttu-id="0e39f-146">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="0e39f-146">Data type: string</span></span>  
  
 <span data-ttu-id="0e39f-147">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="0e39f-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0e39f-148">一个值，指定对消息进行缓冲处理还是流式处理，或者指定消息是请求还是响应。</span><span class="sxs-lookup"><span data-stu-id="0e39f-148">A value that specifies whether messages are buffered or streamed or a request or response.</span></span>  
  
### <a name="unsafeconnectionntlmauthentication"></a><span data-ttu-id="0e39f-149">UnsafeConnectionNtlmAuthentication</span><span class="sxs-lookup"><span data-stu-id="0e39f-149">UnsafeConnectionNtlmAuthentication</span></span>  
 <span data-ttu-id="0e39f-150">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="0e39f-150">Data type: boolean</span></span>  
  
 <span data-ttu-id="0e39f-151">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="0e39f-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0e39f-152">一个值，指示服务器上是否启用了不安全连接共享。</span><span class="sxs-lookup"><span data-stu-id="0e39f-152">A value that indicates whether Unsafe Connection Sharing is enabled on the server.</span></span>  
  
### <a name="usedefaultwebproxy"></a><span data-ttu-id="0e39f-153">UseDefaultWebProxy</span><span class="sxs-lookup"><span data-stu-id="0e39f-153">UseDefaultWebProxy</span></span>  
 <span data-ttu-id="0e39f-154">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="0e39f-154">Data type: boolean</span></span>  
  
 <span data-ttu-id="0e39f-155">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="0e39f-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0e39f-156">一个值，指示是否使用计算机范围的代理设置，而不使用用户特定的设置。</span><span class="sxs-lookup"><span data-stu-id="0e39f-156">A value that indicates whether the machine-wide proxy settings are used rather than the user specific settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e39f-157">要求</span><span class="sxs-lookup"><span data-stu-id="0e39f-157">Requirements</span></span>  
  
|<span data-ttu-id="0e39f-158">MOF</span><span class="sxs-lookup"><span data-stu-id="0e39f-158">MOF</span></span>|<span data-ttu-id="0e39f-159">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="0e39f-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="0e39f-160">命名空间</span><span class="sxs-lookup"><span data-stu-id="0e39f-160">Namespace</span></span>|<span data-ttu-id="0e39f-161">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="0e39f-161">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0e39f-162">请参阅</span><span class="sxs-lookup"><span data-stu-id="0e39f-162">See also</span></span>
- <xref:System.ServiceModel.Channels.HttpTransportBindingElement>
