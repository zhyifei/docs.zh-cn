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
ms.openlocfilehash: aa0bc34c3cb3ac330582cee0843022e913376fc2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73192163"
---
# <a name="icordebugassemblyenum-interface"></a><span data-ttu-id="4f8be-102">ICorDebugAssemblyEnum 接口</span><span class="sxs-lookup"><span data-stu-id="4f8be-102">ICorDebugAssemblyEnum Interface</span></span>

<span data-ttu-id="4f8be-103">实现 ICorDebugEnum 方法并枚举 ICorDebugAssembly 数组。</span><span class="sxs-lookup"><span data-stu-id="4f8be-103">Implements ICorDebugEnum methods and enumerates ICorDebugAssembly arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4f8be-104">方法</span><span class="sxs-lookup"><span data-stu-id="4f8be-104">Methods</span></span>  
  
|<span data-ttu-id="4f8be-105">方法</span><span class="sxs-lookup"><span data-stu-id="4f8be-105">Method</span></span>|<span data-ttu-id="4f8be-106">描述</span><span class="sxs-lookup"><span data-stu-id="4f8be-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4f8be-107">Next 方法</span><span class="sxs-lookup"><span data-stu-id="4f8be-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassemblyenum-next-method.md)|<span data-ttu-id="4f8be-108">从当前位置开始，获取枚举中指定数目的 `ICorDebugAssembly` 实例。</span><span class="sxs-lookup"><span data-stu-id="4f8be-108">Gets the specified number of `ICorDebugAssembly` instances in the enumeration, starting from the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4f8be-109">备注</span><span class="sxs-lookup"><span data-stu-id="4f8be-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4f8be-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="4f8be-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f8be-111">要求</span><span class="sxs-lookup"><span data-stu-id="4f8be-111">Requirements</span></span>  
 <span data-ttu-id="4f8be-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4f8be-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f8be-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4f8be-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4f8be-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4f8be-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4f8be-115">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f8be-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f8be-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="4f8be-116">See also</span></span>

- [<span data-ttu-id="4f8be-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="4f8be-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
