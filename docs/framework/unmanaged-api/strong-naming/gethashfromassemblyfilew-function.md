---
title: GetHashFromAssemblyFileW 函数
ms.date: 03/30/2017
api_name:
- GetHashFromAssemblyFileW
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromAssemblyFileW
helpviewer_keywords:
- GetHashFromAssemblyFileW function [.NET Framework strong naming]
ms.assetid: d1b2b172-5353-42af-a877-cf653c68ece0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 832d66eee14680870e70f1e0e8d40987eff3257f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33457569"
---
# <a name="gethashfromassemblyfilew-function"></a><span data-ttu-id="47a91-102">GetHashFromAssemblyFileW 函数</span><span class="sxs-lookup"><span data-stu-id="47a91-102">GetHashFromAssemblyFileW Function</span></span>
<span data-ttu-id="47a91-103">获取使用指定的哈希算法对指定的程序集文件的哈希值。</span><span class="sxs-lookup"><span data-stu-id="47a91-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span> <span data-ttu-id="47a91-104">必须为 Unicode 字符串中指定的程序集文件的路径。</span><span class="sxs-lookup"><span data-stu-id="47a91-104">The path to the assembly file must be specified as a Unicode string.</span></span>  
  
 <span data-ttu-id="47a91-105">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="47a91-105">This function has been deprecated.</span></span> <span data-ttu-id="47a91-106">使用[iclrstrongname:: Gethashfromassemblyfilew](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md)方法相反。</span><span class="sxs-lookup"><span data-stu-id="47a91-106">Use the [ICLRStrongName::GetHashFromAssemblyFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47a91-107">语法</span><span class="sxs-lookup"><span data-stu-id="47a91-107">Syntax</span></span>  
  
```  
HRESULT GetHashFromAssemblyFileW (  
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="47a91-108">参数</span><span class="sxs-lookup"><span data-stu-id="47a91-108">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="47a91-109">[in]要进行哈希处理的文件路径。</span><span class="sxs-lookup"><span data-stu-id="47a91-109">[in] The path to the file to be hashed.</span></span> <span data-ttu-id="47a91-110">此参数必须是 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="47a91-110">This parameter must be a Unicode string.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="47a91-111">[在中，out]一个指定的哈希算法的常数。</span><span class="sxs-lookup"><span data-stu-id="47a91-111">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="47a91-112">使用默认哈希算法的零。</span><span class="sxs-lookup"><span data-stu-id="47a91-112">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="47a91-113">[out]返回的哈希缓冲区中。</span><span class="sxs-lookup"><span data-stu-id="47a91-113">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="47a91-114">[in]请求的最大大小的`pbHash`。</span><span class="sxs-lookup"><span data-stu-id="47a91-114">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="47a91-115">[out]返回的大小，以字节为单位， `pbHash`。</span><span class="sxs-lookup"><span data-stu-id="47a91-115">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47a91-116">要求</span><span class="sxs-lookup"><span data-stu-id="47a91-116">Requirements</span></span>  
 <span data-ttu-id="47a91-117">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="47a91-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47a91-118">**标头：** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="47a91-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="47a91-119">**库：** 作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="47a91-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="47a91-120">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47a91-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47a91-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="47a91-121">See Also</span></span>  
 [<span data-ttu-id="47a91-122">GetHashFromAssemblyFileW 方法</span><span class="sxs-lookup"><span data-stu-id="47a91-122">GetHashFromAssemblyFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md)  
 [<span data-ttu-id="47a91-123">GetHashFromAssemblyFile 方法</span><span class="sxs-lookup"><span data-stu-id="47a91-123">GetHashFromAssemblyFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)  
 [<span data-ttu-id="47a91-124">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="47a91-124">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
