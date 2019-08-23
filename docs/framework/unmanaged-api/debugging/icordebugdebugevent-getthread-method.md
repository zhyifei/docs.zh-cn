---
title: ICorDebugDebugEvent::GetThread Method
ms.date: 03/30/2017
ms.assetid: 4f2e9a2c-8369-4a07-a881-ad5422626353
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4f85dccd5b59610c52adcf685828984c9344fd49
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69911287"
---
# <a name="icordebugdebugeventgetthread-method"></a><span data-ttu-id="babdc-102">ICorDebugDebugEvent::GetThread Method</span><span class="sxs-lookup"><span data-stu-id="babdc-102">ICorDebugDebugEvent::GetThread Method</span></span>
<span data-ttu-id="babdc-103">获取发生事件的线程。</span><span class="sxs-lookup"><span data-stu-id="babdc-103">Gets the thread on which the event occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="babdc-104">语法</span><span class="sxs-lookup"><span data-stu-id="babdc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThread(  
        [out]ICorDebugThread **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="babdc-105">参数</span><span class="sxs-lookup"><span data-stu-id="babdc-105">Parameters</span></span>  
 <span data-ttu-id="babdc-106">ppThread</span><span class="sxs-lookup"><span data-stu-id="babdc-106">ppThread</span></span>  
 <span data-ttu-id="babdc-107">弄指向 ICorDebugThread 对象的地址的指针, 该对象表示发生事件的线程。</span><span class="sxs-lookup"><span data-stu-id="babdc-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread on which the event occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="babdc-108">备注</span><span class="sxs-lookup"><span data-stu-id="babdc-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="babdc-109">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="babdc-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="babdc-110">要求</span><span class="sxs-lookup"><span data-stu-id="babdc-110">Requirements</span></span>  
 <span data-ttu-id="babdc-111">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="babdc-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="babdc-112">**标头：** Cordebug.idl, Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="babdc-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="babdc-113">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="babdc-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="babdc-114">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="babdc-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="babdc-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="babdc-115">See also</span></span>

- [<span data-ttu-id="babdc-116">ICorDebugDebugEvent 接口</span><span class="sxs-lookup"><span data-stu-id="babdc-116">ICorDebugDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)
- [<span data-ttu-id="babdc-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="babdc-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
