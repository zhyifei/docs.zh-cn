---
title: "ICorDebugModule2::SetJITCompilerFlags 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule2.SetJITCompilerFlags
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule2::SetJITCompilerFlags
helpviewer_keywords:
- ICorDebugModule2::SetJITCompilerFlags method [.NET Framework debugging]
- SetJITCompilerFlags method [.NET Framework debugging]
ms.assetid: ea574c84-c622-4589-9a14-b55771af5e06
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 42eea356214fedb22a2f60842f6007f3eb6a0e2a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmodule2setjitcompilerflags-method"></a><span data-ttu-id="805ed-102">ICorDebugModule2::SetJITCompilerFlags 方法</span><span class="sxs-lookup"><span data-stu-id="805ed-102">ICorDebugModule2::SetJITCompilerFlags Method</span></span>
<span data-ttu-id="805ed-103">设置用于控制此 ICorDebugModule2 实时 (JIT) 编译的标志。</span><span class="sxs-lookup"><span data-stu-id="805ed-103">Sets the flags that control the just-in-time (JIT) compilation of this ICorDebugModule2.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="805ed-104">语法</span><span class="sxs-lookup"><span data-stu-id="805ed-104">Syntax</span></span>  
  
```  
HRESULT SetJITCompilerFlags (  
    [in] DWORD dwFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="805ed-105">参数</span><span class="sxs-lookup"><span data-stu-id="805ed-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="805ed-106">[in]按位组合[CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md)枚举值。</span><span class="sxs-lookup"><span data-stu-id="805ed-106">[in] A bitwise combination of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="805ed-107">备注</span><span class="sxs-lookup"><span data-stu-id="805ed-107">Remarks</span></span>  
 <span data-ttu-id="805ed-108">如果`dwFlags`值无效，`SetJITCompilerFlags`方法将失败。</span><span class="sxs-lookup"><span data-stu-id="805ed-108">If the `dwFlags` value is invalid, the `SetJITCompilerFlags` method will fail.</span></span>  
  
 <span data-ttu-id="805ed-109">`SetJITCompilerFlags`方法可以调用仅从[icordebugmanagedcallback:: Loadmodule](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadmodule-method.md)为此模块的回调。</span><span class="sxs-lookup"><span data-stu-id="805ed-109">The `SetJITCompilerFlags` method can be called only from within the [ICorDebugManagedCallback::LoadModule](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadmodule-method.md) callback for this module.</span></span> <span data-ttu-id="805ed-110">尝试调用则在此之后`ICorDebugManagedCallback::LoadModule`回调传递将失败。</span><span class="sxs-lookup"><span data-stu-id="805ed-110">Attempts to call it after the `ICorDebugManagedCallback::LoadModule` callback has been delivered will fail.</span></span>  
  
 <span data-ttu-id="805ed-111">在 64 位或 Win9x 平台上不支持编辑并继续。</span><span class="sxs-lookup"><span data-stu-id="805ed-111">Edit and Continue is not supported on 64-bit or Win9x platforms.</span></span> <span data-ttu-id="805ed-112">因此，如果调用`SetJITCompilerFlags`CORDEBUG_JIT_ENABLE_ENC 标志设置这两个平台中的任何一个方法`dwFlags`、`SetJITCompilerFlags`方法和特定的所有方法编辑并继续，如[ICorDebugModule2::ApplyChanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md)，将会失败。</span><span class="sxs-lookup"><span data-stu-id="805ed-112">Therefore, if you call the `SetJITCompilerFlags` method on either of these two platforms with the CORDEBUG_JIT_ENABLE_ENC flag set in `dwFlags`, the `SetJITCompilerFlags` method and all methods specific to Edit and Continue, such as [ICorDebugModule2::ApplyChanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md), will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="805ed-113">要求</span><span class="sxs-lookup"><span data-stu-id="805ed-113">Requirements</span></span>  
 <span data-ttu-id="805ed-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="805ed-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="805ed-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="805ed-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="805ed-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="805ed-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="805ed-117">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="805ed-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
