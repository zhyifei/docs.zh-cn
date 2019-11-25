---
title: 安全 ETW 事件
ms.date: 03/30/2017
helpviewer_keywords:
- security events [.NET Framework]
- ETW, security events (CLR)
ms.assetid: 0ed69f73-5c01-4514-bd63-979c6e38d41d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b1dad042595608a805f978673858acaa5c01130f
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2019
ms.locfileid: "73974882"
---
# <a name="security-etw-events"></a><span data-ttu-id="a12fe-102">安全 ETW 事件</span><span class="sxs-lookup"><span data-stu-id="a12fe-102">Security ETW Events</span></span>

<span data-ttu-id="a12fe-103">在强名称验证和验证码验证期间会引发安全事件。</span><span class="sxs-lookup"><span data-stu-id="a12fe-103">Security events are raised during strong name verification and Authenticode verification.</span></span>  

## <a name="strongnameverificationstart_v1-and-strongnameverificationstop_v1-events"></a><span data-ttu-id="a12fe-104">StrongNameVerificationStart_V1 和 StrongNameVerificationStop_V1 事件</span><span class="sxs-lookup"><span data-stu-id="a12fe-104">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="a12fe-105">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="a12fe-105">The following table shows the keyword and level.</span></span> <span data-ttu-id="a12fe-106">（有关详细信息，请参阅 [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md)。）</span><span class="sxs-lookup"><span data-stu-id="a12fe-106">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="a12fe-107">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="a12fe-107">Keyword for raising the event</span></span>|<span data-ttu-id="a12fe-108">层次</span><span class="sxs-lookup"><span data-stu-id="a12fe-108">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a12fe-109">`SecurityKeyword` (0x400)</span><span class="sxs-lookup"><span data-stu-id="a12fe-109">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="a12fe-110">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="a12fe-110">Informational(4)</span></span>|  
  
 <span data-ttu-id="a12fe-111">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="a12fe-111">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a12fe-112">Event — 事件</span><span class="sxs-lookup"><span data-stu-id="a12fe-112">Event</span></span>|<span data-ttu-id="a12fe-113">事件 ID</span><span class="sxs-lookup"><span data-stu-id="a12fe-113">Event ID</span></span>|<span data-ttu-id="a12fe-114">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="a12fe-114">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`StrongNameVerificationStart_V1`|<span data-ttu-id="a12fe-115">181</span><span class="sxs-lookup"><span data-stu-id="a12fe-115">181</span></span>|<span data-ttu-id="a12fe-116">强名称验证开始。</span><span class="sxs-lookup"><span data-stu-id="a12fe-116">Start of strong name verification.</span></span>|  
|`StrongNameVerificationStop_V1`|<span data-ttu-id="a12fe-117">182</span><span class="sxs-lookup"><span data-stu-id="a12fe-117">182</span></span>|<span data-ttu-id="a12fe-118">强名称验证结束。</span><span class="sxs-lookup"><span data-stu-id="a12fe-118">End of strong name verification.</span></span>|  
  
 <span data-ttu-id="a12fe-119">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="a12fe-119">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="a12fe-120">字段名</span><span class="sxs-lookup"><span data-stu-id="a12fe-120">Field name</span></span>|<span data-ttu-id="a12fe-121">数据类型</span><span class="sxs-lookup"><span data-stu-id="a12fe-121">Data type</span></span>|<span data-ttu-id="a12fe-122">描述</span><span class="sxs-lookup"><span data-stu-id="a12fe-122">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="a12fe-123">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="a12fe-123">VerificationFlags</span></span>|<span data-ttu-id="a12fe-124">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a12fe-124">win:UInt32</span></span>|<span data-ttu-id="a12fe-125">验证标志。</span><span class="sxs-lookup"><span data-stu-id="a12fe-125">The verification flags.</span></span>|  
|<span data-ttu-id="a12fe-126">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="a12fe-126">ErrorCode</span></span>|<span data-ttu-id="a12fe-127">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a12fe-127">win:UInt32</span></span>|<span data-ttu-id="a12fe-128">HResult 错误代码。</span><span class="sxs-lookup"><span data-stu-id="a12fe-128">The HResult error code.</span></span>|  
|<span data-ttu-id="a12fe-129">FullyQualifiedAssemblyName</span><span class="sxs-lookup"><span data-stu-id="a12fe-129">FullyQualifiedAssemblyName</span></span>|<span data-ttu-id="a12fe-130">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="a12fe-130">win:UnicodeString</span></span>|<span data-ttu-id="a12fe-131">完全限定程序集名称。</span><span class="sxs-lookup"><span data-stu-id="a12fe-131">The fully qualified assembly name.</span></span>|  
|<span data-ttu-id="a12fe-132">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a12fe-132">ClrInstanceID</span></span>|<span data-ttu-id="a12fe-133">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a12fe-133">win:UInt16</span></span>|<span data-ttu-id="a12fe-134">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="a12fe-134">Unique ID for the instance of CLR or CoreCLR.</span></span>|  

## <a name="authenticodeverificationstart_v1-and-authenticodeverificationstop_v1-events"></a><span data-ttu-id="a12fe-135">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 事件</span><span class="sxs-lookup"><span data-stu-id="a12fe-135">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="a12fe-136">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="a12fe-136">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="a12fe-137">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="a12fe-137">Keyword for raising the event</span></span>|<span data-ttu-id="a12fe-138">层次</span><span class="sxs-lookup"><span data-stu-id="a12fe-138">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a12fe-139">`SecurityKeyword` (0x400)</span><span class="sxs-lookup"><span data-stu-id="a12fe-139">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="a12fe-140">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="a12fe-140">Informational(4)</span></span>|  
  
 <span data-ttu-id="a12fe-141">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="a12fe-141">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a12fe-142">Event — 事件</span><span class="sxs-lookup"><span data-stu-id="a12fe-142">Event</span></span>|<span data-ttu-id="a12fe-143">事件 ID</span><span class="sxs-lookup"><span data-stu-id="a12fe-143">Event ID</span></span>|<span data-ttu-id="a12fe-144">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="a12fe-144">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AuthenticodeVerificationStart_V1`|<span data-ttu-id="a12fe-145">183</span><span class="sxs-lookup"><span data-stu-id="a12fe-145">183</span></span>|<span data-ttu-id="a12fe-146">验证码验证开始。</span><span class="sxs-lookup"><span data-stu-id="a12fe-146">Start of Authenticode verification.</span></span>|  
|`AuthenticodeVerificationStop_V1`|<span data-ttu-id="a12fe-147">184</span><span class="sxs-lookup"><span data-stu-id="a12fe-147">184</span></span>|<span data-ttu-id="a12fe-148">验证码验证结束。</span><span class="sxs-lookup"><span data-stu-id="a12fe-148">End of Authenticode verification.</span></span>|  
  
 <span data-ttu-id="a12fe-149">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="a12fe-149">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="a12fe-150">字段名</span><span class="sxs-lookup"><span data-stu-id="a12fe-150">Field name</span></span>|<span data-ttu-id="a12fe-151">数据类型</span><span class="sxs-lookup"><span data-stu-id="a12fe-151">Data type</span></span>|<span data-ttu-id="a12fe-152">描述</span><span class="sxs-lookup"><span data-stu-id="a12fe-152">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="a12fe-153">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="a12fe-153">VerificationFlags</span></span>|<span data-ttu-id="a12fe-154">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a12fe-154">win:UInt32</span></span>|<span data-ttu-id="a12fe-155">验证标志。</span><span class="sxs-lookup"><span data-stu-id="a12fe-155">The verification flags.</span></span>|  
|<span data-ttu-id="a12fe-156">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="a12fe-156">ErrorCode</span></span>|<span data-ttu-id="a12fe-157">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a12fe-157">win:UInt32</span></span>|<span data-ttu-id="a12fe-158">HResult 错误代码。</span><span class="sxs-lookup"><span data-stu-id="a12fe-158">The HResult error code.</span></span>|  
|<span data-ttu-id="a12fe-159">ModulePath</span><span class="sxs-lookup"><span data-stu-id="a12fe-159">ModulePath</span></span>|<span data-ttu-id="a12fe-160">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="a12fe-160">win:UnicodeString</span></span>|<span data-ttu-id="a12fe-161">模块路径。</span><span class="sxs-lookup"><span data-stu-id="a12fe-161">The module path.</span></span>|  
|<span data-ttu-id="a12fe-162">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a12fe-162">ClrInstanceID</span></span>|<span data-ttu-id="a12fe-163">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a12fe-163">win:UInt16</span></span>|<span data-ttu-id="a12fe-164">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="a12fe-164">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a12fe-165">请参阅</span><span class="sxs-lookup"><span data-stu-id="a12fe-165">See also</span></span>

- [<span data-ttu-id="a12fe-166">CLR ETW 事件</span><span class="sxs-lookup"><span data-stu-id="a12fe-166">CLR ETW Events</span></span>](clr-etw-events.md)
