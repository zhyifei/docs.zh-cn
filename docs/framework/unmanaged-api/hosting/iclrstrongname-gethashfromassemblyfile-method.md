---
title: "ICLRStrongName::GetHashFromAssemblyFile 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.GetHashFromAssemblyFile
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::GetHashFromAssemblyFile
helpviewer_keywords:
- ICLRStrongName::GetHashFromAssemblyFile method [.NET Framework hosting]
- GetHashFromAssemblyFile method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 0b67ea03-d474-4605-acaa-57455790250c
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9a205f4225269f959efec9576bea047fb51ea946
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iclrstrongnamegethashfromassemblyfile-method"></a><span data-ttu-id="edec4-102">ICLRStrongName::GetHashFromAssemblyFile 方法</span><span class="sxs-lookup"><span data-stu-id="edec4-102">ICLRStrongName::GetHashFromAssemblyFile Method</span></span>
<span data-ttu-id="edec4-103">获取使用指定的哈希算法对指定的程序集文件的哈希值。</span><span class="sxs-lookup"><span data-stu-id="edec4-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="edec4-104">语法</span><span class="sxs-lookup"><span data-stu-id="edec4-104">Syntax</span></span>  
  
```  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="edec4-105">参数</span><span class="sxs-lookup"><span data-stu-id="edec4-105">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="edec4-106">[in]要进行哈希处理的文件路径。</span><span class="sxs-lookup"><span data-stu-id="edec4-106">[in] The path to the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="edec4-107">[在中，out]一个指定的哈希算法的常数。</span><span class="sxs-lookup"><span data-stu-id="edec4-107">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="edec4-108">使用默认哈希算法的零。</span><span class="sxs-lookup"><span data-stu-id="edec4-108">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="edec4-109">[out]返回的哈希缓冲区中。</span><span class="sxs-lookup"><span data-stu-id="edec4-109">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="edec4-110">[in]请求的最大大小的`pbHash`。</span><span class="sxs-lookup"><span data-stu-id="edec4-110">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="edec4-111">[out]返回的大小，以字节为单位， `pbHash`。</span><span class="sxs-lookup"><span data-stu-id="edec4-111">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="edec4-112">返回值</span><span class="sxs-lookup"><span data-stu-id="edec4-112">Return Value</span></span>  
 <span data-ttu-id="edec4-113">`S_OK`如果成功，则完成的方法否则为该值指示失败的 HRESULT 值 (请参阅[常见的 HRESULT 值](http://go.microsoft.com/fwlink/?LinkId=213878)有关的列表)。</span><span class="sxs-lookup"><span data-stu-id="edec4-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="edec4-114">要求</span><span class="sxs-lookup"><span data-stu-id="edec4-114">Requirements</span></span>  
 <span data-ttu-id="edec4-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="edec4-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="edec4-116">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="edec4-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="edec4-117">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="edec4-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="edec4-118">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="edec4-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edec4-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="edec4-119">See Also</span></span>  
 [<span data-ttu-id="edec4-120">GetHashFromAssemblyFileW 方法</span><span class="sxs-lookup"><span data-stu-id="edec4-120">GetHashFromAssemblyFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md)  
 [<span data-ttu-id="edec4-121">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="edec4-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
