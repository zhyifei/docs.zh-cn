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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61949196"
---
# <a name="security-etw-events"></a><span data-ttu-id="cec5d-102">安全 ETW 事件</span><span class="sxs-lookup"><span data-stu-id="cec5d-102">Security ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="cec5d-103">在强名称验证和验证码验证期间会引发安全事件。</span><span class="sxs-lookup"><span data-stu-id="cec5d-103">Security events are raised during strong name verification and Authenticode verification.</span></span>  
  
 <span data-ttu-id="cec5d-104">此类别包含以下事件：</span><span class="sxs-lookup"><span data-stu-id="cec5d-104">This category consists of the following events:</span></span>  
  
- [<span data-ttu-id="cec5d-105">StrongNameVerificationStart_V1 和 StrongNameVerificationStop_V1 事件</span><span class="sxs-lookup"><span data-stu-id="cec5d-105">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>](#strongnameverificationstart_v1_and_strongnameverificationstop_v1_events)  
  
- [<span data-ttu-id="cec5d-106">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 事件</span><span class="sxs-lookup"><span data-stu-id="cec5d-106">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>](#authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events)  
  
<a name="strongnameverificationstart_v1_and_strongnameverificationstop_v1_events"></a>   
## <a name="strongnameverificationstartv1-and-strongnameverificationstopv1-events"></a><span data-ttu-id="cec5d-107">StrongNameVerificationStart_V1 和 StrongNameVerificationStop_V1 事件</span><span class="sxs-lookup"><span data-stu-id="cec5d-107">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="cec5d-108">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="cec5d-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="cec5d-109">（有关详细信息，请参阅 [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)。）</span><span class="sxs-lookup"><span data-stu-id="cec5d-109">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="cec5d-110">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="cec5d-110">Keyword for raising the event</span></span>|<span data-ttu-id="cec5d-111">级别</span><span class="sxs-lookup"><span data-stu-id="cec5d-111">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="cec5d-112">`SecurityKeyword` (0x400)</span><span class="sxs-lookup"><span data-stu-id="cec5d-112">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="cec5d-113">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="cec5d-113">Informational(4)</span></span>|  
  
 <span data-ttu-id="cec5d-114">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="cec5d-114">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="cec5d-115">Event</span><span class="sxs-lookup"><span data-stu-id="cec5d-115">Event</span></span>|<span data-ttu-id="cec5d-116">事件 ID</span><span class="sxs-lookup"><span data-stu-id="cec5d-116">Event ID</span></span>|<span data-ttu-id="cec5d-117">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="cec5d-117">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`StrongNameVerificationStart_V1`|<span data-ttu-id="cec5d-118">181</span><span class="sxs-lookup"><span data-stu-id="cec5d-118">181</span></span>|<span data-ttu-id="cec5d-119">强名称验证开始。</span><span class="sxs-lookup"><span data-stu-id="cec5d-119">Start of strong name verification.</span></span>|  
|`StrongNameVerificationStop_V1`|<span data-ttu-id="cec5d-120">182</span><span class="sxs-lookup"><span data-stu-id="cec5d-120">182</span></span>|<span data-ttu-id="cec5d-121">强名称验证结束。</span><span class="sxs-lookup"><span data-stu-id="cec5d-121">End of strong name verification.</span></span>|  
  
 <span data-ttu-id="cec5d-122">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="cec5d-122">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="cec5d-123">字段名</span><span class="sxs-lookup"><span data-stu-id="cec5d-123">Field name</span></span>|<span data-ttu-id="cec5d-124">数据类型</span><span class="sxs-lookup"><span data-stu-id="cec5d-124">Data type</span></span>|<span data-ttu-id="cec5d-125">描述</span><span class="sxs-lookup"><span data-stu-id="cec5d-125">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="cec5d-126">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="cec5d-126">VerificationFlags</span></span>|<span data-ttu-id="cec5d-127">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="cec5d-127">win:UInt32</span></span>|<span data-ttu-id="cec5d-128">验证标志。</span><span class="sxs-lookup"><span data-stu-id="cec5d-128">The verification flags.</span></span>|  
|<span data-ttu-id="cec5d-129">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="cec5d-129">ErrorCode</span></span>|<span data-ttu-id="cec5d-130">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="cec5d-130">win:UInt32</span></span>|<span data-ttu-id="cec5d-131">HResult 错误代码。</span><span class="sxs-lookup"><span data-stu-id="cec5d-131">The HResult error code.</span></span>|  
|<span data-ttu-id="cec5d-132">FullyQualifiedAssemblyName</span><span class="sxs-lookup"><span data-stu-id="cec5d-132">FullyQualifiedAssemblyName</span></span>|<span data-ttu-id="cec5d-133">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="cec5d-133">win:UnicodeString</span></span>|<span data-ttu-id="cec5d-134">完全限定程序集名称。</span><span class="sxs-lookup"><span data-stu-id="cec5d-134">The fully qualified assembly name.</span></span>|  
|<span data-ttu-id="cec5d-135">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="cec5d-135">ClrInstanceID</span></span>|<span data-ttu-id="cec5d-136">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="cec5d-136">win:UInt16</span></span>|<span data-ttu-id="cec5d-137">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="cec5d-137">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="cec5d-138">返回页首</span><span class="sxs-lookup"><span data-stu-id="cec5d-138">Back to top</span></span>](#top)  
  
<a name="authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events"></a>   
## <a name="authenticodeverificationstartv1-and-authenticodeverificationstopv1-events"></a><span data-ttu-id="cec5d-139">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 事件</span><span class="sxs-lookup"><span data-stu-id="cec5d-139">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="cec5d-140">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="cec5d-140">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="cec5d-141">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="cec5d-141">Keyword for raising the event</span></span>|<span data-ttu-id="cec5d-142">级别</span><span class="sxs-lookup"><span data-stu-id="cec5d-142">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="cec5d-143">`SecurityKeyword` (0x400)</span><span class="sxs-lookup"><span data-stu-id="cec5d-143">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="cec5d-144">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="cec5d-144">Informational(4)</span></span>|  
  
 <span data-ttu-id="cec5d-145">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="cec5d-145">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="cec5d-146">Event</span><span class="sxs-lookup"><span data-stu-id="cec5d-146">Event</span></span>|<span data-ttu-id="cec5d-147">事件 ID</span><span class="sxs-lookup"><span data-stu-id="cec5d-147">Event ID</span></span>|<span data-ttu-id="cec5d-148">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="cec5d-148">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AuthenticodeVerificationStart_V1`|<span data-ttu-id="cec5d-149">183</span><span class="sxs-lookup"><span data-stu-id="cec5d-149">183</span></span>|<span data-ttu-id="cec5d-150">验证码验证开始。</span><span class="sxs-lookup"><span data-stu-id="cec5d-150">Start of Authenticode verification.</span></span>|  
|`AuthenticodeVerificationStop_V1`|<span data-ttu-id="cec5d-151">184</span><span class="sxs-lookup"><span data-stu-id="cec5d-151">184</span></span>|<span data-ttu-id="cec5d-152">验证码验证结束。</span><span class="sxs-lookup"><span data-stu-id="cec5d-152">End of Authenticode verification.</span></span>|  
  
 <span data-ttu-id="cec5d-153">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="cec5d-153">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="cec5d-154">字段名</span><span class="sxs-lookup"><span data-stu-id="cec5d-154">Field name</span></span>|<span data-ttu-id="cec5d-155">数据类型</span><span class="sxs-lookup"><span data-stu-id="cec5d-155">Data type</span></span>|<span data-ttu-id="cec5d-156">描述</span><span class="sxs-lookup"><span data-stu-id="cec5d-156">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="cec5d-157">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="cec5d-157">VerificationFlags</span></span>|<span data-ttu-id="cec5d-158">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="cec5d-158">win:UInt32</span></span>|<span data-ttu-id="cec5d-159">验证标志。</span><span class="sxs-lookup"><span data-stu-id="cec5d-159">The verification flags.</span></span>|  
|<span data-ttu-id="cec5d-160">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="cec5d-160">ErrorCode</span></span>|<span data-ttu-id="cec5d-161">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="cec5d-161">win:UInt32</span></span>|<span data-ttu-id="cec5d-162">HResult 错误代码。</span><span class="sxs-lookup"><span data-stu-id="cec5d-162">The HResult error code.</span></span>|  
|<span data-ttu-id="cec5d-163">ModulePath</span><span class="sxs-lookup"><span data-stu-id="cec5d-163">ModulePath</span></span>|<span data-ttu-id="cec5d-164">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="cec5d-164">win:UnicodeString</span></span>|<span data-ttu-id="cec5d-165">模块路径。</span><span class="sxs-lookup"><span data-stu-id="cec5d-165">The module path.</span></span>|  
|<span data-ttu-id="cec5d-166">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="cec5d-166">ClrInstanceID</span></span>|<span data-ttu-id="cec5d-167">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="cec5d-167">win:UInt16</span></span>|<span data-ttu-id="cec5d-168">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="cec5d-168">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cec5d-169">请参阅</span><span class="sxs-lookup"><span data-stu-id="cec5d-169">See also</span></span>

- [<span data-ttu-id="cec5d-170">CLR ETW 事件</span><span class="sxs-lookup"><span data-stu-id="cec5d-170">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
