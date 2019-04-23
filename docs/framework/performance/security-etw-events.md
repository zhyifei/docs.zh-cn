---
title: 安全 ETW 事件
ms.date: 03/30/2017
helpviewer_keywords:
- security events [.NET Framework]
- ETW, security events (CLR)
ms.assetid: 0ed69f73-5c01-4514-bd63-979c6e38d41d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 11a19dce496423883e5fed62375c6db8ed5efdb1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59134025"
---
# <a name="security-etw-events"></a><span data-ttu-id="0f259-102">安全 ETW 事件</span><span class="sxs-lookup"><span data-stu-id="0f259-102">Security ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="0f259-103">在强名称验证和验证码验证期间会引发安全事件。</span><span class="sxs-lookup"><span data-stu-id="0f259-103">Security events are raised during strong name verification and Authenticode verification.</span></span>  
  
 <span data-ttu-id="0f259-104">此类别包含以下事件：</span><span class="sxs-lookup"><span data-stu-id="0f259-104">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="0f259-105">StrongNameVerificationStart_V1 和 StrongNameVerificationStop_V1 事件</span><span class="sxs-lookup"><span data-stu-id="0f259-105">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>](#strongnameverificationstart_v1_and_strongnameverificationstop_v1_events)  
  
-   [<span data-ttu-id="0f259-106">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 事件</span><span class="sxs-lookup"><span data-stu-id="0f259-106">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>](#authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events)  
  
<a name="strongnameverificationstart_v1_and_strongnameverificationstop_v1_events"></a>   
## <a name="strongnameverificationstartv1-and-strongnameverificationstopv1-events"></a><span data-ttu-id="0f259-107">StrongNameVerificationStart_V1 和 StrongNameVerificationStop_V1 事件</span><span class="sxs-lookup"><span data-stu-id="0f259-107">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="0f259-108">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="0f259-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="0f259-109">（有关详细信息，请参阅 [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)。）</span><span class="sxs-lookup"><span data-stu-id="0f259-109">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="0f259-110">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="0f259-110">Keyword for raising the event</span></span>|<span data-ttu-id="0f259-111">级别</span><span class="sxs-lookup"><span data-stu-id="0f259-111">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="0f259-112">`SecurityKeyword` (0x400)</span><span class="sxs-lookup"><span data-stu-id="0f259-112">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="0f259-113">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="0f259-113">Informational(4)</span></span>|  
  
 <span data-ttu-id="0f259-114">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="0f259-114">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="0f259-115">Event</span><span class="sxs-lookup"><span data-stu-id="0f259-115">Event</span></span>|<span data-ttu-id="0f259-116">事件 ID</span><span class="sxs-lookup"><span data-stu-id="0f259-116">Event ID</span></span>|<span data-ttu-id="0f259-117">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="0f259-117">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`StrongNameVerificationStart_V1`|<span data-ttu-id="0f259-118">181</span><span class="sxs-lookup"><span data-stu-id="0f259-118">181</span></span>|<span data-ttu-id="0f259-119">强名称验证开始。</span><span class="sxs-lookup"><span data-stu-id="0f259-119">Start of strong name verification.</span></span>|  
|`StrongNameVerificationStop_V1`|<span data-ttu-id="0f259-120">182</span><span class="sxs-lookup"><span data-stu-id="0f259-120">182</span></span>|<span data-ttu-id="0f259-121">强名称验证结束。</span><span class="sxs-lookup"><span data-stu-id="0f259-121">End of strong name verification.</span></span>|  
  
 <span data-ttu-id="0f259-122">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="0f259-122">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="0f259-123">字段名</span><span class="sxs-lookup"><span data-stu-id="0f259-123">Field name</span></span>|<span data-ttu-id="0f259-124">数据类型</span><span class="sxs-lookup"><span data-stu-id="0f259-124">Data type</span></span>|<span data-ttu-id="0f259-125">描述</span><span class="sxs-lookup"><span data-stu-id="0f259-125">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="0f259-126">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="0f259-126">VerificationFlags</span></span>|<span data-ttu-id="0f259-127">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="0f259-127">win:UInt32</span></span>|<span data-ttu-id="0f259-128">验证标志。</span><span class="sxs-lookup"><span data-stu-id="0f259-128">The verification flags.</span></span>|  
|<span data-ttu-id="0f259-129">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="0f259-129">ErrorCode</span></span>|<span data-ttu-id="0f259-130">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="0f259-130">win:UInt32</span></span>|<span data-ttu-id="0f259-131">HResult 错误代码。</span><span class="sxs-lookup"><span data-stu-id="0f259-131">The HResult error code.</span></span>|  
|<span data-ttu-id="0f259-132">FullyQualifiedAssemblyName</span><span class="sxs-lookup"><span data-stu-id="0f259-132">FullyQualifiedAssemblyName</span></span>|<span data-ttu-id="0f259-133">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="0f259-133">win:UnicodeString</span></span>|<span data-ttu-id="0f259-134">完全限定程序集名称。</span><span class="sxs-lookup"><span data-stu-id="0f259-134">The fully qualified assembly name.</span></span>|  
|<span data-ttu-id="0f259-135">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="0f259-135">ClrInstanceID</span></span>|<span data-ttu-id="0f259-136">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="0f259-136">win:UInt16</span></span>|<span data-ttu-id="0f259-137">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="0f259-137">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="0f259-138">返回页首</span><span class="sxs-lookup"><span data-stu-id="0f259-138">Back to top</span></span>](#top)  
  
<a name="authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events"></a>   
## <a name="authenticodeverificationstartv1-and-authenticodeverificationstopv1-events"></a><span data-ttu-id="0f259-139">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 事件</span><span class="sxs-lookup"><span data-stu-id="0f259-139">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="0f259-140">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="0f259-140">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="0f259-141">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="0f259-141">Keyword for raising the event</span></span>|<span data-ttu-id="0f259-142">级别</span><span class="sxs-lookup"><span data-stu-id="0f259-142">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="0f259-143">`SecurityKeyword` (0x400)</span><span class="sxs-lookup"><span data-stu-id="0f259-143">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="0f259-144">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="0f259-144">Informational(4)</span></span>|  
  
 <span data-ttu-id="0f259-145">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="0f259-145">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="0f259-146">Event</span><span class="sxs-lookup"><span data-stu-id="0f259-146">Event</span></span>|<span data-ttu-id="0f259-147">事件 ID</span><span class="sxs-lookup"><span data-stu-id="0f259-147">Event ID</span></span>|<span data-ttu-id="0f259-148">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="0f259-148">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AuthenticodeVerificationStart_V1`|<span data-ttu-id="0f259-149">183</span><span class="sxs-lookup"><span data-stu-id="0f259-149">183</span></span>|<span data-ttu-id="0f259-150">验证码验证开始。</span><span class="sxs-lookup"><span data-stu-id="0f259-150">Start of Authenticode verification.</span></span>|  
|`AuthenticodeVerificationStop_V1`|<span data-ttu-id="0f259-151">184</span><span class="sxs-lookup"><span data-stu-id="0f259-151">184</span></span>|<span data-ttu-id="0f259-152">验证码验证结束。</span><span class="sxs-lookup"><span data-stu-id="0f259-152">End of Authenticode verification.</span></span>|  
  
 <span data-ttu-id="0f259-153">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="0f259-153">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="0f259-154">字段名</span><span class="sxs-lookup"><span data-stu-id="0f259-154">Field name</span></span>|<span data-ttu-id="0f259-155">数据类型</span><span class="sxs-lookup"><span data-stu-id="0f259-155">Data type</span></span>|<span data-ttu-id="0f259-156">描述</span><span class="sxs-lookup"><span data-stu-id="0f259-156">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="0f259-157">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="0f259-157">VerificationFlags</span></span>|<span data-ttu-id="0f259-158">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="0f259-158">win:UInt32</span></span>|<span data-ttu-id="0f259-159">验证标志。</span><span class="sxs-lookup"><span data-stu-id="0f259-159">The verification flags.</span></span>|  
|<span data-ttu-id="0f259-160">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="0f259-160">ErrorCode</span></span>|<span data-ttu-id="0f259-161">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="0f259-161">win:UInt32</span></span>|<span data-ttu-id="0f259-162">HResult 错误代码。</span><span class="sxs-lookup"><span data-stu-id="0f259-162">The HResult error code.</span></span>|  
|<span data-ttu-id="0f259-163">ModulePath</span><span class="sxs-lookup"><span data-stu-id="0f259-163">ModulePath</span></span>|<span data-ttu-id="0f259-164">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="0f259-164">win:UnicodeString</span></span>|<span data-ttu-id="0f259-165">模块路径。</span><span class="sxs-lookup"><span data-stu-id="0f259-165">The module path.</span></span>|  
|<span data-ttu-id="0f259-166">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="0f259-166">ClrInstanceID</span></span>|<span data-ttu-id="0f259-167">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="0f259-167">win:UInt16</span></span>|<span data-ttu-id="0f259-168">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="0f259-168">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0f259-169">请参阅</span><span class="sxs-lookup"><span data-stu-id="0f259-169">See also</span></span>

- [<span data-ttu-id="0f259-170">CLR ETW 事件</span><span class="sxs-lookup"><span data-stu-id="0f259-170">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
