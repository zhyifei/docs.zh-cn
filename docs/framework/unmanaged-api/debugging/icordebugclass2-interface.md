---
title: "ICorDebugClass2 接口 1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugClass2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass2
helpviewer_keywords:
- ICorDebugClass2 interface [.NET Framework debugging]
ms.assetid: 5416de70-43f2-4cdf-a11f-d570759c9c0c
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5053ea14ac7a8af33319bbbb289db01dbbc86169
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugclass2-interface1"></a><span data-ttu-id="7ef18-102">ICorDebugClass2 接口 1</span><span class="sxs-lookup"><span data-stu-id="7ef18-102">ICorDebugClass2 Interface1</span></span>
<span data-ttu-id="7ef18-103">表示泛型类或具有 <xref:System.Type> 类型的方法参数的类。</span><span class="sxs-lookup"><span data-stu-id="7ef18-103">Represents a generic class or a class with a method parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="7ef18-104">此接口扩展[ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="7ef18-104">This interface extends [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7ef18-105">方法</span><span class="sxs-lookup"><span data-stu-id="7ef18-105">Methods</span></span>  
  
|<span data-ttu-id="7ef18-106">方法</span><span class="sxs-lookup"><span data-stu-id="7ef18-106">Method</span></span>|<span data-ttu-id="7ef18-107">描述</span><span class="sxs-lookup"><span data-stu-id="7ef18-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7ef18-108">GetParameterizedType 方法</span><span class="sxs-lookup"><span data-stu-id="7ef18-108">GetParameterizedType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass2-getparameterizedtype-method.md)|<span data-ttu-id="7ef18-109">获取此类的类型声明。</span><span class="sxs-lookup"><span data-stu-id="7ef18-109">Gets the type declaration for this class.</span></span>|  
|[<span data-ttu-id="7ef18-110">SetJMCStatus 方法</span><span class="sxs-lookup"><span data-stu-id="7ef18-110">SetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass2-setjmcstatus-method.md)|<span data-ttu-id="7ef18-111">对于此类的每个方法，设置一个值，该值指示方法是否是由用户定义代码。</span><span class="sxs-lookup"><span data-stu-id="7ef18-111">For each method of this class, sets a value that indicates whether the method is user-defined code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7ef18-112">备注</span><span class="sxs-lookup"><span data-stu-id="7ef18-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7ef18-113">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="7ef18-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ef18-114">惠?</span><span class="sxs-lookup"><span data-stu-id="7ef18-114">Requirements</span></span>  
 <span data-ttu-id="7ef18-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7ef18-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ef18-116">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7ef18-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7ef18-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7ef18-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7ef18-118">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ef18-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ef18-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="7ef18-119">See Also</span></span>  
 [<span data-ttu-id="7ef18-120">ICorDebugClass Interface1</span><span class="sxs-lookup"><span data-stu-id="7ef18-120">ICorDebugClass Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md)  
 [<span data-ttu-id="7ef18-121">调试接口</span><span class="sxs-lookup"><span data-stu-id="7ef18-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
