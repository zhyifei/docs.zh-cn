---
title: ICoreClrDebugTarget::FreeMemory 方法
ms.date: 03/30/2017
api_name:
- ICoreDebugTarget.FreeMemory
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- ICoreClrDebugTarget::FreeMemory
helpviewer_keywords:
- remote debugging API [Silverlight]
- FreeMemory method, ICoreClrDebugTarget interface [Silverlight debugging]
- ICorClrDebugTarget::FreeMemory method [Silverlight debugging]
- Silverlight, remote debugging
ms.assetid: 98f2a0db-a6ec-4f9b-861d-f82485237d08
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1a3448512cb486419e524df012fcd1b8fcf639f1
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466370"
---
# <a name="icoreclrdebugtargetfreememory-method"></a><span data-ttu-id="ecbf3-102">ICoreClrDebugTarget::FreeMemory 方法</span><span class="sxs-lookup"><span data-stu-id="ecbf3-102">ICoreClrDebugTarget::FreeMemory Method</span></span>
<span data-ttu-id="ecbf3-103">释放分配的内存[icoreclrdebugtarget:: Enumprocesses](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumprocesses-method.md)并[icoreclrdebugtarget:: Enumruntimes](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumruntimes-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="ecbf3-103">Frees the memory allocated by the [ICoreClrDebugTarget::EnumProcesses](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumprocesses-method.md) and [ICoreClrDebugTarget::EnumRuntimes](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumruntimes-method.md) methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecbf3-104">语法</span><span class="sxs-lookup"><span data-stu-id="ecbf3-104">Syntax</span></span>  
  
```  
void FreeMemory (  
     [in] void*pMemory);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ecbf3-105">参数</span><span class="sxs-lookup"><span data-stu-id="ecbf3-105">Parameters</span></span>  
 `pMemory`  
 <span data-ttu-id="ecbf3-106">[in]指向通过以下任一方法返回的数组的指针[icoreclrdebugtarget:: Enumprocesses](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumprocesses-method.md)或[icoreclrdebugtarget:: Enumruntimes](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumruntimes-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="ecbf3-106">[in] A pointer to the array that is returned by either the [ICoreClrDebugTarget::EnumProcesses](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumprocesses-method.md) or the [ICoreClrDebugTarget::EnumRuntimes](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumruntimes-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ecbf3-107">要求</span><span class="sxs-lookup"><span data-stu-id="ecbf3-107">Requirements</span></span>  
 <span data-ttu-id="ecbf3-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ecbf3-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ecbf3-109">**标头：** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="ecbf3-109">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="ecbf3-110">**库：** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="ecbf3-110">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="ecbf3-111">**.NET framework 版本：** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="ecbf3-111">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecbf3-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="ecbf3-112">See also</span></span>
- [<span data-ttu-id="ecbf3-113">ICoreClrDebugTarget 接口</span><span class="sxs-lookup"><span data-stu-id="ecbf3-113">ICoreClrDebugTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md)
