---
title: ICorDebugManagedCallback::LoadModule 方法
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LoadModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LoadModule
helpviewer_keywords:
- ICorDebugManagedCallback::LoadModule method [.NET Framework debugging]
- LoadModule method [.NET Framework debugging]
ms.assetid: 66ec04e9-87cb-42ce-9720-81522abb5d5a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cbf538f066058b4f80d8cfd6cdf1a79683c79be9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413412"
---
# <a name="icordebugmanagedcallbackloadmodule-method"></a><span data-ttu-id="67062-102">ICorDebugManagedCallback::LoadModule 方法</span><span class="sxs-lookup"><span data-stu-id="67062-102">ICorDebugManagedCallback::LoadModule Method</span></span>
<span data-ttu-id="67062-103">通知调试器已成功加载了公共语言运行时 (CLR) 模块。</span><span class="sxs-lookup"><span data-stu-id="67062-103">Notifies the debugger that a common language runtime (CLR) module has been successfully loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67062-104">语法</span><span class="sxs-lookup"><span data-stu-id="67062-104">Syntax</span></span>  
  
```  
HRESULT LoadModule (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugModule    *pModule  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="67062-105">参数</span><span class="sxs-lookup"><span data-stu-id="67062-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="67062-106">[in]指向一个表示已向其中加载模块的应用程序域的 ICorDebugAppDomain 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="67062-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain into which the module has been loaded.</span></span>  
  
 `pModule`  
 <span data-ttu-id="67062-107">[in]指向一个 icor 调试模块对象，表示 CLR 模块的指针。</span><span class="sxs-lookup"><span data-stu-id="67062-107">[in] A pointer to an ICorDebugModule object that represents the CLR module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="67062-108">备注</span><span class="sxs-lookup"><span data-stu-id="67062-108">Remarks</span></span>  
 <span data-ttu-id="67062-109">`LoadModule`回调提供适当的时候检查模块的元数据、 设置在实时 (JIT) 编译器标志，或启用或禁用类加载模块的回调。</span><span class="sxs-lookup"><span data-stu-id="67062-109">The `LoadModule` callback provides an appropriate time to examine metadata for the module, set just-in-time (JIT) compiler flags, or enable or disable class loading callbacks for the module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67062-110">要求</span><span class="sxs-lookup"><span data-stu-id="67062-110">Requirements</span></span>  
 <span data-ttu-id="67062-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="67062-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67062-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="67062-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="67062-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="67062-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="67062-114">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67062-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67062-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="67062-115">See Also</span></span>  
 [<span data-ttu-id="67062-116">UnloadModule 方法</span><span class="sxs-lookup"><span data-stu-id="67062-116">UnloadModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadmodule-method.md)  
 [<span data-ttu-id="67062-117">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="67062-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
