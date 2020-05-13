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
ms.openlocfilehash: c39c047cce97db7c98f1fad403bd16d0e6a2c0fe
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379457"
---
# <a name="icordebugstepperenum-interface"></a><span data-ttu-id="8b403-102">ICorDebugStepperEnum 接口</span><span class="sxs-lookup"><span data-stu-id="8b403-102">ICorDebugStepperEnum Interface</span></span>
<span data-ttu-id="8b403-103">实现 ICorDebugEnum 方法，并枚举 ICorDebugStepper 数组。</span><span class="sxs-lookup"><span data-stu-id="8b403-103">Implements ICorDebugEnum methods, and enumerates ICorDebugStepper arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8b403-104">方法</span><span class="sxs-lookup"><span data-stu-id="8b403-104">Methods</span></span>  
  
|<span data-ttu-id="8b403-105">方法</span><span class="sxs-lookup"><span data-stu-id="8b403-105">Method</span></span>|<span data-ttu-id="8b403-106">描述</span><span class="sxs-lookup"><span data-stu-id="8b403-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8b403-107">Next 方法</span><span class="sxs-lookup"><span data-stu-id="8b403-107">Next Method</span></span>](icordebugstepperenum-next-method.md)|<span data-ttu-id="8b403-108">`ICorDebugStepper`从当前位置开始，从枚举中获取指定数目的实例。</span><span class="sxs-lookup"><span data-stu-id="8b403-108">Gets the specified number of `ICorDebugStepper` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8b403-109">备注</span><span class="sxs-lookup"><span data-stu-id="8b403-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8b403-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="8b403-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b403-111">要求</span><span class="sxs-lookup"><span data-stu-id="8b403-111">Requirements</span></span>  
 <span data-ttu-id="8b403-112">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8b403-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b403-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8b403-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8b403-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8b403-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8b403-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b403-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b403-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="8b403-116">See also</span></span>

- [<span data-ttu-id="8b403-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="8b403-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
