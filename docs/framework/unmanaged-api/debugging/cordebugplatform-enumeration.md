---
title: CorDebugPlatform 枚举
ms.date: 03/30/2017
api_name:
- CorDebugPlatformEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugPlatformEnum
helpviewer_keywords:
- CorDebugPlatformEnum enumeration [.NET Framework debugging]
ms.assetid: c5444816-7378-4521-afd3-bf5e4b5303d5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 03b6f1b29157889d0e84e5dddc94d5e3ae27efce
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59180930"
---
# <a name="cordebugplatform-enumeration"></a><span data-ttu-id="5d99f-102">CorDebugPlatform 枚举</span><span class="sxs-lookup"><span data-stu-id="5d99f-102">CorDebugPlatform Enumeration</span></span>
<span data-ttu-id="5d99f-103">提供了使用的目标平台值[icordebugdatatarget:: Getplatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="5d99f-103">Provides target platform values that are used by the [ICorDebugDataTarget::GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d99f-104">语法</span><span class="sxs-lookup"><span data-stu-id="5d99f-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="5d99f-105">成员</span><span class="sxs-lookup"><span data-stu-id="5d99f-105">Members</span></span>  
  
|<span data-ttu-id="5d99f-106">成员</span><span class="sxs-lookup"><span data-stu-id="5d99f-106">Member</span></span>|<span data-ttu-id="5d99f-107">描述</span><span class="sxs-lookup"><span data-stu-id="5d99f-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="5d99f-108">CORDB_PLATFORM_WINDOWS_X86</span><span class="sxs-lookup"><span data-stu-id="5d99f-108">CORDB_PLATFORM_WINDOWS_X86</span></span>|<span data-ttu-id="5d99f-109">目标平台是在 Intel x86 硬件上运行的 Windows。</span><span class="sxs-lookup"><span data-stu-id="5d99f-109">The target platform is Windows running on Intel x86 hardware.</span></span>|  
|<span data-ttu-id="5d99f-110">CORDB_PLATFORM_WINDOWS_AMD64</span><span class="sxs-lookup"><span data-stu-id="5d99f-110">CORDB_PLATFORM_WINDOWS_AMD64</span></span>|<span data-ttu-id="5d99f-111">目标平台是在 AMD64 或 Intel EM64T 硬件上运行的 64 位 Windows。</span><span class="sxs-lookup"><span data-stu-id="5d99f-111">The target platform is 64 bit Windows running on AMD64 or Intel EM64T hardware.</span></span>|  
|<span data-ttu-id="5d99f-112">CORDB_PLATFORM_WINDOWS_IA64</span><span class="sxs-lookup"><span data-stu-id="5d99f-112">CORDB_PLATFORM_WINDOWS_IA64</span></span>|<span data-ttu-id="5d99f-113">目标平台是在 Intel IA-64 硬件上运行的 32 位 Windows。</span><span class="sxs-lookup"><span data-stu-id="5d99f-113">The target platform is 32 bit Windows running on Intel IA-64 hardware.</span></span>|  
|<span data-ttu-id="5d99f-114">CORDB_PLATFORM_MAC_PPC</span><span class="sxs-lookup"><span data-stu-id="5d99f-114">CORDB_PLATFORM_MAC_PPC</span></span>|<span data-ttu-id="5d99f-115">目标平台是在 PowerPC 硬件上运行的 Macintosh 操作系统。</span><span class="sxs-lookup"><span data-stu-id="5d99f-115">The target platform is the Macintosh operating system running on PowerPC hardware.</span></span>|  
|<span data-ttu-id="5d99f-116">CORDB_PLATFORM_MAC_X86</span><span class="sxs-lookup"><span data-stu-id="5d99f-116">CORDB_PLATFORM_MAC_X86</span></span>|<span data-ttu-id="5d99f-117">目标平台是在 Intel x86 硬件上运行的 Macintosh 操作系统。</span><span class="sxs-lookup"><span data-stu-id="5d99f-117">The target platform is the Macintosh operating system running on Intel x86 hardware.</span></span>|  
|<span data-ttu-id="5d99f-118">CORDB_PLATFORM_WINDOWS_ARM</span><span class="sxs-lookup"><span data-stu-id="5d99f-118">CORDB_PLATFORM_WINDOWS_ARM</span></span>|<span data-ttu-id="5d99f-119">目标平台是在 Windows ARM 硬件上运行的 Macintosh 操作系统。</span><span class="sxs-lookup"><span data-stu-id="5d99f-119">The target platform is the Macintosh operating system running on Windows ARM hardware.</span></span>|  
|<span data-ttu-id="5d99f-120">CORDB_PLATFORM_MAC_AMD64</span><span class="sxs-lookup"><span data-stu-id="5d99f-120">CORDB_PLATFORM_MAC_AMD64</span></span>|<span data-ttu-id="5d99f-121">目标平台是在 AMD64 硬件上运行的 Macintosh 操作系统。</span><span class="sxs-lookup"><span data-stu-id="5d99f-121">The target platform is the Macintosh operating system running on AMD64 hardware.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5d99f-122">要求</span><span class="sxs-lookup"><span data-stu-id="5d99f-122">Requirements</span></span>  
 <span data-ttu-id="5d99f-123">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5d99f-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d99f-124">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5d99f-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5d99f-125">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5d99f-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5d99f-126">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d99f-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
 <span data-ttu-id="5d99f-127">`CORDB_PLATFORM_WINDOWS_ARM` 成员和 `CORDB_PLATFORM_MAC_AMD64` 成员在 .NET Framework 4.5.2 及更高版本中可用。</span><span class="sxs-lookup"><span data-stu-id="5d99f-127">The `CORDB_PLATFORM_WINDOWS_ARM` and `CORDB_PLATFORM_MAC_AMD64` members are available in the .NET Framework 4.5.2 and later versions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d99f-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="5d99f-128">See also</span></span>

- [<span data-ttu-id="5d99f-129">调试枚举</span><span class="sxs-lookup"><span data-stu-id="5d99f-129">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
