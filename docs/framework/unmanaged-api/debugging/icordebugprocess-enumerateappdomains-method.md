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
ms.openlocfilehash: e09e25503ad00ab3542f0c4f50221b6014b25561
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128883"
---
# <a name="icordebugprocessenumerateappdomains-method"></a><span data-ttu-id="e5cae-102">ICorDebugProcess::EnumerateAppDomains 方法</span><span class="sxs-lookup"><span data-stu-id="e5cae-102">ICorDebugProcess::EnumerateAppDomains Method</span></span>
<span data-ttu-id="e5cae-103">枚举此进程中的所有应用程序域。</span><span class="sxs-lookup"><span data-stu-id="e5cae-103">Enumerates all the application domains in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5cae-104">语法</span><span class="sxs-lookup"><span data-stu-id="e5cae-104">Syntax</span></span>  
  
``` cpp 
HRESULT EnumerateAppDomains(  
    [out] ICorDebugAppDomainEnum **ppAppDomains);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5cae-105">参数</span><span class="sxs-lookup"><span data-stu-id="e5cae-105">Parameters</span></span>  
 `ppAppDomains`  
 <span data-ttu-id="e5cae-106">弄一个指针，指向[ICorDebugAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-interface.md)的地址，该地址是此进程中的应用程序域的枚举器。</span><span class="sxs-lookup"><span data-stu-id="e5cae-106">[out] A pointer to the address of an [ICorDebugAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-interface.md) that is an enumerator for the application domains in this process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5cae-107">备注</span><span class="sxs-lookup"><span data-stu-id="e5cae-107">Remarks</span></span>  
 <span data-ttu-id="e5cae-108">此方法可在[ICorDebugManagedCallback：： CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md)回调之前使用。</span><span class="sxs-lookup"><span data-stu-id="e5cae-108">This method can be used before the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5cae-109">要求</span><span class="sxs-lookup"><span data-stu-id="e5cae-109">Requirements</span></span>  
 <span data-ttu-id="e5cae-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e5cae-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5cae-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e5cae-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e5cae-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5cae-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e5cae-113">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5cae-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
