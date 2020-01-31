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
ms.openlocfilehash: e104f8c522af2ee4cd42332b7459f4a2fd185511
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792685"
---
# <a name="icordebugobjectvalue-interface"></a><span data-ttu-id="87ab0-102">ICorDebugObjectValue 接口</span><span class="sxs-lookup"><span data-stu-id="87ab0-102">ICorDebugObjectValue Interface</span></span>

<span data-ttu-id="87ab0-103">"ICorDebugValue" 的子类，表示包含对象的值。</span><span class="sxs-lookup"><span data-stu-id="87ab0-103">A subclass of "ICorDebugValue" that represents a value that contains an object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="87ab0-104">方法</span><span class="sxs-lookup"><span data-stu-id="87ab0-104">Methods</span></span>  
  
|<span data-ttu-id="87ab0-105">方法</span><span class="sxs-lookup"><span data-stu-id="87ab0-105">Method</span></span>|<span data-ttu-id="87ab0-106">描述</span><span class="sxs-lookup"><span data-stu-id="87ab0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="87ab0-107">GetClass 方法</span><span class="sxs-lookup"><span data-stu-id="87ab0-107">GetClass Method</span></span>](icordebugobjectvalue-getclass-method.md)|<span data-ttu-id="87ab0-108">获取一个接口指针，该指针指向此 `ICorDebugObjectValue` 引用的对象的公共语言运行时（CLR） <xref:System.Type>。</span><span class="sxs-lookup"><span data-stu-id="87ab0-108">Gets an interface pointer to the common language runtime (CLR) <xref:System.Type> of the object that this `ICorDebugObjectValue` references.</span></span>|  
|[<span data-ttu-id="87ab0-109">GetContext 方法</span><span class="sxs-lookup"><span data-stu-id="87ab0-109">GetContext Method</span></span>](icordebugobjectvalue-getcontext-method.md)|<span data-ttu-id="87ab0-110">未实现。</span><span class="sxs-lookup"><span data-stu-id="87ab0-110">Not implemented.</span></span>|  
|[<span data-ttu-id="87ab0-111">GetFieldValue 方法</span><span class="sxs-lookup"><span data-stu-id="87ab0-111">GetFieldValue Method</span></span>](icordebugobjectvalue-getfieldvalue-method.md)|<span data-ttu-id="87ab0-112">获取一个指向[ICorDebugValue](icordebugvalue-interface.md)的接口指针，该指针表示指定类的指定字段的值。</span><span class="sxs-lookup"><span data-stu-id="87ab0-112">Gets an interface pointer to an [ICorDebugValue](icordebugvalue-interface.md) that represents the value of the specified field of the specified class.</span></span>|  
|[<span data-ttu-id="87ab0-113">GetManagedCopy 方法</span><span class="sxs-lookup"><span data-stu-id="87ab0-113">GetManagedCopy Method</span></span>](icordebugobjectvalue-getmanagedcopy-method.md)|<span data-ttu-id="87ab0-114">已过时。</span><span class="sxs-lookup"><span data-stu-id="87ab0-114">Obsolete.</span></span> <span data-ttu-id="87ab0-115">请勿调用此方法。</span><span class="sxs-lookup"><span data-stu-id="87ab0-115">Do not call this method.</span></span>|  
|[<span data-ttu-id="87ab0-116">GetVirtualMethod 方法</span><span class="sxs-lookup"><span data-stu-id="87ab0-116">GetVirtualMethod Method</span></span>](icordebugobjectvalue-getvirtualmethod-method.md)|<span data-ttu-id="87ab0-117">未实现。</span><span class="sxs-lookup"><span data-stu-id="87ab0-117">Not implemented.</span></span>|  
|[<span data-ttu-id="87ab0-118">IsValueClass 方法</span><span class="sxs-lookup"><span data-stu-id="87ab0-118">IsValueClass Method</span></span>](icordebugobjectvalue-isvalueclass-method.md)|<span data-ttu-id="87ab0-119">获取一个值，该值指示由此 `ICorDebugObjectValue` 引用的对象是否为值类型。</span><span class="sxs-lookup"><span data-stu-id="87ab0-119">Gets a value that indicates whether the object referenced by this `ICorDebugObjectValue` is a value type.</span></span>|  
|[<span data-ttu-id="87ab0-120">SetFromManagedCopy 方法</span><span class="sxs-lookup"><span data-stu-id="87ab0-120">SetFromManagedCopy Method</span></span>](icordebugobjectvalue-setfrommanagedcopy-method.md)|<span data-ttu-id="87ab0-121">已过时。</span><span class="sxs-lookup"><span data-stu-id="87ab0-121">Obsolete.</span></span> <span data-ttu-id="87ab0-122">请勿调用此方法。</span><span class="sxs-lookup"><span data-stu-id="87ab0-122">Do not call this method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="87ab0-123">备注</span><span class="sxs-lookup"><span data-stu-id="87ab0-123">Remarks</span></span>  
 <span data-ttu-id="87ab0-124">`ICorDebugObjectValue` 保持有效，直到正在调试的进程继续。</span><span class="sxs-lookup"><span data-stu-id="87ab0-124">An `ICorDebugObjectValue` remains valid until the process being debugged is continued.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="87ab0-125">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="87ab0-125">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87ab0-126">需求</span><span class="sxs-lookup"><span data-stu-id="87ab0-126">Requirements</span></span>  
 <span data-ttu-id="87ab0-127">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="87ab0-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87ab0-128">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="87ab0-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="87ab0-129">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="87ab0-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="87ab0-130">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87ab0-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87ab0-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="87ab0-131">See also</span></span>

- [<span data-ttu-id="87ab0-132">调试接口</span><span class="sxs-lookup"><span data-stu-id="87ab0-132">Debugging Interfaces</span></span>](debugging-interfaces.md)
