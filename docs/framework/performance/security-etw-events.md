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
ms.openlocfilehash: a7e28eeabecfe0f1043328618f6e1be143f198a6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="security-etw-events"></a><span data-ttu-id="27184-102">安全 ETW 事件</span><span class="sxs-lookup"><span data-stu-id="27184-102">Security ETW Events</span></span>
<span data-ttu-id="27184-103"><a name="top"></a> 在强名称验证和验证码验证期间会引发安全事件。</span><span class="sxs-lookup"><span data-stu-id="27184-103"><a name="top"></a> Security events are raised during strong name verification and Authenticode verification.</span></span>  
  
 <span data-ttu-id="27184-104">此类别包含以下事件：</span><span class="sxs-lookup"><span data-stu-id="27184-104">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="27184-105">StrongNameVerificationStart_V1 和 StrongNameVerificationStop_V1 事件</span><span class="sxs-lookup"><span data-stu-id="27184-105">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>](#strongnameverificationstart_v1_and_strongnameverificationstop_v1_events)  
  
-   [<span data-ttu-id="27184-106">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 事件</span><span class="sxs-lookup"><span data-stu-id="27184-106">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>](#authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events)  
  
<a name="strongnameverificationstart_v1_and_strongnameverificationstop_v1_events"></a>   
## <a name="strongnameverificationstartv1-and-strongnameverificationstopv1-events"></a><span data-ttu-id="27184-107">StrongNameVerificationStart_V1 和 StrongNameVerificationStop_V1 事件</span><span class="sxs-lookup"><span data-stu-id="27184-107">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="27184-108">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="27184-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="27184-109">（有关详细信息，请参阅 [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)。）</span><span class="sxs-lookup"><span data-stu-id="27184-109">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="27184-110">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="27184-110">Keyword for raising the event</span></span>|<span data-ttu-id="27184-111">级别</span><span class="sxs-lookup"><span data-stu-id="27184-111">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="27184-112">`SecurityKeyword` (0x400)</span><span class="sxs-lookup"><span data-stu-id="27184-112">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="27184-113">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="27184-113">Informational(4)</span></span>|  
  
 <span data-ttu-id="27184-114">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="27184-114">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="27184-115">Event</span><span class="sxs-lookup"><span data-stu-id="27184-115">Event</span></span>|<span data-ttu-id="27184-116">事件 ID</span><span class="sxs-lookup"><span data-stu-id="27184-116">Event ID</span></span>|<span data-ttu-id="27184-117">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="27184-117">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`StrongNameVerificationStart_V1`|<span data-ttu-id="27184-118">181</span><span class="sxs-lookup"><span data-stu-id="27184-118">181</span></span>|<span data-ttu-id="27184-119">强名称验证开始。</span><span class="sxs-lookup"><span data-stu-id="27184-119">Start of strong name verification.</span></span>|  
|`StrongNameVerificationStop_V1`|<span data-ttu-id="27184-120">182</span><span class="sxs-lookup"><span data-stu-id="27184-120">182</span></span>|<span data-ttu-id="27184-121">强名称验证结束。</span><span class="sxs-lookup"><span data-stu-id="27184-121">End of strong name verification.</span></span>|  
  
 <span data-ttu-id="27184-122">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="27184-122">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="27184-123">字段名</span><span class="sxs-lookup"><span data-stu-id="27184-123">Field name</span></span>|<span data-ttu-id="27184-124">数据类型</span><span class="sxs-lookup"><span data-stu-id="27184-124">Data type</span></span>|<span data-ttu-id="27184-125">说明</span><span class="sxs-lookup"><span data-stu-id="27184-125">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="27184-126">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="27184-126">VerificationFlags</span></span>|<span data-ttu-id="27184-127">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="27184-127">win:UInt32</span></span>|<span data-ttu-id="27184-128">验证标志。</span><span class="sxs-lookup"><span data-stu-id="27184-128">The verification flags.</span></span>|  
|<span data-ttu-id="27184-129">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="27184-129">ErrorCode</span></span>|<span data-ttu-id="27184-130">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="27184-130">win:UInt32</span></span>|<span data-ttu-id="27184-131">HResult 错误代码。</span><span class="sxs-lookup"><span data-stu-id="27184-131">The HResult error code.</span></span>|  
|<span data-ttu-id="27184-132">FullyQualifiedAssemblyName</span><span class="sxs-lookup"><span data-stu-id="27184-132">FullyQualifiedAssemblyName</span></span>|<span data-ttu-id="27184-133">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="27184-133">win:UnicodeString</span></span>|<span data-ttu-id="27184-134">完全限定程序集名称。</span><span class="sxs-lookup"><span data-stu-id="27184-134">The fully qualified assembly name.</span></span>|  
|<span data-ttu-id="27184-135">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="27184-135">ClrInstanceID</span></span>|<span data-ttu-id="27184-136">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="27184-136">win:UInt16</span></span>|<span data-ttu-id="27184-137">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="27184-137">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="27184-138">返回页首</span><span class="sxs-lookup"><span data-stu-id="27184-138">Back to top</span></span>](#top)  
  
<a name="authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events"></a>   
## <a name="authenticodeverificationstartv1-and-authenticodeverificationstopv1-events"></a><span data-ttu-id="27184-139">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 事件</span><span class="sxs-lookup"><span data-stu-id="27184-139">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="27184-140">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="27184-140">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="27184-141">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="27184-141">Keyword for raising the event</span></span>|<span data-ttu-id="27184-142">级别</span><span class="sxs-lookup"><span data-stu-id="27184-142">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="27184-143">`SecurityKeyword` (0x400)</span><span class="sxs-lookup"><span data-stu-id="27184-143">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="27184-144">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="27184-144">Informational(4)</span></span>|  
  
 <span data-ttu-id="27184-145">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="27184-145">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="27184-146">Event</span><span class="sxs-lookup"><span data-stu-id="27184-146">Event</span></span>|<span data-ttu-id="27184-147">事件 ID</span><span class="sxs-lookup"><span data-stu-id="27184-147">Event ID</span></span>|<span data-ttu-id="27184-148">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="27184-148">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AuthenticodeVerificationStart_V1`|<span data-ttu-id="27184-149">183</span><span class="sxs-lookup"><span data-stu-id="27184-149">183</span></span>|<span data-ttu-id="27184-150">验证码验证开始。</span><span class="sxs-lookup"><span data-stu-id="27184-150">Start of Authenticode verification.</span></span>|  
|`AuthenticodeVerificationStop_V1`|<span data-ttu-id="27184-151">184</span><span class="sxs-lookup"><span data-stu-id="27184-151">184</span></span>|<span data-ttu-id="27184-152">验证码验证结束。</span><span class="sxs-lookup"><span data-stu-id="27184-152">End of Authenticode verification.</span></span>|  
  
 <span data-ttu-id="27184-153">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="27184-153">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="27184-154">字段名</span><span class="sxs-lookup"><span data-stu-id="27184-154">Field name</span></span>|<span data-ttu-id="27184-155">数据类型</span><span class="sxs-lookup"><span data-stu-id="27184-155">Data type</span></span>|<span data-ttu-id="27184-156">说明</span><span class="sxs-lookup"><span data-stu-id="27184-156">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="27184-157">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="27184-157">VerificationFlags</span></span>|<span data-ttu-id="27184-158">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="27184-158">win:UInt32</span></span>|<span data-ttu-id="27184-159">验证标志。</span><span class="sxs-lookup"><span data-stu-id="27184-159">The verification flags.</span></span>|  
|<span data-ttu-id="27184-160">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="27184-160">ErrorCode</span></span>|<span data-ttu-id="27184-161">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="27184-161">win:UInt32</span></span>|<span data-ttu-id="27184-162">HResult 错误代码。</span><span class="sxs-lookup"><span data-stu-id="27184-162">The HResult error code.</span></span>|  
|<span data-ttu-id="27184-163">ModulePath</span><span class="sxs-lookup"><span data-stu-id="27184-163">ModulePath</span></span>|<span data-ttu-id="27184-164">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="27184-164">win:UnicodeString</span></span>|<span data-ttu-id="27184-165">模块路径。</span><span class="sxs-lookup"><span data-stu-id="27184-165">The module path.</span></span>|  
|<span data-ttu-id="27184-166">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="27184-166">ClrInstanceID</span></span>|<span data-ttu-id="27184-167">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="27184-167">win:UInt16</span></span>|<span data-ttu-id="27184-168">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="27184-168">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="27184-169">另请参阅</span><span class="sxs-lookup"><span data-stu-id="27184-169">See Also</span></span>  
 [<span data-ttu-id="27184-170">CLR ETW 事件</span><span class="sxs-lookup"><span data-stu-id="27184-170">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
