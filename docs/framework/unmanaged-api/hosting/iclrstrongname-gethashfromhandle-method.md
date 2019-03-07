---
title: ICLRStrongName::GetHashFromHandle 方法
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromHandle
- ICLRStrongName.StrongNameCompareAssemblies
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromHandle
helpviewer_keywords:
- GetHashFromHandle method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::GetHashFromHandle method [.NET Framework hosting]
ms.assetid: 3bedbb7d-3cdd-4175-b370-10ae734062db
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9688635532e0ccc35ff8826a53da80738bfc528e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57470011"
---
# <a name="iclrstrongnamegethashfromhandle-method"></a><span data-ttu-id="2c73b-102">ICLRStrongName::GetHashFromHandle 方法</span><span class="sxs-lookup"><span data-stu-id="2c73b-102">ICLRStrongName::GetHashFromHandle Method</span></span>
<span data-ttu-id="2c73b-103">生成具有指定的文件句柄，使用指定的哈希算法的文件的内容哈希代码。</span><span class="sxs-lookup"><span data-stu-id="2c73b-103">Generates a hash over the contents of the file that has the specified file handle, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c73b-104">语法</span><span class="sxs-lookup"><span data-stu-id="2c73b-104">Syntax</span></span>  
  
```  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c73b-105">参数</span><span class="sxs-lookup"><span data-stu-id="2c73b-105">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="2c73b-106">[in]要进行哈希处理的文件句柄。</span><span class="sxs-lookup"><span data-stu-id="2c73b-106">[in] The handle of the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="2c73b-107">[in、 out]一个常量，它指定哈希算法。</span><span class="sxs-lookup"><span data-stu-id="2c73b-107">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="2c73b-108">使用默认的算法为零。</span><span class="sxs-lookup"><span data-stu-id="2c73b-108">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="2c73b-109">[out]返回的哈希缓冲区中。</span><span class="sxs-lookup"><span data-stu-id="2c73b-109">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="2c73b-110">[in]请求的最大大小的`pbHash`。</span><span class="sxs-lookup"><span data-stu-id="2c73b-110">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="2c73b-111">[out]大小 （字节），则返回的`pbHash`。</span><span class="sxs-lookup"><span data-stu-id="2c73b-111">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2c73b-112">返回值</span><span class="sxs-lookup"><span data-stu-id="2c73b-112">Return Value</span></span>  
 <span data-ttu-id="2c73b-113">`S_OK` 如果成功，则完成的方法否则为指示失败的 HRESULT 值 (请参阅[常见的 HRESULT 值](https://go.microsoft.com/fwlink/?LinkId=213878)列表)。</span><span class="sxs-lookup"><span data-stu-id="2c73b-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c73b-114">要求</span><span class="sxs-lookup"><span data-stu-id="2c73b-114">Requirements</span></span>  
 <span data-ttu-id="2c73b-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2c73b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c73b-116">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="2c73b-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="2c73b-117">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="2c73b-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2c73b-118">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c73b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c73b-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="2c73b-119">See also</span></span>
- [<span data-ttu-id="2c73b-120">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="2c73b-120">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
