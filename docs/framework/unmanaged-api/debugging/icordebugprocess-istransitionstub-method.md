---
title: ICorDebugProcess::IsTransitionStub 方法
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.IsTransitionStub
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::IsTransitionStub
helpviewer_keywords:
- ICorDebugProcess::IsTransitionStub method [.NET Framework debugging]
- IsTransitionStub method [.NET Framework debugging]
ms.assetid: f7653317-7e48-4163-be03-f50f1a4b0f70
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 18084cb69d2c620fc892cc05e5a561e8fda3bc1c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57488183"
---
# <a name="icordebugprocessistransitionstub-method"></a><span data-ttu-id="70328-102">ICorDebugProcess::IsTransitionStub 方法</span><span class="sxs-lookup"><span data-stu-id="70328-102">ICorDebugProcess::IsTransitionStub Method</span></span>
<span data-ttu-id="70328-103">获取一个值，指示的地址是否会导致转换为托管代码的存根内。</span><span class="sxs-lookup"><span data-stu-id="70328-103">Gets a value that indicates whether an address is inside a stub that will cause a transition to managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70328-104">语法</span><span class="sxs-lookup"><span data-stu-id="70328-104">Syntax</span></span>  
  
```  
HRESULT IsTransitionStub(  
    [in]  CORDB_ADDRESS address,  
    [out] BOOL *pbTransitionStub);  
```  
  
## <a name="parameters"></a><span data-ttu-id="70328-105">参数</span><span class="sxs-lookup"><span data-stu-id="70328-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="70328-106">[in]一个`CORDB_ADDRESS`值，该值指定相关的地址。</span><span class="sxs-lookup"><span data-stu-id="70328-106">[in] A `CORDB_ADDRESS` value that specifies the address in question.</span></span>  
  
 `pbTransitionStub`  
 <span data-ttu-id="70328-107">[out]一个布尔值，是一个指向`true`如果指定的地址位于存根 （stub） 将导致转换为托管代码; 否则为 \*`pbTransitionStub`是`false`。</span><span class="sxs-lookup"><span data-stu-id="70328-107">[out] A pointer to a Boolean value that is `true` if the specified address is inside a stub that will cause a transition to managed code; otherwise \*`pbTransitionStub` is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="70328-108">备注</span><span class="sxs-lookup"><span data-stu-id="70328-108">Remarks</span></span>  
 <span data-ttu-id="70328-109">`IsTransitionStub`方法可以使用由非托管的单步执行代码，以决定何时将单步执行控制返回到托管分档器。</span><span class="sxs-lookup"><span data-stu-id="70328-109">The `IsTransitionStub` method can be used by unmanaged stepping code to decide when to return stepping control to the managed stepper.</span></span>  
  
 <span data-ttu-id="70328-110">您还可以标识转换存根 （stub） 通过查看可移植可执行 (PE) 文件中的信息。</span><span class="sxs-lookup"><span data-stu-id="70328-110">You can also identity transition stubs by looking at information in the portable executable (PE) file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70328-111">要求</span><span class="sxs-lookup"><span data-stu-id="70328-111">Requirements</span></span>  
 <span data-ttu-id="70328-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="70328-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70328-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="70328-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="70328-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="70328-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="70328-115">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70328-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
