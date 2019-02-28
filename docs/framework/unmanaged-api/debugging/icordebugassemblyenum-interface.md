---
title: ICorDebugAssemblyEnum 接口
ms.date: 03/30/2017
api_name:
- ICorDebugAssemblyEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssemblyEnum
helpviewer_keywords:
- ICorDebugAssemblyEnum interface [.NET Framework debugging]
ms.assetid: 891ceb43-5161-421e-a0bf-299962fd7efd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b259ceb8af61785bc77536d2718bdfbb3683c066
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56979887"
---
# <a name="icordebugassemblyenum-interface"></a><span data-ttu-id="c7d2f-102">ICorDebugAssemblyEnum 接口</span><span class="sxs-lookup"><span data-stu-id="c7d2f-102">ICorDebugAssemblyEnum Interface</span></span>

<span data-ttu-id="c7d2f-103">实现 ICorDebugEnum 方法，并枚举 icor 调试程序集数组。</span><span class="sxs-lookup"><span data-stu-id="c7d2f-103">Implements ICorDebugEnum methods and enumerates ICorDebugAssembly arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c7d2f-104">方法</span><span class="sxs-lookup"><span data-stu-id="c7d2f-104">Methods</span></span>  
  
|<span data-ttu-id="c7d2f-105">方法</span><span class="sxs-lookup"><span data-stu-id="c7d2f-105">Method</span></span>|<span data-ttu-id="c7d2f-106">描述</span><span class="sxs-lookup"><span data-stu-id="c7d2f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c7d2f-107">Next 方法</span><span class="sxs-lookup"><span data-stu-id="c7d2f-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassemblyenum-next-method.md)|<span data-ttu-id="c7d2f-108">获取指定的数目的`ICorDebugAssembly`实例在枚举中，从当前的位置开始。</span><span class="sxs-lookup"><span data-stu-id="c7d2f-108">Gets the specified number of `ICorDebugAssembly` instances in the enumeration, starting from the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c7d2f-109">备注</span><span class="sxs-lookup"><span data-stu-id="c7d2f-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c7d2f-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="c7d2f-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7d2f-111">要求</span><span class="sxs-lookup"><span data-stu-id="c7d2f-111">Requirements</span></span>  
 <span data-ttu-id="c7d2f-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c7d2f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7d2f-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c7d2f-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c7d2f-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c7d2f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c7d2f-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7d2f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7d2f-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="c7d2f-116">See also</span></span>
- [<span data-ttu-id="c7d2f-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="c7d2f-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
