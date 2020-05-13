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
ms.openlocfilehash: 07996a78d7f559de587c8a3eb2babfc06675169d
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212641"
---
# <a name="icordebugmanagedcallbackunloadassembly-method"></a><span data-ttu-id="9f8e2-102">ICorDebugManagedCallback::UnloadAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="9f8e2-102">ICorDebugManagedCallback::UnloadAssembly Method</span></span>
<span data-ttu-id="9f8e2-103">通知调试器已卸载了公共语言运行时程序集。</span><span class="sxs-lookup"><span data-stu-id="9f8e2-103">Notifies the debugger that a common language runtime assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f8e2-104">语法</span><span class="sxs-lookup"><span data-stu-id="9f8e2-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadAssembly (  
    [in] IcorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugAssembly   *pAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9f8e2-105">参数</span><span class="sxs-lookup"><span data-stu-id="9f8e2-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="9f8e2-106">中指向 ICorDebugAppDomain 对象的指针，该对象表示包含程序集的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="9f8e2-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the assembly.</span></span>  
  
 `pAssembly`  
 <span data-ttu-id="9f8e2-107">中指向表示程序集的 ICorDebugAssembly 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="9f8e2-107">[in] A pointer to an ICorDebugAssembly object that represents the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9f8e2-108">备注</span><span class="sxs-lookup"><span data-stu-id="9f8e2-108">Remarks</span></span>  
 <span data-ttu-id="9f8e2-109">不应在此回调后使用该程序集。</span><span class="sxs-lookup"><span data-stu-id="9f8e2-109">The assembly should not be used after this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f8e2-110">要求</span><span class="sxs-lookup"><span data-stu-id="9f8e2-110">Requirements</span></span>  
 <span data-ttu-id="9f8e2-111">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9f8e2-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f8e2-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9f8e2-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9f8e2-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9f8e2-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9f8e2-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f8e2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f8e2-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="9f8e2-115">See also</span></span>

- [<span data-ttu-id="9f8e2-116">LoadAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="9f8e2-116">LoadAssembly Method</span></span>](icordebugmanagedcallback-loadassembly-method.md)
- [<span data-ttu-id="9f8e2-117">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="9f8e2-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
