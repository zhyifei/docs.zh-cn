---
title: GetHashFromHandle 函数
ms.date: 03/30/2017
api_name:
- GetHashFromHandle
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromHandle
helpviewer_keywords:
- GetHashFromHandle function [.NET Framework strong naming]
ms.assetid: 9e00337f-b307-4602-9bc3-965a8dbf02cd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 48dd987896536006fe81bc01528cadb507123e27
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049422"
---
# <a name="gethashfromhandle-function"></a><span data-ttu-id="b8366-102">GetHashFromHandle 函数</span><span class="sxs-lookup"><span data-stu-id="b8366-102">GetHashFromHandle Function</span></span>
<span data-ttu-id="b8366-103">使用指定的哈希算法，生成具有指定文件句柄的文件内容的哈希。</span><span class="sxs-lookup"><span data-stu-id="b8366-103">Generates a hash over the contents of the file with the specified file handle, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="b8366-104">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="b8366-104">This function has been deprecated.</span></span> <span data-ttu-id="b8366-105">使用[iclrstrongname:: Gethashfromhandle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md)方法相反。</span><span class="sxs-lookup"><span data-stu-id="b8366-105">Use the [ICLRStrongName::GetHashFromHandle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8366-106">语法</span><span class="sxs-lookup"><span data-stu-id="b8366-106">Syntax</span></span>  
  
```  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b8366-107">参数</span><span class="sxs-lookup"><span data-stu-id="b8366-107">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="b8366-108">[in]要进行哈希处理的文件句柄。</span><span class="sxs-lookup"><span data-stu-id="b8366-108">[in] The handle of the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="b8366-109">[in、 out]一个常量，它指定哈希算法。</span><span class="sxs-lookup"><span data-stu-id="b8366-109">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="b8366-110">使用默认的算法为零。</span><span class="sxs-lookup"><span data-stu-id="b8366-110">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="b8366-111">[out]返回的哈希缓冲区中。</span><span class="sxs-lookup"><span data-stu-id="b8366-111">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="b8366-112">[in]请求的最大大小的`pbHash`。</span><span class="sxs-lookup"><span data-stu-id="b8366-112">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="b8366-113">[out]大小 （字节），则返回的`pbHash`。</span><span class="sxs-lookup"><span data-stu-id="b8366-113">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8366-114">要求</span><span class="sxs-lookup"><span data-stu-id="b8366-114">Requirements</span></span>  
 <span data-ttu-id="b8366-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b8366-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8366-116">**标头：** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="b8366-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="b8366-117">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="b8366-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b8366-118">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8366-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8366-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="b8366-119">See also</span></span>

- [<span data-ttu-id="b8366-120">GetHashFromHandle 方法</span><span class="sxs-lookup"><span data-stu-id="b8366-120">GetHashFromHandle Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md)
- [<span data-ttu-id="b8366-121">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="b8366-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
