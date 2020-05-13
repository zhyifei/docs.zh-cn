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
ms.openlocfilehash: 748a44075f7f73e54bab689bcb8865dee2b14946
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83207830"
---
# <a name="icordebugprocessenumerateappdomains-method"></a><span data-ttu-id="6fe8c-102">ICorDebugProcess::EnumerateAppDomains 方法</span><span class="sxs-lookup"><span data-stu-id="6fe8c-102">ICorDebugProcess::EnumerateAppDomains Method</span></span>
<span data-ttu-id="6fe8c-103">枚举此进程中的所有应用程序域。</span><span class="sxs-lookup"><span data-stu-id="6fe8c-103">Enumerates all the application domains in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fe8c-104">语法</span><span class="sxs-lookup"><span data-stu-id="6fe8c-104">Syntax</span></span>  
  
``` cpp
HRESULT EnumerateAppDomains(  
    [out] ICorDebugAppDomainEnum **ppAppDomains);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6fe8c-105">参数</span><span class="sxs-lookup"><span data-stu-id="6fe8c-105">Parameters</span></span>  
 `ppAppDomains`  
 <span data-ttu-id="6fe8c-106">弄一个指针，指向[ICorDebugAppDomainEnum](icordebugappdomainenum-interface.md)的地址，该地址是此进程中的应用程序域的枚举器。</span><span class="sxs-lookup"><span data-stu-id="6fe8c-106">[out] A pointer to the address of an [ICorDebugAppDomainEnum](icordebugappdomainenum-interface.md) that is an enumerator for the application domains in this process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6fe8c-107">备注</span><span class="sxs-lookup"><span data-stu-id="6fe8c-107">Remarks</span></span>  
 <span data-ttu-id="6fe8c-108">此方法可在[ICorDebugManagedCallback：： CreateProcess](icordebugmanagedcallback-createprocess-method.md)回调之前使用。</span><span class="sxs-lookup"><span data-stu-id="6fe8c-108">This method can be used before the [ICorDebugManagedCallback::CreateProcess](icordebugmanagedcallback-createprocess-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6fe8c-109">要求</span><span class="sxs-lookup"><span data-stu-id="6fe8c-109">Requirements</span></span>  
 <span data-ttu-id="6fe8c-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6fe8c-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6fe8c-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6fe8c-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6fe8c-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6fe8c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6fe8c-113">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6fe8c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
