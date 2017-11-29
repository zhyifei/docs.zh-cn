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
ms.openlocfilehash: 22fe068af577c3c3eb056acae388747f88d3f8df
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess6processstatechanged-method"></a><span data-ttu-id="0ebbb-102">ICorDebugProcess6::ProcessStateChanged 方法</span><span class="sxs-lookup"><span data-stu-id="0ebbb-102">ICorDebugProcess6::ProcessStateChanged Method</span></span>
<span data-ttu-id="0ebbb-103">通知[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)进程运行。</span><span class="sxs-lookup"><span data-stu-id="0ebbb-103">Notifies [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ebbb-104">语法</span><span class="sxs-lookup"><span data-stu-id="0ebbb-104">Syntax</span></span>  
  
```  
HRESULT ProcessStateChanged(   [in] CorDebugStateChange change);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0ebbb-105">参数</span><span class="sxs-lookup"><span data-stu-id="0ebbb-105">Parameters</span></span>  
 `change`  
 <span data-ttu-id="0ebbb-106">[in]成员[进程状态已更改](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md)枚举</span><span class="sxs-lookup"><span data-stu-id="0ebbb-106">[in] A member of the [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) enumeration</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0ebbb-107">备注</span><span class="sxs-lookup"><span data-stu-id="0ebbb-107">Remarks</span></span>  
 <span data-ttu-id="0ebbb-108">调试程序调用该方法以通知[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)进程运行。</span><span class="sxs-lookup"><span data-stu-id="0ebbb-108">The debugger calls this method to notify [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0ebbb-109">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="0ebbb-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ebbb-110">要求</span><span class="sxs-lookup"><span data-stu-id="0ebbb-110">Requirements</span></span>  
 <span data-ttu-id="0ebbb-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0ebbb-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ebbb-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0ebbb-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0ebbb-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0ebbb-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0ebbb-114">**.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ebbb-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ebbb-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0ebbb-115">See Also</span></span>  
 [<span data-ttu-id="0ebbb-116">ICorDebugProcess6 接口</span><span class="sxs-lookup"><span data-stu-id="0ebbb-116">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)  
 [<span data-ttu-id="0ebbb-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="0ebbb-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
