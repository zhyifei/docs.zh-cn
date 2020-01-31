---
title: ICorDebugManagedCallback::UnloadAssembly 方法
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UnloadAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UnloadAssembly
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadAssembly method [.NET Framework debugging]
- UnloadAssembly method [.NET Framework debugging]
ms.assetid: 6734321c-c8a9-401f-a558-cad715ec4a77
topic_type:
- apiref
ms.openlocfilehash: 06c08499298656c8314d72667d9dac88c8d11e6a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788345"
---
# <a name="icordebugmanagedcallbackunloadassembly-method"></a><span data-ttu-id="20377-102">ICorDebugManagedCallback::UnloadAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="20377-102">ICorDebugManagedCallback::UnloadAssembly Method</span></span>
<span data-ttu-id="20377-103">通知调试器已卸载了公共语言运行时程序集。</span><span class="sxs-lookup"><span data-stu-id="20377-103">Notifies the debugger that a common language runtime assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20377-104">语法</span><span class="sxs-lookup"><span data-stu-id="20377-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadAssembly (  
    [in] IcorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugAssembly   *pAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="20377-105">参数</span><span class="sxs-lookup"><span data-stu-id="20377-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="20377-106">中指向 ICorDebugAppDomain 对象的指针，该对象表示包含程序集的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="20377-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the assembly.</span></span>  
  
 `pAssembly`  
 <span data-ttu-id="20377-107">中指向表示程序集的 ICorDebugAssembly 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="20377-107">[in] A pointer to an ICorDebugAssembly object that represents the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="20377-108">备注</span><span class="sxs-lookup"><span data-stu-id="20377-108">Remarks</span></span>  
 <span data-ttu-id="20377-109">不应在此回调后使用该程序集。</span><span class="sxs-lookup"><span data-stu-id="20377-109">The assembly should not be used after this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20377-110">需求</span><span class="sxs-lookup"><span data-stu-id="20377-110">Requirements</span></span>  
 <span data-ttu-id="20377-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="20377-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20377-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="20377-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="20377-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="20377-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="20377-114">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20377-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20377-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="20377-115">See also</span></span>

- [<span data-ttu-id="20377-116">LoadAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="20377-116">LoadAssembly Method</span></span>](icordebugmanagedcallback-loadassembly-method.md)
- [<span data-ttu-id="20377-117">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="20377-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
