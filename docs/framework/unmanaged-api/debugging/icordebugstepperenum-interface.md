---
title: ICorDebugStepperEnum 接口
ms.date: 03/30/2017
api_name:
- ICorDebugStepperEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepperEnum
helpviewer_keywords:
- ICorDebugStepperEnum interface [.NET Framework debugging]
ms.assetid: 988718c1-1a4a-40f2-a04c-7d67e5cfe1e2
topic_type:
- apiref
ms.openlocfilehash: aa0ff0ff7c8fe32f181fb86ee5b778ea618df3b2
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791694"
---
# <a name="icordebugstepperenum-interface"></a><span data-ttu-id="04f94-102">ICorDebugStepperEnum 接口</span><span class="sxs-lookup"><span data-stu-id="04f94-102">ICorDebugStepperEnum Interface</span></span>
<span data-ttu-id="04f94-103">实现 ICorDebugEnum 方法，并枚举 ICorDebugStepper 数组。</span><span class="sxs-lookup"><span data-stu-id="04f94-103">Implements ICorDebugEnum methods, and enumerates ICorDebugStepper arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="04f94-104">方法</span><span class="sxs-lookup"><span data-stu-id="04f94-104">Methods</span></span>  
  
|<span data-ttu-id="04f94-105">方法</span><span class="sxs-lookup"><span data-stu-id="04f94-105">Method</span></span>|<span data-ttu-id="04f94-106">描述</span><span class="sxs-lookup"><span data-stu-id="04f94-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="04f94-107">Next 方法</span><span class="sxs-lookup"><span data-stu-id="04f94-107">Next Method</span></span>](icordebugstepperenum-next-method.md)|<span data-ttu-id="04f94-108">从当前位置开始，从枚举中获取指定数目的 `ICorDebugStepper` 实例。</span><span class="sxs-lookup"><span data-stu-id="04f94-108">Gets the specified number of `ICorDebugStepper` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="04f94-109">备注</span><span class="sxs-lookup"><span data-stu-id="04f94-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="04f94-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="04f94-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04f94-111">需求</span><span class="sxs-lookup"><span data-stu-id="04f94-111">Requirements</span></span>  
 <span data-ttu-id="04f94-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="04f94-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04f94-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="04f94-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="04f94-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="04f94-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="04f94-115">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04f94-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04f94-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="04f94-116">See also</span></span>

- [<span data-ttu-id="04f94-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="04f94-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
