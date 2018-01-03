---
title: "CorDebugPlatform 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugPlatformEnum
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugPlatformEnum
helpviewer_keywords: CorDebugPlatformEnum enumeration [.NET Framework debugging]
ms.assetid: c5444816-7378-4521-afd3-bf5e4b5303d5
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1f67ed6ad886c137eddaa42840f3f0edda88bd4a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="cordebugplatform-enumeration"></a><span data-ttu-id="ebdd0-102">CorDebugPlatform 枚举</span><span class="sxs-lookup"><span data-stu-id="ebdd0-102">CorDebugPlatform Enumeration</span></span>
<span data-ttu-id="ebdd0-103">提供通过使用的目标平台值[icordebugdatatarget:: Getplatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="ebdd0-103">Provides target platform values that are used by the [ICorDebugDataTarget::GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebdd0-104">语法</span><span class="sxs-lookup"><span data-stu-id="ebdd0-104">Syntax</span></span>  
  
```  
typedef enum CorDebugPlatform  
{  
    CORDB_PLATFORM_WINDOWS_X86,    // Windows on Intel x86  
    CORDB_PLATFORM_WINDOWS_AMD64,  // Windows x64 (AMD64, Intel EM64T)  
    CORDB_PLATFORM_WINDOWS_IA64,   // Windows on Intel IA-64  
    CORDB_PLATFORM_MAC_PPC,        // Macintosh OS on PowerPC  
    CORDB_PLATFORM_MAC_X86,        // Macintosh OS on Intel x86  
    CORDB_PLATFORM_WINDOWS_ARM,    // Windows on ARM  
    CORDB_PLATFORM_MAC_AMD64       // MacOS on Intel x64  
} CorDebugPlatform;  
```  
  
## <a name="members"></a><span data-ttu-id="ebdd0-105">成员</span><span class="sxs-lookup"><span data-stu-id="ebdd0-105">Members</span></span>  
  
|<span data-ttu-id="ebdd0-106">成员</span><span class="sxs-lookup"><span data-stu-id="ebdd0-106">Member</span></span>|<span data-ttu-id="ebdd0-107">描述</span><span class="sxs-lookup"><span data-stu-id="ebdd0-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="ebdd0-108">CORDB_PLATFORM_WINDOWS_X86</span><span class="sxs-lookup"><span data-stu-id="ebdd0-108">CORDB_PLATFORM_WINDOWS_X86</span></span>|<span data-ttu-id="ebdd0-109">目标平台是在 Intel x86 硬件上运行的 Windows。</span><span class="sxs-lookup"><span data-stu-id="ebdd0-109">The target platform is Windows running on Intel x86 hardware.</span></span>|  
|<span data-ttu-id="ebdd0-110">CORDB_PLATFORM_WINDOWS_AMD64</span><span class="sxs-lookup"><span data-stu-id="ebdd0-110">CORDB_PLATFORM_WINDOWS_AMD64</span></span>|<span data-ttu-id="ebdd0-111">目标平台是在 AMD64 或 Intel EM64T 硬件上运行的 64 位 Windows。</span><span class="sxs-lookup"><span data-stu-id="ebdd0-111">The target platform is 64 bit Windows running on AMD64 or Intel EM64T hardware.</span></span>|  
|<span data-ttu-id="ebdd0-112">CORDB_PLATFORM_WINDOWS_IA64</span><span class="sxs-lookup"><span data-stu-id="ebdd0-112">CORDB_PLATFORM_WINDOWS_IA64</span></span>|<span data-ttu-id="ebdd0-113">目标平台是在 Intel IA-64 硬件上运行的 32 位 Windows。</span><span class="sxs-lookup"><span data-stu-id="ebdd0-113">The target platform is 32 bit Windows running on Intel IA-64 hardware.</span></span>|  
|<span data-ttu-id="ebdd0-114">CORDB_PLATFORM_MAC_PPC</span><span class="sxs-lookup"><span data-stu-id="ebdd0-114">CORDB_PLATFORM_MAC_PPC</span></span>|<span data-ttu-id="ebdd0-115">目标平台是在 PowerPC 硬件上运行的 Macintosh 操作系统。</span><span class="sxs-lookup"><span data-stu-id="ebdd0-115">The target platform is the Macintosh operating system running on PowerPC hardware.</span></span>|  
|<span data-ttu-id="ebdd0-116">CORDB_PLATFORM_MAC_X86</span><span class="sxs-lookup"><span data-stu-id="ebdd0-116">CORDB_PLATFORM_MAC_X86</span></span>|<span data-ttu-id="ebdd0-117">目标平台是在 Intel x86 硬件上运行的 Macintosh 操作系统。</span><span class="sxs-lookup"><span data-stu-id="ebdd0-117">The target platform is the Macintosh operating system running on Intel x86 hardware.</span></span>|  
|<span data-ttu-id="ebdd0-118">CORDB_PLATFORM_WINDOWS_ARM</span><span class="sxs-lookup"><span data-stu-id="ebdd0-118">CORDB_PLATFORM_WINDOWS_ARM</span></span>|<span data-ttu-id="ebdd0-119">目标平台是在 Windows ARM 硬件上运行的 Macintosh 操作系统。</span><span class="sxs-lookup"><span data-stu-id="ebdd0-119">The target platform is the Macintosh operating system running on Windows ARM hardware.</span></span>|  
|<span data-ttu-id="ebdd0-120">CORDB_PLATFORM_MAC_AMD64</span><span class="sxs-lookup"><span data-stu-id="ebdd0-120">CORDB_PLATFORM_MAC_AMD64</span></span>|<span data-ttu-id="ebdd0-121">目标平台是在 AMD64 硬件上运行的 Macintosh 操作系统。</span><span class="sxs-lookup"><span data-stu-id="ebdd0-121">The target platform is the Macintosh operating system running on AMD64 hardware.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ebdd0-122">惠?</span><span class="sxs-lookup"><span data-stu-id="ebdd0-122">Requirements</span></span>  
 <span data-ttu-id="ebdd0-123">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ebdd0-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ebdd0-124">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ebdd0-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ebdd0-125">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ebdd0-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ebdd0-126">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ebdd0-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
 <span data-ttu-id="ebdd0-127">`CORDB_PLATFORM_WINDOWS_ARM` 成员和 `CORDB_PLATFORM_MAC_AMD64` 成员在 .NET Framework 4.5.2 及更高版本中可用。</span><span class="sxs-lookup"><span data-stu-id="ebdd0-127">The `CORDB_PLATFORM_WINDOWS_ARM` and `CORDB_PLATFORM_MAC_AMD64` members are available in the .NET Framework 4.5.2 and later versions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebdd0-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="ebdd0-128">See Also</span></span>  
 [<span data-ttu-id="ebdd0-129">调试枚举</span><span class="sxs-lookup"><span data-stu-id="ebdd0-129">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
