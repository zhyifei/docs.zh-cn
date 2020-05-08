---
title: ICorDebugDebugEvent::GetThread Method
ms.date: 03/30/2017
ms.assetid: 4f2e9a2c-8369-4a07-a881-ad5422626353
ms.openlocfilehash: acce18517c105739417fc734b49ff004ca9546dc
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976373"
---
# <a name="icordebugdebugeventgetthread-method"></a><span data-ttu-id="20dad-102">ICorDebugDebugEvent::GetThread Method</span><span class="sxs-lookup"><span data-stu-id="20dad-102">ICorDebugDebugEvent::GetThread Method</span></span>
<span data-ttu-id="20dad-103">获取发生事件的线程。</span><span class="sxs-lookup"><span data-stu-id="20dad-103">Gets the thread on which the event occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20dad-104">语法</span><span class="sxs-lookup"><span data-stu-id="20dad-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThread(  
        [out]ICorDebugThread **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="20dad-105">参数</span><span class="sxs-lookup"><span data-stu-id="20dad-105">Parameters</span></span>  
 <span data-ttu-id="20dad-106">ppThread</span><span class="sxs-lookup"><span data-stu-id="20dad-106">ppThread</span></span>  
 <span data-ttu-id="20dad-107">[输出] 指针指向代表事件发生线程的 ICorDebugThread 对象的地址。</span><span class="sxs-lookup"><span data-stu-id="20dad-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread on which the event occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="20dad-108">备注</span><span class="sxs-lookup"><span data-stu-id="20dad-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="20dad-109">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="20dad-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20dad-110">要求</span><span class="sxs-lookup"><span data-stu-id="20dad-110">Requirements</span></span>  
 <span data-ttu-id="20dad-111">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="20dad-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20dad-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="20dad-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="20dad-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="20dad-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="20dad-114">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20dad-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20dad-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="20dad-115">See also</span></span>

- [<span data-ttu-id="20dad-116">“ICor调试调试事件”接口</span><span class="sxs-lookup"><span data-stu-id="20dad-116">ICorDebugDebugEvent Interface</span></span>](icordebugdebugevent-interface.md)
- [<span data-ttu-id="20dad-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="20dad-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
