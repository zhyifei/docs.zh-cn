---
title: ICorDebugAppDomain 接口
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
ms.openlocfilehash: 40619aa40f9924d94c82541eb8d30790e774a675
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61996185"
---
# <a name="icordebugappdomain-interface"></a><span data-ttu-id="1c011-102">ICorDebugAppDomain 接口</span><span class="sxs-lookup"><span data-stu-id="1c011-102">ICorDebugAppDomain Interface</span></span>

<span data-ttu-id="1c011-103">提供用于调试应用程序域的方法。</span><span class="sxs-lookup"><span data-stu-id="1c011-103">Provides methods for debugging application domains.</span></span> <span data-ttu-id="1c011-104">此接口是 ICorDebugController 的子类。</span><span class="sxs-lookup"><span data-stu-id="1c011-104">This interface is a subclass of ICorDebugController.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1c011-105">方法</span><span class="sxs-lookup"><span data-stu-id="1c011-105">Methods</span></span>  
  
|<span data-ttu-id="1c011-106">方法</span><span class="sxs-lookup"><span data-stu-id="1c011-106">Method</span></span>|<span data-ttu-id="1c011-107">描述</span><span class="sxs-lookup"><span data-stu-id="1c011-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1c011-108">Attach 方法</span><span class="sxs-lookup"><span data-stu-id="1c011-108">Attach Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-attach-method.md)|<span data-ttu-id="1c011-109">将调试器附加到应用程序域。</span><span class="sxs-lookup"><span data-stu-id="1c011-109">Attaches the debugger to the application domain.</span></span>|  
|[<span data-ttu-id="1c011-110">EnumerateAssemblies 方法</span><span class="sxs-lookup"><span data-stu-id="1c011-110">EnumerateAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumerateassemblies-method.md)|<span data-ttu-id="1c011-111">获取可枚举的程序集应用程序域中。</span><span class="sxs-lookup"><span data-stu-id="1c011-111">Gets an enumerator for the assemblies in the application domain.</span></span>|  
|[<span data-ttu-id="1c011-112">EnumerateBreakpoints 方法</span><span class="sxs-lookup"><span data-stu-id="1c011-112">EnumerateBreakpoints Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumeratebreakpoints-method.md)|<span data-ttu-id="1c011-113">获取应用程序域中所有活动断点的枚举数。</span><span class="sxs-lookup"><span data-stu-id="1c011-113">Gets an enumerator for all active breakpoints in the application domain.</span></span>|  
|[<span data-ttu-id="1c011-114">EnumerateSteppers 方法</span><span class="sxs-lookup"><span data-stu-id="1c011-114">EnumerateSteppers Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumeratesteppers-method.md)|<span data-ttu-id="1c011-115">获取可枚举所有活动分档应用程序域中。</span><span class="sxs-lookup"><span data-stu-id="1c011-115">Gets an enumerator for all active steppers in the application domain.</span></span>|  
|[<span data-ttu-id="1c011-116">GetId 方法</span><span class="sxs-lookup"><span data-stu-id="1c011-116">GetId Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getid-method.md)|<span data-ttu-id="1c011-117">获取应用程序域的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="1c011-117">Gets the unique ID of the application domain.</span></span>|  
|[<span data-ttu-id="1c011-118">GetModuleFromMetaDataInterface 方法</span><span class="sxs-lookup"><span data-stu-id="1c011-118">GetModuleFromMetaDataInterface Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getmodulefrommetadatainterface-method.md)|<span data-ttu-id="1c011-119">获取具有给定元数据接口的 icor 调试模块对象。</span><span class="sxs-lookup"><span data-stu-id="1c011-119">Gets the ICorDebugModule object with the given metadata interface.</span></span>|  
|[<span data-ttu-id="1c011-120">GetName 方法</span><span class="sxs-lookup"><span data-stu-id="1c011-120">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getname-method.md)|<span data-ttu-id="1c011-121">获取应用程序域的名称。</span><span class="sxs-lookup"><span data-stu-id="1c011-121">Gets the name of the application domain.</span></span>|  
|[<span data-ttu-id="1c011-122">GetObject 方法</span><span class="sxs-lookup"><span data-stu-id="1c011-122">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getobject-method.md)|<span data-ttu-id="1c011-123">获取对公共语言运行时 (CLR) 应用程序域的接口指针。</span><span class="sxs-lookup"><span data-stu-id="1c011-123">Gets an interface pointer to the common language runtime (CLR) application domain.</span></span>|  
|[<span data-ttu-id="1c011-124">GetProcess 方法</span><span class="sxs-lookup"><span data-stu-id="1c011-124">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getprocess-method.md)|<span data-ttu-id="1c011-125">获取包含应用程序域的进程。</span><span class="sxs-lookup"><span data-stu-id="1c011-125">Gets the process containing the application domain.</span></span>|  
|[<span data-ttu-id="1c011-126">IsAttached 方法</span><span class="sxs-lookup"><span data-stu-id="1c011-126">IsAttached Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-isattached-method.md)|<span data-ttu-id="1c011-127">确定调试器是否附加到应用程序域。</span><span class="sxs-lookup"><span data-stu-id="1c011-127">Determines whether the debugger is attached to the application domain.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1c011-128">备注</span><span class="sxs-lookup"><span data-stu-id="1c011-128">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1c011-129">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="1c011-129">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c011-130">要求</span><span class="sxs-lookup"><span data-stu-id="1c011-130">Requirements</span></span>  
 <span data-ttu-id="1c011-131">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1c011-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c011-132">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1c011-132">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1c011-133">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1c011-133">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1c011-134">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c011-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c011-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="1c011-135">See also</span></span>

- [<span data-ttu-id="1c011-136">调试接口</span><span class="sxs-lookup"><span data-stu-id="1c011-136">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
