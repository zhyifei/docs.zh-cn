---
title: ICorDebugProcessEnum 接口
ms.date: 03/30/2017
api_name:
- ICorDebugProcessEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcessEnum
helpviewer_keywords:
- ICorDebugProcessEnum interface [.NET Framework debugging]
ms.assetid: b63a507a-ca97-4be0-8e4f-401cce2125f6
topic_type:
- apiref
ms.openlocfilehash: c11e286d8c33d6823127d9a6d5989064e2299bc4
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792147"
---
# <a name="icordebugprocessenum-interface"></a><span data-ttu-id="d541b-102">ICorDebugProcessEnum 接口</span><span class="sxs-lookup"><span data-stu-id="d541b-102">ICorDebugProcessEnum Interface</span></span>
<span data-ttu-id="d541b-103">实现 ICorDebugEnum 方法并枚举 ICorDebugProcess 数组。</span><span class="sxs-lookup"><span data-stu-id="d541b-103">Implements ICorDebugEnum methods and enumerates ICorDebugProcess arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d541b-104">方法</span><span class="sxs-lookup"><span data-stu-id="d541b-104">Methods</span></span>  
  
|<span data-ttu-id="d541b-105">方法</span><span class="sxs-lookup"><span data-stu-id="d541b-105">Method</span></span>|<span data-ttu-id="d541b-106">描述</span><span class="sxs-lookup"><span data-stu-id="d541b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d541b-107">Next 方法</span><span class="sxs-lookup"><span data-stu-id="d541b-107">Next Method</span></span>](icordebugprocessenum-next-method.md)|<span data-ttu-id="d541b-108">从当前位置开始，从枚举中获取指定数目的 `ICorDebugProcess` 实例。</span><span class="sxs-lookup"><span data-stu-id="d541b-108">Gets the specified number of `ICorDebugProcess` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d541b-109">备注</span><span class="sxs-lookup"><span data-stu-id="d541b-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d541b-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="d541b-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d541b-111">需求</span><span class="sxs-lookup"><span data-stu-id="d541b-111">Requirements</span></span>  
 <span data-ttu-id="d541b-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d541b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d541b-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d541b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d541b-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d541b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d541b-115">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d541b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d541b-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d541b-116">See also</span></span>

- [<span data-ttu-id="d541b-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="d541b-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
