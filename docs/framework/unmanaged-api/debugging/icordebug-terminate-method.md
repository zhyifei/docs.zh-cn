---
title: ICorDebug::Terminate 方法
ms.date: 03/30/2017
api_name:
- ICorDebug.Terminate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::Terminate
helpviewer_keywords:
- Terminate method, ICorDebug interface [.NET Framework debugging]
- ICorDebug::Terminate method [.NET Framework debugging]
ms.assetid: fffe5616-0896-4426-ab5e-21869b514883
topic_type:
- apiref
ms.openlocfilehash: 44bb98f54debb129f951cc388fea81ca0f17b20c
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895312"
---
# <a name="icordebugterminate-method"></a><span data-ttu-id="6b105-102">ICorDebug::Terminate 方法</span><span class="sxs-lookup"><span data-stu-id="6b105-102">ICorDebug::Terminate Method</span></span>
<span data-ttu-id="6b105-103">终止`ICorDebug`对象。</span><span class="sxs-lookup"><span data-stu-id="6b105-103">Terminates the `ICorDebug` object.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6b105-104">`Terminate`在为所有正在调试的进程接收到[ICorDebugManagedCallback：： ExitProcess](icordebugmanagedcallback-exitprocess-method.md)回调之前，不应调用。</span><span class="sxs-lookup"><span data-stu-id="6b105-104">`Terminate` should not be called until an [ICorDebugManagedCallback::ExitProcess](icordebugmanagedcallback-exitprocess-method.md) callback has been received for all processes being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b105-105">语法</span><span class="sxs-lookup"><span data-stu-id="6b105-105">Syntax</span></span>  
  
```cpp  
HRESULT Terminate ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="6b105-106">备注</span><span class="sxs-lookup"><span data-stu-id="6b105-106">Remarks</span></span>  
 <span data-ttu-id="6b105-107">`Terminate`当不再需要`ICorDebug`对象时，必须调用。</span><span class="sxs-lookup"><span data-stu-id="6b105-107">`Terminate` must be called when the `ICorDebug` object is no longer needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b105-108">要求</span><span class="sxs-lookup"><span data-stu-id="6b105-108">Requirements</span></span>  
 <span data-ttu-id="6b105-109">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6b105-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b105-110">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6b105-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6b105-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6b105-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6b105-112">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b105-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b105-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6b105-113">See also</span></span>

- [<span data-ttu-id="6b105-114">ICorDebug 接口</span><span class="sxs-lookup"><span data-stu-id="6b105-114">ICorDebug Interface</span></span>](icordebug-interface.md)
