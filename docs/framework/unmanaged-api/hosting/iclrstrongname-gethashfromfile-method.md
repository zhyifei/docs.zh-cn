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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f410e38d846969bbd23ff5b0a6751a5202088254
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59157489"
---
# <a name="iclrstrongnamegethashfromfile-method"></a><span data-ttu-id="e1554-102">ICLRStrongName::GetHashFromFile 方法</span><span class="sxs-lookup"><span data-stu-id="e1554-102">ICLRStrongName::GetHashFromFile Method</span></span>
<span data-ttu-id="e1554-103">生成指定文件内容的哈希。</span><span class="sxs-lookup"><span data-stu-id="e1554-103">Generates a hash over the contents of the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1554-104">语法</span><span class="sxs-lookup"><span data-stu-id="e1554-104">Syntax</span></span>  
  
```  
HRESULT GetHashFromFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,   
    [out] BYTE     *pbHash,      
    [in]  DWORD    cchHash,      
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e1554-105">参数</span><span class="sxs-lookup"><span data-stu-id="e1554-105">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="e1554-106">[in]哈希的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="e1554-106">[in] The name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="e1554-107">[in、 out]要生成哈希时使用的算法。</span><span class="sxs-lookup"><span data-stu-id="e1554-107">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="e1554-108">有效的算法是定义的 Win32 CryptoAPI。</span><span class="sxs-lookup"><span data-stu-id="e1554-108">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="e1554-109">如果`piHashAlg`设置为 0，使用 CALG_SHA 1 的默认算法。</span><span class="sxs-lookup"><span data-stu-id="e1554-109">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="e1554-110">[out]包含生成的哈希的字节数组。</span><span class="sxs-lookup"><span data-stu-id="e1554-110">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="e1554-111">[in]缓冲区的最大大小的`pbHash`指向。</span><span class="sxs-lookup"><span data-stu-id="e1554-111">[in] The maximum size of the buffer that `pbHash` points to.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="e1554-112">[out]大小 （字节），则返回的`pbHash`。</span><span class="sxs-lookup"><span data-stu-id="e1554-112">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e1554-113">返回值</span><span class="sxs-lookup"><span data-stu-id="e1554-113">Return Value</span></span>  
 `S_OK` <span data-ttu-id="e1554-114">如果成功，则完成的方法否则为指示失败的 HRESULT 值 (请参阅[常见的 HRESULT 值](https://go.microsoft.com/fwlink/?LinkId=213878)列表)。</span><span class="sxs-lookup"><span data-stu-id="e1554-114">if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e1554-115">备注</span><span class="sxs-lookup"><span data-stu-id="e1554-115">Remarks</span></span>  
 <span data-ttu-id="e1554-116">此方法等同于[iclrstrongname:: Gethashfromfilew](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)方法，不同之处在于的文件的名称规范是 ANSI 而不是 Unicode。</span><span class="sxs-lookup"><span data-stu-id="e1554-116">This method is the same as the [ICLRStrongName::GetHashFromFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md) method, except that the file name specification is ANSI instead of Unicode.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1554-117">要求</span><span class="sxs-lookup"><span data-stu-id="e1554-117">Requirements</span></span>  
 <span data-ttu-id="e1554-118">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e1554-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1554-119">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="e1554-119">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="e1554-120">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="e1554-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="e1554-121">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="e1554-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e1554-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="e1554-122">See also</span></span>

- [<span data-ttu-id="e1554-123">GetHashFromFileW 方法</span><span class="sxs-lookup"><span data-stu-id="e1554-123">GetHashFromFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)
- [<span data-ttu-id="e1554-124">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="e1554-124">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
