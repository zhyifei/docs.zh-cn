---
title: GetHashFromFile 函数
ms.date: 03/30/2017
api_name:
- GetHashFromFile
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromFile
helpviewer_keywords:
- GetHashFromFile function [.NET Framework strong naming]
ms.assetid: b3c526a4-8fb4-4ad6-b6af-42ce9c06492e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f98f888280090bfa613acf6ae37bc60ab63c371e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33456509"
---
# <a name="gethashfromfile-function"></a><span data-ttu-id="c16e6-102">GetHashFromFile 函数</span><span class="sxs-lookup"><span data-stu-id="c16e6-102">GetHashFromFile Function</span></span>
<span data-ttu-id="c16e6-103">生成指定的文件的内容哈希代码。</span><span class="sxs-lookup"><span data-stu-id="c16e6-103">Generates a hash over the contents of the specified file.</span></span>  
  
 <span data-ttu-id="c16e6-104">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="c16e6-104">This function has been deprecated.</span></span> <span data-ttu-id="c16e6-105">使用[iclrstrongname:: Gethashfromfile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)方法相反。</span><span class="sxs-lookup"><span data-stu-id="c16e6-105">Use the [ICLRStrongName::GetHashFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c16e6-106">语法</span><span class="sxs-lookup"><span data-stu-id="c16e6-106">Syntax</span></span>  
  
```  
HRESULT GetHashFromFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,   
    [out] BYTE     *pbHash,      
    [in]  DWORD    cchHash,      
    [out] DWORD    *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c16e6-107">参数</span><span class="sxs-lookup"><span data-stu-id="c16e6-107">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="c16e6-108">[in]哈希的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="c16e6-108">[in] The name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="c16e6-109">[在中，out]要生成哈希时使用的算法。</span><span class="sxs-lookup"><span data-stu-id="c16e6-109">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="c16e6-110">有效算法是定义的 Win32 CryptoAPI。</span><span class="sxs-lookup"><span data-stu-id="c16e6-110">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="c16e6-111">如果`piHashAlg`设置为 0，则使用 CALG_SHA 1 的默认算法。</span><span class="sxs-lookup"><span data-stu-id="c16e6-111">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="c16e6-112">[out]包含生成的哈希的字节数组。</span><span class="sxs-lookup"><span data-stu-id="c16e6-112">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="c16e6-113">[in]缓冲区的最大大小，`pbHash`指向。</span><span class="sxs-lookup"><span data-stu-id="c16e6-113">[in] The maximum size of the buffer that `pbHash` points to.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="c16e6-114">[out]大小，以字节为单位，则返回的`pbHash`。</span><span class="sxs-lookup"><span data-stu-id="c16e6-114">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c16e6-115">备注</span><span class="sxs-lookup"><span data-stu-id="c16e6-115">Remarks</span></span>  
 <span data-ttu-id="c16e6-116">此函数是与相同[GetHashFromFileW](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfilew-function.md)，只指定文件名称是 ANSI 而不是 Unicode。</span><span class="sxs-lookup"><span data-stu-id="c16e6-116">This function is the same as [GetHashFromFileW](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfilew-function.md), except that the file name specification is ANSI instead of Unicode.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c16e6-117">要求</span><span class="sxs-lookup"><span data-stu-id="c16e6-117">Requirements</span></span>  
 <span data-ttu-id="c16e6-118">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c16e6-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c16e6-119">**标头：** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="c16e6-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="c16e6-120">**库：** 作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="c16e6-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c16e6-121">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c16e6-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c16e6-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="c16e6-122">See Also</span></span>  
 [<span data-ttu-id="c16e6-123">GetHashFromFile 方法</span><span class="sxs-lookup"><span data-stu-id="c16e6-123">GetHashFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)  
 [<span data-ttu-id="c16e6-124">GetHashFromFileW 方法</span><span class="sxs-lookup"><span data-stu-id="c16e6-124">GetHashFromFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)  
 [<span data-ttu-id="c16e6-125">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="c16e6-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
