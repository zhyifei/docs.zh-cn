---
title: ICorDebugModule3 接口
ms.date: 03/30/2017
api_name:
- ICorDebugModule3
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule3
helpviewer_keywords:
- ICorDebugModule3 interface [.NET Framework debugging]
ms.assetid: 0b69f945-263a-4e11-8512-89d27f6ea296
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e51ff64115ce3417087eee6845aa802ad64f2a72
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960994"
---
# <a name="icordebugmodule3-interface"></a><span data-ttu-id="e54ab-102">ICorDebugModule3 接口</span><span class="sxs-lookup"><span data-stu-id="e54ab-102">ICorDebugModule3 Interface</span></span>
<span data-ttu-id="e54ab-103">为动态模块创建符号读取器。</span><span class="sxs-lookup"><span data-stu-id="e54ab-103">Creates a symbol reader for a dynamic module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e54ab-104">语法</span><span class="sxs-lookup"><span data-stu-id="e54ab-104">Syntax</span></span>  
  
```cpp  
interface ICorDebugModule3 : IUnknown  
{  
    HRESULT CreateReaderForInMemorySymbols  
      (  
      [in] REFIID riid,  
      [out][iid_is(riid)] void **  ppObj  
      );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="e54ab-105">方法</span><span class="sxs-lookup"><span data-stu-id="e54ab-105">Methods</span></span>  
  
|<span data-ttu-id="e54ab-106">方法</span><span class="sxs-lookup"><span data-stu-id="e54ab-106">Method</span></span>|<span data-ttu-id="e54ab-107">描述</span><span class="sxs-lookup"><span data-stu-id="e54ab-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e54ab-108">ICorDebugModule3::CreateReaderForInMemorySymbols 方法</span><span class="sxs-lookup"><span data-stu-id="e54ab-108">ICorDebugModule3::CreateReaderForInMemorySymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule3-createreaderforinmemorysymbols-method.md)|<span data-ttu-id="e54ab-109">为动态模块创建符号读取器 (通常为[ISymUnmanagedReader 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md))。</span><span class="sxs-lookup"><span data-stu-id="e54ab-109">Creates a symbol reader (typically [ISymUnmanagedReader Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)) for a dynamic module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e54ab-110">备注</span><span class="sxs-lookup"><span data-stu-id="e54ab-110">Remarks</span></span>  
 <span data-ttu-id="e54ab-111">此接口以逻辑方式扩展了 "ICorDebugModule" 和 "ICorDebugModule2" 接口。</span><span class="sxs-lookup"><span data-stu-id="e54ab-111">This interface logically extends the "ICorDebugModule" and "ICorDebugModule2" interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e54ab-112">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="e54ab-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e54ab-113">要求</span><span class="sxs-lookup"><span data-stu-id="e54ab-113">Requirements</span></span>  
 <span data-ttu-id="e54ab-114">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e54ab-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e54ab-115">**标头：** Cordebug.idl, Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="e54ab-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e54ab-116">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e54ab-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e54ab-117">**.NET Framework 版本:** 4.5, 4, 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="e54ab-117">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e54ab-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="e54ab-118">See also</span></span>

- [<span data-ttu-id="e54ab-119">ICorDebugRemoteTarget 接口</span><span class="sxs-lookup"><span data-stu-id="e54ab-119">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)
- [<span data-ttu-id="e54ab-120">ICorDebug 接口</span><span class="sxs-lookup"><span data-stu-id="e54ab-120">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [<span data-ttu-id="e54ab-121">调试接口</span><span class="sxs-lookup"><span data-stu-id="e54ab-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
