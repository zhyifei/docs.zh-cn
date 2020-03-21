---
title: ICLRStrongName::GetHashFromFile 方法
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromFile
helpviewer_keywords:
- ICLRStrongName::GetHashFromFile method [.NET Framework hosting]
- GetHashFromFile method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 9e50480a-8ada-4044-b2a5-97bb14ed3525
topic_type:
- apiref
ms.openlocfilehash: ed735c3d7830551581df35793f3f6fdc4953dc8c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178075"
---
# <a name="iclrstrongnamegethashfromfile-method"></a><span data-ttu-id="11859-102">ICLRStrongName::GetHashFromFile 方法</span><span class="sxs-lookup"><span data-stu-id="11859-102">ICLRStrongName::GetHashFromFile Method</span></span>
<span data-ttu-id="11859-103">生成指定文件内容的哈希。</span><span class="sxs-lookup"><span data-stu-id="11859-103">Generates a hash over the contents of the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11859-104">语法</span><span class="sxs-lookup"><span data-stu-id="11859-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,
    [out] BYTE     *pbHash,
    [in]  DWORD    cchHash,
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="11859-105">parameters</span><span class="sxs-lookup"><span data-stu-id="11859-105">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="11859-106">[在]要哈希的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="11859-106">[in] The name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="11859-107">[进出]生成哈希时使用的算法。</span><span class="sxs-lookup"><span data-stu-id="11859-107">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="11859-108">有效的算法是由 Win32 加密 API 定义的算法。</span><span class="sxs-lookup"><span data-stu-id="11859-108">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="11859-109">如果`piHashAlg`设置为 0，则使用默认算法CALG_SHA-1。</span><span class="sxs-lookup"><span data-stu-id="11859-109">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="11859-110">[出]包含生成的哈希的字节数组。</span><span class="sxs-lookup"><span data-stu-id="11859-110">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="11859-111">[在]`pbHash`指向的缓冲区的最大大小。</span><span class="sxs-lookup"><span data-stu-id="11859-111">[in] The maximum size of the buffer that `pbHash` points to.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="11859-112">[出]返回`pbHash`的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="11859-112">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="11859-113">返回值</span><span class="sxs-lookup"><span data-stu-id="11859-113">Return Value</span></span>  
 <span data-ttu-id="11859-114">`S_OK`如果方法成功完成;如果方法成功完成;否则，指示失败的 HRESULT 值（请参阅列表[的常用 HRESULT 值](/windows/win32/seccrypto/common-hresult-values)）。</span><span class="sxs-lookup"><span data-stu-id="11859-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="11859-115">备注</span><span class="sxs-lookup"><span data-stu-id="11859-115">Remarks</span></span>  
 <span data-ttu-id="11859-116">此方法与[ICLRStrongName：：getHashFromFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)方法相同，只不过文件名规范是 ANSI 而不是 Unicode。</span><span class="sxs-lookup"><span data-stu-id="11859-116">This method is the same as the [ICLRStrongName::GetHashFromFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md) method, except that the file name specification is ANSI instead of Unicode.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11859-117">要求</span><span class="sxs-lookup"><span data-stu-id="11859-117">Requirements</span></span>  
 <span data-ttu-id="11859-118">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="11859-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11859-119">**标题：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="11859-119">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="11859-120">**库：** 作为资源包含在 MSCorEE.dll 中</span><span class="sxs-lookup"><span data-stu-id="11859-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="11859-121">**.NET 框架版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11859-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11859-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="11859-122">See also</span></span>

- [<span data-ttu-id="11859-123">GetHashFromFileW 方法</span><span class="sxs-lookup"><span data-stu-id="11859-123">GetHashFromFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)
- [<span data-ttu-id="11859-124">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="11859-124">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
