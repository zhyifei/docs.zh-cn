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
ms.openlocfilehash: b42079d138e754996470e07b884d49c1ebb625c3
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901170"
---
# <a name="iclrstrongnamegethashfromblob-method"></a><span data-ttu-id="6a774-102">ICLRStrongName::GetHashFromBlob 方法</span><span class="sxs-lookup"><span data-stu-id="6a774-102">ICLRStrongName::GetHashFromBlob Method</span></span>
<span data-ttu-id="6a774-103">使用指定的哈希算法获取指定内存地址处的程序集的哈希。</span><span class="sxs-lookup"><span data-stu-id="6a774-103">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a774-104">语法</span><span class="sxs-lookup"><span data-stu-id="6a774-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromBlob (  
    [in]  BYTE    *pbBlob,  
    [in]  DWORD   cchBlob,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE    *pbHash,  
    [in]  DWORD   cchHash,  
    [out] DWORD   *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6a774-105">参数</span><span class="sxs-lookup"><span data-stu-id="6a774-105">Parameters</span></span>  
 `pbBlob`  
 <span data-ttu-id="6a774-106">中一个指针，指向要进行哈希处理的内存块的地址。</span><span class="sxs-lookup"><span data-stu-id="6a774-106">[in] A pointer to the address of the memory block to be hashed.</span></span>  
  
 `cchBlob`  
 <span data-ttu-id="6a774-107">中内存块的长度（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="6a774-107">[in] The length, in bytes, of the memory block.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="6a774-108">[in，out]指定哈希算法的常量。</span><span class="sxs-lookup"><span data-stu-id="6a774-108">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="6a774-109">对于默认算法，使用零。</span><span class="sxs-lookup"><span data-stu-id="6a774-109">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="6a774-110">弄返回的哈希缓冲区。</span><span class="sxs-lookup"><span data-stu-id="6a774-110">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="6a774-111">中请求的最大 `pbHash`大小。</span><span class="sxs-lookup"><span data-stu-id="6a774-111">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="6a774-112">弄返回 `pbHash`的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="6a774-112">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6a774-113">返回值</span><span class="sxs-lookup"><span data-stu-id="6a774-113">Return Value</span></span>  
 <span data-ttu-id="6a774-114">如果方法已成功完成，则 `S_OK`;否则，表示失败的 HRESULT 值（请参阅列表的[常见 HRESULT 值](/windows/win32/seccrypto/common-hresult-values)）。</span><span class="sxs-lookup"><span data-stu-id="6a774-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a774-115">需求</span><span class="sxs-lookup"><span data-stu-id="6a774-115">Requirements</span></span>  
 <span data-ttu-id="6a774-116">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6a774-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a774-117">**标头：** MetaHost</span><span class="sxs-lookup"><span data-stu-id="6a774-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="6a774-118">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="6a774-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6a774-119">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a774-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a774-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6a774-120">See also</span></span>

- [<span data-ttu-id="6a774-121">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="6a774-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
