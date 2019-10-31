---
title: ICorDebugDataTarget2::CreateVirtualUnwinder 方法
ms.date: 03/30/2017
ms.assetid: 354c8b4c-7d23-45c6-a7d7-3be4c2a5b772
ms.openlocfilehash: f9a9038bd0d268e09d8518fa50534a9959b456de
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122188"
---
# <a name="icordebugdatatarget2createvirtualunwinder-method"></a><span data-ttu-id="7def8-102">ICorDebugDataTarget2::CreateVirtualUnwinder 方法</span><span class="sxs-lookup"><span data-stu-id="7def8-102">ICorDebugDataTarget2::CreateVirtualUnwinder Method</span></span>
<span data-ttu-id="7def8-103">创建一个从初始上下文（不一定是线程叶）开始展开的新堆栈开卷机。</span><span class="sxs-lookup"><span data-stu-id="7def8-103">Creates a new stack unwinder that starts unwinding from an initial context (which isn't necessarily the leaf of a thread).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7def8-104">语法</span><span class="sxs-lookup"><span data-stu-id="7def8-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateVirtualUnwinder(  
    [in] DWORD nativeThreadID,  
    [in] ULONG32 contextFlags,  
    [in] ULONG32 cbContext,  
    [in, size_is(cbContext)] BYTE initialContext[],  
    [out] ICorDebugVirtualUnwinder ** ppUnwinder);  
};  
```  
  
## <a name="parameters"></a><span data-ttu-id="7def8-105">参数</span><span class="sxs-lookup"><span data-stu-id="7def8-105">Parameters</span></span>  
 <span data-ttu-id="7def8-106">本机线程ID</span><span class="sxs-lookup"><span data-stu-id="7def8-106">nativeThreadID</span></span>  
 <span data-ttu-id="7def8-107">[输入] 线程（其堆栈未展开）的本机线程 ID。</span><span class="sxs-lookup"><span data-stu-id="7def8-107">[in] The native thread ID of the thread whose stack is to be unwound.</span></span>  
  
 <span data-ttu-id="7def8-108">上下文标记</span><span class="sxs-lookup"><span data-stu-id="7def8-108">contextFlags</span></span>  
 <span data-ttu-id="7def8-109">[输入] `initialContext` 中规定了指定上下文部分的标记。</span><span class="sxs-lookup"><span data-stu-id="7def8-109">[in] Flags that specify which parts of the context are defined in `initialContext`.</span></span>  
  
 <span data-ttu-id="7def8-110">cb上下文</span><span class="sxs-lookup"><span data-stu-id="7def8-110">cbContext</span></span>  
 <span data-ttu-id="7def8-111">[输入] `initialContext` 的大小。</span><span class="sxs-lookup"><span data-stu-id="7def8-111">[in] The size of `initialContext`.</span></span>  
  
 <span data-ttu-id="7def8-112">初始上下文</span><span class="sxs-lookup"><span data-stu-id="7def8-112">initialContext</span></span>  
 <span data-ttu-id="7def8-113">[输入] 上下文中的数据。</span><span class="sxs-lookup"><span data-stu-id="7def8-113">[in] The data in the context.</span></span>  
  
 <span data-ttu-id="7def8-114">pp开卷机</span><span class="sxs-lookup"><span data-stu-id="7def8-114">ppUnwinder</span></span>  
 <span data-ttu-id="7def8-115">[输出] 指针指向“ICor调试虚拟开卷机”接口对象的地址。</span><span class="sxs-lookup"><span data-stu-id="7def8-115">[out] A pointer to the address of an ICorDebugVirtualUnwinder interface object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7def8-116">返回值</span><span class="sxs-lookup"><span data-stu-id="7def8-116">Return Value</span></span>  
 <span data-ttu-id="7def8-117">`S_OK` 如果成功。</span><span class="sxs-lookup"><span data-stu-id="7def8-117">`S_OK` if successful.</span></span> <span data-ttu-id="7def8-118">所有其他 `HRESULT` 都表示故障。</span><span class="sxs-lookup"><span data-stu-id="7def8-118">Any other `HRESULT` indicates failure.</span></span> <span data-ttu-id="7def8-119">Mscordbi.dll 收到的任何失败的 `HRESULT` 都被视为致命错误，并导致[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)方法返回 `CORDBG_E_DATA_TARGET_ERROR`。</span><span class="sxs-lookup"><span data-stu-id="7def8-119">Any failing `HRESULT` received by mscordbi is considered fatal and causes [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) methods to return `CORDBG_E_DATA_TARGET_ERROR`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7def8-120">备注</span><span class="sxs-lookup"><span data-stu-id="7def8-120">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7def8-121">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="7def8-121">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7def8-122">要求</span><span class="sxs-lookup"><span data-stu-id="7def8-122">Requirements</span></span>  
 <span data-ttu-id="7def8-123">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7def8-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7def8-124">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7def8-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7def8-125">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7def8-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7def8-126">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7def8-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7def8-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="7def8-127">See also</span></span>

- [<span data-ttu-id="7def8-128">ICorDebugDataTarget2 接口</span><span class="sxs-lookup"><span data-stu-id="7def8-128">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)
- [<span data-ttu-id="7def8-129">调试接口</span><span class="sxs-lookup"><span data-stu-id="7def8-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
