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
ms.openlocfilehash: cfa313d286d0decad82f51bcedc582470549c8e1
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790776"
---
# <a name="icoreclrdebugtargetfreememory-method"></a><span data-ttu-id="fab18-102">ICoreClrDebugTarget::FreeMemory 方法</span><span class="sxs-lookup"><span data-stu-id="fab18-102">ICoreClrDebugTarget::FreeMemory Method</span></span>
<span data-ttu-id="fab18-103">释放由[ICoreClrDebugTarget：： EnumProcesses](icoreclrdebugtarget-enumprocesses-method.md)和[ICoreClrDebugTarget：： EnumRuntimes](icoreclrdebugtarget-enumruntimes-method.md)方法分配的内存。</span><span class="sxs-lookup"><span data-stu-id="fab18-103">Frees the memory allocated by the [ICoreClrDebugTarget::EnumProcesses](icoreclrdebugtarget-enumprocesses-method.md) and [ICoreClrDebugTarget::EnumRuntimes](icoreclrdebugtarget-enumruntimes-method.md) methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fab18-104">语法</span><span class="sxs-lookup"><span data-stu-id="fab18-104">Syntax</span></span>  
  
```cpp  
void FreeMemory (  
     [in] void*pMemory);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fab18-105">参数</span><span class="sxs-lookup"><span data-stu-id="fab18-105">Parameters</span></span>  
 `pMemory`  
 <span data-ttu-id="fab18-106">中指向由[ICoreClrDebugTarget：： EnumProcesses](icoreclrdebugtarget-enumprocesses-method.md)或[ICoreClrDebugTarget：： EnumRuntimes](icoreclrdebugtarget-enumruntimes-method.md)方法返回的数组的指针。</span><span class="sxs-lookup"><span data-stu-id="fab18-106">[in] A pointer to the array that is returned by either the [ICoreClrDebugTarget::EnumProcesses](icoreclrdebugtarget-enumprocesses-method.md) or the [ICoreClrDebugTarget::EnumRuntimes](icoreclrdebugtarget-enumruntimes-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fab18-107">需求</span><span class="sxs-lookup"><span data-stu-id="fab18-107">Requirements</span></span>  
 <span data-ttu-id="fab18-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fab18-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fab18-109">**标头：** CoreClrRemoteDebuggingInterfaces</span><span class="sxs-lookup"><span data-stu-id="fab18-109">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="fab18-110">**库：** mscordbi_macx86</span><span class="sxs-lookup"><span data-stu-id="fab18-110">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="fab18-111">**.NET Framework 版本：** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="fab18-111">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fab18-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fab18-112">See also</span></span>

- [<span data-ttu-id="fab18-113">ICoreClrDebugTarget 接口</span><span class="sxs-lookup"><span data-stu-id="fab18-113">ICoreClrDebugTarget Interface</span></span>](icoreclrdebugtarget-interface.md)
