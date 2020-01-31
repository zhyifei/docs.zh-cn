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
ms.openlocfilehash: 80836cbbf82a97ccd6dc7251e5cbe934e0cbe66f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777274"
---
# <a name="icordebugmanagedcallbackloadassembly-method"></a><span data-ttu-id="63d1e-102">ICorDebugManagedCallback::LoadAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="63d1e-102">ICorDebugManagedCallback::LoadAssembly Method</span></span>
<span data-ttu-id="63d1e-103">通知调试器已成功加载公共语言运行时（CLR）程序集。</span><span class="sxs-lookup"><span data-stu-id="63d1e-103">Notifies the debugger that a common language runtime (CLR) assembly has been successfully loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63d1e-104">语法</span><span class="sxs-lookup"><span data-stu-id="63d1e-104">Syntax</span></span>  
  
```cpp  
HRESULT LoadAssembly (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugAssembly  *pAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="63d1e-105">参数</span><span class="sxs-lookup"><span data-stu-id="63d1e-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="63d1e-106">中指向 ICorDebugAppDomain 对象的指针，该对象表示已加载程序集的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="63d1e-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain into which the assembly has been loaded.</span></span>  
  
 `pAssembly`  
 <span data-ttu-id="63d1e-107">中指向表示程序集的 ICorDebugAssembly 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="63d1e-107">[in] A pointer to an ICorDebugAssembly object that represents the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63d1e-108">需求</span><span class="sxs-lookup"><span data-stu-id="63d1e-108">Requirements</span></span>  
 <span data-ttu-id="63d1e-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="63d1e-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63d1e-110">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="63d1e-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="63d1e-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="63d1e-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="63d1e-112">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63d1e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63d1e-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="63d1e-113">See also</span></span>

- [<span data-ttu-id="63d1e-114">UnloadAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="63d1e-114">UnloadAssembly Method</span></span>](icordebugmanagedcallback-unloadassembly-method.md)
- [<span data-ttu-id="63d1e-115">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="63d1e-115">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
