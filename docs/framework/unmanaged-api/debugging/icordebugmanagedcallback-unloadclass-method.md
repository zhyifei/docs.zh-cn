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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b3eb8bf59ee2a91c62a6ff74b1903d92607a9ffe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995145"
---
# <a name="icordebugmanagedcallbackunloadclass-method"></a><span data-ttu-id="3f4e7-102">ICorDebugManagedCallback::UnloadClass 方法</span><span class="sxs-lookup"><span data-stu-id="3f4e7-102">ICorDebugManagedCallback::UnloadClass Method</span></span>
<span data-ttu-id="3f4e7-103">通知调试器卸载某个类。</span><span class="sxs-lookup"><span data-stu-id="3f4e7-103">Notifies the debugger that a class is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f4e7-104">语法</span><span class="sxs-lookup"><span data-stu-id="3f4e7-104">Syntax</span></span>  
  
```  
HRESULT UnloadClass (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugClass      *c  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f4e7-105">参数</span><span class="sxs-lookup"><span data-stu-id="3f4e7-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="3f4e7-106">[in]指向一个 ICorDebugAppDomain 对象，表示包含类的应用程序域的指针。</span><span class="sxs-lookup"><span data-stu-id="3f4e7-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the class.</span></span>  
  
 `c`  
 <span data-ttu-id="3f4e7-107">[in]指向一个 ICorDebugClass 对象，表示类的指针。</span><span class="sxs-lookup"><span data-stu-id="3f4e7-107">[in] A pointer to an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3f4e7-108">备注</span><span class="sxs-lookup"><span data-stu-id="3f4e7-108">Remarks</span></span>  
 <span data-ttu-id="3f4e7-109">不应进行此调用后引用类。</span><span class="sxs-lookup"><span data-stu-id="3f4e7-109">The class should not be referenced after this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f4e7-110">要求</span><span class="sxs-lookup"><span data-stu-id="3f4e7-110">Requirements</span></span>  
 <span data-ttu-id="3f4e7-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3f4e7-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f4e7-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3f4e7-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3f4e7-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f4e7-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f4e7-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f4e7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f4e7-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="3f4e7-115">See also</span></span>

- [<span data-ttu-id="3f4e7-116">LoadClass 方法</span><span class="sxs-lookup"><span data-stu-id="3f4e7-116">LoadClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md)
- [<span data-ttu-id="3f4e7-117">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="3f4e7-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
