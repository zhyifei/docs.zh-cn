---
title: ICorDebugDataTarget::GetPlatform 方法
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget.GetPlatform Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget::GetPlatform
helpviewer_keywords:
- GetPlatform method [.NET Framework debugging]
- ICorDebugDataTarget::GetPlatform method [.NET Framework debugging]
ms.assetid: 9ee96c9d-7a3d-4129-a6cc-7675c7f2dda4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 17ae761b2d48552aded8191ddbea26552d8da277
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33411013"
---
# <a name="icordebugdatatargetgetplatform-method"></a><span data-ttu-id="6c716-102">ICorDebugDataTarget::GetPlatform 方法</span><span class="sxs-lookup"><span data-stu-id="6c716-102">ICorDebugDataTarget::GetPlatform Method</span></span>
<span data-ttu-id="6c716-103">提供有关平台，包括处理器体系结构和目标进程正在其运行的操作系统的信息。</span><span class="sxs-lookup"><span data-stu-id="6c716-103">Provides information about the platform, including processor architecture and operating system, on which the target process is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c716-104">语法</span><span class="sxs-lookup"><span data-stu-id="6c716-104">Syntax</span></span>  
  
```  
HRESULT GetPlatform([out] CorDebugPlatform * pTargetPlatform);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6c716-105">参数</span><span class="sxs-lookup"><span data-stu-id="6c716-105">Parameters</span></span>  
 `pTargetPlatform`  
 <span data-ttu-id="6c716-106">[out]指向的指针[CorDebugPlatformEnum](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md)描述目标平台的枚举。</span><span class="sxs-lookup"><span data-stu-id="6c716-106">[out] A pointer to a [CorDebugPlatformEnum](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md) enumeration that describes the target platform.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6c716-107">备注</span><span class="sxs-lookup"><span data-stu-id="6c716-107">Remarks</span></span>  
 <span data-ttu-id="6c716-108">`CorDebugPlatformEnum`枚举返回的值由[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)接口来确定目标进程，如其指针大小、 地址空间布局、 注册设置、 指令格式、 上下文布局的详细信息和调用约定。</span><span class="sxs-lookup"><span data-stu-id="6c716-108">The `CorDebugPlatformEnum` enumeration return value is used by the [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interface to determine details of the target process such as its pointer size, address space layout, register set, instruction format, context layout, and calling conventions.</span></span>  
  
 <span data-ttu-id="6c716-109">`pTargetPlatform`值可能引用而不是在使用指定实际硬件的目标模拟的平台。</span><span class="sxs-lookup"><span data-stu-id="6c716-109">The `pTargetPlatform` value may refer to a platform that is being emulated for the target instead of specifying the actual hardware in use.</span></span> <span data-ttu-id="6c716-110">例如，在 64 位版本的 Windows 操作系统在 Windows (WOW) 环境上的 Windows 中运行的进程应使用`CORDB_PLATFORM_WINDOWS_X86`值[CorDebugPlatformEnum](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md)枚举。</span><span class="sxs-lookup"><span data-stu-id="6c716-110">For example, a process that is running in the Windows on Windows (WOW) environment on a 64-bit edition of the Windows operating system should use the `CORDB_PLATFORM_WINDOWS_X86` value of the [CorDebugPlatformEnum](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md) enumeration.</span></span>  
  
 <span data-ttu-id="6c716-111">此方法必须成功。</span><span class="sxs-lookup"><span data-stu-id="6c716-111">This method must succeed.</span></span> <span data-ttu-id="6c716-112">如果失败，则目标平台是不可用。</span><span class="sxs-lookup"><span data-stu-id="6c716-112">If it fails, the target platform is unusable.</span></span> <span data-ttu-id="6c716-113">该方法可能会出于以下原因失败：</span><span class="sxs-lookup"><span data-stu-id="6c716-113">The method may fail for the following reasons:</span></span>  
  
-   <span data-ttu-id="6c716-114">目标模拟该平台是不可用。</span><span class="sxs-lookup"><span data-stu-id="6c716-114">The platform that is being emulated for the target is unusable.</span></span>  
  
-   <span data-ttu-id="6c716-115">目标平台上的实际硬件不可用。</span><span class="sxs-lookup"><span data-stu-id="6c716-115">The actual hardware on the target platform is unusable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c716-116">要求</span><span class="sxs-lookup"><span data-stu-id="6c716-116">Requirements</span></span>  
 <span data-ttu-id="6c716-117">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6c716-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c716-118">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6c716-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6c716-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6c716-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6c716-120">**.NET framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c716-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c716-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="6c716-121">See Also</span></span>  
 [<span data-ttu-id="6c716-122">ICorDebugDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="6c716-122">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)  
 [<span data-ttu-id="6c716-123">调试接口</span><span class="sxs-lookup"><span data-stu-id="6c716-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="6c716-124">调试</span><span class="sxs-lookup"><span data-stu-id="6c716-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
