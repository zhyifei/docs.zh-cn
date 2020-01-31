---
title: ICorDebugDebugEvent::GetThread 方法
ms.date: 03/30/2017
ms.assetid: 4f2e9a2c-8369-4a07-a881-ad5422626353
ms.openlocfilehash: 0900ac2ae5bcf2141e720dad6efdf68d4fafaccc
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793536"
---
# <a name="icordebugdebugeventgetthread-method"></a><span data-ttu-id="32d00-102">ICorDebugDebugEvent::GetThread 方法</span><span class="sxs-lookup"><span data-stu-id="32d00-102">ICorDebugDebugEvent::GetThread Method</span></span>
<span data-ttu-id="32d00-103">获取发生事件的线程。</span><span class="sxs-lookup"><span data-stu-id="32d00-103">Gets the thread on which the event occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32d00-104">语法</span><span class="sxs-lookup"><span data-stu-id="32d00-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThread(  
        [out]ICorDebugThread **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="32d00-105">参数</span><span class="sxs-lookup"><span data-stu-id="32d00-105">Parameters</span></span>  
 <span data-ttu-id="32d00-106">ppThread</span><span class="sxs-lookup"><span data-stu-id="32d00-106">ppThread</span></span>  
 <span data-ttu-id="32d00-107">[输出] 指针指向代表事件发生线程的 ICorDebugThread 对象的地址。</span><span class="sxs-lookup"><span data-stu-id="32d00-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread on which the event occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="32d00-108">备注</span><span class="sxs-lookup"><span data-stu-id="32d00-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="32d00-109">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="32d00-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32d00-110">需求</span><span class="sxs-lookup"><span data-stu-id="32d00-110">Requirements</span></span>  
 <span data-ttu-id="32d00-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="32d00-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32d00-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="32d00-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="32d00-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="32d00-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="32d00-114">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32d00-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32d00-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="32d00-115">See also</span></span>

- [<span data-ttu-id="32d00-116">ICorDebugDebugEvent 接口</span><span class="sxs-lookup"><span data-stu-id="32d00-116">ICorDebugDebugEvent Interface</span></span>](icordebugdebugevent-interface.md)
- [<span data-ttu-id="32d00-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="32d00-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
