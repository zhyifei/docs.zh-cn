---
title: "ICLRStrongName::GetHashFromFileW 方法"
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
- ICLRStrongName.GetHashFromFileW
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromFileW
helpviewer_keywords:
- GetHashFromFileW method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::GetHashFromFileW method [.NET Framework hosting]
ms.assetid: c6ff45fc-905d-4c6e-b00c-97c6c7c55d99
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: eec58e0cf062e405c757a506e9c26955009b710b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongnamegethashfromfilew-method"></a><span data-ttu-id="8dc6f-102">ICLRStrongName::GetHashFromFileW 方法</span><span class="sxs-lookup"><span data-stu-id="8dc6f-102">ICLRStrongName::GetHashFromFileW Method</span></span>
<span data-ttu-id="8dc6f-103">生成指定的 Unicode 字符串的文件的内容哈希代码。</span><span class="sxs-lookup"><span data-stu-id="8dc6f-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8dc6f-104">语法</span><span class="sxs-lookup"><span data-stu-id="8dc6f-104">Syntax</span></span>  
  
```  
HRESULT GetHashFromFileW (   
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="8dc6f-105">参数</span><span class="sxs-lookup"><span data-stu-id="8dc6f-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="8dc6f-106">[in]Unicode 哈希的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="8dc6f-106">[in] The Unicode name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="8dc6f-107">[在中，out]要生成哈希时使用的算法。</span><span class="sxs-lookup"><span data-stu-id="8dc6f-107">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="8dc6f-108">有效算法是定义的 Win32 CryptoAPI。</span><span class="sxs-lookup"><span data-stu-id="8dc6f-108">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="8dc6f-109">如果`piHashAlg`设置为 0，则使用 CALG_SHA 1 的默认算法。</span><span class="sxs-lookup"><span data-stu-id="8dc6f-109">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="8dc6f-110">[out]包含生成的哈希的字节数组。</span><span class="sxs-lookup"><span data-stu-id="8dc6f-110">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="8dc6f-111">[in]指向缓冲区的最大大小`pbHash`。</span><span class="sxs-lookup"><span data-stu-id="8dc6f-111">[in] The maximum size of the buffer pointed to by `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="8dc6f-112">[out]大小，以字节为单位的`pbHash`。</span><span class="sxs-lookup"><span data-stu-id="8dc6f-112">[out] The size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8dc6f-113">返回值</span><span class="sxs-lookup"><span data-stu-id="8dc6f-113">Return Value</span></span>  
 <span data-ttu-id="8dc6f-114">`S_OK`如果成功，则完成的方法否则为该值指示失败的 HRESULT 值 (请参阅[常见的 HRESULT 值](http://go.microsoft.com/fwlink/?LinkId=213878)有关的列表)。</span><span class="sxs-lookup"><span data-stu-id="8dc6f-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8dc6f-115">备注</span><span class="sxs-lookup"><span data-stu-id="8dc6f-115">Remarks</span></span>  
 <span data-ttu-id="8dc6f-116">此方法等同于[iclrstrongname:: Gethashfromfile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)方法，只不过文件名规范是 Unicode 而不是 ANSI。</span><span class="sxs-lookup"><span data-stu-id="8dc6f-116">This method is the same as the [ICLRStrongName::GetHashFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md) method, except that the file name specification is Unicode instead of ANSI.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8dc6f-117">惠?</span><span class="sxs-lookup"><span data-stu-id="8dc6f-117">Requirements</span></span>  
 <span data-ttu-id="8dc6f-118">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8dc6f-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8dc6f-119">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="8dc6f-119">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="8dc6f-120">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="8dc6f-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8dc6f-121">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8dc6f-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8dc6f-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="8dc6f-122">See Also</span></span>  
 [<span data-ttu-id="8dc6f-123">GetHashFromFile 方法</span><span class="sxs-lookup"><span data-stu-id="8dc6f-123">GetHashFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)  
 [<span data-ttu-id="8dc6f-124">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="8dc6f-124">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
