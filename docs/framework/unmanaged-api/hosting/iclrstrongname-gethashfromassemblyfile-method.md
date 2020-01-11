---
title: ICLRStrongName::GetHashFromAssemblyFile 方法
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromAssemblyFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromAssemblyFile
helpviewer_keywords:
- ICLRStrongName::GetHashFromAssemblyFile method [.NET Framework hosting]
- GetHashFromAssemblyFile method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 0b67ea03-d474-4605-acaa-57455790250c
topic_type:
- apiref
ms.openlocfilehash: 8131a9838cc958405ca23c75c702db5ec65a41c8
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901195"
---
# <a name="iclrstrongnamegethashfromassemblyfile-method"></a><span data-ttu-id="9377b-102">ICLRStrongName::GetHashFromAssemblyFile 方法</span><span class="sxs-lookup"><span data-stu-id="9377b-102">ICLRStrongName::GetHashFromAssemblyFile Method</span></span>
<span data-ttu-id="9377b-103">使用指定的哈希算法获取指定程序集文件的哈希。</span><span class="sxs-lookup"><span data-stu-id="9377b-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9377b-104">语法</span><span class="sxs-lookup"><span data-stu-id="9377b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9377b-105">参数</span><span class="sxs-lookup"><span data-stu-id="9377b-105">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="9377b-106">中要进行哈希处理的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="9377b-106">[in] The path to the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="9377b-107">[in，out]指定哈希算法的常量。</span><span class="sxs-lookup"><span data-stu-id="9377b-107">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="9377b-108">使用零作为默认哈希算法。</span><span class="sxs-lookup"><span data-stu-id="9377b-108">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="9377b-109">弄返回的哈希缓冲区。</span><span class="sxs-lookup"><span data-stu-id="9377b-109">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="9377b-110">中请求的最大 `pbHash`大小。</span><span class="sxs-lookup"><span data-stu-id="9377b-110">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="9377b-111">弄返回 `pbHash`的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="9377b-111">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9377b-112">返回值</span><span class="sxs-lookup"><span data-stu-id="9377b-112">Return Value</span></span>  
 <span data-ttu-id="9377b-113">如果方法已成功完成，则 `S_OK`;否则，表示失败的 HRESULT 值（请参阅列表的[常见 HRESULT 值](/windows/win32/seccrypto/common-hresult-values)）。</span><span class="sxs-lookup"><span data-stu-id="9377b-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9377b-114">需求</span><span class="sxs-lookup"><span data-stu-id="9377b-114">Requirements</span></span>  
 <span data-ttu-id="9377b-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9377b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9377b-116">**标头：** MetaHost</span><span class="sxs-lookup"><span data-stu-id="9377b-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="9377b-117">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="9377b-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9377b-118">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9377b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9377b-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9377b-119">See also</span></span>

- [<span data-ttu-id="9377b-120">GetHashFromAssemblyFileW 方法</span><span class="sxs-lookup"><span data-stu-id="9377b-120">GetHashFromAssemblyFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md)
- [<span data-ttu-id="9377b-121">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="9377b-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
