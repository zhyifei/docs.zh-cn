---
title: "ICLRStrongName::GetHashFromFile 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.GetHashFromFile
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::GetHashFromFile
helpviewer_keywords:
- ICLRStrongName::GetHashFromFile method [.NET Framework hosting]
- GetHashFromFile method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 9e50480a-8ada-4044-b2a5-97bb14ed3525
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bccdb01e098015f61a29ba267da1f3ec37543fcd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iclrstrongnamegethashfromfile-method"></a><span data-ttu-id="1530d-102">ICLRStrongName::GetHashFromFile 方法</span><span class="sxs-lookup"><span data-stu-id="1530d-102">ICLRStrongName::GetHashFromFile Method</span></span>
<span data-ttu-id="1530d-103">生成指定的文件的内容哈希代码。</span><span class="sxs-lookup"><span data-stu-id="1530d-103">Generates a hash over the contents of the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1530d-104">语法</span><span class="sxs-lookup"><span data-stu-id="1530d-104">Syntax</span></span>  
  
```  
HRESULT GetHashFromFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,   
    [out] BYTE     *pbHash,      
    [in]  DWORD    cchHash,      
    [out] DWORD    *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1530d-105">参数</span><span class="sxs-lookup"><span data-stu-id="1530d-105">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="1530d-106">[in]哈希的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="1530d-106">[in] The name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="1530d-107">[在中，out]要生成哈希时使用的算法。</span><span class="sxs-lookup"><span data-stu-id="1530d-107">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="1530d-108">有效算法是定义的 Win32 CryptoAPI。</span><span class="sxs-lookup"><span data-stu-id="1530d-108">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="1530d-109">如果`piHashAlg`设置为 0，则使用 CALG_SHA 1 的默认算法。</span><span class="sxs-lookup"><span data-stu-id="1530d-109">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="1530d-110">[out]包含生成的哈希的字节数组。</span><span class="sxs-lookup"><span data-stu-id="1530d-110">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="1530d-111">[in]缓冲区的最大大小，`pbHash`指向。</span><span class="sxs-lookup"><span data-stu-id="1530d-111">[in] The maximum size of the buffer that `pbHash` points to.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="1530d-112">[out]大小，以字节为单位，则返回的`pbHash`。</span><span class="sxs-lookup"><span data-stu-id="1530d-112">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1530d-113">返回值</span><span class="sxs-lookup"><span data-stu-id="1530d-113">Return Value</span></span>  
 <span data-ttu-id="1530d-114">`S_OK`如果成功，则完成的方法否则为该值指示失败的 HRESULT 值 (请参阅[常见的 HRESULT 值](http://go.microsoft.com/fwlink/?LinkId=213878)有关的列表)。</span><span class="sxs-lookup"><span data-stu-id="1530d-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1530d-115">备注</span><span class="sxs-lookup"><span data-stu-id="1530d-115">Remarks</span></span>  
 <span data-ttu-id="1530d-116">此方法等同于[iclrstrongname:: Gethashfromfilew](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)方法，只不过文件名规范是 ANSI 而不是 Unicode。</span><span class="sxs-lookup"><span data-stu-id="1530d-116">This method is the same as the [ICLRStrongName::GetHashFromFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md) method, except that the file name specification is ANSI instead of Unicode.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1530d-117">要求</span><span class="sxs-lookup"><span data-stu-id="1530d-117">Requirements</span></span>  
 <span data-ttu-id="1530d-118">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1530d-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1530d-119">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="1530d-119">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="1530d-120">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="1530d-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1530d-121">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1530d-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1530d-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1530d-122">See Also</span></span>  
 [<span data-ttu-id="1530d-123">GetHashFromFileW 方法</span><span class="sxs-lookup"><span data-stu-id="1530d-123">GetHashFromFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)  
 [<span data-ttu-id="1530d-124">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="1530d-124">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
