---
title: ICorDebugValue 接口
ms.date: 03/30/2017
api_name:
- ICorDebugValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue
helpviewer_keywords:
- ICorDebugValue interface [.NET Framework debugging]
ms.assetid: b2f7007f-c446-4b18-aed1-a25cff8aee31
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2de5d3a208594a03bfdca837e592f53b3da7f0f0
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56981408"
---
# <a name="icordebugvalue-interface"></a><span data-ttu-id="7e42a-102">ICorDebugValue 接口</span><span class="sxs-lookup"><span data-stu-id="7e42a-102">ICorDebugValue Interface</span></span>
<span data-ttu-id="7e42a-103">表示正在调试的进程中的值。</span><span class="sxs-lookup"><span data-stu-id="7e42a-103">Represents a value in the process being debugged.</span></span> <span data-ttu-id="7e42a-104">值可以是读取或写入值。</span><span class="sxs-lookup"><span data-stu-id="7e42a-104">The value can be a read or a write value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7e42a-105">方法</span><span class="sxs-lookup"><span data-stu-id="7e42a-105">Methods</span></span>  
  
|<span data-ttu-id="7e42a-106">方法</span><span class="sxs-lookup"><span data-stu-id="7e42a-106">Method</span></span>|<span data-ttu-id="7e42a-107">描述</span><span class="sxs-lookup"><span data-stu-id="7e42a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7e42a-108">CreateBreakpoint 方法</span><span class="sxs-lookup"><span data-stu-id="7e42a-108">CreateBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-createbreakpoint-method.md)|<span data-ttu-id="7e42a-109">目前尚未实现此方法。</span><span class="sxs-lookup"><span data-stu-id="7e42a-109">This method is not currently implemented.</span></span>|  
|[<span data-ttu-id="7e42a-110">GetAddress 方法</span><span class="sxs-lookup"><span data-stu-id="7e42a-110">GetAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md)|<span data-ttu-id="7e42a-111">获取此地址`ICorDebugValue`对象，它是正在调试的过程中。</span><span class="sxs-lookup"><span data-stu-id="7e42a-111">Gets the address of this `ICorDebugValue` object, which is in the process of being debugged.</span></span>|  
|[<span data-ttu-id="7e42a-112">GetSize 方法</span><span class="sxs-lookup"><span data-stu-id="7e42a-112">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md)|<span data-ttu-id="7e42a-113">获取大小，以字节为单位，此`ICorDebugValue`对象。</span><span class="sxs-lookup"><span data-stu-id="7e42a-113">Gets the size, in bytes, of this `ICorDebugValue` object.</span></span>|  
|[<span data-ttu-id="7e42a-114">GetType 方法</span><span class="sxs-lookup"><span data-stu-id="7e42a-114">GetType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md)|<span data-ttu-id="7e42a-115">获取此的基元类型`ICorDebugValue`对象。</span><span class="sxs-lookup"><span data-stu-id="7e42a-115">Gets the primitive type of this `ICorDebugValue` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7e42a-116">备注</span><span class="sxs-lookup"><span data-stu-id="7e42a-116">Remarks</span></span>  
 <span data-ttu-id="7e42a-117">一般情况下，它返回时传递的值对象的所有权。</span><span class="sxs-lookup"><span data-stu-id="7e42a-117">In general, ownership of a value object is passed when it is returned.</span></span> <span data-ttu-id="7e42a-118">接收方负责完成与该对象从对象中移除引用。</span><span class="sxs-lookup"><span data-stu-id="7e42a-118">The recipient is responsible for removing a reference from the object when it is finished with the object.</span></span>  
  
 <span data-ttu-id="7e42a-119">具体取决于其中已从检索的值，值可能不会保持有效后恢复进程。</span><span class="sxs-lookup"><span data-stu-id="7e42a-119">Depending on where the value was retrieved from, the value may not remain valid after the process is resumed.</span></span> <span data-ttu-id="7e42a-120">因此，一般情况下，保持的值不应在的调用之间[icordebugcontroller:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="7e42a-120">So, in general, the value shouldn't be held across a call of the [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7e42a-121">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="7e42a-121">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e42a-122">要求</span><span class="sxs-lookup"><span data-stu-id="7e42a-122">Requirements</span></span>  
 <span data-ttu-id="7e42a-123">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7e42a-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e42a-124">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7e42a-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7e42a-125">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7e42a-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7e42a-126">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e42a-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e42a-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="7e42a-127">See also</span></span>




- [<span data-ttu-id="7e42a-128">ICorDebugValue3 接口</span><span class="sxs-lookup"><span data-stu-id="7e42a-128">ICorDebugValue3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)
- [<span data-ttu-id="7e42a-129">调试接口</span><span class="sxs-lookup"><span data-stu-id="7e42a-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
