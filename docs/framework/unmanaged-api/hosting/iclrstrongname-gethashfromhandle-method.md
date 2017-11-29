---
title: "ICLRStrongName::GetHashFromHandle 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRStrongName.GetHashFromHandle
- ICLRStrongName.StrongNameCompareAssemblies
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::GetHashFromHandle
helpviewer_keywords:
- GetHashFromHandle method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::GetHashFromHandle method [.NET Framework hosting]
ms.assetid: 3bedbb7d-3cdd-4175-b370-10ae734062db
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 01fefe99e82584267b3c0f3e0e528dd798affa15
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="iclrstrongnamegethashfromhandle-method"></a><span data-ttu-id="a37d4-102">ICLRStrongName::GetHashFromHandle 方法</span><span class="sxs-lookup"><span data-stu-id="a37d4-102">ICLRStrongName::GetHashFromHandle Method</span></span>
<span data-ttu-id="a37d4-103">生成具有指定的文件句柄，使用指定的哈希算法的文件的内容哈希代码。</span><span class="sxs-lookup"><span data-stu-id="a37d4-103">Generates a hash over the contents of the file that has the specified file handle, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a37d4-104">语法</span><span class="sxs-lookup"><span data-stu-id="a37d4-104">Syntax</span></span>  
  
```  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a37d4-105">参数</span><span class="sxs-lookup"><span data-stu-id="a37d4-105">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="a37d4-106">[in]要进行哈希处理的文件句柄。</span><span class="sxs-lookup"><span data-stu-id="a37d4-106">[in] The handle of the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="a37d4-107">[在中，out]一个指定的哈希算法的常数。</span><span class="sxs-lookup"><span data-stu-id="a37d4-107">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="a37d4-108">使用默认算法的零。</span><span class="sxs-lookup"><span data-stu-id="a37d4-108">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="a37d4-109">[out]返回的哈希缓冲区中。</span><span class="sxs-lookup"><span data-stu-id="a37d4-109">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="a37d4-110">[in]请求的最大大小的`pbHash`。</span><span class="sxs-lookup"><span data-stu-id="a37d4-110">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="a37d4-111">[out]大小，以字节为单位，则返回的`pbHash`。</span><span class="sxs-lookup"><span data-stu-id="a37d4-111">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a37d4-112">返回值</span><span class="sxs-lookup"><span data-stu-id="a37d4-112">Return Value</span></span>  
 <span data-ttu-id="a37d4-113">`S_OK`如果成功，则完成的方法否则为该值指示失败的 HRESULT 值 (请参阅[常见的 HRESULT 值](http://go.microsoft.com/fwlink/?LinkId=213878)有关的列表)。</span><span class="sxs-lookup"><span data-stu-id="a37d4-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a37d4-114">要求</span><span class="sxs-lookup"><span data-stu-id="a37d4-114">Requirements</span></span>  
 <span data-ttu-id="a37d4-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a37d4-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a37d4-116">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="a37d4-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="a37d4-117">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="a37d4-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a37d4-118">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a37d4-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a37d4-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a37d4-119">See Also</span></span>  
 [<span data-ttu-id="a37d4-120">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="a37d4-120">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
