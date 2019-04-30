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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d0ac91681313b60ebfcaf725dcc2e0d6547e3c1b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61987813"
---
# <a name="icordebugobjectvalue-interface"></a><span data-ttu-id="cdcbc-102">ICorDebugObjectValue 接口</span><span class="sxs-lookup"><span data-stu-id="cdcbc-102">ICorDebugObjectValue Interface</span></span>

<span data-ttu-id="cdcbc-103">表示一个包含对象的值的"ICorDebugValue"的子类。</span><span class="sxs-lookup"><span data-stu-id="cdcbc-103">A subclass of "ICorDebugValue" that represents a value that contains an object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cdcbc-104">方法</span><span class="sxs-lookup"><span data-stu-id="cdcbc-104">Methods</span></span>  
  
|<span data-ttu-id="cdcbc-105">方法</span><span class="sxs-lookup"><span data-stu-id="cdcbc-105">Method</span></span>|<span data-ttu-id="cdcbc-106">描述</span><span class="sxs-lookup"><span data-stu-id="cdcbc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cdcbc-107">GetClass 方法</span><span class="sxs-lookup"><span data-stu-id="cdcbc-107">GetClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md)|<span data-ttu-id="cdcbc-108">公共语言运行时 (CLR) 中获取的接口指针<xref:System.Type>对象的此`ICorDebugObjectValue`的引用。</span><span class="sxs-lookup"><span data-stu-id="cdcbc-108">Gets an interface pointer to the common language runtime (CLR) <xref:System.Type> of the object that this `ICorDebugObjectValue` references.</span></span>|  
|[<span data-ttu-id="cdcbc-109">GetContext 方法</span><span class="sxs-lookup"><span data-stu-id="cdcbc-109">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getcontext-method.md)|<span data-ttu-id="cdcbc-110">未实现。</span><span class="sxs-lookup"><span data-stu-id="cdcbc-110">Not implemented.</span></span>|  
|[<span data-ttu-id="cdcbc-111">GetFieldValue 方法</span><span class="sxs-lookup"><span data-stu-id="cdcbc-111">GetFieldValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getfieldvalue-method.md)|<span data-ttu-id="cdcbc-112">获取到的接口指针[ICorDebugValue](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-interface.md) ，表示指定类的指定字段的值。</span><span class="sxs-lookup"><span data-stu-id="cdcbc-112">Gets an interface pointer to an [ICorDebugValue](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-interface.md) that represents the value of the specified field of the specified class.</span></span>|  
|[<span data-ttu-id="cdcbc-113">GetManagedCopy 方法</span><span class="sxs-lookup"><span data-stu-id="cdcbc-113">GetManagedCopy Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getmanagedcopy-method.md)|<span data-ttu-id="cdcbc-114">已过时。</span><span class="sxs-lookup"><span data-stu-id="cdcbc-114">Obsolete.</span></span> <span data-ttu-id="cdcbc-115">请勿调用此方法。</span><span class="sxs-lookup"><span data-stu-id="cdcbc-115">Do not call this method.</span></span>|  
|[<span data-ttu-id="cdcbc-116">GetVirtualMethod 方法</span><span class="sxs-lookup"><span data-stu-id="cdcbc-116">GetVirtualMethod Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getvirtualmethod-method.md)|<span data-ttu-id="cdcbc-117">未实现。</span><span class="sxs-lookup"><span data-stu-id="cdcbc-117">Not implemented.</span></span>|  
|[<span data-ttu-id="cdcbc-118">IsValueClass 方法</span><span class="sxs-lookup"><span data-stu-id="cdcbc-118">IsValueClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-isvalueclass-method.md)|<span data-ttu-id="cdcbc-119">获取一个值，指示对象是否引用此`ICorDebugObjectValue`是值类型。</span><span class="sxs-lookup"><span data-stu-id="cdcbc-119">Gets a value that indicates whether the object referenced by this `ICorDebugObjectValue` is a value type.</span></span>|  
|[<span data-ttu-id="cdcbc-120">SetFromManagedCopy 方法</span><span class="sxs-lookup"><span data-stu-id="cdcbc-120">SetFromManagedCopy Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-setfrommanagedcopy-method.md)|<span data-ttu-id="cdcbc-121">已过时。</span><span class="sxs-lookup"><span data-stu-id="cdcbc-121">Obsolete.</span></span> <span data-ttu-id="cdcbc-122">请勿调用此方法。</span><span class="sxs-lookup"><span data-stu-id="cdcbc-122">Do not call this method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cdcbc-123">备注</span><span class="sxs-lookup"><span data-stu-id="cdcbc-123">Remarks</span></span>  
 <span data-ttu-id="cdcbc-124">`ICorDebugObjectValue`正在调试的进程继续执行之前一直有效。</span><span class="sxs-lookup"><span data-stu-id="cdcbc-124">An `ICorDebugObjectValue` remains valid until the process being debugged is continued.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cdcbc-125">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="cdcbc-125">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cdcbc-126">要求</span><span class="sxs-lookup"><span data-stu-id="cdcbc-126">Requirements</span></span>  
 <span data-ttu-id="cdcbc-127">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cdcbc-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cdcbc-128">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cdcbc-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cdcbc-129">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cdcbc-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cdcbc-130">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cdcbc-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdcbc-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="cdcbc-131">See also</span></span>

- [<span data-ttu-id="cdcbc-132">调试接口</span><span class="sxs-lookup"><span data-stu-id="cdcbc-132">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
