---
title: CreateCoreClrDebugTarget 函数
ms.date: 03/30/2017
api_name:
- CreateCorClrDebugTarget
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CreateCoreClrDebugTarget
helpviewer_keywords:
- remote debugging API [Silverlight]
- Silverlight, remote debugging
- CreateCoreClrDebugTarget function
ms.assetid: 1cf4ca8e-d9bb-4633-9adf-5e24315bf87a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 48ce5381c745669b813f5b28d801add7daba7825
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57470052"
---
# <a name="createcoreclrdebugtarget-function"></a><span data-ttu-id="c9a67-102">CreateCoreClrDebugTarget 函数</span><span class="sxs-lookup"><span data-stu-id="c9a67-102">CreateCoreClrDebugTarget Function</span></span>
<span data-ttu-id="c9a67-103">创建一个与远程计算机上运行，并返回的调试器代理连接[ICoreClrDebugTarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md)可用于查询正在运行的进程和远程计算机上加载的运行时的对象。</span><span class="sxs-lookup"><span data-stu-id="c9a67-103">Creates a connection to a debugger proxy that is running on a remote machine, and returns an [ICoreClrDebugTarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md) object that can be used to query running processes and loaded runtimes on the remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9a67-104">语法</span><span class="sxs-lookup"><span data-stu-id="c9a67-104">Syntax</span></span>  
  
```  
HRESULT CreateCoreClrDebugTarget (  
       [in]  DWORD    dwAddress,   
       [out] ICoreClrDebugTarget**     ppTarget  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c9a67-105">参数</span><span class="sxs-lookup"><span data-stu-id="c9a67-105">Parameters</span></span>  
 `dwAddress`  
 <span data-ttu-id="c9a67-106">[in] 远程目标计算机的 IPv4 地址。</span><span class="sxs-lookup"><span data-stu-id="c9a67-106">[in] IPv4 address of a remote target machine.</span></span>  
  
 `ppTarget`  
 <span data-ttu-id="c9a67-107">[out]指针到指向[ICoreClrDebugTarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md)将创建的对象。</span><span class="sxs-lookup"><span data-stu-id="c9a67-107">[out] Pointer to a pointer to an [ICoreClrDebugTarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md) object that will be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c9a67-108">返回值</span><span class="sxs-lookup"><span data-stu-id="c9a67-108">Return Value</span></span>  
 <span data-ttu-id="c9a67-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="c9a67-109">S_OK</span></span>  
 <span data-ttu-id="c9a67-110">已成功确定该进程中的 CLR 的数目，并已正确填写相应的句柄数组和路径数组。</span><span class="sxs-lookup"><span data-stu-id="c9a67-110">The number of CLRs in the process was successfully determined, and the corresponding handle and path arrays were properly filled.</span></span>  
  
 <span data-ttu-id="c9a67-111">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="c9a67-111">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="c9a67-112">无法为 `ppTarget` 分配足够的内存。</span><span class="sxs-lookup"><span data-stu-id="c9a67-112">Unable to allocate enough memory for `ppTarget`.</span></span>  
  
 <span data-ttu-id="c9a67-113">E_FAIL（或其他 E_ 返回代码）</span><span class="sxs-lookup"><span data-stu-id="c9a67-113">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="c9a67-114">其他故障。</span><span class="sxs-lookup"><span data-stu-id="c9a67-114">Other failures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9a67-115">要求</span><span class="sxs-lookup"><span data-stu-id="c9a67-115">Requirements</span></span>  
 <span data-ttu-id="c9a67-116">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c9a67-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9a67-117">**标头：** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="c9a67-117">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="c9a67-118">**库：** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="c9a67-118">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="c9a67-119">**.NET framework 版本：** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="c9a67-119">**.NET Framework Versions:** 3.5 SP1</span></span>
