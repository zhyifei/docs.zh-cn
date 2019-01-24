---
title: ICorDebugAppDomain 接口 1
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain
api_location:
- corguids.lib
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain
helpviewer_keywords:
- ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: be7ae711-1217-4a44-be40-166e29641b77
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9588ac26c698a8369f1ae4be89af7440a2dd1de4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54546301"
---
# <a name="icordebugappdomain-interface1"></a><span data-ttu-id="d2a9f-102">ICorDebugAppDomain 接口 1</span><span class="sxs-lookup"><span data-stu-id="d2a9f-102">ICorDebugAppDomain Interface1</span></span>
<span data-ttu-id="d2a9f-103">提供用于调试应用程序域的方法。</span><span class="sxs-lookup"><span data-stu-id="d2a9f-103">Provides methods for debugging application domains.</span></span> <span data-ttu-id="d2a9f-104">此接口是 ICorDebugController 的子类。</span><span class="sxs-lookup"><span data-stu-id="d2a9f-104">This interface is a subclass of ICorDebugController.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d2a9f-105">方法</span><span class="sxs-lookup"><span data-stu-id="d2a9f-105">Methods</span></span>  
  
|<span data-ttu-id="d2a9f-106">方法</span><span class="sxs-lookup"><span data-stu-id="d2a9f-106">Method</span></span>|<span data-ttu-id="d2a9f-107">描述</span><span class="sxs-lookup"><span data-stu-id="d2a9f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d2a9f-108">Attach 方法</span><span class="sxs-lookup"><span data-stu-id="d2a9f-108">Attach Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-attach-method.md)|<span data-ttu-id="d2a9f-109">将调试器附加到应用程序域。</span><span class="sxs-lookup"><span data-stu-id="d2a9f-109">Attaches the debugger to the application domain.</span></span>|  
|[<span data-ttu-id="d2a9f-110">EnumerateAssemblies 方法</span><span class="sxs-lookup"><span data-stu-id="d2a9f-110">EnumerateAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumerateassemblies-method.md)|<span data-ttu-id="d2a9f-111">获取可枚举的程序集应用程序域中。</span><span class="sxs-lookup"><span data-stu-id="d2a9f-111">Gets an enumerator for the assemblies in the application domain.</span></span>|  
|[<span data-ttu-id="d2a9f-112">EnumerateBreakpoints 方法</span><span class="sxs-lookup"><span data-stu-id="d2a9f-112">EnumerateBreakpoints Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumeratebreakpoints-method.md)|<span data-ttu-id="d2a9f-113">获取应用程序域中所有活动断点的枚举数。</span><span class="sxs-lookup"><span data-stu-id="d2a9f-113">Gets an enumerator for all active breakpoints in the application domain.</span></span>|  
|[<span data-ttu-id="d2a9f-114">EnumerateSteppers 方法</span><span class="sxs-lookup"><span data-stu-id="d2a9f-114">EnumerateSteppers Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumeratesteppers-method.md)|<span data-ttu-id="d2a9f-115">获取可枚举所有活动分档应用程序域中。</span><span class="sxs-lookup"><span data-stu-id="d2a9f-115">Gets an enumerator for all active steppers in the application domain.</span></span>|  
|[<span data-ttu-id="d2a9f-116">GetId 方法</span><span class="sxs-lookup"><span data-stu-id="d2a9f-116">GetId Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getid-method.md)|<span data-ttu-id="d2a9f-117">获取应用程序域的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="d2a9f-117">Gets the unique ID of the application domain.</span></span>|  
|[<span data-ttu-id="d2a9f-118">GetModuleFromMetaDataInterface 方法</span><span class="sxs-lookup"><span data-stu-id="d2a9f-118">GetModuleFromMetaDataInterface Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getmodulefrommetadatainterface-method.md)|<span data-ttu-id="d2a9f-119">获取具有给定元数据接口的 icor 调试模块对象。</span><span class="sxs-lookup"><span data-stu-id="d2a9f-119">Gets the ICorDebugModule object with the given metadata interface.</span></span>|  
|[<span data-ttu-id="d2a9f-120">GetName 方法</span><span class="sxs-lookup"><span data-stu-id="d2a9f-120">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getname-method.md)|<span data-ttu-id="d2a9f-121">获取应用程序域的名称。</span><span class="sxs-lookup"><span data-stu-id="d2a9f-121">Gets the name of the application domain.</span></span>|  
|[<span data-ttu-id="d2a9f-122">GetObject 方法</span><span class="sxs-lookup"><span data-stu-id="d2a9f-122">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getobject-method.md)|<span data-ttu-id="d2a9f-123">获取对公共语言运行时 (CLR) 应用程序域的接口指针。</span><span class="sxs-lookup"><span data-stu-id="d2a9f-123">Gets an interface pointer to the common language runtime (CLR) application domain.</span></span>|  
|[<span data-ttu-id="d2a9f-124">GetProcess 方法</span><span class="sxs-lookup"><span data-stu-id="d2a9f-124">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getprocess-method.md)|<span data-ttu-id="d2a9f-125">获取包含应用程序域的进程。</span><span class="sxs-lookup"><span data-stu-id="d2a9f-125">Gets the process containing the application domain.</span></span>|  
|[<span data-ttu-id="d2a9f-126">IsAttached 方法</span><span class="sxs-lookup"><span data-stu-id="d2a9f-126">IsAttached Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-isattached-method.md)|<span data-ttu-id="d2a9f-127">确定调试器是否附加到应用程序域。</span><span class="sxs-lookup"><span data-stu-id="d2a9f-127">Determines whether the debugger is attached to the application domain.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d2a9f-128">备注</span><span class="sxs-lookup"><span data-stu-id="d2a9f-128">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d2a9f-129">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="d2a9f-129">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2a9f-130">要求</span><span class="sxs-lookup"><span data-stu-id="d2a9f-130">Requirements</span></span>  
 <span data-ttu-id="d2a9f-131">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d2a9f-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2a9f-132">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d2a9f-132">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d2a9f-133">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d2a9f-133">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d2a9f-134">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2a9f-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2a9f-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="d2a9f-135">See also</span></span>
- [<span data-ttu-id="d2a9f-136">调试接口</span><span class="sxs-lookup"><span data-stu-id="d2a9f-136">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
