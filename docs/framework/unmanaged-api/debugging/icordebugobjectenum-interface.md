---
title: ICorDebugObjectEnum 接口
ms.date: 03/30/2017
api_name:
- ICorDebugObjectEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectEnum
helpviewer_keywords:
- ICorDebugObjectEnum interface [.NET Framework debugging]
ms.assetid: 9ffb4498-7719-49d3-8890-df2c22248a0c
topic_type:
- apiref
ms.openlocfilehash: b77d5859986c90d6ef61c02547014d0bec354106
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73096145"
---
# <a name="icordebugobjectenum-interface"></a><span data-ttu-id="44760-102">ICorDebugObjectEnum 接口</span><span class="sxs-lookup"><span data-stu-id="44760-102">ICorDebugObjectEnum Interface</span></span>

<span data-ttu-id="44760-103">实现 ICorDebugEnum 方法，并按它们的相对虚拟地址（Rva）枚举对象的数组。</span><span class="sxs-lookup"><span data-stu-id="44760-103">Implements ICorDebugEnum methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="44760-104">方法</span><span class="sxs-lookup"><span data-stu-id="44760-104">Methods</span></span>  
  
|<span data-ttu-id="44760-105">方法</span><span class="sxs-lookup"><span data-stu-id="44760-105">Method</span></span>|<span data-ttu-id="44760-106">描述</span><span class="sxs-lookup"><span data-stu-id="44760-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="44760-107">Next 方法</span><span class="sxs-lookup"><span data-stu-id="44760-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectenum-next-method.md)|<span data-ttu-id="44760-108">从当前位置开始，获取枚举中指定数量的对象的 Rva。</span><span class="sxs-lookup"><span data-stu-id="44760-108">Gets the RVAs of the specified number of objects from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="44760-109">备注</span><span class="sxs-lookup"><span data-stu-id="44760-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="44760-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="44760-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44760-111">要求</span><span class="sxs-lookup"><span data-stu-id="44760-111">Requirements</span></span>  
 <span data-ttu-id="44760-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="44760-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44760-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="44760-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="44760-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="44760-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="44760-115">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44760-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44760-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="44760-116">See also</span></span>

- [<span data-ttu-id="44760-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="44760-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
