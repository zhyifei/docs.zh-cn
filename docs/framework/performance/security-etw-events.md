---
title: 安全 ETW 事件
ms.date: 03/30/2017
helpviewer_keywords:
- security events [.NET Framework]
- ETW, security events (CLR)
ms.assetid: 0ed69f73-5c01-4514-bd63-979c6e38d41d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e02274b63ddf7df42d26621791de0286df9655b8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33395507"
---
# <a name="security-etw-events"></a><span data-ttu-id="a5d1c-102">安全 ETW 事件</span><span class="sxs-lookup"><span data-stu-id="a5d1c-102">Security ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="a5d1c-103">在强名称验证和验证码验证期间会引发安全事件。</span><span class="sxs-lookup"><span data-stu-id="a5d1c-103">Security events are raised during strong name verification and Authenticode verification.</span></span>  
  
 <span data-ttu-id="a5d1c-104">此类别包含以下事件：</span><span class="sxs-lookup"><span data-stu-id="a5d1c-104">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="a5d1c-105">StrongNameVerificationStart_V1 和 StrongNameVerificationStop_V1 事件</span><span class="sxs-lookup"><span data-stu-id="a5d1c-105">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>](#strongnameverificationstart_v1_and_strongnameverificationstop_v1_events)  
  
-   [<span data-ttu-id="a5d1c-106">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 事件</span><span class="sxs-lookup"><span data-stu-id="a5d1c-106">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>](#authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events)  
  
<a name="strongnameverificationstart_v1_and_strongnameverificationstop_v1_events"></a>   
## <a name="strongnameverificationstartv1-and-strongnameverificationstopv1-events"></a><span data-ttu-id="a5d1c-107">StrongNameVerificationStart_V1 和 StrongNameVerificationStop_V1 事件</span><span class="sxs-lookup"><span data-stu-id="a5d1c-107">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="a5d1c-108">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="a5d1c-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="a5d1c-109">（有关详细信息，请参阅 [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)。）</span><span class="sxs-lookup"><span data-stu-id="a5d1c-109">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="a5d1c-110">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="a5d1c-110">Keyword for raising the event</span></span>|<span data-ttu-id="a5d1c-111">级别</span><span class="sxs-lookup"><span data-stu-id="a5d1c-111">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a5d1c-112">`SecurityKeyword` (0x400)</span><span class="sxs-lookup"><span data-stu-id="a5d1c-112">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="a5d1c-113">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="a5d1c-113">Informational(4)</span></span>|  
  
 <span data-ttu-id="a5d1c-114">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="a5d1c-114">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a5d1c-115">Event</span><span class="sxs-lookup"><span data-stu-id="a5d1c-115">Event</span></span>|<span data-ttu-id="a5d1c-116">事件 ID</span><span class="sxs-lookup"><span data-stu-id="a5d1c-116">Event ID</span></span>|<span data-ttu-id="a5d1c-117">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="a5d1c-117">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`StrongNameVerificationStart_V1`|<span data-ttu-id="a5d1c-118">181</span><span class="sxs-lookup"><span data-stu-id="a5d1c-118">181</span></span>|<span data-ttu-id="a5d1c-119">强名称验证开始。</span><span class="sxs-lookup"><span data-stu-id="a5d1c-119">Start of strong name verification.</span></span>|  
|`StrongNameVerificationStop_V1`|<span data-ttu-id="a5d1c-120">182</span><span class="sxs-lookup"><span data-stu-id="a5d1c-120">182</span></span>|<span data-ttu-id="a5d1c-121">强名称验证结束。</span><span class="sxs-lookup"><span data-stu-id="a5d1c-121">End of strong name verification.</span></span>|  
  
 <span data-ttu-id="a5d1c-122">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="a5d1c-122">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="a5d1c-123">字段名</span><span class="sxs-lookup"><span data-stu-id="a5d1c-123">Field name</span></span>|<span data-ttu-id="a5d1c-124">数据类型</span><span class="sxs-lookup"><span data-stu-id="a5d1c-124">Data type</span></span>|<span data-ttu-id="a5d1c-125">描述</span><span class="sxs-lookup"><span data-stu-id="a5d1c-125">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="a5d1c-126">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="a5d1c-126">VerificationFlags</span></span>|<span data-ttu-id="a5d1c-127">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a5d1c-127">win:UInt32</span></span>|<span data-ttu-id="a5d1c-128">验证标志。</span><span class="sxs-lookup"><span data-stu-id="a5d1c-128">The verification flags.</span></span>|  
|<span data-ttu-id="a5d1c-129">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="a5d1c-129">ErrorCode</span></span>|<span data-ttu-id="a5d1c-130">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a5d1c-130">win:UInt32</span></span>|<span data-ttu-id="a5d1c-131">HResult 错误代码。</span><span class="sxs-lookup"><span data-stu-id="a5d1c-131">The HResult error code.</span></span>|  
|<span data-ttu-id="a5d1c-132">FullyQualifiedAssemblyName</span><span class="sxs-lookup"><span data-stu-id="a5d1c-132">FullyQualifiedAssemblyName</span></span>|<span data-ttu-id="a5d1c-133">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="a5d1c-133">win:UnicodeString</span></span>|<span data-ttu-id="a5d1c-134">完全限定程序集名称。</span><span class="sxs-lookup"><span data-stu-id="a5d1c-134">The fully qualified assembly name.</span></span>|  
|<span data-ttu-id="a5d1c-135">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a5d1c-135">ClrInstanceID</span></span>|<span data-ttu-id="a5d1c-136">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a5d1c-136">win:UInt16</span></span>|<span data-ttu-id="a5d1c-137">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="a5d1c-137">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="a5d1c-138">返回页首</span><span class="sxs-lookup"><span data-stu-id="a5d1c-138">Back to top</span></span>](#top)  
  
<a name="authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events"></a>   
## <a name="authenticodeverificationstartv1-and-authenticodeverificationstopv1-events"></a><span data-ttu-id="a5d1c-139">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 事件</span><span class="sxs-lookup"><span data-stu-id="a5d1c-139">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="a5d1c-140">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="a5d1c-140">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="a5d1c-141">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="a5d1c-141">Keyword for raising the event</span></span>|<span data-ttu-id="a5d1c-142">级别</span><span class="sxs-lookup"><span data-stu-id="a5d1c-142">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a5d1c-143">`SecurityKeyword` (0x400)</span><span class="sxs-lookup"><span data-stu-id="a5d1c-143">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="a5d1c-144">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="a5d1c-144">Informational(4)</span></span>|  
  
 <span data-ttu-id="a5d1c-145">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="a5d1c-145">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a5d1c-146">Event</span><span class="sxs-lookup"><span data-stu-id="a5d1c-146">Event</span></span>|<span data-ttu-id="a5d1c-147">事件 ID</span><span class="sxs-lookup"><span data-stu-id="a5d1c-147">Event ID</span></span>|<span data-ttu-id="a5d1c-148">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="a5d1c-148">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AuthenticodeVerificationStart_V1`|<span data-ttu-id="a5d1c-149">183</span><span class="sxs-lookup"><span data-stu-id="a5d1c-149">183</span></span>|<span data-ttu-id="a5d1c-150">验证码验证开始。</span><span class="sxs-lookup"><span data-stu-id="a5d1c-150">Start of Authenticode verification.</span></span>|  
|`AuthenticodeVerificationStop_V1`|<span data-ttu-id="a5d1c-151">184</span><span class="sxs-lookup"><span data-stu-id="a5d1c-151">184</span></span>|<span data-ttu-id="a5d1c-152">验证码验证结束。</span><span class="sxs-lookup"><span data-stu-id="a5d1c-152">End of Authenticode verification.</span></span>|  
  
 <span data-ttu-id="a5d1c-153">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="a5d1c-153">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="a5d1c-154">字段名</span><span class="sxs-lookup"><span data-stu-id="a5d1c-154">Field name</span></span>|<span data-ttu-id="a5d1c-155">数据类型</span><span class="sxs-lookup"><span data-stu-id="a5d1c-155">Data type</span></span>|<span data-ttu-id="a5d1c-156">描述</span><span class="sxs-lookup"><span data-stu-id="a5d1c-156">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="a5d1c-157">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="a5d1c-157">VerificationFlags</span></span>|<span data-ttu-id="a5d1c-158">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a5d1c-158">win:UInt32</span></span>|<span data-ttu-id="a5d1c-159">验证标志。</span><span class="sxs-lookup"><span data-stu-id="a5d1c-159">The verification flags.</span></span>|  
|<span data-ttu-id="a5d1c-160">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="a5d1c-160">ErrorCode</span></span>|<span data-ttu-id="a5d1c-161">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a5d1c-161">win:UInt32</span></span>|<span data-ttu-id="a5d1c-162">HResult 错误代码。</span><span class="sxs-lookup"><span data-stu-id="a5d1c-162">The HResult error code.</span></span>|  
|<span data-ttu-id="a5d1c-163">ModulePath</span><span class="sxs-lookup"><span data-stu-id="a5d1c-163">ModulePath</span></span>|<span data-ttu-id="a5d1c-164">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="a5d1c-164">win:UnicodeString</span></span>|<span data-ttu-id="a5d1c-165">模块路径。</span><span class="sxs-lookup"><span data-stu-id="a5d1c-165">The module path.</span></span>|  
|<span data-ttu-id="a5d1c-166">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a5d1c-166">ClrInstanceID</span></span>|<span data-ttu-id="a5d1c-167">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a5d1c-167">win:UInt16</span></span>|<span data-ttu-id="a5d1c-168">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="a5d1c-168">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a5d1c-169">请参阅</span><span class="sxs-lookup"><span data-stu-id="a5d1c-169">See Also</span></span>  
 [<span data-ttu-id="a5d1c-170">CLR ETW 事件</span><span class="sxs-lookup"><span data-stu-id="a5d1c-170">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
