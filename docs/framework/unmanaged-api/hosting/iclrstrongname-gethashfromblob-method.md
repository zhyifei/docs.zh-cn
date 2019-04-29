---
title: ICLRStrongName::GetHashFromBlob 方法
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f84d50579feade09df1b42a8e2f0c6b3e6a94fac
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61771652"
---
# <a name="iclrstrongnamegethashfromblob-method"></a><span data-ttu-id="cd4e3-102">ICLRStrongName::GetHashFromBlob 方法</span><span class="sxs-lookup"><span data-stu-id="cd4e3-102">ICLRStrongName::GetHashFromBlob Method</span></span>
<span data-ttu-id="cd4e3-103">使用指定的哈希算法获取指定内存地址处的程序集的哈希。</span><span class="sxs-lookup"><span data-stu-id="cd4e3-103">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd4e3-104">语法</span><span class="sxs-lookup"><span data-stu-id="cd4e3-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="cd4e3-105">参数</span><span class="sxs-lookup"><span data-stu-id="cd4e3-105">Parameters</span></span>  
 `pbBlob`  
 <span data-ttu-id="cd4e3-106">[in]指向要进行哈希处理的内存块的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="cd4e3-106">[in] A pointer to the address of the memory block to be hashed.</span></span>  
  
 `cchBlob`  
 <span data-ttu-id="cd4e3-107">[in]内存块的长度，以字节为单位。</span><span class="sxs-lookup"><span data-stu-id="cd4e3-107">[in] The length, in bytes, of the memory block.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="cd4e3-108">[in、 out]一个常量，它指定哈希算法。</span><span class="sxs-lookup"><span data-stu-id="cd4e3-108">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="cd4e3-109">使用默认的算法为零。</span><span class="sxs-lookup"><span data-stu-id="cd4e3-109">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="cd4e3-110">[out]返回的哈希缓冲区中。</span><span class="sxs-lookup"><span data-stu-id="cd4e3-110">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="cd4e3-111">[in]请求的最大大小的`pbHash`。</span><span class="sxs-lookup"><span data-stu-id="cd4e3-111">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="cd4e3-112">[out]大小 （字节），则返回的`pbHash`。</span><span class="sxs-lookup"><span data-stu-id="cd4e3-112">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cd4e3-113">返回值</span><span class="sxs-lookup"><span data-stu-id="cd4e3-113">Return Value</span></span>  
 <span data-ttu-id="cd4e3-114">`S_OK` 如果成功，则完成的方法否则为指示失败的 HRESULT 值 (请参阅[常见的 HRESULT 值](https://go.microsoft.com/fwlink/?LinkId=213878)列表)。</span><span class="sxs-lookup"><span data-stu-id="cd4e3-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd4e3-115">要求</span><span class="sxs-lookup"><span data-stu-id="cd4e3-115">Requirements</span></span>  
 <span data-ttu-id="cd4e3-116">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cd4e3-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd4e3-117">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="cd4e3-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="cd4e3-118">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="cd4e3-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cd4e3-119">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd4e3-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd4e3-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="cd4e3-120">See also</span></span>

- [<span data-ttu-id="cd4e3-121">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="cd4e3-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
