---
title: GetHashFromFileW 函数
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9be512bab30e08ddeb7deadf8a29263e928549a1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59134592"
---
# <a name="gethashfromfilew-function"></a><span data-ttu-id="28d7e-102">GetHashFromFileW 函数</span><span class="sxs-lookup"><span data-stu-id="28d7e-102">GetHashFromFileW Function</span></span>
<span data-ttu-id="28d7e-103">生成由 Unicode 字符串指定的文件内容的哈希。</span><span class="sxs-lookup"><span data-stu-id="28d7e-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
 <span data-ttu-id="28d7e-104">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="28d7e-104">This function has been deprecated.</span></span> <span data-ttu-id="28d7e-105">使用[iclrstrongname:: Gethashfromfilew](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)方法相反。</span><span class="sxs-lookup"><span data-stu-id="28d7e-105">Use the [ICLRStrongName::GetHashFromFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28d7e-106">语法</span><span class="sxs-lookup"><span data-stu-id="28d7e-106">Syntax</span></span>  
  
```  
HRESULT GetHashFromFileW (   
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="28d7e-107">参数</span><span class="sxs-lookup"><span data-stu-id="28d7e-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="28d7e-108">[in]Unicode 哈希的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="28d7e-108">[in] The Unicode name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="28d7e-109">[in、 out]要生成哈希时使用的算法。</span><span class="sxs-lookup"><span data-stu-id="28d7e-109">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="28d7e-110">有效的算法是定义的 Win32 CryptoAPI。</span><span class="sxs-lookup"><span data-stu-id="28d7e-110">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="28d7e-111">如果`piHashAlg`设置为 0，使用 CALG_SHA 1 的默认算法。</span><span class="sxs-lookup"><span data-stu-id="28d7e-111">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="28d7e-112">[out]包含生成的哈希的字节数组。</span><span class="sxs-lookup"><span data-stu-id="28d7e-112">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="28d7e-113">[in]指向缓冲区的最大大小`pbHash`。</span><span class="sxs-lookup"><span data-stu-id="28d7e-113">[in] The maximum size of the buffer pointed to by `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="28d7e-114">[out]大小，以字节为单位的`pbHash`。</span><span class="sxs-lookup"><span data-stu-id="28d7e-114">[out] The size, in bytes, of `pbHash`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="28d7e-115">备注</span><span class="sxs-lookup"><span data-stu-id="28d7e-115">Remarks</span></span>  
 <span data-ttu-id="28d7e-116">此函数等同于[GetHashFromFile](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfile-function.md)，只不过文件名称规范是 Unicode 而不是 ANSI。</span><span class="sxs-lookup"><span data-stu-id="28d7e-116">This function is the same as [GetHashFromFile](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfile-function.md), except that the file name specification is Unicode instead of ANSI.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28d7e-117">要求</span><span class="sxs-lookup"><span data-stu-id="28d7e-117">Requirements</span></span>  
 <span data-ttu-id="28d7e-118">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="28d7e-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28d7e-119">**标头：** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="28d7e-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="28d7e-120">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="28d7e-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="28d7e-121">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28d7e-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28d7e-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="28d7e-122">See also</span></span>

- [<span data-ttu-id="28d7e-123">GetHashFromFileW 方法</span><span class="sxs-lookup"><span data-stu-id="28d7e-123">GetHashFromFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)
- [<span data-ttu-id="28d7e-124">GetHashFromFile 方法</span><span class="sxs-lookup"><span data-stu-id="28d7e-124">GetHashFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)
- [<span data-ttu-id="28d7e-125">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="28d7e-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
