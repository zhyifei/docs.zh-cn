---
title: "CreateCoreClrDebugTarget 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CreateCorClrDebugTarget
api_location: mscordbi_macx86.dll
api_type: COM
f1_keywords: CreateCoreClrDebugTarget
helpviewer_keywords:
- remote debugging API [Silverlight]
- Silverlight, remote debugging
- CreateCoreClrDebugTarget function
ms.assetid: 1cf4ca8e-d9bb-4633-9adf-5e24315bf87a
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e5b05cc6c84f2f891691613a485d35d008ef79e5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="createcoreclrdebugtarget-function"></a><span data-ttu-id="6501f-102">CreateCoreClrDebugTarget 函数</span><span class="sxs-lookup"><span data-stu-id="6501f-102">CreateCoreClrDebugTarget Function</span></span>
<span data-ttu-id="6501f-103">创建一个与运行在远程计算机上，并返回的调试器代理连接[ICoreClrDebugTarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md)可以用于查询正在运行的进程和远程计算机上加载的运行时对象。</span><span class="sxs-lookup"><span data-stu-id="6501f-103">Creates a connection to a debugger proxy that is running on a remote machine, and returns an [ICoreClrDebugTarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md) object that can be used to query running processes and loaded runtimes on the remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6501f-104">语法</span><span class="sxs-lookup"><span data-stu-id="6501f-104">Syntax</span></span>  
  
```  
HRESULT CreateCoreClrDebugTarget (  
       [in]  DWORD    dwAddress,   
       [out] ICoreClrDebugTarget**     ppTarget  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6501f-105">参数</span><span class="sxs-lookup"><span data-stu-id="6501f-105">Parameters</span></span>  
 `dwAddress`  
 <span data-ttu-id="6501f-106">[in] 远程目标计算机的 IPv4 地址。</span><span class="sxs-lookup"><span data-stu-id="6501f-106">[in] IPv4 address of a remote target machine.</span></span>  
  
 `ppTarget`  
 <span data-ttu-id="6501f-107">[out]指针到指向[ICoreClrDebugTarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md)将创建的对象。</span><span class="sxs-lookup"><span data-stu-id="6501f-107">[out] Pointer to a pointer to an [ICoreClrDebugTarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md) object that will be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6501f-108">返回值</span><span class="sxs-lookup"><span data-stu-id="6501f-108">Return Value</span></span>  
 <span data-ttu-id="6501f-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="6501f-109">S_OK</span></span>  
 <span data-ttu-id="6501f-110">已成功确定该进程中的 CLR 的数目，并已正确填写相应的句柄数组和路径数组。</span><span class="sxs-lookup"><span data-stu-id="6501f-110">The number of CLRs in the process was successfully determined, and the corresponding handle and path arrays were properly filled.</span></span>  
  
 <span data-ttu-id="6501f-111">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="6501f-111">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="6501f-112">无法为 `ppTarget` 分配足够的内存。</span><span class="sxs-lookup"><span data-stu-id="6501f-112">Unable to allocate enough memory for `ppTarget`.</span></span>  
  
 <span data-ttu-id="6501f-113">E_FAIL（或其他 E_ 返回代码）</span><span class="sxs-lookup"><span data-stu-id="6501f-113">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="6501f-114">其他故障。</span><span class="sxs-lookup"><span data-stu-id="6501f-114">Other failures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6501f-115">惠?</span><span class="sxs-lookup"><span data-stu-id="6501f-115">Requirements</span></span>  
 <span data-ttu-id="6501f-116">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6501f-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6501f-117">**标头：** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="6501f-117">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="6501f-118">**库：** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="6501f-118">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="6501f-119">**.NET framework 版本：** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="6501f-119">**.NET Framework Versions:** 3.5 SP1</span></span>
