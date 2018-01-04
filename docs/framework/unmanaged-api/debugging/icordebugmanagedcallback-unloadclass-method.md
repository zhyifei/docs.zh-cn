---
title: "ICorDebugManagedCallback::UnloadClass 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.UnloadClass
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::UnloadClass
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadClass method [.NET Framework debugging]
- UnloadClass method [.NET Framework debugging]
ms.assetid: 66a59b18-ce9a-41f4-b23b-4dd6753d6d36
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bc3e5b9eeae63e77f2dc8cc35b4bcef575711916
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallbackunloadclass-method"></a><span data-ttu-id="06b76-102">ICorDebugManagedCallback::UnloadClass 方法</span><span class="sxs-lookup"><span data-stu-id="06b76-102">ICorDebugManagedCallback::UnloadClass Method</span></span>
<span data-ttu-id="06b76-103">通知调试器卸载某个类。</span><span class="sxs-lookup"><span data-stu-id="06b76-103">Notifies the debugger that a class is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06b76-104">语法</span><span class="sxs-lookup"><span data-stu-id="06b76-104">Syntax</span></span>  
  
```  
HRESULT UnloadClass (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugClass      *c  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="06b76-105">参数</span><span class="sxs-lookup"><span data-stu-id="06b76-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="06b76-106">[in]指向一个表示包含类的应用程序域的 ICorDebugAppDomain 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="06b76-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the class.</span></span>  
  
 `c`  
 <span data-ttu-id="06b76-107">[in]指向一个 ICorDebugClass 对象，表示类的指针。</span><span class="sxs-lookup"><span data-stu-id="06b76-107">[in] A pointer to an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="06b76-108">备注</span><span class="sxs-lookup"><span data-stu-id="06b76-108">Remarks</span></span>  
 <span data-ttu-id="06b76-109">不应在此调用后引用类。</span><span class="sxs-lookup"><span data-stu-id="06b76-109">The class should not be referenced after this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06b76-110">惠?</span><span class="sxs-lookup"><span data-stu-id="06b76-110">Requirements</span></span>  
 <span data-ttu-id="06b76-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="06b76-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06b76-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="06b76-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="06b76-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="06b76-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="06b76-114">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06b76-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06b76-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="06b76-115">See Also</span></span>  
 [<span data-ttu-id="06b76-116">LoadClass 方法</span><span class="sxs-lookup"><span data-stu-id="06b76-116">LoadClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md)  
 [<span data-ttu-id="06b76-117">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="06b76-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
