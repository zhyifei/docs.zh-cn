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
ms.openlocfilehash: e49c20d7627f666efd6561cee19ca505f723b714
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474431"
---
# <a name="icordebugmanagedcallbackloadmodule-method"></a><span data-ttu-id="b1545-102">ICorDebugManagedCallback::LoadModule 方法</span><span class="sxs-lookup"><span data-stu-id="b1545-102">ICorDebugManagedCallback::LoadModule Method</span></span>
<span data-ttu-id="b1545-103">通知调试器已成功加载了公共语言运行时 (CLR) 模块。</span><span class="sxs-lookup"><span data-stu-id="b1545-103">Notifies the debugger that a common language runtime (CLR) module has been successfully loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1545-104">语法</span><span class="sxs-lookup"><span data-stu-id="b1545-104">Syntax</span></span>  
  
```  
HRESULT LoadModule (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugModule    *pModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b1545-105">参数</span><span class="sxs-lookup"><span data-stu-id="b1545-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="b1545-106">[in]指向一个 ICorDebugAppDomain 对象，表示在其中加载的模块的应用程序域的指针。</span><span class="sxs-lookup"><span data-stu-id="b1545-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain into which the module has been loaded.</span></span>  
  
 `pModule`  
 <span data-ttu-id="b1545-107">[in]指向一个 icor 调试模块对象，表示 CLR 模块的指针。</span><span class="sxs-lookup"><span data-stu-id="b1545-107">[in] A pointer to an ICorDebugModule object that represents the CLR module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b1545-108">备注</span><span class="sxs-lookup"><span data-stu-id="b1545-108">Remarks</span></span>  
 <span data-ttu-id="b1545-109">`LoadModule`回调提供适当的时间来检查模块的元数据、 设置在实时 (JIT) 编译器标志，或启用或禁用类加载模块的回调。</span><span class="sxs-lookup"><span data-stu-id="b1545-109">The `LoadModule` callback provides an appropriate time to examine metadata for the module, set just-in-time (JIT) compiler flags, or enable or disable class loading callbacks for the module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1545-110">要求</span><span class="sxs-lookup"><span data-stu-id="b1545-110">Requirements</span></span>  
 <span data-ttu-id="b1545-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b1545-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1545-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b1545-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b1545-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b1545-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b1545-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1545-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1545-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="b1545-115">See also</span></span>
- [<span data-ttu-id="b1545-116">UnloadModule 方法</span><span class="sxs-lookup"><span data-stu-id="b1545-116">UnloadModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadmodule-method.md)
- [<span data-ttu-id="b1545-117">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="b1545-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
