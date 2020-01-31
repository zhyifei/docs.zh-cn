---
title: ICorDebugManagedCallback::UnloadClass 方法
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UnloadClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UnloadClass
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadClass method [.NET Framework debugging]
- UnloadClass method [.NET Framework debugging]
ms.assetid: 66a59b18-ce9a-41f4-b23b-4dd6753d6d36
topic_type:
- apiref
ms.openlocfilehash: f2f19987d22502acbe06bd5e5c14b0d6c17cbe24
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76781573"
---
# <a name="icordebugmanagedcallbackunloadclass-method"></a><span data-ttu-id="d4951-102">ICorDebugManagedCallback::UnloadClass 方法</span><span class="sxs-lookup"><span data-stu-id="d4951-102">ICorDebugManagedCallback::UnloadClass Method</span></span>
<span data-ttu-id="d4951-103">通知调试器正在卸载某个类。</span><span class="sxs-lookup"><span data-stu-id="d4951-103">Notifies the debugger that a class is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4951-104">语法</span><span class="sxs-lookup"><span data-stu-id="d4951-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadClass (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugClass      *c  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4951-105">参数</span><span class="sxs-lookup"><span data-stu-id="d4951-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="d4951-106">中指向 ICorDebugAppDomain 对象的指针，该对象表示包含类的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="d4951-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the class.</span></span>  
  
 `c`  
 <span data-ttu-id="d4951-107">中指向 ICorDebugClass 对象的指针，该对象表示类。</span><span class="sxs-lookup"><span data-stu-id="d4951-107">[in] A pointer to an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4951-108">备注</span><span class="sxs-lookup"><span data-stu-id="d4951-108">Remarks</span></span>  
 <span data-ttu-id="d4951-109">不应在此调用后引用此类。</span><span class="sxs-lookup"><span data-stu-id="d4951-109">The class should not be referenced after this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4951-110">需求</span><span class="sxs-lookup"><span data-stu-id="d4951-110">Requirements</span></span>  
 <span data-ttu-id="d4951-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d4951-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4951-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d4951-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d4951-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d4951-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d4951-114">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4951-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4951-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d4951-115">See also</span></span>

- [<span data-ttu-id="d4951-116">LoadClass 方法</span><span class="sxs-lookup"><span data-stu-id="d4951-116">LoadClass Method</span></span>](icordebugmanagedcallback-loadclass-method.md)
- [<span data-ttu-id="d4951-117">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="d4951-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
