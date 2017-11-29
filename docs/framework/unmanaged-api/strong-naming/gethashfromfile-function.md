---
title: "GetHashFromFile 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetHashFromFile
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: GetHashFromFile
helpviewer_keywords: GetHashFromFile function [.NET Framework strong naming]
ms.assetid: b3c526a4-8fb4-4ad6-b6af-42ce9c06492e
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3c8e84881822cbafa8c43c3669f7522c390d5c5e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="gethashfromfile-function"></a><span data-ttu-id="67068-102">GetHashFromFile 函数</span><span class="sxs-lookup"><span data-stu-id="67068-102">GetHashFromFile Function</span></span>
<span data-ttu-id="67068-103">生成指定的文件的内容哈希代码。</span><span class="sxs-lookup"><span data-stu-id="67068-103">Generates a hash over the contents of the specified file.</span></span>  
  
 <span data-ttu-id="67068-104">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="67068-104">This function has been deprecated.</span></span> <span data-ttu-id="67068-105">使用[iclrstrongname:: Gethashfromfile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)方法相反。</span><span class="sxs-lookup"><span data-stu-id="67068-105">Use the [ICLRStrongName::GetHashFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67068-106">语法</span><span class="sxs-lookup"><span data-stu-id="67068-106">Syntax</span></span>  
  
```  
HRESULT GetHashFromFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,   
    [out] BYTE     *pbHash,      
    [in]  DWORD    cchHash,      
    [out] DWORD    *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="67068-107">参数</span><span class="sxs-lookup"><span data-stu-id="67068-107">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="67068-108">[in]哈希的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="67068-108">[in] The name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="67068-109">[在中，out]要生成哈希时使用的算法。</span><span class="sxs-lookup"><span data-stu-id="67068-109">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="67068-110">有效算法是定义的 Win32 CryptoAPI。</span><span class="sxs-lookup"><span data-stu-id="67068-110">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="67068-111">如果`piHashAlg`设置为 0，则使用 CALG_SHA 1 的默认算法。</span><span class="sxs-lookup"><span data-stu-id="67068-111">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="67068-112">[out]包含生成的哈希的字节数组。</span><span class="sxs-lookup"><span data-stu-id="67068-112">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="67068-113">[in]缓冲区的最大大小，`pbHash`指向。</span><span class="sxs-lookup"><span data-stu-id="67068-113">[in] The maximum size of the buffer that `pbHash` points to.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="67068-114">[out]大小，以字节为单位，则返回的`pbHash`。</span><span class="sxs-lookup"><span data-stu-id="67068-114">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="67068-115">备注</span><span class="sxs-lookup"><span data-stu-id="67068-115">Remarks</span></span>  
 <span data-ttu-id="67068-116">此函数是与相同[GetHashFromFileW](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfilew-function.md)，只指定文件名称是 ANSI 而不是 Unicode。</span><span class="sxs-lookup"><span data-stu-id="67068-116">This function is the same as [GetHashFromFileW](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfilew-function.md), except that the file name specification is ANSI instead of Unicode.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67068-117">要求</span><span class="sxs-lookup"><span data-stu-id="67068-117">Requirements</span></span>  
 <span data-ttu-id="67068-118">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="67068-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67068-119">**标头：** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="67068-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="67068-120">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="67068-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="67068-121">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67068-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67068-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="67068-122">See Also</span></span>  
 [<span data-ttu-id="67068-123">GetHashFromFile 方法</span><span class="sxs-lookup"><span data-stu-id="67068-123">GetHashFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)  
 [<span data-ttu-id="67068-124">GetHashFromFileW 方法</span><span class="sxs-lookup"><span data-stu-id="67068-124">GetHashFromFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)  
 [<span data-ttu-id="67068-125">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="67068-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
