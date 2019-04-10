---
title: ICorDebugExceptionDebugEvent::GetFlags 方法
ms.date: 03/30/2017
ms.assetid: 73225303-8852-487e-9a0e-9f0cb95e99d9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: af4c7feb7076eeac6089a3255c7832c17a43469b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59208834"
---
# <a name="icordebugexceptiondebugeventgetflags-method"></a><span data-ttu-id="b1bc8-102">ICorDebugExceptionDebugEvent::GetFlags 方法</span><span class="sxs-lookup"><span data-stu-id="b1bc8-102">ICorDebugExceptionDebugEvent::GetFlags Method</span></span>
<span data-ttu-id="b1bc8-103">获取指示是否可拦截异常的标志。</span><span class="sxs-lookup"><span data-stu-id="b1bc8-103">Gets a flag that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1bc8-104">语法</span><span class="sxs-lookup"><span data-stu-id="b1bc8-104">Syntax</span></span>  
  
```  
HRESULT GetFlags(  
   [out] CorDebugExceptionFlags *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b1bc8-105">参数</span><span class="sxs-lookup"><span data-stu-id="b1bc8-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="b1bc8-106">[out]一个指向[CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md)值，该值指示是否可拦截异常。</span><span class="sxs-lookup"><span data-stu-id="b1bc8-106">[out] A pointer to a [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) value that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b1bc8-107">备注</span><span class="sxs-lookup"><span data-stu-id="b1bc8-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b1bc8-108">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="b1bc8-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1bc8-109">要求</span><span class="sxs-lookup"><span data-stu-id="b1bc8-109">Requirements</span></span>  
 <span data-ttu-id="b1bc8-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b1bc8-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1bc8-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b1bc8-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b1bc8-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b1bc8-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="b1bc8-113">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="b1bc8-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b1bc8-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="b1bc8-114">See also</span></span>

- [<span data-ttu-id="b1bc8-115">“ICor调试异常调试事件”接口</span><span class="sxs-lookup"><span data-stu-id="b1bc8-115">ICorDebugExceptionDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="b1bc8-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="b1bc8-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
