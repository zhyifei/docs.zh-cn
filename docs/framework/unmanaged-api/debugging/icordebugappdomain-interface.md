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
ms.openlocfilehash: 140e67417f4fad552f972a93bc8c620b440b2370
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895177"
---
# <a name="icordebugappdomain-interface"></a><span data-ttu-id="01877-102">ICorDebugAppDomain 接口</span><span class="sxs-lookup"><span data-stu-id="01877-102">ICorDebugAppDomain Interface</span></span>

<span data-ttu-id="01877-103">提供用于调试应用程序域的方法。</span><span class="sxs-lookup"><span data-stu-id="01877-103">Provides methods for debugging application domains.</span></span> <span data-ttu-id="01877-104">此接口是 ICorDebugController 的子类。</span><span class="sxs-lookup"><span data-stu-id="01877-104">This interface is a subclass of ICorDebugController.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="01877-105">方法</span><span class="sxs-lookup"><span data-stu-id="01877-105">Methods</span></span>  
  
|<span data-ttu-id="01877-106">方法</span><span class="sxs-lookup"><span data-stu-id="01877-106">Method</span></span>|<span data-ttu-id="01877-107">说明</span><span class="sxs-lookup"><span data-stu-id="01877-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="01877-108">Attach 方法</span><span class="sxs-lookup"><span data-stu-id="01877-108">Attach Method</span></span>](icordebugappdomain-attach-method.md)|<span data-ttu-id="01877-109">将调试器附加到应用程序域。</span><span class="sxs-lookup"><span data-stu-id="01877-109">Attaches the debugger to the application domain.</span></span>|  
|[<span data-ttu-id="01877-110">EnumerateAssemblies 方法</span><span class="sxs-lookup"><span data-stu-id="01877-110">EnumerateAssemblies Method</span></span>](icordebugappdomain-enumerateassemblies-method.md)|<span data-ttu-id="01877-111">获取应用程序域中的程序集的枚举器。</span><span class="sxs-lookup"><span data-stu-id="01877-111">Gets an enumerator for the assemblies in the application domain.</span></span>|  
|[<span data-ttu-id="01877-112">EnumerateBreakpoints 方法</span><span class="sxs-lookup"><span data-stu-id="01877-112">EnumerateBreakpoints Method</span></span>](icordebugappdomain-enumeratebreakpoints-method.md)|<span data-ttu-id="01877-113">获取应用程序域中所有活动断点的枚举器。</span><span class="sxs-lookup"><span data-stu-id="01877-113">Gets an enumerator for all active breakpoints in the application domain.</span></span>|  
|[<span data-ttu-id="01877-114">EnumerateSteppers 方法</span><span class="sxs-lookup"><span data-stu-id="01877-114">EnumerateSteppers Method</span></span>](icordebugappdomain-enumeratesteppers-method.md)|<span data-ttu-id="01877-115">获取应用程序域中所有活动 steppers 的枚举器。</span><span class="sxs-lookup"><span data-stu-id="01877-115">Gets an enumerator for all active steppers in the application domain.</span></span>|  
|[<span data-ttu-id="01877-116">GetId 方法</span><span class="sxs-lookup"><span data-stu-id="01877-116">GetId Method</span></span>](icordebugappdomain-getid-method.md)|<span data-ttu-id="01877-117">获取应用程序域的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="01877-117">Gets the unique ID of the application domain.</span></span>|  
|[<span data-ttu-id="01877-118">GetModuleFromMetaDataInterface 方法</span><span class="sxs-lookup"><span data-stu-id="01877-118">GetModuleFromMetaDataInterface Method</span></span>](icordebugappdomain-getmodulefrommetadatainterface-method.md)|<span data-ttu-id="01877-119">获取具有给定元数据接口的 ICorDebugModule 对象。</span><span class="sxs-lookup"><span data-stu-id="01877-119">Gets the ICorDebugModule object with the given metadata interface.</span></span>|  
|[<span data-ttu-id="01877-120">GetName 方法</span><span class="sxs-lookup"><span data-stu-id="01877-120">GetName Method</span></span>](icordebugappdomain-getname-method.md)|<span data-ttu-id="01877-121">获取应用程序域的名称。</span><span class="sxs-lookup"><span data-stu-id="01877-121">Gets the name of the application domain.</span></span>|  
|[<span data-ttu-id="01877-122">GetObject 方法</span><span class="sxs-lookup"><span data-stu-id="01877-122">GetObject Method</span></span>](icordebugappdomain-getobject-method.md)|<span data-ttu-id="01877-123">获取指向公共语言运行时（CLR）应用程序域的接口指针。</span><span class="sxs-lookup"><span data-stu-id="01877-123">Gets an interface pointer to the common language runtime (CLR) application domain.</span></span>|  
|[<span data-ttu-id="01877-124">GetProcess 方法</span><span class="sxs-lookup"><span data-stu-id="01877-124">GetProcess Method</span></span>](icordebugappdomain-getprocess-method.md)|<span data-ttu-id="01877-125">获取包含应用程序域的进程。</span><span class="sxs-lookup"><span data-stu-id="01877-125">Gets the process containing the application domain.</span></span>|  
|[<span data-ttu-id="01877-126">IsAttached 方法</span><span class="sxs-lookup"><span data-stu-id="01877-126">IsAttached Method</span></span>](icordebugappdomain-isattached-method.md)|<span data-ttu-id="01877-127">确定调试器是否已附加到应用程序域。</span><span class="sxs-lookup"><span data-stu-id="01877-127">Determines whether the debugger is attached to the application domain.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="01877-128">备注</span><span class="sxs-lookup"><span data-stu-id="01877-128">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="01877-129">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="01877-129">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01877-130">要求</span><span class="sxs-lookup"><span data-stu-id="01877-130">Requirements</span></span>  
 <span data-ttu-id="01877-131">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="01877-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01877-132">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="01877-132">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="01877-133">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="01877-133">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="01877-134">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01877-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01877-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="01877-135">See also</span></span>

- [<span data-ttu-id="01877-136">调试接口</span><span class="sxs-lookup"><span data-stu-id="01877-136">Debugging Interfaces</span></span>](debugging-interfaces.md)
