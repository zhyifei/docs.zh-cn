---
title: ICorDebugObjectValue 接口
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue
helpviewer_keywords:
- ICorDebugObjectValue interface [.NET Framework debugging]
ms.assetid: 937de6a0-6fbf-4ddc-80ea-a6217b73e62b
topic_type:
- apiref
ms.openlocfilehash: b782207503a2c3f739a30f68d509e6b481d2b6a4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129755"
---
# <a name="icordebugobjectvalue-interface"></a><span data-ttu-id="86983-102">ICorDebugObjectValue 接口</span><span class="sxs-lookup"><span data-stu-id="86983-102">ICorDebugObjectValue Interface</span></span>

<span data-ttu-id="86983-103">"ICorDebugValue" 的子类，表示包含对象的值。</span><span class="sxs-lookup"><span data-stu-id="86983-103">A subclass of "ICorDebugValue" that represents a value that contains an object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="86983-104">方法</span><span class="sxs-lookup"><span data-stu-id="86983-104">Methods</span></span>  
  
|<span data-ttu-id="86983-105">方法</span><span class="sxs-lookup"><span data-stu-id="86983-105">Method</span></span>|<span data-ttu-id="86983-106">描述</span><span class="sxs-lookup"><span data-stu-id="86983-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="86983-107">GetClass 方法</span><span class="sxs-lookup"><span data-stu-id="86983-107">GetClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md)|<span data-ttu-id="86983-108">获取一个接口指针，该指针指向此 `ICorDebugObjectValue` 引用的对象的公共语言运行时（CLR） <xref:System.Type>。</span><span class="sxs-lookup"><span data-stu-id="86983-108">Gets an interface pointer to the common language runtime (CLR) <xref:System.Type> of the object that this `ICorDebugObjectValue` references.</span></span>|  
|[<span data-ttu-id="86983-109">GetContext 方法</span><span class="sxs-lookup"><span data-stu-id="86983-109">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getcontext-method.md)|<span data-ttu-id="86983-110">未实现。</span><span class="sxs-lookup"><span data-stu-id="86983-110">Not implemented.</span></span>|  
|[<span data-ttu-id="86983-111">GetFieldValue 方法</span><span class="sxs-lookup"><span data-stu-id="86983-111">GetFieldValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getfieldvalue-method.md)|<span data-ttu-id="86983-112">获取一个指向[ICorDebugValue](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-interface.md)的接口指针，该指针表示指定类的指定字段的值。</span><span class="sxs-lookup"><span data-stu-id="86983-112">Gets an interface pointer to an [ICorDebugValue](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-interface.md) that represents the value of the specified field of the specified class.</span></span>|  
|[<span data-ttu-id="86983-113">GetManagedCopy 方法</span><span class="sxs-lookup"><span data-stu-id="86983-113">GetManagedCopy Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getmanagedcopy-method.md)|<span data-ttu-id="86983-114">已过时。</span><span class="sxs-lookup"><span data-stu-id="86983-114">Obsolete.</span></span> <span data-ttu-id="86983-115">请勿调用此方法。</span><span class="sxs-lookup"><span data-stu-id="86983-115">Do not call this method.</span></span>|  
|[<span data-ttu-id="86983-116">GetVirtualMethod 方法</span><span class="sxs-lookup"><span data-stu-id="86983-116">GetVirtualMethod Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getvirtualmethod-method.md)|<span data-ttu-id="86983-117">未实现。</span><span class="sxs-lookup"><span data-stu-id="86983-117">Not implemented.</span></span>|  
|[<span data-ttu-id="86983-118">IsValueClass 方法</span><span class="sxs-lookup"><span data-stu-id="86983-118">IsValueClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-isvalueclass-method.md)|<span data-ttu-id="86983-119">获取一个值，该值指示由此 `ICorDebugObjectValue` 引用的对象是否为值类型。</span><span class="sxs-lookup"><span data-stu-id="86983-119">Gets a value that indicates whether the object referenced by this `ICorDebugObjectValue` is a value type.</span></span>|  
|[<span data-ttu-id="86983-120">SetFromManagedCopy 方法</span><span class="sxs-lookup"><span data-stu-id="86983-120">SetFromManagedCopy Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-setfrommanagedcopy-method.md)|<span data-ttu-id="86983-121">已过时。</span><span class="sxs-lookup"><span data-stu-id="86983-121">Obsolete.</span></span> <span data-ttu-id="86983-122">请勿调用此方法。</span><span class="sxs-lookup"><span data-stu-id="86983-122">Do not call this method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="86983-123">备注</span><span class="sxs-lookup"><span data-stu-id="86983-123">Remarks</span></span>  
 <span data-ttu-id="86983-124">`ICorDebugObjectValue` 保持有效，直到正在调试的进程继续。</span><span class="sxs-lookup"><span data-stu-id="86983-124">An `ICorDebugObjectValue` remains valid until the process being debugged is continued.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="86983-125">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="86983-125">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86983-126">要求</span><span class="sxs-lookup"><span data-stu-id="86983-126">Requirements</span></span>  
 <span data-ttu-id="86983-127">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="86983-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86983-128">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="86983-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="86983-129">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="86983-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="86983-130">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86983-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86983-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="86983-131">See also</span></span>

- [<span data-ttu-id="86983-132">调试接口</span><span class="sxs-lookup"><span data-stu-id="86983-132">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
