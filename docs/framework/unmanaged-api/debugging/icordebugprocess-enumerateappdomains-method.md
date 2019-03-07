---
title: ICorDebugProcess::EnumerateAppDomains 方法
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.EnumerateAppDomains
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::EnumerateAppDomains
helpviewer_keywords:
- ICorDebugProcess::EnumerateAppDomains method [.NET Framework debugging]
- EnumerateAppDomains method [.NET Framework debugging]
ms.assetid: d508981f-e2b2-445b-a649-69951c22702d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 02e051d311e447475bea724b0bd7420ee8b590f6
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57495723"
---
# <a name="icordebugprocessenumerateappdomains-method"></a><span data-ttu-id="63740-102">ICorDebugProcess::EnumerateAppDomains 方法</span><span class="sxs-lookup"><span data-stu-id="63740-102">ICorDebugProcess::EnumerateAppDomains Method</span></span>
<span data-ttu-id="63740-103">枚举在此过程中的所有应用程序域。</span><span class="sxs-lookup"><span data-stu-id="63740-103">Enumerates all the application domains in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63740-104">语法</span><span class="sxs-lookup"><span data-stu-id="63740-104">Syntax</span></span>  
  
```  
HRESULT EnumerateAppDomains(  
    [out] ICorDebugAppDomainEnum **ppAppDomains);  
```  
  
## <a name="parameters"></a><span data-ttu-id="63740-105">参数</span><span class="sxs-lookup"><span data-stu-id="63740-105">Parameters</span></span>  
 `ppAppDomains`  
 <span data-ttu-id="63740-106">[out]指向的地址的指针[ICorDebugAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-interface.md) ，它是此过程中的应用程序域的枚举器。</span><span class="sxs-lookup"><span data-stu-id="63740-106">[out] A pointer to the address of an [ICorDebugAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-interface.md) that is an enumerator for the application domains in this process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="63740-107">备注</span><span class="sxs-lookup"><span data-stu-id="63740-107">Remarks</span></span>  
 <span data-ttu-id="63740-108">可以使用此方法之前[icordebugmanagedcallback:: Createprocess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md)回调。</span><span class="sxs-lookup"><span data-stu-id="63740-108">This method can be used before the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63740-109">要求</span><span class="sxs-lookup"><span data-stu-id="63740-109">Requirements</span></span>  
 <span data-ttu-id="63740-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="63740-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63740-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="63740-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="63740-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="63740-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="63740-113">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63740-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
