---
title: 安全 ETW 事件
ms.date: 03/30/2017
helpviewer_keywords:
- security events [.NET Framework]
- ETW, security events (CLR)
ms.assetid: 0ed69f73-5c01-4514-bd63-979c6e38d41d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8d09b5b76c39f33848d44beb43d9b09c5e6ed13b
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2019
ms.locfileid: "71046175"
---
# <a name="security-etw-events"></a><span data-ttu-id="474a6-102">安全 ETW 事件</span><span class="sxs-lookup"><span data-stu-id="474a6-102">Security ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="474a6-103">在强名称验证和验证码验证期间会引发安全事件。</span><span class="sxs-lookup"><span data-stu-id="474a6-103">Security events are raised during strong name verification and Authenticode verification.</span></span>  
  
 <span data-ttu-id="474a6-104">此类别包含以下事件：</span><span class="sxs-lookup"><span data-stu-id="474a6-104">This category consists of the following events:</span></span>  
  
- [<span data-ttu-id="474a6-105">StrongNameVerificationStart_V1 和 StrongNameVerificationStop_V1 事件</span><span class="sxs-lookup"><span data-stu-id="474a6-105">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>](#strongnameverificationstart_v1_and_strongnameverificationstop_v1_events)  
  
- [<span data-ttu-id="474a6-106">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 事件</span><span class="sxs-lookup"><span data-stu-id="474a6-106">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>](#authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events)  
  
<a name="strongnameverificationstart_v1_and_strongnameverificationstop_v1_events"></a>   
## <a name="strongnameverificationstart_v1-and-strongnameverificationstop_v1-events"></a><span data-ttu-id="474a6-107">StrongNameVerificationStart_V1 和 StrongNameVerificationStop_V1 事件</span><span class="sxs-lookup"><span data-stu-id="474a6-107">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="474a6-108">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="474a6-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="474a6-109">（有关详细信息，请参阅 [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md)。）</span><span class="sxs-lookup"><span data-stu-id="474a6-109">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="474a6-110">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="474a6-110">Keyword for raising the event</span></span>|<span data-ttu-id="474a6-111">Level</span><span class="sxs-lookup"><span data-stu-id="474a6-111">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="474a6-112">`SecurityKeyword` (0x400)</span><span class="sxs-lookup"><span data-stu-id="474a6-112">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="474a6-113">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="474a6-113">Informational(4)</span></span>|  
  
 <span data-ttu-id="474a6-114">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="474a6-114">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="474a6-115">Event</span><span class="sxs-lookup"><span data-stu-id="474a6-115">Event</span></span>|<span data-ttu-id="474a6-116">事件 ID</span><span class="sxs-lookup"><span data-stu-id="474a6-116">Event ID</span></span>|<span data-ttu-id="474a6-117">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="474a6-117">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`StrongNameVerificationStart_V1`|<span data-ttu-id="474a6-118">181</span><span class="sxs-lookup"><span data-stu-id="474a6-118">181</span></span>|<span data-ttu-id="474a6-119">强名称验证开始。</span><span class="sxs-lookup"><span data-stu-id="474a6-119">Start of strong name verification.</span></span>|  
|`StrongNameVerificationStop_V1`|<span data-ttu-id="474a6-120">182</span><span class="sxs-lookup"><span data-stu-id="474a6-120">182</span></span>|<span data-ttu-id="474a6-121">强名称验证结束。</span><span class="sxs-lookup"><span data-stu-id="474a6-121">End of strong name verification.</span></span>|  
  
 <span data-ttu-id="474a6-122">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="474a6-122">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="474a6-123">字段名</span><span class="sxs-lookup"><span data-stu-id="474a6-123">Field name</span></span>|<span data-ttu-id="474a6-124">数据类型</span><span class="sxs-lookup"><span data-stu-id="474a6-124">Data type</span></span>|<span data-ttu-id="474a6-125">描述</span><span class="sxs-lookup"><span data-stu-id="474a6-125">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="474a6-126">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="474a6-126">VerificationFlags</span></span>|<span data-ttu-id="474a6-127">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="474a6-127">win:UInt32</span></span>|<span data-ttu-id="474a6-128">验证标志。</span><span class="sxs-lookup"><span data-stu-id="474a6-128">The verification flags.</span></span>|  
|<span data-ttu-id="474a6-129">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="474a6-129">ErrorCode</span></span>|<span data-ttu-id="474a6-130">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="474a6-130">win:UInt32</span></span>|<span data-ttu-id="474a6-131">HResult 错误代码。</span><span class="sxs-lookup"><span data-stu-id="474a6-131">The HResult error code.</span></span>|  
|<span data-ttu-id="474a6-132">FullyQualifiedAssemblyName</span><span class="sxs-lookup"><span data-stu-id="474a6-132">FullyQualifiedAssemblyName</span></span>|<span data-ttu-id="474a6-133">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="474a6-133">win:UnicodeString</span></span>|<span data-ttu-id="474a6-134">完全限定程序集名称。</span><span class="sxs-lookup"><span data-stu-id="474a6-134">The fully qualified assembly name.</span></span>|  
|<span data-ttu-id="474a6-135">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="474a6-135">ClrInstanceID</span></span>|<span data-ttu-id="474a6-136">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="474a6-136">win:UInt16</span></span>|<span data-ttu-id="474a6-137">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="474a6-137">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="474a6-138">返回页首</span><span class="sxs-lookup"><span data-stu-id="474a6-138">Back to top</span></span>](#top)  
  
<a name="authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events"></a>   
## <a name="authenticodeverificationstart_v1-and-authenticodeverificationstop_v1-events"></a><span data-ttu-id="474a6-139">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 事件</span><span class="sxs-lookup"><span data-stu-id="474a6-139">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="474a6-140">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="474a6-140">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="474a6-141">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="474a6-141">Keyword for raising the event</span></span>|<span data-ttu-id="474a6-142">Level</span><span class="sxs-lookup"><span data-stu-id="474a6-142">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="474a6-143">`SecurityKeyword` (0x400)</span><span class="sxs-lookup"><span data-stu-id="474a6-143">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="474a6-144">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="474a6-144">Informational(4)</span></span>|  
  
 <span data-ttu-id="474a6-145">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="474a6-145">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="474a6-146">Event</span><span class="sxs-lookup"><span data-stu-id="474a6-146">Event</span></span>|<span data-ttu-id="474a6-147">事件 ID</span><span class="sxs-lookup"><span data-stu-id="474a6-147">Event ID</span></span>|<span data-ttu-id="474a6-148">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="474a6-148">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AuthenticodeVerificationStart_V1`|<span data-ttu-id="474a6-149">183</span><span class="sxs-lookup"><span data-stu-id="474a6-149">183</span></span>|<span data-ttu-id="474a6-150">验证码验证开始。</span><span class="sxs-lookup"><span data-stu-id="474a6-150">Start of Authenticode verification.</span></span>|  
|`AuthenticodeVerificationStop_V1`|<span data-ttu-id="474a6-151">184</span><span class="sxs-lookup"><span data-stu-id="474a6-151">184</span></span>|<span data-ttu-id="474a6-152">验证码验证结束。</span><span class="sxs-lookup"><span data-stu-id="474a6-152">End of Authenticode verification.</span></span>|  
  
 <span data-ttu-id="474a6-153">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="474a6-153">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="474a6-154">字段名</span><span class="sxs-lookup"><span data-stu-id="474a6-154">Field name</span></span>|<span data-ttu-id="474a6-155">数据类型</span><span class="sxs-lookup"><span data-stu-id="474a6-155">Data type</span></span>|<span data-ttu-id="474a6-156">描述</span><span class="sxs-lookup"><span data-stu-id="474a6-156">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="474a6-157">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="474a6-157">VerificationFlags</span></span>|<span data-ttu-id="474a6-158">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="474a6-158">win:UInt32</span></span>|<span data-ttu-id="474a6-159">验证标志。</span><span class="sxs-lookup"><span data-stu-id="474a6-159">The verification flags.</span></span>|  
|<span data-ttu-id="474a6-160">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="474a6-160">ErrorCode</span></span>|<span data-ttu-id="474a6-161">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="474a6-161">win:UInt32</span></span>|<span data-ttu-id="474a6-162">HResult 错误代码。</span><span class="sxs-lookup"><span data-stu-id="474a6-162">The HResult error code.</span></span>|  
|<span data-ttu-id="474a6-163">ModulePath</span><span class="sxs-lookup"><span data-stu-id="474a6-163">ModulePath</span></span>|<span data-ttu-id="474a6-164">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="474a6-164">win:UnicodeString</span></span>|<span data-ttu-id="474a6-165">模块路径。</span><span class="sxs-lookup"><span data-stu-id="474a6-165">The module path.</span></span>|  
|<span data-ttu-id="474a6-166">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="474a6-166">ClrInstanceID</span></span>|<span data-ttu-id="474a6-167">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="474a6-167">win:UInt16</span></span>|<span data-ttu-id="474a6-168">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="474a6-168">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="474a6-169">请参阅</span><span class="sxs-lookup"><span data-stu-id="474a6-169">See also</span></span>

- [<span data-ttu-id="474a6-170">CLR ETW 事件</span><span class="sxs-lookup"><span data-stu-id="474a6-170">CLR ETW Events</span></span>](clr-etw-events.md)
