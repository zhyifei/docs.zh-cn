---
title: "ICorDebugManagedCallback::LoadClass 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.LoadClass
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::LoadClass
helpviewer_keywords:
- ICorDebugManagedCallback::LoadClass method [.NET Framework debugging]
- LoadClass method [.NET Framework debugging]
ms.assetid: e58dac7b-85c3-41ca-b9aa-3a7fc9ae6680
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f3e732b418398e9c917085d22507c9304981b06a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallbackloadclass-method"></a><span data-ttu-id="6481a-102">ICorDebugManagedCallback::LoadClass 方法</span><span class="sxs-lookup"><span data-stu-id="6481a-102">ICorDebugManagedCallback::LoadClass Method</span></span>
<span data-ttu-id="6481a-103">通知调试器已加载的类。</span><span class="sxs-lookup"><span data-stu-id="6481a-103">Notifies the debugger that a class has been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6481a-104">语法</span><span class="sxs-lookup"><span data-stu-id="6481a-104">Syntax</span></span>  
  
```  
HRESULT LoadClass (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugClass     *c  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6481a-105">参数</span><span class="sxs-lookup"><span data-stu-id="6481a-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="6481a-106">[in]指向一个表示已向其中加载类的应用程序域的 ICorDebugAppDomain 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="6481a-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain into which the class has been loaded.</span></span>  
  
 `c`  
 <span data-ttu-id="6481a-107">[in]指向一个 ICorDebugClass 对象，表示类的指针。</span><span class="sxs-lookup"><span data-stu-id="6481a-107">[in] A pointer to an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6481a-108">备注</span><span class="sxs-lookup"><span data-stu-id="6481a-108">Remarks</span></span>  
 <span data-ttu-id="6481a-109">仅当包含的类模块启用了类加载，则会发生此回调。</span><span class="sxs-lookup"><span data-stu-id="6481a-109">This callback occurs only if class loading has been enabled for the module that contains the class.</span></span> <span data-ttu-id="6481a-110">类加载的动态模块始终处于启用状态。</span><span class="sxs-lookup"><span data-stu-id="6481a-110">Class loading is always enabled for dynamic modules.</span></span>  
  
 <span data-ttu-id="6481a-111">`LoadClass`回调提供适当的时候将断点绑定到动态模块中的新生成类。</span><span class="sxs-lookup"><span data-stu-id="6481a-111">The `LoadClass` callback provides an appropriate time to bind breakpoints to newly generated classes in dynamic modules.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6481a-112">惠?</span><span class="sxs-lookup"><span data-stu-id="6481a-112">Requirements</span></span>  
 <span data-ttu-id="6481a-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6481a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6481a-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6481a-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6481a-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6481a-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6481a-116">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6481a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6481a-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="6481a-117">See Also</span></span>  
 [<span data-ttu-id="6481a-118">UnloadClass 方法</span><span class="sxs-lookup"><span data-stu-id="6481a-118">UnloadClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md)  
 [<span data-ttu-id="6481a-119">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="6481a-119">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
