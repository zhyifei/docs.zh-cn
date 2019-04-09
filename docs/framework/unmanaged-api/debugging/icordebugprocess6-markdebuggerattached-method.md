---
title: ICorDebugProcess6::MarkDebuggerAttached 方法
ms.date: 03/30/2017
ms.assetid: bf94f090-5265-4112-8e57-5b4e20e070d0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 15e2e94ac4e30fbdb375175148a5b448c51821f0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59128019"
---
# <a name="icordebugprocess6markdebuggerattached-method"></a><span data-ttu-id="b7d89-102">ICorDebugProcess6::MarkDebuggerAttached 方法</span><span class="sxs-lookup"><span data-stu-id="b7d89-102">ICorDebugProcess6::MarkDebuggerAttached Method</span></span>
<span data-ttu-id="b7d89-103">更改调试对象的内部状态，以便 .NET Framework 类库中的 <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> 方法返回 `true`。</span><span class="sxs-lookup"><span data-stu-id="b7d89-103">Changes the internal state of the debugee so that the <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> method in the .NET Framework Class Library returns `true`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7d89-104">语法</span><span class="sxs-lookup"><span data-stu-id="b7d89-104">Syntax</span></span>  
  
```  
HRESULT MarkDebuggerAttached(  
    BOOL fIsAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b7d89-105">参数</span><span class="sxs-lookup"><span data-stu-id="b7d89-105">Parameters</span></span>  
 `fIsAttached`  
 `true` <span data-ttu-id="b7d89-106">如果<xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType>方法应指示附加有调试器;`false`否则为。</span><span class="sxs-lookup"><span data-stu-id="b7d89-106">if the <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> method should indicate that a debugger is attached; `false` otherwise.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b7d89-107">返回值</span><span class="sxs-lookup"><span data-stu-id="b7d89-107">Return Value</span></span>  
 <span data-ttu-id="b7d89-108">该方法可以返回下表所列的值。</span><span class="sxs-lookup"><span data-stu-id="b7d89-108">The method can return the values listed in the following table.</span></span>  
  
|<span data-ttu-id="b7d89-109">返回值</span><span class="sxs-lookup"><span data-stu-id="b7d89-109">Return value</span></span>|<span data-ttu-id="b7d89-110">描述</span><span class="sxs-lookup"><span data-stu-id="b7d89-110">Description</span></span>|  
|------------------|-----------------|  
|`S_OK`|<span data-ttu-id="b7d89-111">调试对象已成功更新。</span><span class="sxs-lookup"><span data-stu-id="b7d89-111">The debuggee was successfully updated.</span></span>|  
|`CORDBG_E_MODULE_NOT_LOADED`|<span data-ttu-id="b7d89-112">程序集包含未加载的 <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> 方法或一些其他错误（例如元数据丢失），无法被识别。</span><span class="sxs-lookup"><span data-stu-id="b7d89-112">The assembly that contains the <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> method is not loaded, or some other error, such as missing metadata, is preventing it from being recognized.</span></span><br /><br /> <span data-ttu-id="b7d89-113">该错误很常见，没有危害。</span><span class="sxs-lookup"><span data-stu-id="b7d89-113">This error is common and benign.</span></span> <span data-ttu-id="b7d89-114">你应当在其他程序集加载时再次调用方法。</span><span class="sxs-lookup"><span data-stu-id="b7d89-114">You should call the method again when additional assemblies load.</span></span>|  
|<span data-ttu-id="b7d89-115">其他失败 `HRESULT` 值。</span><span class="sxs-lookup"><span data-stu-id="b7d89-115">Other failing `HRESULT` values.</span></span>|<span data-ttu-id="b7d89-116">其他值可能表示错误调试程序或编译器组件。</span><span class="sxs-lookup"><span data-stu-id="b7d89-116">Other values likely indicate misbehaving debugger or compiler components.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7d89-117">备注</span><span class="sxs-lookup"><span data-stu-id="b7d89-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b7d89-118">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="b7d89-118">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7d89-119">要求</span><span class="sxs-lookup"><span data-stu-id="b7d89-119">Requirements</span></span>  
 <span data-ttu-id="b7d89-120">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b7d89-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7d89-121">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b7d89-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b7d89-122">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b7d89-122">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="b7d89-123">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="b7d89-123">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b7d89-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="b7d89-124">See also</span></span>

- [<span data-ttu-id="b7d89-125">“ICor调试进程6”接口</span><span class="sxs-lookup"><span data-stu-id="b7d89-125">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)
- [<span data-ttu-id="b7d89-126">调试接口</span><span class="sxs-lookup"><span data-stu-id="b7d89-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
