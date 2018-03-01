---
title: "ICorDebugRemoteTarget::GetHostName 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugRemoteTarget.GetHostName
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget::GetHostName
helpviewer_keywords:
- ICorDebugRemoteTarget::GetHostName method [.NET Framework debugging]
- GetHostName method, ICorDebugRemoteTarget interface [.NET Framework debugging]
ms.assetid: 1c7276f7-7e54-470c-808c-e13745ac07a1
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 45fa4afebda00cb2549a5c18ba81c6bb4e8210e0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugremotetargetgethostname-method"></a><span data-ttu-id="431b6-102">ICorDebugRemoteTarget::GetHostName 方法</span><span class="sxs-lookup"><span data-stu-id="431b6-102">ICorDebugRemoteTarget::GetHostName Method</span></span>
<span data-ttu-id="431b6-103">返回远程调试目标计算机的完全限定域名或 IPv4 地址。</span><span class="sxs-lookup"><span data-stu-id="431b6-103">Returns the fully qualified domain name or IPv4 address of the remote debugging target machine.</span></span> <span data-ttu-id="431b6-104">此时不支持 IPV6。</span><span class="sxs-lookup"><span data-stu-id="431b6-104">IPV6 is not supported at this time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="431b6-105">语法</span><span class="sxs-lookup"><span data-stu-id="431b6-105">Syntax</span></span>  
  
```  
HRESULT GetHostName (  
    [in] ULONG32      cchHostName,  
    [out] ULONG32*    pcchHostName,  
    [out, size_is(cchHostName), length_is(*pcchHostName)]  
            WCHAR szHostName[]  
```  
  
#### <a name="parameters"></a><span data-ttu-id="431b6-106">参数</span><span class="sxs-lookup"><span data-stu-id="431b6-106">Parameters</span></span>  
 `cchHostName`  
 <span data-ttu-id="431b6-107">[in]大小，以字符为单位的`szHostName`缓冲区。</span><span class="sxs-lookup"><span data-stu-id="431b6-107">[in] The size, in characters, of the `szHostName` buffer.</span></span> <span data-ttu-id="431b6-108">如果此参数为 0（零），`szHostName` 必须为 null。</span><span class="sxs-lookup"><span data-stu-id="431b6-108">If this parameter is 0 (zero), `szHostName` must be null.</span></span>  
  
 `pcchHostName`  
 <span data-ttu-id="431b6-109">[out] 主机名或 IP 地址中的字符数，包括 null 结束符。</span><span class="sxs-lookup"><span data-stu-id="431b6-109">[out] The number of characters, including a null terminator, in the host name or IP address.</span></span> <span data-ttu-id="431b6-110">此参数可以为 null。</span><span class="sxs-lookup"><span data-stu-id="431b6-110">This parameter can be null.</span></span>  
  
 `szHostName`  
 <span data-ttu-id="431b6-111">[out] 包含主机名或 IP 地址的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="431b6-111">[out] Buffer that contains the host name or IP address.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="431b6-112">返回值</span><span class="sxs-lookup"><span data-stu-id="431b6-112">Return Value</span></span>  
 <span data-ttu-id="431b6-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="431b6-113">S_OK</span></span>  
 <span data-ttu-id="431b6-114">主机名或 IP 地址成功返回。</span><span class="sxs-lookup"><span data-stu-id="431b6-114">The host name or IP address was successfully returned.</span></span>  
  
 <span data-ttu-id="431b6-115">E_FAIL（或其他 E_ 返回代码）</span><span class="sxs-lookup"><span data-stu-id="431b6-115">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="431b6-116">无法返回主机名或 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="431b6-116">Unable to return the host name or IP address.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="431b6-117">备注</span><span class="sxs-lookup"><span data-stu-id="431b6-117">Remarks</span></span>  
 <span data-ttu-id="431b6-118">此方法由调试器编写器实现。</span><span class="sxs-lookup"><span data-stu-id="431b6-118">This method is implemented by the debugger writer.</span></span> <span data-ttu-id="431b6-119">它必须遵循多次调用范例：第一次调用时，调用方将 null 传递到 `cchHostName` 和 `szHostName`，并且 `pcchHostName` 返回所需缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="431b6-119">It must follow the multiple call paradigm: On the first call, the caller passes null to both `cchHostName` and `szHostName`, and `pcchHostName` returns the size of the required buffer .</span></span> <span data-ttu-id="431b6-120">第二次调用时，先前返回的大小在 `cchHostName` 中传递，相应大小的缓冲区在 `szHostName` 中传递。</span><span class="sxs-lookup"><span data-stu-id="431b6-120">On the second call, the size that was previously returned is passed in `cchHostName`, and an appropriately sized buffer is passed in `szHostName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="431b6-121">惠?</span><span class="sxs-lookup"><span data-stu-id="431b6-121">Requirements</span></span>  
 <span data-ttu-id="431b6-122">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="431b6-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="431b6-123">**标头：** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="431b6-123">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="431b6-124">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="431b6-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="431b6-125">**.NET framework 版本：** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="431b6-125">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="431b6-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="431b6-126">See Also</span></span>  
 [<span data-ttu-id="431b6-127">ICorDebugRemoteTarget 接口</span><span class="sxs-lookup"><span data-stu-id="431b6-127">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)  
 [<span data-ttu-id="431b6-128">ICorDebug 接口</span><span class="sxs-lookup"><span data-stu-id="431b6-128">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
