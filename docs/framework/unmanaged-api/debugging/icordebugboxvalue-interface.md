---
title: ICorDebugBoxValue 接口
ms.date: 03/30/2017
api_name:
- ICorDebugBoxValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBoxValue
helpviewer_keywords:
- ICorDebugBoxValue interface [.NET Framework debugging]
ms.assetid: 3d3ae7e2-97d4-46de-a2c3-cb78f3490f9d
topic_type:
- apiref
ms.openlocfilehash: a40e12655106cca01add065c2f95384b0eb1a286
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122814"
---
# <a name="icordebugboxvalue-interface"></a><span data-ttu-id="a5425-102">ICorDebugBoxValue 接口</span><span class="sxs-lookup"><span data-stu-id="a5425-102">ICorDebugBoxValue Interface</span></span>

<span data-ttu-id="a5425-103">表示装箱值类对象的 "ICorDebugHeapValue" 的子类。</span><span class="sxs-lookup"><span data-stu-id="a5425-103">A subclass of "ICorDebugHeapValue" that represents a boxed value class object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a5425-104">方法</span><span class="sxs-lookup"><span data-stu-id="a5425-104">Methods</span></span>  
  
|<span data-ttu-id="a5425-105">方法</span><span class="sxs-lookup"><span data-stu-id="a5425-105">Method</span></span>|<span data-ttu-id="a5425-106">描述</span><span class="sxs-lookup"><span data-stu-id="a5425-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a5425-107">GetObject 方法</span><span class="sxs-lookup"><span data-stu-id="a5425-107">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugboxvalue-getobject-method.md)|<span data-ttu-id="a5425-108">获取指向装箱的 "ICorDebugObjectValue" 实例的接口指针。</span><span class="sxs-lookup"><span data-stu-id="a5425-108">Gets an interface pointer to the boxed "ICorDebugObjectValue" instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a5425-109">备注</span><span class="sxs-lookup"><span data-stu-id="a5425-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a5425-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="a5425-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5425-111">要求</span><span class="sxs-lookup"><span data-stu-id="a5425-111">Requirements</span></span>  
 <span data-ttu-id="a5425-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a5425-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5425-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a5425-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a5425-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a5425-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a5425-115">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5425-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5425-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="a5425-116">See also</span></span>

- [<span data-ttu-id="a5425-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="a5425-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
