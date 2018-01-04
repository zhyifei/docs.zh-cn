---
title: "ICorDebugProcess6::ProcessStateChanged 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: fb6d30d9-54f3-462b-8ebf-ce0440791ad5
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9e5aad3e95668525fe607bf4e90b4e05b2b58cad
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess6processstatechanged-method"></a><span data-ttu-id="e78a4-102">ICorDebugProcess6::ProcessStateChanged 方法</span><span class="sxs-lookup"><span data-stu-id="e78a4-102">ICorDebugProcess6::ProcessStateChanged Method</span></span>
<span data-ttu-id="e78a4-103">通知[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)进程运行。</span><span class="sxs-lookup"><span data-stu-id="e78a4-103">Notifies [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e78a4-104">语法</span><span class="sxs-lookup"><span data-stu-id="e78a4-104">Syntax</span></span>  
  
```  
HRESULT ProcessStateChanged(   [in] CorDebugStateChange change);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e78a4-105">参数</span><span class="sxs-lookup"><span data-stu-id="e78a4-105">Parameters</span></span>  
 `change`  
 <span data-ttu-id="e78a4-106">[in]成员[进程状态已更改](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md)枚举</span><span class="sxs-lookup"><span data-stu-id="e78a4-106">[in] A member of the [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) enumeration</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e78a4-107">备注</span><span class="sxs-lookup"><span data-stu-id="e78a4-107">Remarks</span></span>  
 <span data-ttu-id="e78a4-108">调试程序调用该方法以通知[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)进程运行。</span><span class="sxs-lookup"><span data-stu-id="e78a4-108">The debugger calls this method to notify [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e78a4-109">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="e78a4-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e78a4-110">惠?</span><span class="sxs-lookup"><span data-stu-id="e78a4-110">Requirements</span></span>  
 <span data-ttu-id="e78a4-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e78a4-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e78a4-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e78a4-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e78a4-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e78a4-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e78a4-114">**.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e78a4-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e78a4-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="e78a4-115">See Also</span></span>  
 [<span data-ttu-id="e78a4-116">ICorDebugProcess6 接口</span><span class="sxs-lookup"><span data-stu-id="e78a4-116">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)  
 [<span data-ttu-id="e78a4-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="e78a4-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
