---
title: ICorDebugAssemblyEnum 接口 1
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
ms.openlocfilehash: c6b8fa9304296765fcdb6ebe42db5523e5ff387d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33399066"
---
# <a name="icordebugassemblyenum-interface1"></a><span data-ttu-id="72f7d-102">ICorDebugAssemblyEnum 接口 1</span><span class="sxs-lookup"><span data-stu-id="72f7d-102">ICorDebugAssemblyEnum Interface1</span></span>
<span data-ttu-id="72f7d-103">实现 ICorDebugEnum 方法，并枚举 icor 调试程序集的数组。</span><span class="sxs-lookup"><span data-stu-id="72f7d-103">Implements ICorDebugEnum methods and enumerates ICorDebugAssembly arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="72f7d-104">方法</span><span class="sxs-lookup"><span data-stu-id="72f7d-104">Methods</span></span>  
  
|<span data-ttu-id="72f7d-105">方法</span><span class="sxs-lookup"><span data-stu-id="72f7d-105">Method</span></span>|<span data-ttu-id="72f7d-106">描述</span><span class="sxs-lookup"><span data-stu-id="72f7d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="72f7d-107">Next 方法</span><span class="sxs-lookup"><span data-stu-id="72f7d-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassemblyenum-next-method.md)|<span data-ttu-id="72f7d-108">获取指定的数目的`ICorDebugAssembly`在枚举中，从当前的位置开始的实例。</span><span class="sxs-lookup"><span data-stu-id="72f7d-108">Gets the specified number of `ICorDebugAssembly` instances in the enumeration, starting from the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="72f7d-109">备注</span><span class="sxs-lookup"><span data-stu-id="72f7d-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="72f7d-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="72f7d-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72f7d-111">要求</span><span class="sxs-lookup"><span data-stu-id="72f7d-111">Requirements</span></span>  
 <span data-ttu-id="72f7d-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="72f7d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72f7d-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="72f7d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="72f7d-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="72f7d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="72f7d-115">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72f7d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72f7d-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="72f7d-116">See Also</span></span>  
 [<span data-ttu-id="72f7d-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="72f7d-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
