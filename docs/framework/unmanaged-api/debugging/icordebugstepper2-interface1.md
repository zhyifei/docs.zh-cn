---
title: ICorDebugStepper2 接口
ms.date: 03/30/2017
api_name:
- ICorDebugStepper2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper2
helpviewer_keywords:
- ICorDebugStepper2 interface [.NET Framework debugging]
ms.assetid: 7a191c2a-95ea-4d47-83b0-44de2b632d63
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 256f67d21a22ee4692d88311cc150736e61563a0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59073042"
---
# <a name="icordebugstepper2-interface"></a><span data-ttu-id="8bed1-102">ICorDebugStepper2 接口</span><span class="sxs-lookup"><span data-stu-id="8bed1-102">ICorDebugStepper2 Interface</span></span>
<span data-ttu-id="8bed1-103">仅我的代码 (JMC) 调试提供支持。</span><span class="sxs-lookup"><span data-stu-id="8bed1-103">Provides support for just my code (JMC) debugging.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8bed1-104">方法</span><span class="sxs-lookup"><span data-stu-id="8bed1-104">Methods</span></span>  
  
|<span data-ttu-id="8bed1-105">方法</span><span class="sxs-lookup"><span data-stu-id="8bed1-105">Method</span></span>|<span data-ttu-id="8bed1-106">描述</span><span class="sxs-lookup"><span data-stu-id="8bed1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8bed1-107">SetJMC 方法</span><span class="sxs-lookup"><span data-stu-id="8bed1-107">SetJMC Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper2-setjmc-method.md)|<span data-ttu-id="8bed1-108">设置一个值，指定是否有此 ICorDebugStepper 步骤只能通过由应用程序的开发人员编写的代码。</span><span class="sxs-lookup"><span data-stu-id="8bed1-108">Sets a value that specifies whether this ICorDebugStepper steps only through code that is authored by an application's developer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8bed1-109">备注</span><span class="sxs-lookup"><span data-stu-id="8bed1-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8bed1-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="8bed1-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8bed1-111">要求</span><span class="sxs-lookup"><span data-stu-id="8bed1-111">Requirements</span></span>  
 <span data-ttu-id="8bed1-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8bed1-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8bed1-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8bed1-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8bed1-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8bed1-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8bed1-115">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8bed1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bed1-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="8bed1-116">See also</span></span>

- [<span data-ttu-id="8bed1-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="8bed1-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
