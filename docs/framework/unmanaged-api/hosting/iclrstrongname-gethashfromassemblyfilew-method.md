---
title: ICLRStrongName::GetHashFromAssemblyFileW 方法
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromAssemblyFileW
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromAssemblyFileW
helpviewer_keywords:
- ICLRStrongName::GetHashFromAssemblyFileW method [.NET Framework hosting]
- GetHashFromAssemblyFileW method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 5d0b44a2-5a14-44a2-9a0e-e8682fd4e106
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 36e4f07f04968579be2e42efad666b0453cc4796
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="iclrstrongnamegethashfromassemblyfilew-method"></a><span data-ttu-id="a9000-102">ICLRStrongName::GetHashFromAssemblyFileW 方法</span><span class="sxs-lookup"><span data-stu-id="a9000-102">ICLRStrongName::GetHashFromAssemblyFileW Method</span></span>
<span data-ttu-id="a9000-103">生成指定的 Unicode 字符串的文件的内容哈希代码。</span><span class="sxs-lookup"><span data-stu-id="a9000-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9000-104">语法</span><span class="sxs-lookup"><span data-stu-id="a9000-104">Syntax</span></span>  
  
```  
HRESULT GetHashFromAssemblyFileW (  
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a9000-105">参数</span><span class="sxs-lookup"><span data-stu-id="a9000-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="a9000-106">[in]要进行哈希处理的文件路径。</span><span class="sxs-lookup"><span data-stu-id="a9000-106">[in] The path to the file to be hashed.</span></span> <span data-ttu-id="a9000-107">此参数必须是 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="a9000-107">This parameter must be a Unicode string.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="a9000-108">[在中，out]一个指定的哈希算法的常数。</span><span class="sxs-lookup"><span data-stu-id="a9000-108">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="a9000-109">使用默认哈希算法的零。</span><span class="sxs-lookup"><span data-stu-id="a9000-109">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="a9000-110">[out]返回的哈希缓冲区中。</span><span class="sxs-lookup"><span data-stu-id="a9000-110">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="a9000-111">[in]请求的最大大小的`pbHash`。</span><span class="sxs-lookup"><span data-stu-id="a9000-111">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="a9000-112">[out]返回的大小，以字节为单位， `pbHash`。</span><span class="sxs-lookup"><span data-stu-id="a9000-112">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a9000-113">返回值</span><span class="sxs-lookup"><span data-stu-id="a9000-113">Return Value</span></span>  
 <span data-ttu-id="a9000-114">`S_OK` 如果成功，则完成的方法否则为该值指示失败的 HRESULT 值 (请参阅[常见的 HRESULT 值](http://go.microsoft.com/fwlink/?LinkId=213878)有关的列表)。</span><span class="sxs-lookup"><span data-stu-id="a9000-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9000-115">要求</span><span class="sxs-lookup"><span data-stu-id="a9000-115">Requirements</span></span>  
 <span data-ttu-id="a9000-116">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a9000-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9000-117">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="a9000-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="a9000-118">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="a9000-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a9000-119">**.NET framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9000-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9000-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="a9000-120">See Also</span></span>  
 [<span data-ttu-id="a9000-121">GetHashFromAssemblyFile 方法</span><span class="sxs-lookup"><span data-stu-id="a9000-121">GetHashFromAssemblyFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)  
 [<span data-ttu-id="a9000-122">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="a9000-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
