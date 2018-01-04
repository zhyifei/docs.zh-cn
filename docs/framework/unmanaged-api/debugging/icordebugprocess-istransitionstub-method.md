---
title: "ICorDebugProcess::IsTransitionStub 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess.IsTransitionStub
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess::IsTransitionStub
helpviewer_keywords:
- ICorDebugProcess::IsTransitionStub method [.NET Framework debugging]
- IsTransitionStub method [.NET Framework debugging]
ms.assetid: f7653317-7e48-4163-be03-f50f1a4b0f70
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9fe38cf5f53c2514b845238c1d52fa12df526fdd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocessistransitionstub-method"></a><span data-ttu-id="5feea-102">ICorDebugProcess::IsTransitionStub 方法</span><span class="sxs-lookup"><span data-stu-id="5feea-102">ICorDebugProcess::IsTransitionStub Method</span></span>
<span data-ttu-id="5feea-103">获取一个值，该值指示是否处于存根，将导致向托管代码转换内的地址。</span><span class="sxs-lookup"><span data-stu-id="5feea-103">Gets a value that indicates whether an address is inside a stub that will cause a transition to managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5feea-104">语法</span><span class="sxs-lookup"><span data-stu-id="5feea-104">Syntax</span></span>  
  
```  
HRESULT IsTransitionStub(  
    [in]  CORDB_ADDRESS address,  
    [out] BOOL *pbTransitionStub);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5feea-105">参数</span><span class="sxs-lookup"><span data-stu-id="5feea-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="5feea-106">[in]A`CORDB_ADDRESS`值，该值指定有问题的地址。</span><span class="sxs-lookup"><span data-stu-id="5feea-106">[in] A `CORDB_ADDRESS` value that specifies the address in question.</span></span>  
  
 `pbTransitionStub`  
 <span data-ttu-id="5feea-107">[out]一个布尔值，是一个指向`true`如果指定的地址位于存根，将导致转换为托管代码; 否则为 *`pbTransitionStub`是`false`。</span><span class="sxs-lookup"><span data-stu-id="5feea-107">[out] A pointer to a Boolean value that is `true` if the specified address is inside a stub that will cause a transition to managed code; otherwise *`pbTransitionStub` is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5feea-108">备注</span><span class="sxs-lookup"><span data-stu-id="5feea-108">Remarks</span></span>  
 <span data-ttu-id="5feea-109">`IsTransitionStub`方法可以使用由非托管的单步执行代码，以决定何时将单步执行控制权返回给托管分档器。</span><span class="sxs-lookup"><span data-stu-id="5feea-109">The `IsTransitionStub` method can be used by unmanaged stepping code to decide when to return stepping control to the managed stepper.</span></span>  
  
 <span data-ttu-id="5feea-110">你还可以标识转换存根 （stub） 通过查看可移植可执行 (PE) 文件中的信息。</span><span class="sxs-lookup"><span data-stu-id="5feea-110">You can also identity transition stubs by looking at information in the portable executable (PE) file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5feea-111">惠?</span><span class="sxs-lookup"><span data-stu-id="5feea-111">Requirements</span></span>  
 <span data-ttu-id="5feea-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5feea-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5feea-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5feea-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5feea-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5feea-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5feea-115">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5feea-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
