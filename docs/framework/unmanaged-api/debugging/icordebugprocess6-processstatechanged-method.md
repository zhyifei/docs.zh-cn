---
title: ICorDebugProcess6::ProcessStateChanged 方法
ms.date: 03/30/2017
ms.assetid: fb6d30d9-54f3-462b-8ebf-ce0440791ad5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bc5861762242412d7ab6f0c02f2b8f5c149f9453
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420174"
---
# <a name="icordebugprocess6processstatechanged-method"></a><span data-ttu-id="d2b5a-102">ICorDebugProcess6::ProcessStateChanged 方法</span><span class="sxs-lookup"><span data-stu-id="d2b5a-102">ICorDebugProcess6::ProcessStateChanged Method</span></span>
<span data-ttu-id="d2b5a-103">通知[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)进程运行。</span><span class="sxs-lookup"><span data-stu-id="d2b5a-103">Notifies [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2b5a-104">语法</span><span class="sxs-lookup"><span data-stu-id="d2b5a-104">Syntax</span></span>  
  
```  
HRESULT ProcessStateChanged(   [in] CorDebugStateChange change);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d2b5a-105">参数</span><span class="sxs-lookup"><span data-stu-id="d2b5a-105">Parameters</span></span>  
 `change`  
 <span data-ttu-id="d2b5a-106">[in]成员[进程状态已更改](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md)枚举</span><span class="sxs-lookup"><span data-stu-id="d2b5a-106">[in] A member of the [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) enumeration</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d2b5a-107">备注</span><span class="sxs-lookup"><span data-stu-id="d2b5a-107">Remarks</span></span>  
 <span data-ttu-id="d2b5a-108">调试程序调用该方法以通知[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)进程运行。</span><span class="sxs-lookup"><span data-stu-id="d2b5a-108">The debugger calls this method to notify [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d2b5a-109">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="d2b5a-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2b5a-110">要求</span><span class="sxs-lookup"><span data-stu-id="d2b5a-110">Requirements</span></span>  
 <span data-ttu-id="d2b5a-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d2b5a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2b5a-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d2b5a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d2b5a-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d2b5a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d2b5a-114">**.NET framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2b5a-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2b5a-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="d2b5a-115">See Also</span></span>  
 [<span data-ttu-id="d2b5a-116">ICorDebugProcess6 接口</span><span class="sxs-lookup"><span data-stu-id="d2b5a-116">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)  
 [<span data-ttu-id="d2b5a-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="d2b5a-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
