---
title: 安全 ETW 事件
ms.date: 03/30/2017
helpviewer_keywords:
- security events [.NET Framework]
- ETW, security events (CLR)
ms.assetid: 0ed69f73-5c01-4514-bd63-979c6e38d41d
ms.openlocfilehash: c443bda8cdc2c6b32760e9dcba8b81a29d81660b
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715944"
---
# <a name="security-etw-events"></a><span data-ttu-id="ce4a1-102">安全 ETW 事件</span><span class="sxs-lookup"><span data-stu-id="ce4a1-102">Security ETW Events</span></span>

<span data-ttu-id="ce4a1-103">在强名称验证和验证码验证期间会引发安全事件。</span><span class="sxs-lookup"><span data-stu-id="ce4a1-103">Security events are raised during strong name verification and Authenticode verification.</span></span>  

## <a name="strongnameverificationstart_v1-and-strongnameverificationstop_v1-events"></a><span data-ttu-id="ce4a1-104">StrongNameVerificationStart_V1 和 StrongNameVerificationStop_V1 事件</span><span class="sxs-lookup"><span data-stu-id="ce4a1-104">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="ce4a1-105">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="ce4a1-105">The following table shows the keyword and level.</span></span> <span data-ttu-id="ce4a1-106">（有关详细信息，请参阅 [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md)。）</span><span class="sxs-lookup"><span data-stu-id="ce4a1-106">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="ce4a1-107">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="ce4a1-107">Keyword for raising the event</span></span>|<span data-ttu-id="ce4a1-108">Level</span><span class="sxs-lookup"><span data-stu-id="ce4a1-108">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="ce4a1-109">`SecurityKeyword` (0x400)</span><span class="sxs-lookup"><span data-stu-id="ce4a1-109">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="ce4a1-110">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="ce4a1-110">Informational(4)</span></span>|  
  
 <span data-ttu-id="ce4a1-111">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="ce4a1-111">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="ce4a1-112">Event</span><span class="sxs-lookup"><span data-stu-id="ce4a1-112">Event</span></span>|<span data-ttu-id="ce4a1-113">事件 ID</span><span class="sxs-lookup"><span data-stu-id="ce4a1-113">Event ID</span></span>|<span data-ttu-id="ce4a1-114">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="ce4a1-114">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`StrongNameVerificationStart_V1`|<span data-ttu-id="ce4a1-115">181</span><span class="sxs-lookup"><span data-stu-id="ce4a1-115">181</span></span>|<span data-ttu-id="ce4a1-116">强名称验证开始。</span><span class="sxs-lookup"><span data-stu-id="ce4a1-116">Start of strong name verification.</span></span>|  
|`StrongNameVerificationStop_V1`|<span data-ttu-id="ce4a1-117">182</span><span class="sxs-lookup"><span data-stu-id="ce4a1-117">182</span></span>|<span data-ttu-id="ce4a1-118">强名称验证结束。</span><span class="sxs-lookup"><span data-stu-id="ce4a1-118">End of strong name verification.</span></span>|  
  
 <span data-ttu-id="ce4a1-119">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="ce4a1-119">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="ce4a1-120">字段名</span><span class="sxs-lookup"><span data-stu-id="ce4a1-120">Field name</span></span>|<span data-ttu-id="ce4a1-121">数据类型</span><span class="sxs-lookup"><span data-stu-id="ce4a1-121">Data type</span></span>|<span data-ttu-id="ce4a1-122">描述</span><span class="sxs-lookup"><span data-stu-id="ce4a1-122">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="ce4a1-123">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="ce4a1-123">VerificationFlags</span></span>|<span data-ttu-id="ce4a1-124">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="ce4a1-124">win:UInt32</span></span>|<span data-ttu-id="ce4a1-125">验证标志。</span><span class="sxs-lookup"><span data-stu-id="ce4a1-125">The verification flags.</span></span>|  
|<span data-ttu-id="ce4a1-126">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="ce4a1-126">ErrorCode</span></span>|<span data-ttu-id="ce4a1-127">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="ce4a1-127">win:UInt32</span></span>|<span data-ttu-id="ce4a1-128">HResult 错误代码。</span><span class="sxs-lookup"><span data-stu-id="ce4a1-128">The HResult error code.</span></span>|  
|<span data-ttu-id="ce4a1-129">FullyQualifiedAssemblyName</span><span class="sxs-lookup"><span data-stu-id="ce4a1-129">FullyQualifiedAssemblyName</span></span>|<span data-ttu-id="ce4a1-130">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="ce4a1-130">win:UnicodeString</span></span>|<span data-ttu-id="ce4a1-131">完全限定程序集名称。</span><span class="sxs-lookup"><span data-stu-id="ce4a1-131">The fully qualified assembly name.</span></span>|  
|<span data-ttu-id="ce4a1-132">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="ce4a1-132">ClrInstanceID</span></span>|<span data-ttu-id="ce4a1-133">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="ce4a1-133">win:UInt16</span></span>|<span data-ttu-id="ce4a1-134">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="ce4a1-134">Unique ID for the instance of CLR or CoreCLR.</span></span>|  

## <a name="authenticodeverificationstart_v1-and-authenticodeverificationstop_v1-events"></a><span data-ttu-id="ce4a1-135">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 事件</span><span class="sxs-lookup"><span data-stu-id="ce4a1-135">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="ce4a1-136">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="ce4a1-136">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="ce4a1-137">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="ce4a1-137">Keyword for raising the event</span></span>|<span data-ttu-id="ce4a1-138">Level</span><span class="sxs-lookup"><span data-stu-id="ce4a1-138">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="ce4a1-139">`SecurityKeyword` (0x400)</span><span class="sxs-lookup"><span data-stu-id="ce4a1-139">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="ce4a1-140">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="ce4a1-140">Informational(4)</span></span>|  
  
 <span data-ttu-id="ce4a1-141">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="ce4a1-141">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="ce4a1-142">Event</span><span class="sxs-lookup"><span data-stu-id="ce4a1-142">Event</span></span>|<span data-ttu-id="ce4a1-143">事件 ID</span><span class="sxs-lookup"><span data-stu-id="ce4a1-143">Event ID</span></span>|<span data-ttu-id="ce4a1-144">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="ce4a1-144">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AuthenticodeVerificationStart_V1`|<span data-ttu-id="ce4a1-145">183</span><span class="sxs-lookup"><span data-stu-id="ce4a1-145">183</span></span>|<span data-ttu-id="ce4a1-146">验证码验证开始。</span><span class="sxs-lookup"><span data-stu-id="ce4a1-146">Start of Authenticode verification.</span></span>|  
|`AuthenticodeVerificationStop_V1`|<span data-ttu-id="ce4a1-147">184</span><span class="sxs-lookup"><span data-stu-id="ce4a1-147">184</span></span>|<span data-ttu-id="ce4a1-148">验证码验证结束。</span><span class="sxs-lookup"><span data-stu-id="ce4a1-148">End of Authenticode verification.</span></span>|  
  
 <span data-ttu-id="ce4a1-149">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="ce4a1-149">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="ce4a1-150">字段名</span><span class="sxs-lookup"><span data-stu-id="ce4a1-150">Field name</span></span>|<span data-ttu-id="ce4a1-151">数据类型</span><span class="sxs-lookup"><span data-stu-id="ce4a1-151">Data type</span></span>|<span data-ttu-id="ce4a1-152">描述</span><span class="sxs-lookup"><span data-stu-id="ce4a1-152">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="ce4a1-153">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="ce4a1-153">VerificationFlags</span></span>|<span data-ttu-id="ce4a1-154">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="ce4a1-154">win:UInt32</span></span>|<span data-ttu-id="ce4a1-155">验证标志。</span><span class="sxs-lookup"><span data-stu-id="ce4a1-155">The verification flags.</span></span>|  
|<span data-ttu-id="ce4a1-156">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="ce4a1-156">ErrorCode</span></span>|<span data-ttu-id="ce4a1-157">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="ce4a1-157">win:UInt32</span></span>|<span data-ttu-id="ce4a1-158">HResult 错误代码。</span><span class="sxs-lookup"><span data-stu-id="ce4a1-158">The HResult error code.</span></span>|  
|<span data-ttu-id="ce4a1-159">ModulePath</span><span class="sxs-lookup"><span data-stu-id="ce4a1-159">ModulePath</span></span>|<span data-ttu-id="ce4a1-160">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="ce4a1-160">win:UnicodeString</span></span>|<span data-ttu-id="ce4a1-161">模块路径。</span><span class="sxs-lookup"><span data-stu-id="ce4a1-161">The module path.</span></span>|  
|<span data-ttu-id="ce4a1-162">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="ce4a1-162">ClrInstanceID</span></span>|<span data-ttu-id="ce4a1-163">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="ce4a1-163">win:UInt16</span></span>|<span data-ttu-id="ce4a1-164">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="ce4a1-164">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ce4a1-165">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ce4a1-165">See also</span></span>

- [<span data-ttu-id="ce4a1-166">CLR ETW 事件</span><span class="sxs-lookup"><span data-stu-id="ce4a1-166">CLR ETW Events</span></span>](clr-etw-events.md)
