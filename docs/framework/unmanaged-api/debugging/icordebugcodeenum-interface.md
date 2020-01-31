---
title: ICorDebugCodeEnum 接口
ms.date: 03/30/2017
api_name:
- ICorDebugCodeEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCodeEnum
helpviewer_keywords:
- ICorDebugCodeEnum interface [.NET Framework debugging]
ms.assetid: b5589171-a4a0-4c00-bbdc-6e0a42233b75
topic_type:
- apiref
ms.openlocfilehash: 127022fb8e9f9559ccb0f0c877d25db67eea3037
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784009"
---
# <a name="icordebugcodeenum-interface"></a><span data-ttu-id="efd08-102">ICorDebugCodeEnum 接口</span><span class="sxs-lookup"><span data-stu-id="efd08-102">ICorDebugCodeEnum Interface</span></span>

<span data-ttu-id="efd08-103">实现 "ICorDebugEnum" 方法，并枚举 "ICorDebugCode" 数组。</span><span class="sxs-lookup"><span data-stu-id="efd08-103">Implements "ICorDebugEnum" methods, and enumerates "ICorDebugCode" arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="efd08-104">方法</span><span class="sxs-lookup"><span data-stu-id="efd08-104">Methods</span></span>  
  
|<span data-ttu-id="efd08-105">方法</span><span class="sxs-lookup"><span data-stu-id="efd08-105">Method</span></span>|<span data-ttu-id="efd08-106">描述</span><span class="sxs-lookup"><span data-stu-id="efd08-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="efd08-107">Next 方法</span><span class="sxs-lookup"><span data-stu-id="efd08-107">Next Method</span></span>](icordebugcodeenum-next-method.md)|<span data-ttu-id="efd08-108">从当前位置开始，从枚举中获取指定数目的 `ICorDebugCode` 实例。</span><span class="sxs-lookup"><span data-stu-id="efd08-108">Gets the specified number of `ICorDebugCode` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="efd08-109">备注</span><span class="sxs-lookup"><span data-stu-id="efd08-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="efd08-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="efd08-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="efd08-111">需求</span><span class="sxs-lookup"><span data-stu-id="efd08-111">Requirements</span></span>  
 <span data-ttu-id="efd08-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="efd08-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="efd08-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="efd08-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="efd08-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="efd08-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="efd08-115">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="efd08-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efd08-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="efd08-116">See also</span></span>

- [<span data-ttu-id="efd08-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="efd08-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
