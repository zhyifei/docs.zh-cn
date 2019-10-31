---
title: ICorDebugProcess6::ProcessStateChanged 方法
ms.date: 03/30/2017
ms.assetid: fb6d30d9-54f3-462b-8ebf-ce0440791ad5
ms.openlocfilehash: 3927e57883ebe282b262cb03ececc3b2cd96fd46
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123420"
---
# <a name="icordebugprocess6processstatechanged-method"></a><span data-ttu-id="111c0-102">ICorDebugProcess6::ProcessStateChanged 方法</span><span class="sxs-lookup"><span data-stu-id="111c0-102">ICorDebugProcess6::ProcessStateChanged Method</span></span>
<span data-ttu-id="111c0-103">通知[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)进程正在运行。</span><span class="sxs-lookup"><span data-stu-id="111c0-103">Notifies [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="111c0-104">语法</span><span class="sxs-lookup"><span data-stu-id="111c0-104">Syntax</span></span>  
  
```cpp  
HRESULT ProcessStateChanged(   [in] CorDebugStateChange change);  
```  
  
## <a name="parameters"></a><span data-ttu-id="111c0-105">参数</span><span class="sxs-lookup"><span data-stu-id="111c0-105">Parameters</span></span>  
 `change`  
 <span data-ttu-id="111c0-106">中[ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md)枚举的成员</span><span class="sxs-lookup"><span data-stu-id="111c0-106">[in] A member of the [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) enumeration</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="111c0-107">备注</span><span class="sxs-lookup"><span data-stu-id="111c0-107">Remarks</span></span>  
 <span data-ttu-id="111c0-108">调试器调用此方法来通知[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)进程正在运行。</span><span class="sxs-lookup"><span data-stu-id="111c0-108">The debugger calls this method to notify [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="111c0-109">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="111c0-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="111c0-110">要求</span><span class="sxs-lookup"><span data-stu-id="111c0-110">Requirements</span></span>  
 <span data-ttu-id="111c0-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="111c0-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="111c0-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="111c0-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="111c0-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="111c0-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="111c0-114">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="111c0-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="111c0-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="111c0-115">See also</span></span>

- [<span data-ttu-id="111c0-116">ICorDebugProcess6 接口</span><span class="sxs-lookup"><span data-stu-id="111c0-116">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)
- [<span data-ttu-id="111c0-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="111c0-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
