---
title: ICLRStrongName::GetHashFromFileW 方法
ms.date: 03/30/2017
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
ms.openlocfilehash: 8f2d74531233f2ba423c39126ddc43e499cbb5d8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176365"
---
# <a name="iclrstrongnamegethashfromfilew-method"></a><span data-ttu-id="39e06-102">ICLRStrongName::GetHashFromFileW 方法</span><span class="sxs-lookup"><span data-stu-id="39e06-102">ICLRStrongName::GetHashFromFileW Method</span></span>
<span data-ttu-id="39e06-103">生成由 Unicode 字符串指定的文件内容的哈希。</span><span class="sxs-lookup"><span data-stu-id="39e06-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39e06-104">语法</span><span class="sxs-lookup"><span data-stu-id="39e06-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFileW (
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="39e06-105">parameters</span><span class="sxs-lookup"><span data-stu-id="39e06-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="39e06-106">[在]要哈希的文件的 Unicode 名称。</span><span class="sxs-lookup"><span data-stu-id="39e06-106">[in] The Unicode name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="39e06-107">[进出]生成哈希时使用的算法。</span><span class="sxs-lookup"><span data-stu-id="39e06-107">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="39e06-108">有效的算法是由 Win32 加密 API 定义的算法。</span><span class="sxs-lookup"><span data-stu-id="39e06-108">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="39e06-109">如果`piHashAlg`设置为 0，则使用默认算法CALG_SHA-1。</span><span class="sxs-lookup"><span data-stu-id="39e06-109">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="39e06-110">[出]包含生成的哈希的字节数组。</span><span class="sxs-lookup"><span data-stu-id="39e06-110">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="39e06-111">[在]指向 的缓冲区的最大大小`pbHash`。</span><span class="sxs-lookup"><span data-stu-id="39e06-111">[in] The maximum size of the buffer pointed to by `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="39e06-112">[出]的大小（以字节为单位）的大小`pbHash`。</span><span class="sxs-lookup"><span data-stu-id="39e06-112">[out] The size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="39e06-113">返回值</span><span class="sxs-lookup"><span data-stu-id="39e06-113">Return Value</span></span>  
 <span data-ttu-id="39e06-114">`S_OK`如果方法成功完成;如果方法成功完成;否则，指示失败的 HRESULT 值（请参阅列表[的常用 HRESULT 值](/windows/win32/seccrypto/common-hresult-values)）。</span><span class="sxs-lookup"><span data-stu-id="39e06-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="39e06-115">备注</span><span class="sxs-lookup"><span data-stu-id="39e06-115">Remarks</span></span>  
 <span data-ttu-id="39e06-116">此方法与[ICLRStrongName：：getHashFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)方法相同，只不过文件名规范是 Unicode 而不是 ANSI。</span><span class="sxs-lookup"><span data-stu-id="39e06-116">This method is the same as the [ICLRStrongName::GetHashFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md) method, except that the file name specification is Unicode instead of ANSI.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39e06-117">要求</span><span class="sxs-lookup"><span data-stu-id="39e06-117">Requirements</span></span>  
 <span data-ttu-id="39e06-118">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="39e06-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39e06-119">**标题：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="39e06-119">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="39e06-120">**库：** 作为资源包含在 MSCorEE.dll 中</span><span class="sxs-lookup"><span data-stu-id="39e06-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="39e06-121">**.NET 框架版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39e06-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39e06-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="39e06-122">See also</span></span>

- [<span data-ttu-id="39e06-123">GetHashFromFile 方法</span><span class="sxs-lookup"><span data-stu-id="39e06-123">GetHashFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)
- [<span data-ttu-id="39e06-124">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="39e06-124">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
