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
ms.openlocfilehash: 3518a20567cdac8ed6587aa3dc06408ae6bf7b06
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmanagedcallbackloadclass-method"></a><span data-ttu-id="832cf-102">ICorDebugManagedCallback::LoadClass 方法</span><span class="sxs-lookup"><span data-stu-id="832cf-102">ICorDebugManagedCallback::LoadClass Method</span></span>
<span data-ttu-id="832cf-103">通知调试器已加载的类。</span><span class="sxs-lookup"><span data-stu-id="832cf-103">Notifies the debugger that a class has been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="832cf-104">语法</span><span class="sxs-lookup"><span data-stu-id="832cf-104">Syntax</span></span>  
  
```  
HRESULT LoadClass (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugClass     *c  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="832cf-105">参数</span><span class="sxs-lookup"><span data-stu-id="832cf-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="832cf-106">[in]指向一个表示已向其中加载类的应用程序域的 ICorDebugAppDomain 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="832cf-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain into which the class has been loaded.</span></span>  
  
 `c`  
 <span data-ttu-id="832cf-107">[in]指向一个 ICorDebugClass 对象，表示类的指针。</span><span class="sxs-lookup"><span data-stu-id="832cf-107">[in] A pointer to an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="832cf-108">备注</span><span class="sxs-lookup"><span data-stu-id="832cf-108">Remarks</span></span>  
 <span data-ttu-id="832cf-109">仅当包含的类模块启用了类加载，则会发生此回调。</span><span class="sxs-lookup"><span data-stu-id="832cf-109">This callback occurs only if class loading has been enabled for the module that contains the class.</span></span> <span data-ttu-id="832cf-110">类加载的动态模块始终处于启用状态。</span><span class="sxs-lookup"><span data-stu-id="832cf-110">Class loading is always enabled for dynamic modules.</span></span>  
  
 <span data-ttu-id="832cf-111">`LoadClass`回调提供适当的时候将断点绑定到动态模块中的新生成类。</span><span class="sxs-lookup"><span data-stu-id="832cf-111">The `LoadClass` callback provides an appropriate time to bind breakpoints to newly generated classes in dynamic modules.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="832cf-112">要求</span><span class="sxs-lookup"><span data-stu-id="832cf-112">Requirements</span></span>  
 <span data-ttu-id="832cf-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="832cf-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="832cf-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="832cf-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="832cf-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="832cf-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="832cf-116">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="832cf-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="832cf-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="832cf-117">See Also</span></span>  
 [<span data-ttu-id="832cf-118">UnloadClass 方法</span><span class="sxs-lookup"><span data-stu-id="832cf-118">UnloadClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md)  
 [<span data-ttu-id="832cf-119">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="832cf-119">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
