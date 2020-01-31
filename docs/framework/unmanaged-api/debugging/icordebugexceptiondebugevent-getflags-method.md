---
title: ICorDebugExceptionDebugEvent::GetFlags 方法
ms.date: 03/30/2017
ms.assetid: 73225303-8852-487e-9a0e-9f0cb95e99d9
ms.openlocfilehash: aaf137b1d851d0de86bde697c9e3a512f34d2aa9
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782922"
---
# <a name="icordebugexceptiondebugeventgetflags-method"></a><span data-ttu-id="f2ab3-102">ICorDebugExceptionDebugEvent::GetFlags 方法</span><span class="sxs-lookup"><span data-stu-id="f2ab3-102">ICorDebugExceptionDebugEvent::GetFlags Method</span></span>
<span data-ttu-id="f2ab3-103">获取指示是否可拦截异常的标志。</span><span class="sxs-lookup"><span data-stu-id="f2ab3-103">Gets a flag that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2ab3-104">语法</span><span class="sxs-lookup"><span data-stu-id="f2ab3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFlags(  
   [out] CorDebugExceptionFlags *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f2ab3-105">参数</span><span class="sxs-lookup"><span data-stu-id="f2ab3-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="f2ab3-106">弄指向[CorDebugExceptionFlags](cordebugexceptionflags-enumeration.md)值的指针，该指针指示是否可以截获异常。</span><span class="sxs-lookup"><span data-stu-id="f2ab3-106">[out] A pointer to a [CorDebugExceptionFlags](cordebugexceptionflags-enumeration.md) value that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f2ab3-107">备注</span><span class="sxs-lookup"><span data-stu-id="f2ab3-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f2ab3-108">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="f2ab3-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2ab3-109">需求</span><span class="sxs-lookup"><span data-stu-id="f2ab3-109">Requirements</span></span>  
 <span data-ttu-id="f2ab3-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f2ab3-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2ab3-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f2ab3-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f2ab3-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f2ab3-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f2ab3-113">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2ab3-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2ab3-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f2ab3-114">See also</span></span>

- [<span data-ttu-id="f2ab3-115">ICorDebugExceptionDebugEvent 接口</span><span class="sxs-lookup"><span data-stu-id="f2ab3-115">ICorDebugExceptionDebugEvent Interface</span></span>](icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="f2ab3-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="f2ab3-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
