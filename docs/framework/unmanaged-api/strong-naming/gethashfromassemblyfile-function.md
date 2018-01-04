---
title: "GetHashFromAssemblyFile 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetHashFromAssemblyFile
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: GetHashFromAssemblyFile
helpviewer_keywords: GetHashFromAssemblyFile function [.NET Framework strong naming]
ms.assetid: 751ed69f-b7ab-4e07-80de-e17ca9319b0c
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ed5de637f8b8d51e2619ba205d89c753b27722bb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="gethashfromassemblyfile-function"></a><span data-ttu-id="43150-102">GetHashFromAssemblyFile 函数</span><span class="sxs-lookup"><span data-stu-id="43150-102">GetHashFromAssemblyFile Function</span></span>
<span data-ttu-id="43150-103">获取使用指定的哈希算法对指定的程序集文件的哈希值。</span><span class="sxs-lookup"><span data-stu-id="43150-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="43150-104">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="43150-104">This function has been deprecated.</span></span> <span data-ttu-id="43150-105">使用[iclrstrongname:: Gethashfromassemblyfile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)方法相反。</span><span class="sxs-lookup"><span data-stu-id="43150-105">Use the [ICLRStrongName::GetHashFromAssemblyFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43150-106">语法</span><span class="sxs-lookup"><span data-stu-id="43150-106">Syntax</span></span>  
  
```  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="43150-107">参数</span><span class="sxs-lookup"><span data-stu-id="43150-107">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="43150-108">[in]要进行哈希处理的文件路径。</span><span class="sxs-lookup"><span data-stu-id="43150-108">[in] The path to the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="43150-109">[在中，out]一个指定的哈希算法的常数。</span><span class="sxs-lookup"><span data-stu-id="43150-109">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="43150-110">使用默认哈希算法的零。</span><span class="sxs-lookup"><span data-stu-id="43150-110">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="43150-111">[out]返回的哈希缓冲区中。</span><span class="sxs-lookup"><span data-stu-id="43150-111">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="43150-112">[in]请求的最大大小的`pbHash`。</span><span class="sxs-lookup"><span data-stu-id="43150-112">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="43150-113">[out]返回的大小，以字节为单位， `pbHash`。</span><span class="sxs-lookup"><span data-stu-id="43150-113">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43150-114">惠?</span><span class="sxs-lookup"><span data-stu-id="43150-114">Requirements</span></span>  
 <span data-ttu-id="43150-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="43150-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43150-116">**标头：** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="43150-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="43150-117">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="43150-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="43150-118">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43150-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43150-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="43150-119">See Also</span></span>  
 [<span data-ttu-id="43150-120">GetHashFromAssemblyFile 方法</span><span class="sxs-lookup"><span data-stu-id="43150-120">GetHashFromAssemblyFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)  
 [<span data-ttu-id="43150-121">GetHashFromAssemblyFileW 方法</span><span class="sxs-lookup"><span data-stu-id="43150-121">GetHashFromAssemblyFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md)  
 [<span data-ttu-id="43150-122">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="43150-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
