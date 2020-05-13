---
title: ICorDebugModule2::SetJITCompilerFlags 方法
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.SetJITCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::SetJITCompilerFlags
helpviewer_keywords:
- ICorDebugModule2::SetJITCompilerFlags method [.NET Framework debugging]
- SetJITCompilerFlags method [.NET Framework debugging]
ms.assetid: ea574c84-c622-4589-9a14-b55771af5e06
topic_type:
- apiref
ms.openlocfilehash: f73919634ba15dfd16694676d1389875fc2d79bc
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210184"
---
# <a name="icordebugmodule2setjitcompilerflags-method"></a><span data-ttu-id="99092-102">ICorDebugModule2::SetJITCompilerFlags 方法</span><span class="sxs-lookup"><span data-stu-id="99092-102">ICorDebugModule2::SetJITCompilerFlags Method</span></span>
<span data-ttu-id="99092-103">设置控制此 ICorDebugModule2 的实时（JIT）编译的标志。</span><span class="sxs-lookup"><span data-stu-id="99092-103">Sets the flags that control the just-in-time (JIT) compilation of this ICorDebugModule2.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99092-104">语法</span><span class="sxs-lookup"><span data-stu-id="99092-104">Syntax</span></span>  
  
```cpp  
HRESULT SetJITCompilerFlags (  
    [in] DWORD dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="99092-105">参数</span><span class="sxs-lookup"><span data-stu-id="99092-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="99092-106">中[CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md)枚举值的按位组合。</span><span class="sxs-lookup"><span data-stu-id="99092-106">[in] A bitwise combination of the [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) enumeration values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99092-107">备注</span><span class="sxs-lookup"><span data-stu-id="99092-107">Remarks</span></span>  
 <span data-ttu-id="99092-108">如果 `dwFlags` 值无效，则该 `SetJITCompilerFlags` 方法将失败。</span><span class="sxs-lookup"><span data-stu-id="99092-108">If the `dwFlags` value is invalid, the `SetJITCompilerFlags` method will fail.</span></span>  
  
 <span data-ttu-id="99092-109">只能在 `SetJITCompilerFlags` 此模块的[ICorDebugManagedCallback：： LoadModule](icordebugmanagedcallback-loadmodule-method.md)回调中调用方法。</span><span class="sxs-lookup"><span data-stu-id="99092-109">The `SetJITCompilerFlags` method can be called only from within the [ICorDebugManagedCallback::LoadModule](icordebugmanagedcallback-loadmodule-method.md) callback for this module.</span></span> <span data-ttu-id="99092-110">在提供回调后，尝试调用它 `ICorDebugManagedCallback::LoadModule` 将会失败。</span><span class="sxs-lookup"><span data-stu-id="99092-110">Attempts to call it after the `ICorDebugManagedCallback::LoadModule` callback has been delivered will fail.</span></span>  
  
 <span data-ttu-id="99092-111">64位或 Win9x 平台不支持 "编辑并继续"。</span><span class="sxs-lookup"><span data-stu-id="99092-111">Edit and Continue is not supported on 64-bit or Win9x platforms.</span></span> <span data-ttu-id="99092-112">因此，如果在这 `SetJITCompilerFlags` 两个平台中的任何一个上调用方法，并且在中设置了 CORDEBUG_JIT_ENABLE_ENC 标志 `dwFlags` ，则 `SetJITCompilerFlags` 特定于 "编辑并继续" 的方法和所有方法（例如[ICorDebugModule2：： ApplyChanges](icordebugmodule2-applychanges-method.md)）将会失败。</span><span class="sxs-lookup"><span data-stu-id="99092-112">Therefore, if you call the `SetJITCompilerFlags` method on either of these two platforms with the CORDEBUG_JIT_ENABLE_ENC flag set in `dwFlags`, the `SetJITCompilerFlags` method and all methods specific to Edit and Continue, such as [ICorDebugModule2::ApplyChanges](icordebugmodule2-applychanges-method.md), will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99092-113">要求</span><span class="sxs-lookup"><span data-stu-id="99092-113">Requirements</span></span>  
 <span data-ttu-id="99092-114">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="99092-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99092-115">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="99092-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="99092-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="99092-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="99092-117">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99092-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
