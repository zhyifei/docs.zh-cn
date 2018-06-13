---
title: ICorDebugVariableHomeEnum 接口
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHomeEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHomeEnum
helpviewer_keywords:
- ICorDebugVariableHomeEnum interface [.NET Framework debugging]
ms.assetid: c312ae6d-c8dc-48d6-9f1e-ead515c88fdf
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a80a334d1b586aec30c6cf2715d7fb841bc76929
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423255"
---
# <a name="icordebugvariablehomeenum-interface"></a><span data-ttu-id="f1165-102">ICorDebugVariableHomeEnum 接口</span><span class="sxs-lookup"><span data-stu-id="f1165-102">ICorDebugVariableHomeEnum Interface</span></span>
<span data-ttu-id="f1165-103">提供对本地变量和函数中的参数的枚举器。</span><span class="sxs-lookup"><span data-stu-id="f1165-103">Provides an enumerator to the local variables and arguments in a function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f1165-104">方法</span><span class="sxs-lookup"><span data-stu-id="f1165-104">Methods</span></span>  
  
|<span data-ttu-id="f1165-105">方法</span><span class="sxs-lookup"><span data-stu-id="f1165-105">Method</span></span>|<span data-ttu-id="f1165-106">描述</span><span class="sxs-lookup"><span data-stu-id="f1165-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f1165-107">Next 方法</span><span class="sxs-lookup"><span data-stu-id="f1165-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md)|<span data-ttu-id="f1165-108">获取指定的数目的[ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)包含有关本地变量和函数中的自变量的信息的实例。</span><span class="sxs-lookup"><span data-stu-id="f1165-108">Gets the specified number of [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instances that contain information about the local variables and arguments in a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f1165-109">备注</span><span class="sxs-lookup"><span data-stu-id="f1165-109">Remarks</span></span>  
 <span data-ttu-id="f1165-110">`ICorDebugVariableHomeEnum`接口实现 ICorDebugEnum 接口。</span><span class="sxs-lookup"><span data-stu-id="f1165-110">The `ICorDebugVariableHomeEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="f1165-111">`ICorDebugVariableHomeEnum`实例填入[ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)实例通过调用[ICorDebugCode4::EnumerateVariableHomes](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-enumeratevariablehomes-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="f1165-111">An `ICorDebugVariableHomeEnum` instance is populated with [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instances by calling the [ICorDebugCode4::EnumerateVariableHomes](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-enumeratevariablehomes-method.md) method.</span></span> <span data-ttu-id="f1165-112">每个[ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)集合中的实例表示的本地变量或函数中的参数。</span><span class="sxs-lookup"><span data-stu-id="f1165-112">Each [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instance in the collection represents a local variable or argument in a function.</span></span> <span data-ttu-id="f1165-113">[ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)集合中的对象可以通过调用枚举[ICorDebugVariableHomeEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="f1165-113">The  [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) objects in the collection can be enumerated by calling the [ICorDebugVariableHomeEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1165-114">要求</span><span class="sxs-lookup"><span data-stu-id="f1165-114">Requirements</span></span>  
 <span data-ttu-id="f1165-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f1165-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1165-116">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f1165-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f1165-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1165-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1165-118">**.NET framework 版本：** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1165-118">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1165-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="f1165-119">See Also</span></span>  
 [<span data-ttu-id="f1165-120">ICorDebugVariableHome 接口</span><span class="sxs-lookup"><span data-stu-id="f1165-120">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)  
 [<span data-ttu-id="f1165-121">调试接口</span><span class="sxs-lookup"><span data-stu-id="f1165-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
