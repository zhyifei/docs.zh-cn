---
title: "安全 ETW 事件"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security events [.NET Framework]
- ETW, security events (CLR)
ms.assetid: 0ed69f73-5c01-4514-bd63-979c6e38d41d
caps.latest.revision: 8
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a7e28eeabecfe0f1043328618f6e1be143f198a6
ms.contentlocale: zh-cn
ms.lasthandoff: 08/21/2017

---
# <a name="security-etw-events"></a><span data-ttu-id="a48b3-102">安全 ETW 事件</span><span class="sxs-lookup"><span data-stu-id="a48b3-102">Security ETW Events</span></span>
<span data-ttu-id="a48b3-103"><a name="top"></a> 在强名称验证和验证码验证期间会引发安全事件。</span><span class="sxs-lookup"><span data-stu-id="a48b3-103"><a name="top"></a> Security events are raised during strong name verification and Authenticode verification.</span></span>  
  
 <span data-ttu-id="a48b3-104">此类别包含以下事件：</span><span class="sxs-lookup"><span data-stu-id="a48b3-104">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="a48b3-105">StrongNameVerificationStart_V1 和 StrongNameVerificationStop_V1 事件</span><span class="sxs-lookup"><span data-stu-id="a48b3-105">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>](#strongnameverificationstart_v1_and_strongnameverificationstop_v1_events)  
  
-   [<span data-ttu-id="a48b3-106">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 事件</span><span class="sxs-lookup"><span data-stu-id="a48b3-106">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>](#authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events)  
  
<a name="strongnameverificationstart_v1_and_strongnameverificationstop_v1_events"></a>   
## <a name="strongnameverificationstartv1-and-strongnameverificationstopv1-events"></a><span data-ttu-id="a48b3-107">StrongNameVerificationStart_V1 和 StrongNameVerificationStop_V1 事件</span><span class="sxs-lookup"><span data-stu-id="a48b3-107">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="a48b3-108">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="a48b3-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="a48b3-109">（有关详细信息，请参阅 [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)。）</span><span class="sxs-lookup"><span data-stu-id="a48b3-109">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="a48b3-110">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="a48b3-110">Keyword for raising the event</span></span>|<span data-ttu-id="a48b3-111">级别</span><span class="sxs-lookup"><span data-stu-id="a48b3-111">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a48b3-112">`SecurityKeyword` (0x400)</span><span class="sxs-lookup"><span data-stu-id="a48b3-112">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="a48b3-113">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="a48b3-113">Informational(4)</span></span>|  
  
 <span data-ttu-id="a48b3-114">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="a48b3-114">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a48b3-115">Event</span><span class="sxs-lookup"><span data-stu-id="a48b3-115">Event</span></span>|<span data-ttu-id="a48b3-116">事件 ID</span><span class="sxs-lookup"><span data-stu-id="a48b3-116">Event ID</span></span>|<span data-ttu-id="a48b3-117">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="a48b3-117">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`StrongNameVerificationStart_V1`|<span data-ttu-id="a48b3-118">181</span><span class="sxs-lookup"><span data-stu-id="a48b3-118">181</span></span>|<span data-ttu-id="a48b3-119">强名称验证开始。</span><span class="sxs-lookup"><span data-stu-id="a48b3-119">Start of strong name verification.</span></span>|  
|`StrongNameVerificationStop_V1`|<span data-ttu-id="a48b3-120">182</span><span class="sxs-lookup"><span data-stu-id="a48b3-120">182</span></span>|<span data-ttu-id="a48b3-121">强名称验证结束。</span><span class="sxs-lookup"><span data-stu-id="a48b3-121">End of strong name verification.</span></span>|  
  
 <span data-ttu-id="a48b3-122">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="a48b3-122">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="a48b3-123">字段名</span><span class="sxs-lookup"><span data-stu-id="a48b3-123">Field name</span></span>|<span data-ttu-id="a48b3-124">数据类型</span><span class="sxs-lookup"><span data-stu-id="a48b3-124">Data type</span></span>|<span data-ttu-id="a48b3-125">说明</span><span class="sxs-lookup"><span data-stu-id="a48b3-125">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="a48b3-126">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="a48b3-126">VerificationFlags</span></span>|<span data-ttu-id="a48b3-127">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a48b3-127">win:UInt32</span></span>|<span data-ttu-id="a48b3-128">验证标志。</span><span class="sxs-lookup"><span data-stu-id="a48b3-128">The verification flags.</span></span>|  
|<span data-ttu-id="a48b3-129">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="a48b3-129">ErrorCode</span></span>|<span data-ttu-id="a48b3-130">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a48b3-130">win:UInt32</span></span>|<span data-ttu-id="a48b3-131">HResult 错误代码。</span><span class="sxs-lookup"><span data-stu-id="a48b3-131">The HResult error code.</span></span>|  
|<span data-ttu-id="a48b3-132">FullyQualifiedAssemblyName</span><span class="sxs-lookup"><span data-stu-id="a48b3-132">FullyQualifiedAssemblyName</span></span>|<span data-ttu-id="a48b3-133">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="a48b3-133">win:UnicodeString</span></span>|<span data-ttu-id="a48b3-134">完全限定程序集名称。</span><span class="sxs-lookup"><span data-stu-id="a48b3-134">The fully qualified assembly name.</span></span>|  
|<span data-ttu-id="a48b3-135">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a48b3-135">ClrInstanceID</span></span>|<span data-ttu-id="a48b3-136">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a48b3-136">win:UInt16</span></span>|<span data-ttu-id="a48b3-137">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="a48b3-137">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="a48b3-138">返回页首</span><span class="sxs-lookup"><span data-stu-id="a48b3-138">Back to top</span></span>](#top)  
  
<a name="authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events"></a>   
## <a name="authenticodeverificationstartv1-and-authenticodeverificationstopv1-events"></a><span data-ttu-id="a48b3-139">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 事件</span><span class="sxs-lookup"><span data-stu-id="a48b3-139">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="a48b3-140">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="a48b3-140">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="a48b3-141">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="a48b3-141">Keyword for raising the event</span></span>|<span data-ttu-id="a48b3-142">级别</span><span class="sxs-lookup"><span data-stu-id="a48b3-142">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a48b3-143">`SecurityKeyword` (0x400)</span><span class="sxs-lookup"><span data-stu-id="a48b3-143">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="a48b3-144">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="a48b3-144">Informational(4)</span></span>|  
  
 <span data-ttu-id="a48b3-145">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="a48b3-145">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a48b3-146">Event</span><span class="sxs-lookup"><span data-stu-id="a48b3-146">Event</span></span>|<span data-ttu-id="a48b3-147">事件 ID</span><span class="sxs-lookup"><span data-stu-id="a48b3-147">Event ID</span></span>|<span data-ttu-id="a48b3-148">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="a48b3-148">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AuthenticodeVerificationStart_V1`|<span data-ttu-id="a48b3-149">183</span><span class="sxs-lookup"><span data-stu-id="a48b3-149">183</span></span>|<span data-ttu-id="a48b3-150">验证码验证开始。</span><span class="sxs-lookup"><span data-stu-id="a48b3-150">Start of Authenticode verification.</span></span>|  
|`AuthenticodeVerificationStop_V1`|<span data-ttu-id="a48b3-151">184</span><span class="sxs-lookup"><span data-stu-id="a48b3-151">184</span></span>|<span data-ttu-id="a48b3-152">验证码验证结束。</span><span class="sxs-lookup"><span data-stu-id="a48b3-152">End of Authenticode verification.</span></span>|  
  
 <span data-ttu-id="a48b3-153">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="a48b3-153">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="a48b3-154">字段名</span><span class="sxs-lookup"><span data-stu-id="a48b3-154">Field name</span></span>|<span data-ttu-id="a48b3-155">数据类型</span><span class="sxs-lookup"><span data-stu-id="a48b3-155">Data type</span></span>|<span data-ttu-id="a48b3-156">说明</span><span class="sxs-lookup"><span data-stu-id="a48b3-156">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="a48b3-157">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="a48b3-157">VerificationFlags</span></span>|<span data-ttu-id="a48b3-158">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a48b3-158">win:UInt32</span></span>|<span data-ttu-id="a48b3-159">验证标志。</span><span class="sxs-lookup"><span data-stu-id="a48b3-159">The verification flags.</span></span>|  
|<span data-ttu-id="a48b3-160">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="a48b3-160">ErrorCode</span></span>|<span data-ttu-id="a48b3-161">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a48b3-161">win:UInt32</span></span>|<span data-ttu-id="a48b3-162">HResult 错误代码。</span><span class="sxs-lookup"><span data-stu-id="a48b3-162">The HResult error code.</span></span>|  
|<span data-ttu-id="a48b3-163">ModulePath</span><span class="sxs-lookup"><span data-stu-id="a48b3-163">ModulePath</span></span>|<span data-ttu-id="a48b3-164">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="a48b3-164">win:UnicodeString</span></span>|<span data-ttu-id="a48b3-165">模块路径。</span><span class="sxs-lookup"><span data-stu-id="a48b3-165">The module path.</span></span>|  
|<span data-ttu-id="a48b3-166">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a48b3-166">ClrInstanceID</span></span>|<span data-ttu-id="a48b3-167">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a48b3-167">win:UInt16</span></span>|<span data-ttu-id="a48b3-168">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="a48b3-168">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a48b3-169">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a48b3-169">See Also</span></span>  
 [<span data-ttu-id="a48b3-170">CLR ETW 事件</span><span class="sxs-lookup"><span data-stu-id="a48b3-170">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)

