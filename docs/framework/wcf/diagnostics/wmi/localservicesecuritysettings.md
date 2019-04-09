---
title: LocalServiceSecuritySettings
ms.date: 03/30/2017
ms.assetid: 490aa0e5-5242-4f8d-b505-5ec6287633b4
ms.openlocfilehash: 15304630eb8a14e01d4815ddddc84cd32796fdcf
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59133472"
---
# <a name="localservicesecuritysettings"></a><span data-ttu-id="8d701-102">LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="8d701-102">LocalServiceSecuritySettings</span></span>
<span data-ttu-id="8d701-103">LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="8d701-103">LocalServiceSecuritySettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d701-104">语法</span><span class="sxs-lookup"><span data-stu-id="8d701-104">Syntax</span></span>  
  
```csharp
class LocalServiceSecuritySettings  
{  
  boolean DetectReplays;  
  datetime InactivityTimeout;  
  datetime IssuedCookieLifetime;  
  sint32 MaxCachedCookies;  
  datetime MaxClockSkew;  
  sint32 MaxPendingSessions;  
  sint32 MaxStatefulNegotiations;  
  datetime NegotiationTimeout;  
  boolean ReconnectTransportOnFailure;  
  sint32 ReplayCacheSize;  
  datetime ReplayWindow;  
  datetime SessionKeyRenewalInterval;  
  datetime SessionKeyRolloverInterval;  
  datetime TimestampValidityDuration;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="8d701-105">方法</span><span class="sxs-lookup"><span data-stu-id="8d701-105">Methods</span></span>  
 <span data-ttu-id="8d701-106">LocalServiceSecuritySettings 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="8d701-106">The LocalServiceSecuritySettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="8d701-107">属性</span><span class="sxs-lookup"><span data-stu-id="8d701-107">Properties</span></span>  
 <span data-ttu-id="8d701-108">LocalServiceSecuritySettings 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="8d701-108">The LocalServiceSecuritySettings class has the following properties:</span></span>  
  
### <a name="detectreplays"></a><span data-ttu-id="8d701-109">DetectReplays</span><span class="sxs-lookup"><span data-stu-id="8d701-109">DetectReplays</span></span>  
 <span data-ttu-id="8d701-110">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="8d701-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="8d701-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="8d701-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8d701-112">一个布尔值，指定是否自动检测和处理针对通道的重放攻击。</span><span class="sxs-lookup"><span data-stu-id="8d701-112">A Boolean value that specifies whether replay attacks against the channel are detected and dealt with automatically.</span></span>  
  
### <a name="inactivitytimeout"></a><span data-ttu-id="8d701-113">InactivityTimeout</span><span class="sxs-lookup"><span data-stu-id="8d701-113">InactivityTimeout</span></span>  
 <span data-ttu-id="8d701-114">数据类型：DateTime</span><span class="sxs-lookup"><span data-stu-id="8d701-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="8d701-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="8d701-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8d701-116">服务支持的最大挂起安全会话数。</span><span class="sxs-lookup"><span data-stu-id="8d701-116">The maximum number of pending security sessions that the service supports.</span></span>  
  
### <a name="issuedcookielifetime"></a><span data-ttu-id="8d701-117">IssuedCookieLifetime</span><span class="sxs-lookup"><span data-stu-id="8d701-117">IssuedCookieLifetime</span></span>  
 <span data-ttu-id="8d701-118">数据类型：DateTime</span><span class="sxs-lookup"><span data-stu-id="8d701-118">Data type: datetime</span></span>  
  
 <span data-ttu-id="8d701-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="8d701-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8d701-120">一个时间跨度，指定颁发给所有新的安全 Cookie 的生存期。</span><span class="sxs-lookup"><span data-stu-id="8d701-120">A TimeSpan that specifies the lifetime issued to all new security cookies.</span></span>  
  
### <a name="maxcachedcookies"></a><span data-ttu-id="8d701-121">MaxCachedCookies</span><span class="sxs-lookup"><span data-stu-id="8d701-121">MaxCachedCookies</span></span>  
 <span data-ttu-id="8d701-122">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="8d701-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="8d701-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="8d701-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8d701-124">可以缓存的最大 Cookie 数。</span><span class="sxs-lookup"><span data-stu-id="8d701-124">The maximum number of cookies that can be cached.</span></span>  
  
### <a name="maxclockskew"></a><span data-ttu-id="8d701-125">MaxClockSkew</span><span class="sxs-lookup"><span data-stu-id="8d701-125">MaxClockSkew</span></span>  
 <span data-ttu-id="8d701-126">数据类型：DateTime</span><span class="sxs-lookup"><span data-stu-id="8d701-126">Data type: datetime</span></span>  
  
 <span data-ttu-id="8d701-127">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="8d701-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8d701-128">一个时间跨度，指定通信双方系统时钟之间的最大时间差。</span><span class="sxs-lookup"><span data-stu-id="8d701-128">A TimeSpan that specifies the maximum time difference between the system clocks of the two communicating parties.</span></span>  
  
### <a name="maxpendingsessions"></a><span data-ttu-id="8d701-129">MaxPendingSessions</span><span class="sxs-lookup"><span data-stu-id="8d701-129">MaxPendingSessions</span></span>  
 <span data-ttu-id="8d701-130">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="8d701-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="8d701-131">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="8d701-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8d701-132">服务上的最大挂起连接数。</span><span class="sxs-lookup"><span data-stu-id="8d701-132">The maximum number of pending connections on the service.</span></span>  
  
### <a name="maxstatefulnegotiations"></a><span data-ttu-id="8d701-133">MaxStatefulNegotiations</span><span class="sxs-lookup"><span data-stu-id="8d701-133">MaxStatefulNegotiations</span></span>  
 <span data-ttu-id="8d701-134">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="8d701-134">Data type: sint32</span></span>  
  
 <span data-ttu-id="8d701-135">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="8d701-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8d701-136">可以同时处于活动状态的安全协商数。</span><span class="sxs-lookup"><span data-stu-id="8d701-136">The number of security negotiations that can be active concurrently.</span></span>  
  
### <a name="negotiationtimeout"></a><span data-ttu-id="8d701-137">NegotiationTimeout</span><span class="sxs-lookup"><span data-stu-id="8d701-137">NegotiationTimeout</span></span>  
 <span data-ttu-id="8d701-138">数据类型：DateTime</span><span class="sxs-lookup"><span data-stu-id="8d701-138">Data type: datetime</span></span>  
  
 <span data-ttu-id="8d701-139">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="8d701-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8d701-140">一个时间跨度，指定服务器和客户端之间的安全协商阶段的最大持续时间。</span><span class="sxs-lookup"><span data-stu-id="8d701-140">A TimeSpan that specifies the maximum duration for the security negotiation phase between server and client.</span></span>  
  
### <a name="reconnecttransportonfailure"></a><span data-ttu-id="8d701-141">ReconnectTransportOnFailure</span><span class="sxs-lookup"><span data-stu-id="8d701-141">ReconnectTransportOnFailure</span></span>  
 <span data-ttu-id="8d701-142">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="8d701-142">Data type: boolean</span></span>  
  
 <span data-ttu-id="8d701-143">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="8d701-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8d701-144">一个布尔值，指定使用 WS-ReliableMessaging 的连接是否将在传输失败后尝试重新连接。</span><span class="sxs-lookup"><span data-stu-id="8d701-144">A Boolean value that specifies whether connections using WS-Reliable messaging attempt to reconnect after transport failures.</span></span>  
  
### <a name="replaycachesize"></a><span data-ttu-id="8d701-145">ReplayCacheSize</span><span class="sxs-lookup"><span data-stu-id="8d701-145">ReplayCacheSize</span></span>  
 <span data-ttu-id="8d701-146">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="8d701-146">Data type: sint32</span></span>  
  
 <span data-ttu-id="8d701-147">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="8d701-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8d701-148">用于重播检测的缓存 Nonce 的数目。</span><span class="sxs-lookup"><span data-stu-id="8d701-148">The number of cached nonces used for replay detection.</span></span>  
  
### <a name="replaywindow"></a><span data-ttu-id="8d701-149">ReplayWindow</span><span class="sxs-lookup"><span data-stu-id="8d701-149">ReplayWindow</span></span>  
 <span data-ttu-id="8d701-150">数据类型：DateTime</span><span class="sxs-lookup"><span data-stu-id="8d701-150">Data type: datetime</span></span>  
  
 <span data-ttu-id="8d701-151">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="8d701-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8d701-152">一个时间跨度，指定单个消息 Nonce 的有效持续时间。</span><span class="sxs-lookup"><span data-stu-id="8d701-152">A TimeSpan that specifies the duration in which individual message nonces are valid.</span></span>  
  
### <a name="sessionkeyrenewalinterval"></a><span data-ttu-id="8d701-153">SessionKeyRenewalInterval</span><span class="sxs-lookup"><span data-stu-id="8d701-153">SessionKeyRenewalInterval</span></span>  
 <span data-ttu-id="8d701-154">数据类型：DateTime</span><span class="sxs-lookup"><span data-stu-id="8d701-154">Data type: datetime</span></span>  
  
 <span data-ttu-id="8d701-155">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="8d701-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8d701-156">一个时间跨度，指定一个持续时间，发起方将在此段时间之后续订安全会话的密钥。</span><span class="sxs-lookup"><span data-stu-id="8d701-156">A TimeSpan that specifies the duration after which the initiator renews the key for the security session.</span></span>  
  
### <a name="sessionkeyrolloverinterval"></a><span data-ttu-id="8d701-157">SessionKeyRolloverInterval</span><span class="sxs-lookup"><span data-stu-id="8d701-157">SessionKeyRolloverInterval</span></span>  
 <span data-ttu-id="8d701-158">数据类型：DateTime</span><span class="sxs-lookup"><span data-stu-id="8d701-158">Data type: datetime</span></span>  
  
 <span data-ttu-id="8d701-159">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="8d701-159">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8d701-160">一个时间跨度，指定在密钥续订期间，上一个会话密钥对于传入消息有效的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="8d701-160">A TimeSpan that specifies the time interval a previous session key is valid on incoming messages during a key renewal.</span></span>  
  
### <a name="timestampvalidityduration"></a><span data-ttu-id="8d701-161">TimestampValidityDuration</span><span class="sxs-lookup"><span data-stu-id="8d701-161">TimestampValidityDuration</span></span>  
 <span data-ttu-id="8d701-162">数据类型：DateTime</span><span class="sxs-lookup"><span data-stu-id="8d701-162">Data type: datetime</span></span>  
  
 <span data-ttu-id="8d701-163">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="8d701-163">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8d701-164">一个时间跨度，指定时间戳的有效持续时间。</span><span class="sxs-lookup"><span data-stu-id="8d701-164">A TimeSpan that specifies the duration in which a time stamp is valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d701-165">要求</span><span class="sxs-lookup"><span data-stu-id="8d701-165">Requirements</span></span>  
  
|<span data-ttu-id="8d701-166">MOF</span><span class="sxs-lookup"><span data-stu-id="8d701-166">MOF</span></span>|<span data-ttu-id="8d701-167">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="8d701-167">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="8d701-168">命名空间</span><span class="sxs-lookup"><span data-stu-id="8d701-168">Namespace</span></span>|<span data-ttu-id="8d701-169">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="8d701-169">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8d701-170">请参阅</span><span class="sxs-lookup"><span data-stu-id="8d701-170">See also</span></span>

- <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>
