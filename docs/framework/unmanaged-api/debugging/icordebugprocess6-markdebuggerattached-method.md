---
title: "ICorDebugProcess6::MarkDebuggerAttached 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: bf94f090-5265-4112-8e57-5b4e20e070d0
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f6d219e298e04157ea0670681c7550bd920bd284
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess6markdebuggerattached-method"></a><span data-ttu-id="ec418-102">ICorDebugProcess6::MarkDebuggerAttached 方法</span><span class="sxs-lookup"><span data-stu-id="ec418-102">ICorDebugProcess6::MarkDebuggerAttached Method</span></span>
<span data-ttu-id="ec418-103">更改调试对象的内部状态，以便 .NET Framework 类库中的 <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> 方法返回 `true`。</span><span class="sxs-lookup"><span data-stu-id="ec418-103">Changes the internal state of the debugee so that the <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> method in the .NET Framework Class Library returns `true`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec418-104">语法</span><span class="sxs-lookup"><span data-stu-id="ec418-104">Syntax</span></span>  
  
```  
HRESULT MarkDebuggerAttached(  
    BOOL fIsAttached  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ec418-105">参数</span><span class="sxs-lookup"><span data-stu-id="ec418-105">Parameters</span></span>  
 `fIsAttached`  
 <span data-ttu-id="ec418-106">如果 `true` 方法指出已连接调试程序，则为<xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType>；否则即为 `false`。</span><span class="sxs-lookup"><span data-stu-id="ec418-106">`true` if the <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> method should indicate that a debugger is attached; `false` otherwise.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ec418-107">返回值</span><span class="sxs-lookup"><span data-stu-id="ec418-107">Return Value</span></span>  
 <span data-ttu-id="ec418-108">该方法可以返回下表所列的值。</span><span class="sxs-lookup"><span data-stu-id="ec418-108">The method can return the values listed in the following table.</span></span>  
  
|<span data-ttu-id="ec418-109">返回值</span><span class="sxs-lookup"><span data-stu-id="ec418-109">Return value</span></span>|<span data-ttu-id="ec418-110">描述</span><span class="sxs-lookup"><span data-stu-id="ec418-110">Description</span></span>|  
|------------------|-----------------|  
|`S_OK`|<span data-ttu-id="ec418-111">调试对象已成功更新。</span><span class="sxs-lookup"><span data-stu-id="ec418-111">The debuggee was successfully updated.</span></span>|  
|`CORDBG_E_MODULE_NOT_LOADED`|<span data-ttu-id="ec418-112">程序集包含未加载的 <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> 方法或一些其他错误（例如元数据丢失），无法被识别。</span><span class="sxs-lookup"><span data-stu-id="ec418-112">The assembly that contains the <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> method is not loaded, or some other error, such as missing metadata, is preventing it from being recognized.</span></span><br /><br /> <span data-ttu-id="ec418-113">该错误很常见，没有危害。</span><span class="sxs-lookup"><span data-stu-id="ec418-113">This error is common and benign.</span></span> <span data-ttu-id="ec418-114">你应当在其他程序集加载时再次调用方法。</span><span class="sxs-lookup"><span data-stu-id="ec418-114">You should call the method again when additional assemblies load.</span></span>|  
|<span data-ttu-id="ec418-115">其他失败 `HRESULT` 值。</span><span class="sxs-lookup"><span data-stu-id="ec418-115">Other failing `HRESULT` values.</span></span>|<span data-ttu-id="ec418-116">其他值可能表示错误调试程序或编译器组件。</span><span class="sxs-lookup"><span data-stu-id="ec418-116">Other values likely indicate misbehaving debugger or compiler components.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ec418-117">备注</span><span class="sxs-lookup"><span data-stu-id="ec418-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ec418-118">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="ec418-118">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec418-119">要求</span><span class="sxs-lookup"><span data-stu-id="ec418-119">Requirements</span></span>  
 <span data-ttu-id="ec418-120">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ec418-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec418-121">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ec418-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ec418-122">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ec418-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ec418-123">**.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec418-123">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec418-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ec418-124">See Also</span></span>  
 [<span data-ttu-id="ec418-125">ICorDebugProcess6 接口</span><span class="sxs-lookup"><span data-stu-id="ec418-125">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)  
 [<span data-ttu-id="ec418-126">调试接口</span><span class="sxs-lookup"><span data-stu-id="ec418-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
