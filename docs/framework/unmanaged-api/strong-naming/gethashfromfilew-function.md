---
title: "GetHashFromFileW 函数"
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
- GetHashFromFileW
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromFileW
helpviewer_keywords:
- GetHashFromFileW function [.NET Framework strong naming]
ms.assetid: 97c2d7a6-5376-45a1-ba65-146a249147cc
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d7d62526a6ac9bb06a7de8287c9687933402bfb8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="gethashfromfilew-function"></a><span data-ttu-id="43bf2-102">GetHashFromFileW 函数</span><span class="sxs-lookup"><span data-stu-id="43bf2-102">GetHashFromFileW Function</span></span>
<span data-ttu-id="43bf2-103">生成指定的 Unicode 字符串的文件的内容哈希代码。</span><span class="sxs-lookup"><span data-stu-id="43bf2-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
 <span data-ttu-id="43bf2-104">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="43bf2-104">This function has been deprecated.</span></span> <span data-ttu-id="43bf2-105">使用[iclrstrongname:: Gethashfromfilew](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)方法相反。</span><span class="sxs-lookup"><span data-stu-id="43bf2-105">Use the [ICLRStrongName::GetHashFromFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43bf2-106">语法</span><span class="sxs-lookup"><span data-stu-id="43bf2-106">Syntax</span></span>  
  
```  
HRESULT GetHashFromFileW (   
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="43bf2-107">参数</span><span class="sxs-lookup"><span data-stu-id="43bf2-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="43bf2-108">[in]Unicode 哈希的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="43bf2-108">[in] The Unicode name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="43bf2-109">[在中，out]要生成哈希时使用的算法。</span><span class="sxs-lookup"><span data-stu-id="43bf2-109">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="43bf2-110">有效算法是定义的 Win32 CryptoAPI。</span><span class="sxs-lookup"><span data-stu-id="43bf2-110">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="43bf2-111">如果`piHashAlg`设置为 0，则使用 CALG_SHA 1 的默认算法。</span><span class="sxs-lookup"><span data-stu-id="43bf2-111">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="43bf2-112">[out]包含生成的哈希的字节数组。</span><span class="sxs-lookup"><span data-stu-id="43bf2-112">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="43bf2-113">[in]指向缓冲区的最大大小`pbHash`。</span><span class="sxs-lookup"><span data-stu-id="43bf2-113">[in] The maximum size of the buffer pointed to by `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="43bf2-114">[out]大小，以字节为单位的`pbHash`。</span><span class="sxs-lookup"><span data-stu-id="43bf2-114">[out] The size, in bytes, of `pbHash`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43bf2-115">备注</span><span class="sxs-lookup"><span data-stu-id="43bf2-115">Remarks</span></span>  
 <span data-ttu-id="43bf2-116">此函数是与相同[GetHashFromFile](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfile-function.md)，只指定文件名称是 Unicode 而不是 ANSI。</span><span class="sxs-lookup"><span data-stu-id="43bf2-116">This function is the same as [GetHashFromFile](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfile-function.md), except that the file name specification is Unicode instead of ANSI.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43bf2-117">惠?</span><span class="sxs-lookup"><span data-stu-id="43bf2-117">Requirements</span></span>  
 <span data-ttu-id="43bf2-118">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="43bf2-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43bf2-119">**标头：** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="43bf2-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="43bf2-120">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="43bf2-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="43bf2-121">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43bf2-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43bf2-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="43bf2-122">See Also</span></span>  
 [<span data-ttu-id="43bf2-123">GetHashFromFileW 方法</span><span class="sxs-lookup"><span data-stu-id="43bf2-123">GetHashFromFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)  
 [<span data-ttu-id="43bf2-124">GetHashFromFile 方法</span><span class="sxs-lookup"><span data-stu-id="43bf2-124">GetHashFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)  
 [<span data-ttu-id="43bf2-125">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="43bf2-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
