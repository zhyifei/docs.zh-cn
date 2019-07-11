---
title: ICorDebugAppDomain::GetProcess 方法
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetProcess
helpviewer_keywords:
- GetProcess method, ICorDebugAppDomain interface [.NET Framework debugging]
- ICorDebugAppDomain::GetProcess method [.NET Framework debugging]
ms.assetid: 9d0b9628-a91c-40d0-b9bc-00b34a396b8f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eebb0c39cb8ae69dfce1e865f2784bbe9a408786
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737830"
---
# <a name="icordebugappdomaingetprocess-method"></a><span data-ttu-id="f4324-102">ICorDebugAppDomain::GetProcess 方法</span><span class="sxs-lookup"><span data-stu-id="f4324-102">ICorDebugAppDomain::GetProcess Method</span></span>
<span data-ttu-id="f4324-103">获取包含应用程序域的进程。</span><span class="sxs-lookup"><span data-stu-id="f4324-103">Gets the process containing the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4324-104">语法</span><span class="sxs-lookup"><span data-stu-id="f4324-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess (  
    [out] ICorDebugProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f4324-105">参数</span><span class="sxs-lookup"><span data-stu-id="f4324-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="f4324-106">[out]指向表示流程 ICorDebugProcess 对象的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="f4324-106">[out] A pointer to the address of an ICorDebugProcess object that represents the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4324-107">要求</span><span class="sxs-lookup"><span data-stu-id="f4324-107">Requirements</span></span>  
 <span data-ttu-id="f4324-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f4324-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4324-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f4324-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f4324-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f4324-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f4324-111">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4324-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
