---
title: GetHashFromAssemblyFile 函数
ms.date: 03/30/2017
api_name:
- GetHashFromAssemblyFile
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromAssemblyFile
helpviewer_keywords:
- GetHashFromAssemblyFile function [.NET Framework strong naming]
ms.assetid: 751ed69f-b7ab-4e07-80de-e17ca9319b0c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e56a509d08b19cf449177984e7b59481eb7b09a9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59092157"
---
# <a name="gethashfromassemblyfile-function"></a><span data-ttu-id="a5629-102">GetHashFromAssemblyFile 函数</span><span class="sxs-lookup"><span data-stu-id="a5629-102">GetHashFromAssemblyFile Function</span></span>
<span data-ttu-id="a5629-103">使用指定的哈希算法获取指定程序集文件的哈希。</span><span class="sxs-lookup"><span data-stu-id="a5629-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="a5629-104">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="a5629-104">This function has been deprecated.</span></span> <span data-ttu-id="a5629-105">使用[iclrstrongname:: Gethashfromassemblyfile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)方法相反。</span><span class="sxs-lookup"><span data-stu-id="a5629-105">Use the [ICLRStrongName::GetHashFromAssemblyFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5629-106">语法</span><span class="sxs-lookup"><span data-stu-id="a5629-106">Syntax</span></span>  
  
```  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a5629-107">参数</span><span class="sxs-lookup"><span data-stu-id="a5629-107">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="a5629-108">[in]要进行哈希处理的文件路径。</span><span class="sxs-lookup"><span data-stu-id="a5629-108">[in] The path to the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="a5629-109">[in、 out]一个常量，它指定哈希算法。</span><span class="sxs-lookup"><span data-stu-id="a5629-109">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="a5629-110">使用默认哈希算法为零。</span><span class="sxs-lookup"><span data-stu-id="a5629-110">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="a5629-111">[out]返回的哈希缓冲区中。</span><span class="sxs-lookup"><span data-stu-id="a5629-111">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="a5629-112">[in]请求的最大大小的`pbHash`。</span><span class="sxs-lookup"><span data-stu-id="a5629-112">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="a5629-113">[out]返回的大小，以字节为单位， `pbHash`。</span><span class="sxs-lookup"><span data-stu-id="a5629-113">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5629-114">要求</span><span class="sxs-lookup"><span data-stu-id="a5629-114">Requirements</span></span>  
 <span data-ttu-id="a5629-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a5629-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5629-116">**标头：** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="a5629-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="a5629-117">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="a5629-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="a5629-118">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="a5629-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a5629-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="a5629-119">See also</span></span>

- [<span data-ttu-id="a5629-120">GetHashFromAssemblyFile 方法</span><span class="sxs-lookup"><span data-stu-id="a5629-120">GetHashFromAssemblyFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)
- [<span data-ttu-id="a5629-121">GetHashFromAssemblyFileW 方法</span><span class="sxs-lookup"><span data-stu-id="a5629-121">GetHashFromAssemblyFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md)
- [<span data-ttu-id="a5629-122">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="a5629-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
