---
title: "安全 ETW 事件"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security events [.NET Framework]
- ETW, security events (CLR)
ms.assetid: 0ed69f73-5c01-4514-bd63-979c6e38d41d
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: abf6e6896267b6d1c8449b020230381923f38f1f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="security-etw-events"></a><span data-ttu-id="45a58-102">安全 ETW 事件</span><span class="sxs-lookup"><span data-stu-id="45a58-102">Security ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="45a58-103">在强名称验证和验证码验证期间会引发安全事件。</span><span class="sxs-lookup"><span data-stu-id="45a58-103">Security events are raised during strong name verification and Authenticode verification.</span></span>  
  
 <span data-ttu-id="45a58-104">此类别包含以下事件：</span><span class="sxs-lookup"><span data-stu-id="45a58-104">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="45a58-105">StrongNameVerificationStart_V1 和 StrongNameVerificationStop_V1 事件</span><span class="sxs-lookup"><span data-stu-id="45a58-105">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>](#strongnameverificationstart_v1_and_strongnameverificationstop_v1_events)  
  
-   [<span data-ttu-id="45a58-106">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 事件</span><span class="sxs-lookup"><span data-stu-id="45a58-106">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>](#authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events)  
  
<a name="strongnameverificationstart_v1_and_strongnameverificationstop_v1_events"></a>   
## <a name="strongnameverificationstartv1-and-strongnameverificationstopv1-events"></a><span data-ttu-id="45a58-107">StrongNameVerificationStart_V1 和 StrongNameVerificationStop_V1 事件</span><span class="sxs-lookup"><span data-stu-id="45a58-107">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="45a58-108">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="45a58-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="45a58-109">（有关详细信息，请参阅 [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)。）</span><span class="sxs-lookup"><span data-stu-id="45a58-109">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="45a58-110">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="45a58-110">Keyword for raising the event</span></span>|<span data-ttu-id="45a58-111">级别</span><span class="sxs-lookup"><span data-stu-id="45a58-111">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="45a58-112">`SecurityKeyword` (0x400)</span><span class="sxs-lookup"><span data-stu-id="45a58-112">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="45a58-113">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="45a58-113">Informational(4)</span></span>|  
  
 <span data-ttu-id="45a58-114">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="45a58-114">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="45a58-115">Event</span><span class="sxs-lookup"><span data-stu-id="45a58-115">Event</span></span>|<span data-ttu-id="45a58-116">事件 ID</span><span class="sxs-lookup"><span data-stu-id="45a58-116">Event ID</span></span>|<span data-ttu-id="45a58-117">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="45a58-117">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`StrongNameVerificationStart_V1`|<span data-ttu-id="45a58-118">181</span><span class="sxs-lookup"><span data-stu-id="45a58-118">181</span></span>|<span data-ttu-id="45a58-119">强名称验证开始。</span><span class="sxs-lookup"><span data-stu-id="45a58-119">Start of strong name verification.</span></span>|  
|`StrongNameVerificationStop_V1`|<span data-ttu-id="45a58-120">182</span><span class="sxs-lookup"><span data-stu-id="45a58-120">182</span></span>|<span data-ttu-id="45a58-121">强名称验证结束。</span><span class="sxs-lookup"><span data-stu-id="45a58-121">End of strong name verification.</span></span>|  
  
 <span data-ttu-id="45a58-122">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="45a58-122">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="45a58-123">字段名</span><span class="sxs-lookup"><span data-stu-id="45a58-123">Field name</span></span>|<span data-ttu-id="45a58-124">数据类型</span><span class="sxs-lookup"><span data-stu-id="45a58-124">Data type</span></span>|<span data-ttu-id="45a58-125">说明</span><span class="sxs-lookup"><span data-stu-id="45a58-125">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="45a58-126">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="45a58-126">VerificationFlags</span></span>|<span data-ttu-id="45a58-127">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="45a58-127">win:UInt32</span></span>|<span data-ttu-id="45a58-128">验证标志。</span><span class="sxs-lookup"><span data-stu-id="45a58-128">The verification flags.</span></span>|  
|<span data-ttu-id="45a58-129">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="45a58-129">ErrorCode</span></span>|<span data-ttu-id="45a58-130">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="45a58-130">win:UInt32</span></span>|<span data-ttu-id="45a58-131">HResult 错误代码。</span><span class="sxs-lookup"><span data-stu-id="45a58-131">The HResult error code.</span></span>|  
|<span data-ttu-id="45a58-132">FullyQualifiedAssemblyName</span><span class="sxs-lookup"><span data-stu-id="45a58-132">FullyQualifiedAssemblyName</span></span>|<span data-ttu-id="45a58-133">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="45a58-133">win:UnicodeString</span></span>|<span data-ttu-id="45a58-134">完全限定程序集名称。</span><span class="sxs-lookup"><span data-stu-id="45a58-134">The fully qualified assembly name.</span></span>|  
|<span data-ttu-id="45a58-135">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="45a58-135">ClrInstanceID</span></span>|<span data-ttu-id="45a58-136">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="45a58-136">win:UInt16</span></span>|<span data-ttu-id="45a58-137">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="45a58-137">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="45a58-138">返回页首</span><span class="sxs-lookup"><span data-stu-id="45a58-138">Back to top</span></span>](#top)  
  
<a name="authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events"></a>   
## <a name="authenticodeverificationstartv1-and-authenticodeverificationstopv1-events"></a><span data-ttu-id="45a58-139">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 事件</span><span class="sxs-lookup"><span data-stu-id="45a58-139">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="45a58-140">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="45a58-140">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="45a58-141">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="45a58-141">Keyword for raising the event</span></span>|<span data-ttu-id="45a58-142">级别</span><span class="sxs-lookup"><span data-stu-id="45a58-142">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="45a58-143">`SecurityKeyword` (0x400)</span><span class="sxs-lookup"><span data-stu-id="45a58-143">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="45a58-144">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="45a58-144">Informational(4)</span></span>|  
  
 <span data-ttu-id="45a58-145">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="45a58-145">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="45a58-146">Event</span><span class="sxs-lookup"><span data-stu-id="45a58-146">Event</span></span>|<span data-ttu-id="45a58-147">事件 ID</span><span class="sxs-lookup"><span data-stu-id="45a58-147">Event ID</span></span>|<span data-ttu-id="45a58-148">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="45a58-148">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AuthenticodeVerificationStart_V1`|<span data-ttu-id="45a58-149">183</span><span class="sxs-lookup"><span data-stu-id="45a58-149">183</span></span>|<span data-ttu-id="45a58-150">验证码验证开始。</span><span class="sxs-lookup"><span data-stu-id="45a58-150">Start of Authenticode verification.</span></span>|  
|`AuthenticodeVerificationStop_V1`|<span data-ttu-id="45a58-151">184</span><span class="sxs-lookup"><span data-stu-id="45a58-151">184</span></span>|<span data-ttu-id="45a58-152">验证码验证结束。</span><span class="sxs-lookup"><span data-stu-id="45a58-152">End of Authenticode verification.</span></span>|  
  
 <span data-ttu-id="45a58-153">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="45a58-153">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="45a58-154">字段名</span><span class="sxs-lookup"><span data-stu-id="45a58-154">Field name</span></span>|<span data-ttu-id="45a58-155">数据类型</span><span class="sxs-lookup"><span data-stu-id="45a58-155">Data type</span></span>|<span data-ttu-id="45a58-156">说明</span><span class="sxs-lookup"><span data-stu-id="45a58-156">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="45a58-157">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="45a58-157">VerificationFlags</span></span>|<span data-ttu-id="45a58-158">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="45a58-158">win:UInt32</span></span>|<span data-ttu-id="45a58-159">验证标志。</span><span class="sxs-lookup"><span data-stu-id="45a58-159">The verification flags.</span></span>|  
|<span data-ttu-id="45a58-160">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="45a58-160">ErrorCode</span></span>|<span data-ttu-id="45a58-161">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="45a58-161">win:UInt32</span></span>|<span data-ttu-id="45a58-162">HResult 错误代码。</span><span class="sxs-lookup"><span data-stu-id="45a58-162">The HResult error code.</span></span>|  
|<span data-ttu-id="45a58-163">ModulePath</span><span class="sxs-lookup"><span data-stu-id="45a58-163">ModulePath</span></span>|<span data-ttu-id="45a58-164">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="45a58-164">win:UnicodeString</span></span>|<span data-ttu-id="45a58-165">模块路径。</span><span class="sxs-lookup"><span data-stu-id="45a58-165">The module path.</span></span>|  
|<span data-ttu-id="45a58-166">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="45a58-166">ClrInstanceID</span></span>|<span data-ttu-id="45a58-167">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="45a58-167">win:UInt16</span></span>|<span data-ttu-id="45a58-168">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="45a58-168">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="45a58-169">请参阅</span><span class="sxs-lookup"><span data-stu-id="45a58-169">See Also</span></span>  
 [<span data-ttu-id="45a58-170">CLR ETW 事件</span><span class="sxs-lookup"><span data-stu-id="45a58-170">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
