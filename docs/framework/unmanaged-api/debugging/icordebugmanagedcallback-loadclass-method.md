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
ms.openlocfilehash: cc5a2e1de79d6ba04ff3bf2bf86e0cb7ce9a5c0b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788380"
---
# <a name="icordebugmanagedcallbackloadclass-method"></a><span data-ttu-id="3ce4e-102">ICorDebugManagedCallback::LoadClass 方法</span><span class="sxs-lookup"><span data-stu-id="3ce4e-102">ICorDebugManagedCallback::LoadClass Method</span></span>
<span data-ttu-id="3ce4e-103">通知调试器已加载某个类。</span><span class="sxs-lookup"><span data-stu-id="3ce4e-103">Notifies the debugger that a class has been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ce4e-104">语法</span><span class="sxs-lookup"><span data-stu-id="3ce4e-104">Syntax</span></span>  
  
```cpp  
HRESULT LoadClass (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugClass     *c  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3ce4e-105">参数</span><span class="sxs-lookup"><span data-stu-id="3ce4e-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="3ce4e-106">中指向 ICorDebugAppDomain 对象的指针，该对象表示要将该类加载到其中的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="3ce4e-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain into which the class has been loaded.</span></span>  
  
 `c`  
 <span data-ttu-id="3ce4e-107">中指向 ICorDebugClass 对象的指针，该对象表示类。</span><span class="sxs-lookup"><span data-stu-id="3ce4e-107">[in] A pointer to an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3ce4e-108">备注</span><span class="sxs-lookup"><span data-stu-id="3ce4e-108">Remarks</span></span>  
 <span data-ttu-id="3ce4e-109">只有在为包含类的模块启用了类加载的情况下，才会发生此回调。</span><span class="sxs-lookup"><span data-stu-id="3ce4e-109">This callback occurs only if class loading has been enabled for the module that contains the class.</span></span> <span data-ttu-id="3ce4e-110">对于动态模块，始终启用类加载。</span><span class="sxs-lookup"><span data-stu-id="3ce4e-110">Class loading is always enabled for dynamic modules.</span></span>  
  
 <span data-ttu-id="3ce4e-111">`LoadClass` 回调提供适当的时间将断点绑定到动态模块中新生成的类。</span><span class="sxs-lookup"><span data-stu-id="3ce4e-111">The `LoadClass` callback provides an appropriate time to bind breakpoints to newly generated classes in dynamic modules.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ce4e-112">需求</span><span class="sxs-lookup"><span data-stu-id="3ce4e-112">Requirements</span></span>  
 <span data-ttu-id="3ce4e-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3ce4e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ce4e-114">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3ce4e-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3ce4e-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3ce4e-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3ce4e-116">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ce4e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ce4e-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3ce4e-117">See also</span></span>

- [<span data-ttu-id="3ce4e-118">UnloadClass 方法</span><span class="sxs-lookup"><span data-stu-id="3ce4e-118">UnloadClass Method</span></span>](icordebugmanagedcallback-unloadclass-method.md)
- [<span data-ttu-id="3ce4e-119">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="3ce4e-119">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
