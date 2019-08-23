---
title: ICorDebugExceptionDebugEvent::GetFlags 方法
ms.date: 03/30/2017
ms.assetid: 73225303-8852-487e-9a0e-9f0cb95e99d9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fbe6f6a2953c3f815606e881b86a693b7a0e6ec7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69951902"
---
# <a name="icordebugexceptiondebugeventgetflags-method"></a><span data-ttu-id="60c96-102">ICorDebugExceptionDebugEvent::GetFlags 方法</span><span class="sxs-lookup"><span data-stu-id="60c96-102">ICorDebugExceptionDebugEvent::GetFlags Method</span></span>
<span data-ttu-id="60c96-103">获取指示是否可拦截异常的标志。</span><span class="sxs-lookup"><span data-stu-id="60c96-103">Gets a flag that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60c96-104">语法</span><span class="sxs-lookup"><span data-stu-id="60c96-104">Syntax</span></span>  
  
```  
HRESULT GetFlags(  
   [out] CorDebugExceptionFlags *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="60c96-105">参数</span><span class="sxs-lookup"><span data-stu-id="60c96-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="60c96-106">弄指向[CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md)值的指针, 该指针指示是否可以截获异常。</span><span class="sxs-lookup"><span data-stu-id="60c96-106">[out] A pointer to a [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) value that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="60c96-107">备注</span><span class="sxs-lookup"><span data-stu-id="60c96-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="60c96-108">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="60c96-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60c96-109">要求</span><span class="sxs-lookup"><span data-stu-id="60c96-109">Requirements</span></span>  
 <span data-ttu-id="60c96-110">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="60c96-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60c96-111">**标头：** Cordebug.idl, Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="60c96-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="60c96-112">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="60c96-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="60c96-113">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60c96-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60c96-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="60c96-114">See also</span></span>

- [<span data-ttu-id="60c96-115">ICorDebugExceptionDebugEvent 接口</span><span class="sxs-lookup"><span data-stu-id="60c96-115">ICorDebugExceptionDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="60c96-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="60c96-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
