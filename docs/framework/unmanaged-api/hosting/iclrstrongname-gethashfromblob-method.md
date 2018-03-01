---
title: "ICLRStrongName::GetHashFromBlob 方法"
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
- ICLRStrongName.GetHashFromBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromBlob
helpviewer_keywords:
- ICLRStrongName::GetHashFromBlob method [.NET Framework hosting]
- GetHashFromBlob method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: f91d0f89-f356-49ac-aafb-50fad963c13d
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1947441e395ddb9d9d0fd9c4b02e7e991b1c84a2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongnamegethashfromblob-method"></a><span data-ttu-id="34618-102">ICLRStrongName::GetHashFromBlob 方法</span><span class="sxs-lookup"><span data-stu-id="34618-102">ICLRStrongName::GetHashFromBlob Method</span></span>
<span data-ttu-id="34618-103">获取指定的内存地址，使用指定的哈希算法的程序集哈希值。</span><span class="sxs-lookup"><span data-stu-id="34618-103">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34618-104">语法</span><span class="sxs-lookup"><span data-stu-id="34618-104">Syntax</span></span>  
  
```  
HRESULT GetHashFromBlob (  
    [in]  BYTE    *pbBlob,  
    [in]  DWORD   cchBlob,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE    *pbHash,  
    [in]  DWORD   cchHash,  
    [out] DWORD   *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="34618-105">参数</span><span class="sxs-lookup"><span data-stu-id="34618-105">Parameters</span></span>  
 `pbBlob`  
 <span data-ttu-id="34618-106">[in]指向要进行哈希处理的内存块的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="34618-106">[in] A pointer to the address of the memory block to be hashed.</span></span>  
  
 `cchBlob`  
 <span data-ttu-id="34618-107">[in]内存块的长度，以字节为单位。</span><span class="sxs-lookup"><span data-stu-id="34618-107">[in] The length, in bytes, of the memory block.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="34618-108">[在中，out]一个指定的哈希算法的常数。</span><span class="sxs-lookup"><span data-stu-id="34618-108">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="34618-109">使用默认算法的零。</span><span class="sxs-lookup"><span data-stu-id="34618-109">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="34618-110">[out]返回的哈希缓冲区中。</span><span class="sxs-lookup"><span data-stu-id="34618-110">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="34618-111">[in]请求的最大大小的`pbHash`。</span><span class="sxs-lookup"><span data-stu-id="34618-111">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="34618-112">[out]大小，以字节为单位，则返回的`pbHash`。</span><span class="sxs-lookup"><span data-stu-id="34618-112">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="34618-113">返回值</span><span class="sxs-lookup"><span data-stu-id="34618-113">Return Value</span></span>  
 <span data-ttu-id="34618-114">`S_OK`如果成功，则完成的方法否则为该值指示失败的 HRESULT 值 (请参阅[常见的 HRESULT 值](http://go.microsoft.com/fwlink/?LinkId=213878)有关的列表)。</span><span class="sxs-lookup"><span data-stu-id="34618-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34618-115">惠?</span><span class="sxs-lookup"><span data-stu-id="34618-115">Requirements</span></span>  
 <span data-ttu-id="34618-116">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="34618-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34618-117">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="34618-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="34618-118">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="34618-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="34618-119">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34618-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34618-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="34618-120">See Also</span></span>  
 [<span data-ttu-id="34618-121">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="34618-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
