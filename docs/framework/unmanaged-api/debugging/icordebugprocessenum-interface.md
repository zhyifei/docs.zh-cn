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
ms.openlocfilehash: 3a820381f1c4605d620d74a5915c3e08de69d9fb
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210106"
---
# <a name="icordebugprocessenum-interface"></a><span data-ttu-id="1755e-102">ICorDebugProcessEnum 接口</span><span class="sxs-lookup"><span data-stu-id="1755e-102">ICorDebugProcessEnum Interface</span></span>
<span data-ttu-id="1755e-103">实现 ICorDebugEnum 方法并枚举 ICorDebugProcess 数组。</span><span class="sxs-lookup"><span data-stu-id="1755e-103">Implements ICorDebugEnum methods and enumerates ICorDebugProcess arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1755e-104">方法</span><span class="sxs-lookup"><span data-stu-id="1755e-104">Methods</span></span>  
  
|<span data-ttu-id="1755e-105">方法</span><span class="sxs-lookup"><span data-stu-id="1755e-105">Method</span></span>|<span data-ttu-id="1755e-106">描述</span><span class="sxs-lookup"><span data-stu-id="1755e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1755e-107">Next 方法</span><span class="sxs-lookup"><span data-stu-id="1755e-107">Next Method</span></span>](icordebugprocessenum-next-method.md)|<span data-ttu-id="1755e-108">`ICorDebugProcess`从当前位置开始，从枚举中获取指定数目的实例。</span><span class="sxs-lookup"><span data-stu-id="1755e-108">Gets the specified number of `ICorDebugProcess` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1755e-109">备注</span><span class="sxs-lookup"><span data-stu-id="1755e-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1755e-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="1755e-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1755e-111">要求</span><span class="sxs-lookup"><span data-stu-id="1755e-111">Requirements</span></span>  
 <span data-ttu-id="1755e-112">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1755e-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1755e-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1755e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1755e-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1755e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1755e-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1755e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1755e-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="1755e-116">See also</span></span>

- [<span data-ttu-id="1755e-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="1755e-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
