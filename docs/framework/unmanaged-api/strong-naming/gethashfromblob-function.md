---
title: "GetHashFromBlob 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetHashFromBlob
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: GetHashFromBlob
helpviewer_keywords: GetHashFromBlob function [.NET Framework strong naming]
ms.assetid: b712d862-f2d0-4b55-87d4-65bbeadef982
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4564ea36ed8dd4c5de0d1633ba791b47bc2a01b8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="gethashfromblob-function"></a><span data-ttu-id="a577b-102">GetHashFromBlob 函数</span><span class="sxs-lookup"><span data-stu-id="a577b-102">GetHashFromBlob Function</span></span>
<span data-ttu-id="a577b-103">获取指定的内存地址，使用指定的哈希算法的程序集哈希值。</span><span class="sxs-lookup"><span data-stu-id="a577b-103">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="a577b-104">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="a577b-104">This function has been deprecated.</span></span> <span data-ttu-id="a577b-105">使用[ICLRStronName::GetHashFromBlob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md)方法相反。</span><span class="sxs-lookup"><span data-stu-id="a577b-105">Use the [ICLRStronName::GetHashFromBlob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a577b-106">语法</span><span class="sxs-lookup"><span data-stu-id="a577b-106">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="a577b-107">参数</span><span class="sxs-lookup"><span data-stu-id="a577b-107">Parameters</span></span>  
 `pbBlob`  
 <span data-ttu-id="a577b-108">[in]指向要进行哈希处理的内存块的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="a577b-108">[in] A pointer to the address of the memory block to be hashed.</span></span>  
  
 `cchBlob`  
 <span data-ttu-id="a577b-109">[in]内存块的长度，以字节为单位。</span><span class="sxs-lookup"><span data-stu-id="a577b-109">[in] The length, in bytes, of the memory block.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="a577b-110">[在中，out]一个指定的哈希算法的常数。</span><span class="sxs-lookup"><span data-stu-id="a577b-110">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="a577b-111">使用默认算法的零。</span><span class="sxs-lookup"><span data-stu-id="a577b-111">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="a577b-112">[out]返回的哈希缓冲区中。</span><span class="sxs-lookup"><span data-stu-id="a577b-112">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="a577b-113">[in]请求的最大大小的`pbHash`。</span><span class="sxs-lookup"><span data-stu-id="a577b-113">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="a577b-114">[out]大小，以字节为单位，则返回的`pbHash`。</span><span class="sxs-lookup"><span data-stu-id="a577b-114">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a577b-115">惠?</span><span class="sxs-lookup"><span data-stu-id="a577b-115">Requirements</span></span>  
 <span data-ttu-id="a577b-116">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a577b-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a577b-117">**标头：** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="a577b-117">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="a577b-118">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="a577b-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a577b-119">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a577b-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a577b-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="a577b-120">See Also</span></span>  
 [<span data-ttu-id="a577b-121">GetHashFromBlob 方法</span><span class="sxs-lookup"><span data-stu-id="a577b-121">GetHashFromBlob Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md)  
 [<span data-ttu-id="a577b-122">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="a577b-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
