---
title: ICorDebugDebugEvent::GetThread Method
ms.date: 03/30/2017
ms.assetid: 4f2e9a2c-8369-4a07-a881-ad5422626353
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bde1083fe232563aa6129cec79fdfc6c16c77d03
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67750017"
---
# <a name="icordebugdebugeventgetthread-method"></a><span data-ttu-id="d4423-102">ICorDebugDebugEvent::GetThread Method</span><span class="sxs-lookup"><span data-stu-id="d4423-102">ICorDebugDebugEvent::GetThread Method</span></span>
<span data-ttu-id="d4423-103">获取发生事件的线程。</span><span class="sxs-lookup"><span data-stu-id="d4423-103">Gets the thread on which the event occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4423-104">语法</span><span class="sxs-lookup"><span data-stu-id="d4423-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThread(  
        [out]ICorDebugThread **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4423-105">参数</span><span class="sxs-lookup"><span data-stu-id="d4423-105">Parameters</span></span>  
 <span data-ttu-id="d4423-106">ppThread</span><span class="sxs-lookup"><span data-stu-id="d4423-106">ppThread</span></span>  
 <span data-ttu-id="d4423-107">[out]指向一个 ICorDebugThread 对象，表示发生事件的线程的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="d4423-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread on which the event occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4423-108">备注</span><span class="sxs-lookup"><span data-stu-id="d4423-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d4423-109">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="d4423-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4423-110">要求</span><span class="sxs-lookup"><span data-stu-id="d4423-110">Requirements</span></span>  
 <span data-ttu-id="d4423-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d4423-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4423-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d4423-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d4423-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d4423-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d4423-114">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4423-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4423-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="d4423-115">See also</span></span>

- [<span data-ttu-id="d4423-116">ICorDebugDebugEvent 接口</span><span class="sxs-lookup"><span data-stu-id="d4423-116">ICorDebugDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)
- [<span data-ttu-id="d4423-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="d4423-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
