---
title: ICorDebugValue2 接口
ms.date: 03/30/2017
api_name:
- ICorDebugValue2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue2
helpviewer_keywords:
- ICorDebugValue2 interface [.NET Framework debugging]
ms.assetid: 3ff2ad2a-da5a-461b-8627-1a8eba49df9c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a2462d1de9f1b5f94f2581c1a06ca2987712fd7b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugvalue2-interface"></a><span data-ttu-id="888ef-102">ICorDebugValue2 接口</span><span class="sxs-lookup"><span data-stu-id="888ef-102">ICorDebugValue2 Interface</span></span>
<span data-ttu-id="888ef-103">扩展"ICorDebugValue"接口，若要为"ICorDebugType"对象提供支持。</span><span class="sxs-lookup"><span data-stu-id="888ef-103">Extends the "ICorDebugValue" interface to provide support for "ICorDebugType" objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="888ef-104">方法</span><span class="sxs-lookup"><span data-stu-id="888ef-104">Methods</span></span>  
  
|<span data-ttu-id="888ef-105">方法</span><span class="sxs-lookup"><span data-stu-id="888ef-105">Method</span></span>|<span data-ttu-id="888ef-106">描述</span><span class="sxs-lookup"><span data-stu-id="888ef-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="888ef-107">GetExactType 方法</span><span class="sxs-lookup"><span data-stu-id="888ef-107">GetExactType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md)|<span data-ttu-id="888ef-108">获取到的接口指针`ICorDebugType`对象，表示<xref:System.Type>的此值。</span><span class="sxs-lookup"><span data-stu-id="888ef-108">Gets an interface pointer to an `ICorDebugType` object that represents the <xref:System.Type> of this value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="888ef-109">备注</span><span class="sxs-lookup"><span data-stu-id="888ef-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="888ef-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="888ef-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="888ef-111">要求</span><span class="sxs-lookup"><span data-stu-id="888ef-111">Requirements</span></span>  
 <span data-ttu-id="888ef-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="888ef-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="888ef-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="888ef-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="888ef-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="888ef-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="888ef-115">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="888ef-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="888ef-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="888ef-116">See Also</span></span>  
 [<span data-ttu-id="888ef-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="888ef-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
    
 [<span data-ttu-id="888ef-118">ICorDebugValue3 接口</span><span class="sxs-lookup"><span data-stu-id="888ef-118">ICorDebugValue3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)
