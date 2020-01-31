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
ms.openlocfilehash: b28e457ea0b51d320581c0fbe36574698081ea36
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792962"
---
# <a name="icordebugmodule2setjitcompilerflags-method"></a><span data-ttu-id="85066-102">ICorDebugModule2::SetJITCompilerFlags 方法</span><span class="sxs-lookup"><span data-stu-id="85066-102">ICorDebugModule2::SetJITCompilerFlags Method</span></span>
<span data-ttu-id="85066-103">设置控制此 ICorDebugModule2 的实时（JIT）编译的标志。</span><span class="sxs-lookup"><span data-stu-id="85066-103">Sets the flags that control the just-in-time (JIT) compilation of this ICorDebugModule2.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85066-104">语法</span><span class="sxs-lookup"><span data-stu-id="85066-104">Syntax</span></span>  
  
```cpp  
HRESULT SetJITCompilerFlags (  
    [in] DWORD dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="85066-105">参数</span><span class="sxs-lookup"><span data-stu-id="85066-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="85066-106">中[CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md)枚举值的按位组合。</span><span class="sxs-lookup"><span data-stu-id="85066-106">[in] A bitwise combination of the [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) enumeration values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="85066-107">备注</span><span class="sxs-lookup"><span data-stu-id="85066-107">Remarks</span></span>  
 <span data-ttu-id="85066-108">如果 `dwFlags` 值无效，则 `SetJITCompilerFlags` 方法将失败。</span><span class="sxs-lookup"><span data-stu-id="85066-108">If the `dwFlags` value is invalid, the `SetJITCompilerFlags` method will fail.</span></span>  
  
 <span data-ttu-id="85066-109">只能在此模块的[ICorDebugManagedCallback：： LoadModule](icordebugmanagedcallback-loadmodule-method.md)回调内调用 `SetJITCompilerFlags` 方法。</span><span class="sxs-lookup"><span data-stu-id="85066-109">The `SetJITCompilerFlags` method can be called only from within the [ICorDebugManagedCallback::LoadModule](icordebugmanagedcallback-loadmodule-method.md) callback for this module.</span></span> <span data-ttu-id="85066-110">在提供 `ICorDebugManagedCallback::LoadModule` 回调后，尝试调用它将会失败。</span><span class="sxs-lookup"><span data-stu-id="85066-110">Attempts to call it after the `ICorDebugManagedCallback::LoadModule` callback has been delivered will fail.</span></span>  
  
 <span data-ttu-id="85066-111">64位或 Win9x 平台不支持 "编辑并继续"。</span><span class="sxs-lookup"><span data-stu-id="85066-111">Edit and Continue is not supported on 64-bit or Win9x platforms.</span></span> <span data-ttu-id="85066-112">因此，如果在这两个平台中的任一平台上调用 `SetJITCompilerFlags` 方法，并且在 `dwFlags`中设置了 CORDEBUG_JIT_ENABLE_ENC 标志，则 `SetJITCompilerFlags` 方法和特定于 "编辑并继续" 的所有方法（如[ICorDebugModule2：： ApplyChanges](icordebugmodule2-applychanges-method.md)）将会失败。</span><span class="sxs-lookup"><span data-stu-id="85066-112">Therefore, if you call the `SetJITCompilerFlags` method on either of these two platforms with the CORDEBUG_JIT_ENABLE_ENC flag set in `dwFlags`, the `SetJITCompilerFlags` method and all methods specific to Edit and Continue, such as [ICorDebugModule2::ApplyChanges](icordebugmodule2-applychanges-method.md), will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85066-113">需求</span><span class="sxs-lookup"><span data-stu-id="85066-113">Requirements</span></span>  
 <span data-ttu-id="85066-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="85066-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85066-115">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="85066-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="85066-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="85066-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="85066-117">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85066-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
