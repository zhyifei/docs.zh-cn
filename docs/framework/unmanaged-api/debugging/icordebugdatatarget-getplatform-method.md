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
ms.openlocfilehash: 3df35d52a4e5209b282ccef653b065bdcf1f8fe4
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976533"
---
# <a name="icordebugdatatargetgetplatform-method"></a><span data-ttu-id="f35ed-102">ICorDebugDataTarget::GetPlatform 方法</span><span class="sxs-lookup"><span data-stu-id="f35ed-102">ICorDebugDataTarget::GetPlatform Method</span></span>
<span data-ttu-id="f35ed-103">提供有关平台的信息，包括在其上运行目标进程的处理器体系结构和操作系统。</span><span class="sxs-lookup"><span data-stu-id="f35ed-103">Provides information about the platform, including processor architecture and operating system, on which the target process is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f35ed-104">语法</span><span class="sxs-lookup"><span data-stu-id="f35ed-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPlatform([out] CorDebugPlatform * pTargetPlatform);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f35ed-105">参数</span><span class="sxs-lookup"><span data-stu-id="f35ed-105">Parameters</span></span>  
 `pTargetPlatform`  
 <span data-ttu-id="f35ed-106">弄指向描述目标平台的[CorDebugPlatformEnum](cordebugplatform-enumeration.md)枚举的指针。</span><span class="sxs-lookup"><span data-stu-id="f35ed-106">[out] A pointer to a [CorDebugPlatformEnum](cordebugplatform-enumeration.md) enumeration that describes the target platform.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f35ed-107">备注</span><span class="sxs-lookup"><span data-stu-id="f35ed-107">Remarks</span></span>  
 <span data-ttu-id="f35ed-108">`CorDebugPlatformEnum`枚举返回值由[ICorDebug](icordebug-interface.md)接口用于确定目标进程的详细信息，例如，其指针大小、地址空间布局、寄存器集、指令格式、上下文布局和调用约定。</span><span class="sxs-lookup"><span data-stu-id="f35ed-108">The `CorDebugPlatformEnum` enumeration return value is used by the [ICorDebug](icordebug-interface.md) interface to determine details of the target process such as its pointer size, address space layout, register set, instruction format, context layout, and calling conventions.</span></span>  
  
 <span data-ttu-id="f35ed-109">`pTargetPlatform`该值可以引用为目标模拟的平台，而不是指定使用中的实际硬件。</span><span class="sxs-lookup"><span data-stu-id="f35ed-109">The `pTargetPlatform` value may refer to a platform that is being emulated for the target instead of specifying the actual hardware in use.</span></span> <span data-ttu-id="f35ed-110">例如，在 windows 操作系统的64位版本上，在 windows on windows （WOW）环境中运行的进程应使用`CORDB_PLATFORM_WINDOWS_X86` [CorDebugPlatformEnum](cordebugplatform-enumeration.md)枚举的值。</span><span class="sxs-lookup"><span data-stu-id="f35ed-110">For example, a process that is running in the Windows on Windows (WOW) environment on a 64-bit edition of the Windows operating system should use the `CORDB_PLATFORM_WINDOWS_X86` value of the [CorDebugPlatformEnum](cordebugplatform-enumeration.md) enumeration.</span></span>  
  
 <span data-ttu-id="f35ed-111">此方法必须成功。</span><span class="sxs-lookup"><span data-stu-id="f35ed-111">This method must succeed.</span></span> <span data-ttu-id="f35ed-112">如果该操作失败，目标平台将无法使用。</span><span class="sxs-lookup"><span data-stu-id="f35ed-112">If it fails, the target platform is unusable.</span></span> <span data-ttu-id="f35ed-113">此方法可能会由于以下原因而失败：</span><span class="sxs-lookup"><span data-stu-id="f35ed-113">The method may fail for the following reasons:</span></span>  
  
- <span data-ttu-id="f35ed-114">正在为目标模拟的平台不可用。</span><span class="sxs-lookup"><span data-stu-id="f35ed-114">The platform that is being emulated for the target is unusable.</span></span>  
  
- <span data-ttu-id="f35ed-115">目标平台上的实际硬件不可用。</span><span class="sxs-lookup"><span data-stu-id="f35ed-115">The actual hardware on the target platform is unusable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f35ed-116">要求</span><span class="sxs-lookup"><span data-stu-id="f35ed-116">Requirements</span></span>  
 <span data-ttu-id="f35ed-117">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f35ed-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f35ed-118">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f35ed-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f35ed-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f35ed-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f35ed-120">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f35ed-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f35ed-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f35ed-121">See also</span></span>

- [<span data-ttu-id="f35ed-122">ICorDebugDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="f35ed-122">ICorDebugDataTarget Interface</span></span>](icordebugdatatarget-interface.md)
- [<span data-ttu-id="f35ed-123">调试接口</span><span class="sxs-lookup"><span data-stu-id="f35ed-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="f35ed-124">调试</span><span class="sxs-lookup"><span data-stu-id="f35ed-124">Debugging</span></span>](index.md)
