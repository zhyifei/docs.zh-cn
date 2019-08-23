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
ms.openlocfilehash: 0925cf217afafe57abf82cf51a77b1992bad5152
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966832"
---
# <a name="icordebugvalue2-interface"></a><span data-ttu-id="50bf6-102">ICorDebugValue2 接口</span><span class="sxs-lookup"><span data-stu-id="50bf6-102">ICorDebugValue2 Interface</span></span>
<span data-ttu-id="50bf6-103">扩展 "ICorDebugValue" 接口, 以提供对 "ICorDebugType" 对象的支持。</span><span class="sxs-lookup"><span data-stu-id="50bf6-103">Extends the "ICorDebugValue" interface to provide support for "ICorDebugType" objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="50bf6-104">方法</span><span class="sxs-lookup"><span data-stu-id="50bf6-104">Methods</span></span>  
  
|<span data-ttu-id="50bf6-105">方法</span><span class="sxs-lookup"><span data-stu-id="50bf6-105">Method</span></span>|<span data-ttu-id="50bf6-106">描述</span><span class="sxs-lookup"><span data-stu-id="50bf6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="50bf6-107">GetExactType 方法</span><span class="sxs-lookup"><span data-stu-id="50bf6-107">GetExactType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md)|<span data-ttu-id="50bf6-108">获取一个接口指针, 该`ICorDebugType`指针指向<xref:System.Type>表示此值的的对象。</span><span class="sxs-lookup"><span data-stu-id="50bf6-108">Gets an interface pointer to an `ICorDebugType` object that represents the <xref:System.Type> of this value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="50bf6-109">备注</span><span class="sxs-lookup"><span data-stu-id="50bf6-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="50bf6-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="50bf6-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50bf6-111">要求</span><span class="sxs-lookup"><span data-stu-id="50bf6-111">Requirements</span></span>  
 <span data-ttu-id="50bf6-112">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="50bf6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50bf6-113">**标头：** Cordebug.idl, Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="50bf6-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="50bf6-114">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="50bf6-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="50bf6-115">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50bf6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50bf6-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="50bf6-116">See also</span></span>

- [<span data-ttu-id="50bf6-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="50bf6-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

- [<span data-ttu-id="50bf6-118">ICorDebugValue3 接口</span><span class="sxs-lookup"><span data-stu-id="50bf6-118">ICorDebugValue3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)
