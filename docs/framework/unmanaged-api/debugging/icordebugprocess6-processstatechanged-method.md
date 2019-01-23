---
title: ICorDebugProcess6::ProcessStateChanged 方法
ms.date: 03/30/2017
ms.assetid: fb6d30d9-54f3-462b-8ebf-ce0440791ad5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bb134b7d188c2fb966b53e4520a7fb825f11e428
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54612042"
---
# <a name="icordebugprocess6processstatechanged-method"></a><span data-ttu-id="dd40c-102">ICorDebugProcess6::ProcessStateChanged 方法</span><span class="sxs-lookup"><span data-stu-id="dd40c-102">ICorDebugProcess6::ProcessStateChanged Method</span></span>
<span data-ttu-id="dd40c-103">通知[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)运行进程。</span><span class="sxs-lookup"><span data-stu-id="dd40c-103">Notifies [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd40c-104">语法</span><span class="sxs-lookup"><span data-stu-id="dd40c-104">Syntax</span></span>  
  
```  
HRESULT ProcessStateChanged(   [in] CorDebugStateChange change);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dd40c-105">参数</span><span class="sxs-lookup"><span data-stu-id="dd40c-105">Parameters</span></span>  
 `change`  
 <span data-ttu-id="dd40c-106">[in]成员[进程状态已更改](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md)枚举</span><span class="sxs-lookup"><span data-stu-id="dd40c-106">[in] A member of the [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) enumeration</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dd40c-107">备注</span><span class="sxs-lookup"><span data-stu-id="dd40c-107">Remarks</span></span>  
 <span data-ttu-id="dd40c-108">调试程序调用此方法以通知[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)运行进程。</span><span class="sxs-lookup"><span data-stu-id="dd40c-108">The debugger calls this method to notify [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dd40c-109">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="dd40c-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd40c-110">要求</span><span class="sxs-lookup"><span data-stu-id="dd40c-110">Requirements</span></span>  
 <span data-ttu-id="dd40c-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="dd40c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd40c-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dd40c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dd40c-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dd40c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dd40c-114">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd40c-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd40c-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="dd40c-115">See also</span></span>
- [<span data-ttu-id="dd40c-116">ICorDebugProcess6 接口</span><span class="sxs-lookup"><span data-stu-id="dd40c-116">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)
- [<span data-ttu-id="dd40c-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="dd40c-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
