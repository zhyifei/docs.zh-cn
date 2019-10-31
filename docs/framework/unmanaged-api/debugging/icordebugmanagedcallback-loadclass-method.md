---
title: ICorDebugManagedCallback::LoadClass 方法
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LoadClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LoadClass
helpviewer_keywords:
- ICorDebugManagedCallback::LoadClass method [.NET Framework debugging]
- LoadClass method [.NET Framework debugging]
ms.assetid: e58dac7b-85c3-41ca-b9aa-3a7fc9ae6680
topic_type:
- apiref
ms.openlocfilehash: d23b695550c8444264934f7aca4fa185064e89c5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130732"
---
# <a name="icordebugmanagedcallbackloadclass-method"></a><span data-ttu-id="e6f78-102">ICorDebugManagedCallback::LoadClass 方法</span><span class="sxs-lookup"><span data-stu-id="e6f78-102">ICorDebugManagedCallback::LoadClass Method</span></span>
<span data-ttu-id="e6f78-103">通知调试器已加载某个类。</span><span class="sxs-lookup"><span data-stu-id="e6f78-103">Notifies the debugger that a class has been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6f78-104">语法</span><span class="sxs-lookup"><span data-stu-id="e6f78-104">Syntax</span></span>  
  
```cpp  
HRESULT LoadClass (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugClass     *c  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e6f78-105">参数</span><span class="sxs-lookup"><span data-stu-id="e6f78-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="e6f78-106">中指向 ICorDebugAppDomain 对象的指针，该对象表示要将该类加载到其中的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="e6f78-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain into which the class has been loaded.</span></span>  
  
 `c`  
 <span data-ttu-id="e6f78-107">中指向 ICorDebugClass 对象的指针，该对象表示类。</span><span class="sxs-lookup"><span data-stu-id="e6f78-107">[in] A pointer to an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e6f78-108">备注</span><span class="sxs-lookup"><span data-stu-id="e6f78-108">Remarks</span></span>  
 <span data-ttu-id="e6f78-109">只有在为包含类的模块启用了类加载的情况下，才会发生此回调。</span><span class="sxs-lookup"><span data-stu-id="e6f78-109">This callback occurs only if class loading has been enabled for the module that contains the class.</span></span> <span data-ttu-id="e6f78-110">对于动态模块，始终启用类加载。</span><span class="sxs-lookup"><span data-stu-id="e6f78-110">Class loading is always enabled for dynamic modules.</span></span>  
  
 <span data-ttu-id="e6f78-111">`LoadClass` 回调提供适当的时间将断点绑定到动态模块中新生成的类。</span><span class="sxs-lookup"><span data-stu-id="e6f78-111">The `LoadClass` callback provides an appropriate time to bind breakpoints to newly generated classes in dynamic modules.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6f78-112">要求</span><span class="sxs-lookup"><span data-stu-id="e6f78-112">Requirements</span></span>  
 <span data-ttu-id="e6f78-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e6f78-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6f78-114">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e6f78-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e6f78-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e6f78-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e6f78-116">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6f78-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6f78-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="e6f78-117">See also</span></span>

- [<span data-ttu-id="e6f78-118">UnloadClass 方法</span><span class="sxs-lookup"><span data-stu-id="e6f78-118">UnloadClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md)
- [<span data-ttu-id="e6f78-119">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="e6f78-119">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
