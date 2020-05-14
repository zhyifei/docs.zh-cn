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
ms.openlocfilehash: 061a2b9990d4b4d6398d0a31b97bc403a5f10de4
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "83397161"
---
# <a name="icoreclrdebugtargetfreememory-method"></a><span data-ttu-id="1439a-102">ICoreClrDebugTarget::FreeMemory 方法</span><span class="sxs-lookup"><span data-stu-id="1439a-102">ICoreClrDebugTarget::FreeMemory Method</span></span>
<span data-ttu-id="1439a-103">释放由[ICoreClrDebugTarget：： EnumProcesses](icoreclrdebugtarget-enumprocesses-method.md)和[ICoreClrDebugTarget：： EnumRuntimes](icoreclrdebugtarget-enumruntimes-method.md)方法分配的内存。</span><span class="sxs-lookup"><span data-stu-id="1439a-103">Frees the memory allocated by the [ICoreClrDebugTarget::EnumProcesses](icoreclrdebugtarget-enumprocesses-method.md) and [ICoreClrDebugTarget::EnumRuntimes](icoreclrdebugtarget-enumruntimes-method.md) methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1439a-104">语法</span><span class="sxs-lookup"><span data-stu-id="1439a-104">Syntax</span></span>  
  
```cpp  
void FreeMemory (  
     [in] void*pMemory);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1439a-105">参数</span><span class="sxs-lookup"><span data-stu-id="1439a-105">Parameters</span></span>  
 `pMemory`  
 <span data-ttu-id="1439a-106">中指向由[ICoreClrDebugTarget：： EnumProcesses](icoreclrdebugtarget-enumprocesses-method.md)或[ICoreClrDebugTarget：： EnumRuntimes](icoreclrdebugtarget-enumruntimes-method.md)方法返回的数组的指针。</span><span class="sxs-lookup"><span data-stu-id="1439a-106">[in] A pointer to the array that is returned by either the [ICoreClrDebugTarget::EnumProcesses](icoreclrdebugtarget-enumprocesses-method.md) or the [ICoreClrDebugTarget::EnumRuntimes](icoreclrdebugtarget-enumruntimes-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1439a-107">要求</span><span class="sxs-lookup"><span data-stu-id="1439a-107">Requirements</span></span>  
 <span data-ttu-id="1439a-108">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1439a-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1439a-109">**标头：** CoreClrRemoteDebuggingInterfaces</span><span class="sxs-lookup"><span data-stu-id="1439a-109">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="1439a-110">**库：** mscordbi_macx86</span><span class="sxs-lookup"><span data-stu-id="1439a-110">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="1439a-111">**.NET Framework 版本：** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="1439a-111">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1439a-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="1439a-112">See also</span></span>

- [<span data-ttu-id="1439a-113">ICoreClrDebugTarget 接口</span><span class="sxs-lookup"><span data-stu-id="1439a-113">ICoreClrDebugTarget Interface</span></span>](icoreclrdebugtarget-interface.md)
