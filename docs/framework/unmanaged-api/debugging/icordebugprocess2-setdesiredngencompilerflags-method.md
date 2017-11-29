---
title: "ICorDebugProcess2::SetDesiredNGENCompilerFlags 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess2.SetDesiredNGENCompilerFlags
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess2::SetDesiredNGENCompilerFlags
helpviewer_keywords:
- ICorDebugProcess2::SetDesiredNGENCompilerFlags method [.NET Framework debugging]
- SetDesiredNGENCompilerFlags method [.NET Framework debugging]
ms.assetid: 98320175-7c5e-4dbb-8683-86fa82e2641f
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 278f1f79fd929aa8a0c3233e68b30b1154e913ef
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess2setdesiredngencompilerflags-method"></a><span data-ttu-id="57cf5-102">ICorDebugProcess2::SetDesiredNGENCompilerFlags 方法</span><span class="sxs-lookup"><span data-stu-id="57cf5-102">ICorDebugProcess2::SetDesiredNGENCompilerFlags Method</span></span>
<span data-ttu-id="57cf5-103">设置必须在运行时便会将该映像加载到当前过程的顺序预编译映像中嵌入的标志。</span><span class="sxs-lookup"><span data-stu-id="57cf5-103">Sets the flags that must be embedded in a precompiled image in order for the runtime to load that image into the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57cf5-104">语法</span><span class="sxs-lookup"><span data-stu-id="57cf5-104">Syntax</span></span>  
  
```  
HRESULT SetDesiredNGENCompilerFlags (  
    [in] DWORD    pdwFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="57cf5-105">参数</span><span class="sxs-lookup"><span data-stu-id="57cf5-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="57cf5-106">[in]值为[CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md)指定的编译器标志枚举用于选择正确的预编译的映像。</span><span class="sxs-lookup"><span data-stu-id="57cf5-106">[in] A value of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration that specifies the compiler flags used to select the correct pre-compiled image.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="57cf5-107">备注</span><span class="sxs-lookup"><span data-stu-id="57cf5-107">Remarks</span></span>  
 <span data-ttu-id="57cf5-108">`SetDesiredNGENCompilerFlags`方法指定，以便运行时将该映像加载到此过程必须预编译的映像中嵌入的标志。</span><span class="sxs-lookup"><span data-stu-id="57cf5-108">The `SetDesiredNGENCompilerFlags` method specifies the flags that must be embedded in a precompiled image so that the runtime will load that image into this process.</span></span> <span data-ttu-id="57cf5-109">此方法设置的标志仅用于选择正确的预编译的映像。</span><span class="sxs-lookup"><span data-stu-id="57cf5-109">The flags set by this method are used only to select the correct precompiled image.</span></span> <span data-ttu-id="57cf5-110">如果不存在任何此类映像，运行时将加载的 Microsoft 中间语言 (MSIL) 映像，以及在实时 (JIT) 编译器。</span><span class="sxs-lookup"><span data-stu-id="57cf5-110">If no such image exists, the runtime will load the Microsoft intermediate language (MSIL) image and the just-in-time (JIT) compiler instead.</span></span> <span data-ttu-id="57cf5-111">在这种情况下，仍必须使用调试器[icordebugmodule2:: Setjitcompilerflags](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjitcompilerflags-method.md)将标志设置为 JIT 编译所需的方法。</span><span class="sxs-lookup"><span data-stu-id="57cf5-111">In that case, the debugger must still use the [ICorDebugModule2::SetJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjitcompilerflags-method.md) method to set the flags as desired for the JIT compilation.</span></span>  
  
 <span data-ttu-id="57cf5-112">如果图像是否加载，但某些 JIT 编译，则必须执行对该映像 （它将是这种情况，如果映像包含泛型），由指定的编译器标志`SetDesiredNGENCompilerFlags`方法将应用到额外的 JIT 编译。</span><span class="sxs-lookup"><span data-stu-id="57cf5-112">If an image is loaded, but some JIT compiling must take place for that image (which will be the case if the image contains generics), the compiler flags specified by the `SetDesiredNGENCompilerFlags` method will apply to the extra JIT compilation.</span></span>  
  
 <span data-ttu-id="57cf5-113">`SetDesiredNGENCompilerFlags`方法必须调用期间[icordebugmanagedcallback:: Createprocess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md)回调。</span><span class="sxs-lookup"><span data-stu-id="57cf5-113">The `SetDesiredNGENCompilerFlags` method must be called during the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback.</span></span> <span data-ttu-id="57cf5-114">尝试调用`SetDesiredNGENCompilerFlags`方法之后将失败。</span><span class="sxs-lookup"><span data-stu-id="57cf5-114">Attempts to call the `SetDesiredNGENCompilerFlags` method afterwards will fail.</span></span> <span data-ttu-id="57cf5-115">此外，将尝试设置标志，也可以定义在`CorDebugJITCompilerFlags`枚举或不合法给定进程将失败。</span><span class="sxs-lookup"><span data-stu-id="57cf5-115">Also, attempts to set flags that are either not defined in the `CorDebugJITCompilerFlags` enumeration or are not legal for the given process will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57cf5-116">要求</span><span class="sxs-lookup"><span data-stu-id="57cf5-116">Requirements</span></span>  
 <span data-ttu-id="57cf5-117">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="57cf5-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57cf5-118">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="57cf5-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="57cf5-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="57cf5-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="57cf5-120">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57cf5-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57cf5-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="57cf5-121">See Also</span></span>  
 [<span data-ttu-id="57cf5-122">ICorDebug 接口</span><span class="sxs-lookup"><span data-stu-id="57cf5-122">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
 [<span data-ttu-id="57cf5-123">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="57cf5-123">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
