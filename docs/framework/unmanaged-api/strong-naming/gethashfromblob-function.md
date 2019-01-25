---
title: GetHashFromBlob 函数
ms.date: 03/30/2017
api_name:
- GetHashFromBlob
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromBlob
helpviewer_keywords:
- GetHashFromBlob function [.NET Framework strong naming]
ms.assetid: b712d862-f2d0-4b55-87d4-65bbeadef982
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6bfa846aa66345e23e085ca148c7e3f492c529f4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54576338"
---
# <a name="gethashfromblob-function"></a><span data-ttu-id="63505-102">GetHashFromBlob 函数</span><span class="sxs-lookup"><span data-stu-id="63505-102">GetHashFromBlob Function</span></span>
<span data-ttu-id="63505-103">使用指定的哈希算法获取指定内存地址处的程序集的哈希。</span><span class="sxs-lookup"><span data-stu-id="63505-103">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="63505-104">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="63505-104">This function has been deprecated.</span></span> <span data-ttu-id="63505-105">使用[ICLRStronName::GetHashFromBlob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md)方法相反。</span><span class="sxs-lookup"><span data-stu-id="63505-105">Use the [ICLRStronName::GetHashFromBlob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63505-106">语法</span><span class="sxs-lookup"><span data-stu-id="63505-106">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="63505-107">参数</span><span class="sxs-lookup"><span data-stu-id="63505-107">Parameters</span></span>  
 `pbBlob`  
 <span data-ttu-id="63505-108">[in]指向要进行哈希处理的内存块的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="63505-108">[in] A pointer to the address of the memory block to be hashed.</span></span>  
  
 `cchBlob`  
 <span data-ttu-id="63505-109">[in]内存块的长度，以字节为单位。</span><span class="sxs-lookup"><span data-stu-id="63505-109">[in] The length, in bytes, of the memory block.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="63505-110">[in、 out]一个常量，它指定哈希算法。</span><span class="sxs-lookup"><span data-stu-id="63505-110">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="63505-111">使用默认的算法为零。</span><span class="sxs-lookup"><span data-stu-id="63505-111">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="63505-112">[out]返回的哈希缓冲区中。</span><span class="sxs-lookup"><span data-stu-id="63505-112">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="63505-113">[in]请求的最大大小的`pbHash`。</span><span class="sxs-lookup"><span data-stu-id="63505-113">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="63505-114">[out]大小 （字节），则返回的`pbHash`。</span><span class="sxs-lookup"><span data-stu-id="63505-114">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63505-115">要求</span><span class="sxs-lookup"><span data-stu-id="63505-115">Requirements</span></span>  
 <span data-ttu-id="63505-116">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="63505-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63505-117">**标头：** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="63505-117">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="63505-118">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="63505-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="63505-119">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63505-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63505-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="63505-120">See also</span></span>
- [<span data-ttu-id="63505-121">GetHashFromBlob 方法</span><span class="sxs-lookup"><span data-stu-id="63505-121">GetHashFromBlob Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md)
- [<span data-ttu-id="63505-122">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="63505-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
