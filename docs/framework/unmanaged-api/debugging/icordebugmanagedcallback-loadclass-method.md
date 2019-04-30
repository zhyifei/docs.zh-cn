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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 39ce3e8329c4ff32b55341127f68a800246677df
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995210"
---
# <a name="icordebugmanagedcallbackloadclass-method"></a><span data-ttu-id="c0dc1-102">ICorDebugManagedCallback::LoadClass 方法</span><span class="sxs-lookup"><span data-stu-id="c0dc1-102">ICorDebugManagedCallback::LoadClass Method</span></span>
<span data-ttu-id="c0dc1-103">通知调试器已加载的类。</span><span class="sxs-lookup"><span data-stu-id="c0dc1-103">Notifies the debugger that a class has been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0dc1-104">语法</span><span class="sxs-lookup"><span data-stu-id="c0dc1-104">Syntax</span></span>  
  
```  
HRESULT LoadClass (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugClass     *c  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c0dc1-105">参数</span><span class="sxs-lookup"><span data-stu-id="c0dc1-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="c0dc1-106">[in]指向一个 ICorDebugAppDomain 对象，表示应用程序域已在其中加载类的指针。</span><span class="sxs-lookup"><span data-stu-id="c0dc1-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain into which the class has been loaded.</span></span>  
  
 `c`  
 <span data-ttu-id="c0dc1-107">[in]指向一个 ICorDebugClass 对象，表示类的指针。</span><span class="sxs-lookup"><span data-stu-id="c0dc1-107">[in] A pointer to an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c0dc1-108">备注</span><span class="sxs-lookup"><span data-stu-id="c0dc1-108">Remarks</span></span>  
 <span data-ttu-id="c0dc1-109">仅当类加载已启用包含的类的模块，会发生此回调。</span><span class="sxs-lookup"><span data-stu-id="c0dc1-109">This callback occurs only if class loading has been enabled for the module that contains the class.</span></span> <span data-ttu-id="c0dc1-110">类加载始终启用的动态模块。</span><span class="sxs-lookup"><span data-stu-id="c0dc1-110">Class loading is always enabled for dynamic modules.</span></span>  
  
 <span data-ttu-id="c0dc1-111">`LoadClass`回调提供适当的时候若要将断点绑定到动态模块中新生成的类。</span><span class="sxs-lookup"><span data-stu-id="c0dc1-111">The `LoadClass` callback provides an appropriate time to bind breakpoints to newly generated classes in dynamic modules.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0dc1-112">要求</span><span class="sxs-lookup"><span data-stu-id="c0dc1-112">Requirements</span></span>  
 <span data-ttu-id="c0dc1-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c0dc1-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0dc1-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c0dc1-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c0dc1-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c0dc1-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c0dc1-116">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0dc1-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0dc1-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="c0dc1-117">See also</span></span>

- [<span data-ttu-id="c0dc1-118">UnloadClass 方法</span><span class="sxs-lookup"><span data-stu-id="c0dc1-118">UnloadClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md)
- [<span data-ttu-id="c0dc1-119">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="c0dc1-119">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
