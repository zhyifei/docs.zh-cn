---
title: ICorDebugManagedCallback::LoadAssembly 方法
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LoadAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LoadAssembly
helpviewer_keywords:
- LoadAssembly method [.NET Framework debugging]
- ICorDebugManagedCallback::LoadAssembly method [.NET Framework debugging]
ms.assetid: 55cb673a-e240-43a6-a406-6912e7c0fe66
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f1d05914004d3c1fcc5ff109e854d01661367835
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413113"
---
# <a name="icordebugmanagedcallbackloadassembly-method"></a><span data-ttu-id="1828a-102">ICorDebugManagedCallback::LoadAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="1828a-102">ICorDebugManagedCallback::LoadAssembly Method</span></span>
<span data-ttu-id="1828a-103">通知调试器已成功加载公共语言运行时 (CLR) 程序集。</span><span class="sxs-lookup"><span data-stu-id="1828a-103">Notifies the debugger that a common language runtime (CLR) assembly has been successfully loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1828a-104">语法</span><span class="sxs-lookup"><span data-stu-id="1828a-104">Syntax</span></span>  
  
```  
HRESULT LoadAssembly (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugAssembly  *pAssembly  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1828a-105">参数</span><span class="sxs-lookup"><span data-stu-id="1828a-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="1828a-106">[in]指向表示程序集已在其中加载的应用程序域的 ICorDebugAppDomain 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="1828a-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain into which the assembly has been loaded.</span></span>  
  
 `pAssembly`  
 <span data-ttu-id="1828a-107">[in]指向表示程序集的 icor 调试程序集对象的指针。</span><span class="sxs-lookup"><span data-stu-id="1828a-107">[in] A pointer to an ICorDebugAssembly object that represents the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1828a-108">要求</span><span class="sxs-lookup"><span data-stu-id="1828a-108">Requirements</span></span>  
 <span data-ttu-id="1828a-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1828a-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1828a-110">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1828a-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1828a-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1828a-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1828a-112">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1828a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1828a-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="1828a-113">See Also</span></span>  
 [<span data-ttu-id="1828a-114">UnloadAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="1828a-114">UnloadAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadassembly-method.md)  
 [<span data-ttu-id="1828a-115">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="1828a-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
