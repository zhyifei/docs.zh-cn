---
title: "ICorDebugManagedCallback::LoadModule 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.LoadModule
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::LoadModule
helpviewer_keywords:
- ICorDebugManagedCallback::LoadModule method [.NET Framework debugging]
- LoadModule method [.NET Framework debugging]
ms.assetid: 66ec04e9-87cb-42ce-9720-81522abb5d5a
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5d17001db68043f5d46a90738a8ad3e0635de762
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallbackloadmodule-method"></a><span data-ttu-id="1af89-102">ICorDebugManagedCallback::LoadModule 方法</span><span class="sxs-lookup"><span data-stu-id="1af89-102">ICorDebugManagedCallback::LoadModule Method</span></span>
<span data-ttu-id="1af89-103">通知调试器已成功加载了公共语言运行时 (CLR) 模块。</span><span class="sxs-lookup"><span data-stu-id="1af89-103">Notifies the debugger that a common language runtime (CLR) module has been successfully loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1af89-104">语法</span><span class="sxs-lookup"><span data-stu-id="1af89-104">Syntax</span></span>  
  
```  
HRESULT LoadModule (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugModule    *pModule  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1af89-105">参数</span><span class="sxs-lookup"><span data-stu-id="1af89-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="1af89-106">[in]指向一个表示已向其中加载模块的应用程序域的 ICorDebugAppDomain 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="1af89-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain into which the module has been loaded.</span></span>  
  
 `pModule`  
 <span data-ttu-id="1af89-107">[in]指向一个 icor 调试模块对象，表示 CLR 模块的指针。</span><span class="sxs-lookup"><span data-stu-id="1af89-107">[in] A pointer to an ICorDebugModule object that represents the CLR module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1af89-108">备注</span><span class="sxs-lookup"><span data-stu-id="1af89-108">Remarks</span></span>  
 <span data-ttu-id="1af89-109">`LoadModule`回调提供适当的时候检查模块的元数据、 设置在实时 (JIT) 编译器标志，或启用或禁用类加载模块的回调。</span><span class="sxs-lookup"><span data-stu-id="1af89-109">The `LoadModule` callback provides an appropriate time to examine metadata for the module, set just-in-time (JIT) compiler flags, or enable or disable class loading callbacks for the module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1af89-110">惠?</span><span class="sxs-lookup"><span data-stu-id="1af89-110">Requirements</span></span>  
 <span data-ttu-id="1af89-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1af89-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1af89-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1af89-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1af89-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1af89-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1af89-114">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1af89-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1af89-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="1af89-115">See Also</span></span>  
 [<span data-ttu-id="1af89-116">UnloadModule 方法</span><span class="sxs-lookup"><span data-stu-id="1af89-116">UnloadModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadmodule-method.md)  
 [<span data-ttu-id="1af89-117">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="1af89-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
