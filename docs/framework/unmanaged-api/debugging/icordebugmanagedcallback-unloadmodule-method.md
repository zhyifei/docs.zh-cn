---
title: ICorDebugManagedCallback::UnloadModule 方法
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UnloadModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UnloadModule
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadModule method [.NET Framework debugging]
- UnloadModule method [.NET Framework debugging]
ms.assetid: b12bfcd9-1e29-48bf-9a3d-44bfae5df5e8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 12e42da015864e83663d2f4d74bab2a34052d760
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59083539"
---
# <a name="icordebugmanagedcallbackunloadmodule-method"></a><span data-ttu-id="41715-102">ICorDebugManagedCallback::UnloadModule 方法</span><span class="sxs-lookup"><span data-stu-id="41715-102">ICorDebugManagedCallback::UnloadModule Method</span></span>
<span data-ttu-id="41715-103">通知调试器已卸载了公共语言运行时模块 (DLL)。</span><span class="sxs-lookup"><span data-stu-id="41715-103">Notifies the debugger that a common language runtime module (DLL) has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41715-104">语法</span><span class="sxs-lookup"><span data-stu-id="41715-104">Syntax</span></span>  
  
```  
HRESULT UnloadModule (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugModule     *pModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="41715-105">参数</span><span class="sxs-lookup"><span data-stu-id="41715-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="41715-106">[in]指向一个 ICorDebugAppDomain 对象，表示包含该模块的应用程序域的指针。</span><span class="sxs-lookup"><span data-stu-id="41715-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the module.</span></span>  
  
 `pModule`  
 <span data-ttu-id="41715-107">[in]指向一个 icor 调试模块对象，表示该模块的指针。</span><span class="sxs-lookup"><span data-stu-id="41715-107">[in] A pointer to an ICorDebugModule object that represents the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="41715-108">备注</span><span class="sxs-lookup"><span data-stu-id="41715-108">Remarks</span></span>  
 <span data-ttu-id="41715-109">不应进行此调用后使用该模块。</span><span class="sxs-lookup"><span data-stu-id="41715-109">The module should not be used after this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41715-110">要求</span><span class="sxs-lookup"><span data-stu-id="41715-110">Requirements</span></span>  
 <span data-ttu-id="41715-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="41715-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41715-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="41715-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="41715-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="41715-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="41715-114">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="41715-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="41715-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="41715-115">See also</span></span>

- [<span data-ttu-id="41715-116">LoadModule 方法</span><span class="sxs-lookup"><span data-stu-id="41715-116">LoadModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadmodule-method.md)
- [<span data-ttu-id="41715-117">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="41715-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
