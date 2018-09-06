---
title: ICLRStrongName::StrongNameCompareAssemblies 方法
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameCompareAssemblies
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameCompareAssemblies
helpviewer_keywords:
- ICLRStrongName::StrongNameCompareAssemblies method [.NET Framework hosting]
- StrongNameCompareAssemblies method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: b1fb356c-72cf-4aa4-8376-f291a6d97c01
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3eb23da5accd89931ee4b883bfa162035ec26ddd
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43861031"
---
# <a name="iclrstrongnamestrongnamecompareassemblies-method"></a><span data-ttu-id="a9b58-102">ICLRStrongName::StrongNameCompareAssemblies 方法</span><span class="sxs-lookup"><span data-stu-id="a9b58-102">ICLRStrongName::StrongNameCompareAssemblies Method</span></span>
<span data-ttu-id="a9b58-103">确定两个程序集是否仅是强名称签名不同。</span><span class="sxs-lookup"><span data-stu-id="a9b58-103">Determines whether two assemblies differ only by their strong name signatures.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9b58-104">语法</span><span class="sxs-lookup"><span data-stu-id="a9b58-104">Syntax</span></span>  
  
```  
HRESULT StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a9b58-105">参数</span><span class="sxs-lookup"><span data-stu-id="a9b58-105">Parameters</span></span>  
 `wszAssembly1`  
 <span data-ttu-id="a9b58-106">[in]第一个程序集的路径。</span><span class="sxs-lookup"><span data-stu-id="a9b58-106">[in] The path to the first assembly.</span></span>  
  
 `wszAssembly2`  
 <span data-ttu-id="a9b58-107">[in]第二个程序集的路径。</span><span class="sxs-lookup"><span data-stu-id="a9b58-107">[in] The path to the second assembly.</span></span>  
  
 `pdwResult`  
 <span data-ttu-id="a9b58-108">[out]以下值之一：</span><span class="sxs-lookup"><span data-stu-id="a9b58-108">[out] One of the following values:</span></span>  
  
-   <span data-ttu-id="a9b58-109">`SN_CMP_DIFFERENT` (0)-指定程序集包含不同的数据。</span><span class="sxs-lookup"><span data-stu-id="a9b58-109">`SN_CMP_DIFFERENT` (0) - Specifies that the assemblies contain different data.</span></span>  
  
-   <span data-ttu-id="a9b58-110">`SN_CMP_IDENTICAL` (1)-指定程序的程序集完全相同，包括其签名和校验和。</span><span class="sxs-lookup"><span data-stu-id="a9b58-110">`SN_CMP_IDENTICAL` (1) - Specifies that the assemblies are exactly the same, including their signatures and checksum.</span></span>  
  
-   <span data-ttu-id="a9b58-111">`SN_CMP_SIGONLY` (2)-指定程序集仅签名和校验和不同。</span><span class="sxs-lookup"><span data-stu-id="a9b58-111">`SN_CMP_SIGONLY` (2) - Specifies that the assemblies differ only by signature and checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a9b58-112">返回值</span><span class="sxs-lookup"><span data-stu-id="a9b58-112">Return Value</span></span>  
 <span data-ttu-id="a9b58-113">`S_OK` 如果成功，则完成的方法否则为指示失败的 HRESULT 值 (请参阅[常见的 HRESULT 值](https://go.microsoft.com/fwlink/?LinkId=213878)列表)。</span><span class="sxs-lookup"><span data-stu-id="a9b58-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9b58-114">要求</span><span class="sxs-lookup"><span data-stu-id="a9b58-114">Requirements</span></span>  
 <span data-ttu-id="a9b58-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a9b58-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9b58-116">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="a9b58-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="a9b58-117">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="a9b58-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a9b58-118">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9b58-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a9b58-119">备注</span><span class="sxs-lookup"><span data-stu-id="a9b58-119">Remarks</span></span>  
 <span data-ttu-id="a9b58-120">程序集的强名称签名包含程序集的文本名称、 版本、 区域性和公钥标记。</span><span class="sxs-lookup"><span data-stu-id="a9b58-120">The strong name signature of an assembly consists of the assembly's text name, version, culture, and public key token.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9b58-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="a9b58-121">See Also</span></span>  
 [<span data-ttu-id="a9b58-122">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="a9b58-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
