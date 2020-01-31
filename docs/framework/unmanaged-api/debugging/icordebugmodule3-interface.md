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
ms.openlocfilehash: 33acc4d9a0819c43d17c362fcbea2e7636521fd3
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792938"
---
# <a name="icordebugmodule3-interface"></a><span data-ttu-id="a9e0f-102">ICorDebugModule3 接口</span><span class="sxs-lookup"><span data-stu-id="a9e0f-102">ICorDebugModule3 Interface</span></span>
<span data-ttu-id="a9e0f-103">为动态模块创建符号读取器。</span><span class="sxs-lookup"><span data-stu-id="a9e0f-103">Creates a symbol reader for a dynamic module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9e0f-104">语法</span><span class="sxs-lookup"><span data-stu-id="a9e0f-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="a9e0f-105">方法</span><span class="sxs-lookup"><span data-stu-id="a9e0f-105">Methods</span></span>  
  
|<span data-ttu-id="a9e0f-106">方法</span><span class="sxs-lookup"><span data-stu-id="a9e0f-106">Method</span></span>|<span data-ttu-id="a9e0f-107">描述</span><span class="sxs-lookup"><span data-stu-id="a9e0f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a9e0f-108">ICorDebugModule3::CreateReaderForInMemorySymbols 方法</span><span class="sxs-lookup"><span data-stu-id="a9e0f-108">ICorDebugModule3::CreateReaderForInMemorySymbols Method</span></span>](icordebugmodule3-createreaderforinmemorysymbols-method.md)|<span data-ttu-id="a9e0f-109">为动态模块创建符号读取器（通常为[ISymUnmanagedReader 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)）。</span><span class="sxs-lookup"><span data-stu-id="a9e0f-109">Creates a symbol reader (typically [ISymUnmanagedReader Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)) for a dynamic module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a9e0f-110">备注</span><span class="sxs-lookup"><span data-stu-id="a9e0f-110">Remarks</span></span>  
 <span data-ttu-id="a9e0f-111">此接口以逻辑方式扩展了 "ICorDebugModule" 和 "ICorDebugModule2" 接口。</span><span class="sxs-lookup"><span data-stu-id="a9e0f-111">This interface logically extends the "ICorDebugModule" and "ICorDebugModule2" interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a9e0f-112">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="a9e0f-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9e0f-113">需求</span><span class="sxs-lookup"><span data-stu-id="a9e0f-113">Requirements</span></span>  
 <span data-ttu-id="a9e0f-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a9e0f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9e0f-115">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a9e0f-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a9e0f-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a9e0f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a9e0f-117">**.NET Framework 版本：** 4.5、4、3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="a9e0f-117">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a9e0f-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a9e0f-118">See also</span></span>

- [<span data-ttu-id="a9e0f-119">ICorDebugRemoteTarget 接口</span><span class="sxs-lookup"><span data-stu-id="a9e0f-119">ICorDebugRemoteTarget Interface</span></span>](icordebugremotetarget-interface.md)
- [<span data-ttu-id="a9e0f-120">ICorDebug 接口</span><span class="sxs-lookup"><span data-stu-id="a9e0f-120">ICorDebug Interface</span></span>](icordebug-interface.md)

- [<span data-ttu-id="a9e0f-121">调试接口</span><span class="sxs-lookup"><span data-stu-id="a9e0f-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
