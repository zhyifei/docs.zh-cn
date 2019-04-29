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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e1547680800b188d5b5e0032e804c22cae0547ac
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61771535"
---
# <a name="iclrstrongnamegethashfromfilew-method"></a><span data-ttu-id="ec330-102">ICLRStrongName::GetHashFromFileW 方法</span><span class="sxs-lookup"><span data-stu-id="ec330-102">ICLRStrongName::GetHashFromFileW Method</span></span>
<span data-ttu-id="ec330-103">生成由 Unicode 字符串指定的文件内容的哈希。</span><span class="sxs-lookup"><span data-stu-id="ec330-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec330-104">语法</span><span class="sxs-lookup"><span data-stu-id="ec330-104">Syntax</span></span>  
  
```  
HRESULT GetHashFromFileW (   
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="ec330-105">参数</span><span class="sxs-lookup"><span data-stu-id="ec330-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="ec330-106">[in]Unicode 哈希的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="ec330-106">[in] The Unicode name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="ec330-107">[in、 out]要生成哈希时使用的算法。</span><span class="sxs-lookup"><span data-stu-id="ec330-107">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="ec330-108">有效的算法是定义的 Win32 CryptoAPI。</span><span class="sxs-lookup"><span data-stu-id="ec330-108">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="ec330-109">如果`piHashAlg`设置为 0，使用 CALG_SHA 1 的默认算法。</span><span class="sxs-lookup"><span data-stu-id="ec330-109">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="ec330-110">[out]包含生成的哈希的字节数组。</span><span class="sxs-lookup"><span data-stu-id="ec330-110">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="ec330-111">[in]指向缓冲区的最大大小`pbHash`。</span><span class="sxs-lookup"><span data-stu-id="ec330-111">[in] The maximum size of the buffer pointed to by `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="ec330-112">[out]大小，以字节为单位的`pbHash`。</span><span class="sxs-lookup"><span data-stu-id="ec330-112">[out] The size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ec330-113">返回值</span><span class="sxs-lookup"><span data-stu-id="ec330-113">Return Value</span></span>  
 <span data-ttu-id="ec330-114">`S_OK` 如果成功，则完成的方法否则为指示失败的 HRESULT 值 (请参阅[常见的 HRESULT 值](https://go.microsoft.com/fwlink/?LinkId=213878)列表)。</span><span class="sxs-lookup"><span data-stu-id="ec330-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ec330-115">备注</span><span class="sxs-lookup"><span data-stu-id="ec330-115">Remarks</span></span>  
 <span data-ttu-id="ec330-116">此方法等同于[iclrstrongname:: Gethashfromfile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)方法，不同之处在于的文件的名称规范是 Unicode 而不是 ANSI。</span><span class="sxs-lookup"><span data-stu-id="ec330-116">This method is the same as the [ICLRStrongName::GetHashFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md) method, except that the file name specification is Unicode instead of ANSI.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec330-117">要求</span><span class="sxs-lookup"><span data-stu-id="ec330-117">Requirements</span></span>  
 <span data-ttu-id="ec330-118">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ec330-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec330-119">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="ec330-119">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="ec330-120">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="ec330-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ec330-121">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec330-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec330-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="ec330-122">See also</span></span>

- [<span data-ttu-id="ec330-123">GetHashFromFile 方法</span><span class="sxs-lookup"><span data-stu-id="ec330-123">GetHashFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)
- [<span data-ttu-id="ec330-124">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="ec330-124">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
