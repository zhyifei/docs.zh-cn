---
title: ICorDebugManagedCallback::LoadModule 方法
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LoadModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LoadModule
helpviewer_keywords:
- ICorDebugManagedCallback::LoadModule method [.NET Framework debugging]
- LoadModule method [.NET Framework debugging]
ms.assetid: 66ec04e9-87cb-42ce-9720-81522abb5d5a
topic_type:
- apiref
ms.openlocfilehash: 21a97f140a41f8f380c1334652bc2417e19659c6
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777136"
---
# <a name="icordebugmanagedcallbackloadmodule-method"></a><span data-ttu-id="1f594-102">ICorDebugManagedCallback::LoadModule 方法</span><span class="sxs-lookup"><span data-stu-id="1f594-102">ICorDebugManagedCallback::LoadModule Method</span></span>
<span data-ttu-id="1f594-103">通知调试器已成功加载公共语言运行时（CLR）模块。</span><span class="sxs-lookup"><span data-stu-id="1f594-103">Notifies the debugger that a common language runtime (CLR) module has been successfully loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f594-104">语法</span><span class="sxs-lookup"><span data-stu-id="1f594-104">Syntax</span></span>  
  
```cpp  
HRESULT LoadModule (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugModule    *pModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1f594-105">参数</span><span class="sxs-lookup"><span data-stu-id="1f594-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="1f594-106">中指向 ICorDebugAppDomain 对象的指针，该对象表示已加载该模块的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="1f594-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain into which the module has been loaded.</span></span>  
  
 `pModule`  
 <span data-ttu-id="1f594-107">中指向 ICorDebugModule 对象的指针，该对象表示 CLR 模块。</span><span class="sxs-lookup"><span data-stu-id="1f594-107">[in] A pointer to an ICorDebugModule object that represents the CLR module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1f594-108">备注</span><span class="sxs-lookup"><span data-stu-id="1f594-108">Remarks</span></span>  
 <span data-ttu-id="1f594-109">`LoadModule` 回调提供适当的时间来检查模块的元数据、设置实时（JIT）编译器标志，或者为模块启用或禁用类加载回调。</span><span class="sxs-lookup"><span data-stu-id="1f594-109">The `LoadModule` callback provides an appropriate time to examine metadata for the module, set just-in-time (JIT) compiler flags, or enable or disable class loading callbacks for the module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f594-110">需求</span><span class="sxs-lookup"><span data-stu-id="1f594-110">Requirements</span></span>  
 <span data-ttu-id="1f594-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1f594-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f594-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1f594-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1f594-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1f594-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1f594-114">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f594-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f594-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1f594-115">See also</span></span>

- [<span data-ttu-id="1f594-116">UnloadModule 方法</span><span class="sxs-lookup"><span data-stu-id="1f594-116">UnloadModule Method</span></span>](icordebugmanagedcallback-unloadmodule-method.md)
- [<span data-ttu-id="1f594-117">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="1f594-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
