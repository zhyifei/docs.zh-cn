---
title: ICLRStrongName::GetHashFromAssemblyFileW 方法
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromAssemblyFileW
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromAssemblyFileW
helpviewer_keywords:
- ICLRStrongName::GetHashFromAssemblyFileW method [.NET Framework hosting]
- GetHashFromAssemblyFileW method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 5d0b44a2-5a14-44a2-9a0e-e8682fd4e106
topic_type:
- apiref
ms.openlocfilehash: 43a5cd57a8eeaba70f1bb1ffb9cab5bb1a067914
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130956"
---
# <a name="iclrstrongnamegethashfromassemblyfilew-method"></a><span data-ttu-id="4e98d-102">ICLRStrongName::GetHashFromAssemblyFileW 方法</span><span class="sxs-lookup"><span data-stu-id="4e98d-102">ICLRStrongName::GetHashFromAssemblyFileW Method</span></span>
<span data-ttu-id="4e98d-103">生成由 Unicode 字符串指定的文件内容的哈希。</span><span class="sxs-lookup"><span data-stu-id="4e98d-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e98d-104">语法</span><span class="sxs-lookup"><span data-stu-id="4e98d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFileW (  
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4e98d-105">参数</span><span class="sxs-lookup"><span data-stu-id="4e98d-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="4e98d-106">中要进行哈希处理的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="4e98d-106">[in] The path to the file to be hashed.</span></span> <span data-ttu-id="4e98d-107">此参数必须是 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="4e98d-107">This parameter must be a Unicode string.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="4e98d-108">[in，out]指定哈希算法的常量。</span><span class="sxs-lookup"><span data-stu-id="4e98d-108">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="4e98d-109">使用零作为默认哈希算法。</span><span class="sxs-lookup"><span data-stu-id="4e98d-109">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="4e98d-110">弄返回的哈希缓冲区。</span><span class="sxs-lookup"><span data-stu-id="4e98d-110">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="4e98d-111">中请求的最大 `pbHash`大小。</span><span class="sxs-lookup"><span data-stu-id="4e98d-111">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="4e98d-112">弄返回 `pbHash`的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="4e98d-112">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4e98d-113">返回值</span><span class="sxs-lookup"><span data-stu-id="4e98d-113">Return Value</span></span>  
 <span data-ttu-id="4e98d-114">如果方法已成功完成，则 `S_OK`;否则，表示失败的 HRESULT 值（请参阅列表的[常见 HRESULT 值](https://go.microsoft.com/fwlink/?LinkId=213878)）。</span><span class="sxs-lookup"><span data-stu-id="4e98d-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e98d-115">要求</span><span class="sxs-lookup"><span data-stu-id="4e98d-115">Requirements</span></span>  
 <span data-ttu-id="4e98d-116">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4e98d-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e98d-117">**标头：** MetaHost</span><span class="sxs-lookup"><span data-stu-id="4e98d-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="4e98d-118">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="4e98d-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4e98d-119">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e98d-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e98d-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="4e98d-120">See also</span></span>

- [<span data-ttu-id="4e98d-121">GetHashFromAssemblyFile 方法</span><span class="sxs-lookup"><span data-stu-id="4e98d-121">GetHashFromAssemblyFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)
- [<span data-ttu-id="4e98d-122">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="4e98d-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
