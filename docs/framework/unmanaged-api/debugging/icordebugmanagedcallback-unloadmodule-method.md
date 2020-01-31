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
ms.openlocfilehash: 88ef9fd5a0aac19954a247d0215fe698ebe30d40
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788335"
---
# <a name="icordebugmanagedcallbackunloadmodule-method"></a><span data-ttu-id="59123-102">ICorDebugManagedCallback::UnloadModule 方法</span><span class="sxs-lookup"><span data-stu-id="59123-102">ICorDebugManagedCallback::UnloadModule Method</span></span>
<span data-ttu-id="59123-103">通知调试器已卸载了公共语言运行时模块（DLL）。</span><span class="sxs-lookup"><span data-stu-id="59123-103">Notifies the debugger that a common language runtime module (DLL) has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59123-104">语法</span><span class="sxs-lookup"><span data-stu-id="59123-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadModule (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugModule     *pModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="59123-105">参数</span><span class="sxs-lookup"><span data-stu-id="59123-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="59123-106">中指向 ICorDebugAppDomain 对象的指针，该对象表示包含模块的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="59123-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the module.</span></span>  
  
 `pModule`  
 <span data-ttu-id="59123-107">中指向表示模块的 ICorDebugModule 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="59123-107">[in] A pointer to an ICorDebugModule object that represents the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="59123-108">备注</span><span class="sxs-lookup"><span data-stu-id="59123-108">Remarks</span></span>  
 <span data-ttu-id="59123-109">此调用之后不应使用该模块。</span><span class="sxs-lookup"><span data-stu-id="59123-109">The module should not be used after this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59123-110">需求</span><span class="sxs-lookup"><span data-stu-id="59123-110">Requirements</span></span>  
 <span data-ttu-id="59123-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="59123-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59123-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="59123-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="59123-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="59123-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="59123-114">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59123-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59123-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="59123-115">See also</span></span>

- [<span data-ttu-id="59123-116">LoadModule 方法</span><span class="sxs-lookup"><span data-stu-id="59123-116">LoadModule Method</span></span>](icordebugmanagedcallback-loadmodule-method.md)
- [<span data-ttu-id="59123-117">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="59123-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
