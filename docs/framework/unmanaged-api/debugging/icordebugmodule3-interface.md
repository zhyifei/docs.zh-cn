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
ms.openlocfilehash: 1d504e694810bfa1b9f3258f75e307bfb60d4ad7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54496801"
---
# <a name="icordebugmodule3-interface"></a><span data-ttu-id="ebe48-102">ICorDebugModule3 接口</span><span class="sxs-lookup"><span data-stu-id="ebe48-102">ICorDebugModule3 Interface</span></span>
<span data-ttu-id="ebe48-103">为动态模块创建符号读取器。</span><span class="sxs-lookup"><span data-stu-id="ebe48-103">Creates a symbol reader for a dynamic module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebe48-104">语法</span><span class="sxs-lookup"><span data-stu-id="ebe48-104">Syntax</span></span>  
  
```  
interface ICorDebugModule3 : IUnknown  
{  
    HRESULT CreateReaderForInMemorySymbols  
      (  
      [in] REFIID riid,  
      [out][iid_is(riid)] void **  ppObj  
      );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="ebe48-105">方法</span><span class="sxs-lookup"><span data-stu-id="ebe48-105">Methods</span></span>  
  
|<span data-ttu-id="ebe48-106">方法</span><span class="sxs-lookup"><span data-stu-id="ebe48-106">Method</span></span>|<span data-ttu-id="ebe48-107">描述</span><span class="sxs-lookup"><span data-stu-id="ebe48-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ebe48-108">ICorDebugModule3::CreateReaderForInMemorySymbols 方法</span><span class="sxs-lookup"><span data-stu-id="ebe48-108">ICorDebugModule3::CreateReaderForInMemorySymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule3-createreaderforinmemorysymbols-method.md)|<span data-ttu-id="ebe48-109">创建符号读取器 (通常[ISymUnmanagedReader 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)) 的动态模块。</span><span class="sxs-lookup"><span data-stu-id="ebe48-109">Creates a symbol reader (typically [ISymUnmanagedReader Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)) for a dynamic module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ebe48-110">备注</span><span class="sxs-lookup"><span data-stu-id="ebe48-110">Remarks</span></span>  
 <span data-ttu-id="ebe48-111">此接口进行逻辑扩展的"icor 调试模块"和"ICorDebugModule2"接口。</span><span class="sxs-lookup"><span data-stu-id="ebe48-111">This interface logically extends the "ICorDebugModule" and "ICorDebugModule2" interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ebe48-112">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="ebe48-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ebe48-113">要求</span><span class="sxs-lookup"><span data-stu-id="ebe48-113">Requirements</span></span>  
 <span data-ttu-id="ebe48-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ebe48-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ebe48-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ebe48-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ebe48-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ebe48-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ebe48-117">**.NET framework 版本：** 4.5，4，3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="ebe48-117">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ebe48-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="ebe48-118">See also</span></span>
- [<span data-ttu-id="ebe48-119">ICorDebugRemoteTarget 接口</span><span class="sxs-lookup"><span data-stu-id="ebe48-119">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)
- [<span data-ttu-id="ebe48-120">ICorDebug 接口</span><span class="sxs-lookup"><span data-stu-id="ebe48-120">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [<span data-ttu-id="ebe48-121">调试接口</span><span class="sxs-lookup"><span data-stu-id="ebe48-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
