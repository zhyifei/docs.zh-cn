---
title: ICorDebugExceptionDebugEvent::GetFlags 方法
ms.date: 03/30/2017
ms.assetid: 73225303-8852-487e-9a0e-9f0cb95e99d9
ms.openlocfilehash: 5793d939c8497ef842f614048707f69faa8ac568
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976039"
---
# <a name="icordebugexceptiondebugeventgetflags-method"></a><span data-ttu-id="93189-102">ICorDebugExceptionDebugEvent::GetFlags 方法</span><span class="sxs-lookup"><span data-stu-id="93189-102">ICorDebugExceptionDebugEvent::GetFlags Method</span></span>
<span data-ttu-id="93189-103">获取指示是否可拦截异常的标志。</span><span class="sxs-lookup"><span data-stu-id="93189-103">Gets a flag that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93189-104">语法</span><span class="sxs-lookup"><span data-stu-id="93189-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFlags(  
   [out] CorDebugExceptionFlags *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="93189-105">参数</span><span class="sxs-lookup"><span data-stu-id="93189-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="93189-106">弄指向[CorDebugExceptionFlags](cordebugexceptionflags-enumeration.md)值的指针，该指针指示是否可以截获异常。</span><span class="sxs-lookup"><span data-stu-id="93189-106">[out] A pointer to a [CorDebugExceptionFlags](cordebugexceptionflags-enumeration.md) value that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="93189-107">备注</span><span class="sxs-lookup"><span data-stu-id="93189-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="93189-108">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="93189-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93189-109">要求</span><span class="sxs-lookup"><span data-stu-id="93189-109">Requirements</span></span>  
 <span data-ttu-id="93189-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="93189-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93189-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="93189-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="93189-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="93189-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="93189-113">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93189-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93189-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="93189-114">See also</span></span>

- [<span data-ttu-id="93189-115">“ICor调试异常调试事件”接口</span><span class="sxs-lookup"><span data-stu-id="93189-115">ICorDebugExceptionDebugEvent Interface</span></span>](icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="93189-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="93189-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
