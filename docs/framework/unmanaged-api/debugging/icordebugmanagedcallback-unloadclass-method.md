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
ms.openlocfilehash: a7b71170f58ddfe0295da28b8c9fc73286b074e6
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212264"
---
# <a name="icordebugmanagedcallbackunloadclass-method"></a><span data-ttu-id="2e490-102">ICorDebugManagedCallback::UnloadClass 方法</span><span class="sxs-lookup"><span data-stu-id="2e490-102">ICorDebugManagedCallback::UnloadClass Method</span></span>
<span data-ttu-id="2e490-103">通知调试器正在卸载某个类。</span><span class="sxs-lookup"><span data-stu-id="2e490-103">Notifies the debugger that a class is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e490-104">语法</span><span class="sxs-lookup"><span data-stu-id="2e490-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadClass (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugClass      *c  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2e490-105">参数</span><span class="sxs-lookup"><span data-stu-id="2e490-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="2e490-106">中指向 ICorDebugAppDomain 对象的指针，该对象表示包含类的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="2e490-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the class.</span></span>  
  
 `c`  
 <span data-ttu-id="2e490-107">中指向 ICorDebugClass 对象的指针，该对象表示类。</span><span class="sxs-lookup"><span data-stu-id="2e490-107">[in] A pointer to an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2e490-108">备注</span><span class="sxs-lookup"><span data-stu-id="2e490-108">Remarks</span></span>  
 <span data-ttu-id="2e490-109">不应在此调用后引用此类。</span><span class="sxs-lookup"><span data-stu-id="2e490-109">The class should not be referenced after this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e490-110">要求</span><span class="sxs-lookup"><span data-stu-id="2e490-110">Requirements</span></span>  
 <span data-ttu-id="2e490-111">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2e490-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e490-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2e490-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2e490-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2e490-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2e490-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e490-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e490-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="2e490-115">See also</span></span>

- [<span data-ttu-id="2e490-116">LoadClass 方法</span><span class="sxs-lookup"><span data-stu-id="2e490-116">LoadClass Method</span></span>](icordebugmanagedcallback-loadclass-method.md)
- [<span data-ttu-id="2e490-117">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="2e490-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
