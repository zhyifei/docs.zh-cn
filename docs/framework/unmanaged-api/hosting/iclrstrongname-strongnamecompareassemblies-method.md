---
title: "ICLRStrongName::StrongNameCompareAssemblies 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.StrongNameCompareAssemblies
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::StrongNameCompareAssemblies
helpviewer_keywords:
- ICLRStrongName::StrongNameCompareAssemblies method [.NET Framework hosting]
- StrongNameCompareAssemblies method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: b1fb356c-72cf-4aa4-8376-f291a6d97c01
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 96fbeccf76de87a3582bf8c2084d0ca9ad7d27f4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongnamestrongnamecompareassemblies-method"></a><span data-ttu-id="0968b-102">ICLRStrongName::StrongNameCompareAssemblies 方法</span><span class="sxs-lookup"><span data-stu-id="0968b-102">ICLRStrongName::StrongNameCompareAssemblies Method</span></span>
<span data-ttu-id="0968b-103">确定是否两个程序集的差异仅在于其强名称签名。</span><span class="sxs-lookup"><span data-stu-id="0968b-103">Determines whether two assemblies differ only by their strong name signatures.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0968b-104">语法</span><span class="sxs-lookup"><span data-stu-id="0968b-104">Syntax</span></span>  
  
```  
HRESULT StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0968b-105">参数</span><span class="sxs-lookup"><span data-stu-id="0968b-105">Parameters</span></span>  
 `wszAssembly1`  
 <span data-ttu-id="0968b-106">[in]第一个程序集的路径。</span><span class="sxs-lookup"><span data-stu-id="0968b-106">[in] The path to the first assembly.</span></span>  
  
 `wszAssembly2`  
 <span data-ttu-id="0968b-107">[in]第二个程序集的路径。</span><span class="sxs-lookup"><span data-stu-id="0968b-107">[in] The path to the second assembly.</span></span>  
  
 `pdwResult`  
 <span data-ttu-id="0968b-108">[out]以下值之一：</span><span class="sxs-lookup"><span data-stu-id="0968b-108">[out] One of the following values:</span></span>  
  
-   <span data-ttu-id="0968b-109">`SN_CMP_DIFFERENT`(0)-指定程序集包含不同的数据。</span><span class="sxs-lookup"><span data-stu-id="0968b-109">`SN_CMP_DIFFERENT` (0) - Specifies that the assemblies contain different data.</span></span>  
  
-   <span data-ttu-id="0968b-110">`SN_CMP_IDENTICAL`(1)-指定程序程序集完全相同，包括其签名和校验和。</span><span class="sxs-lookup"><span data-stu-id="0968b-110">`SN_CMP_IDENTICAL` (1) - Specifies that the assemblies are exactly the same, including their signatures and checksum.</span></span>  
  
-   <span data-ttu-id="0968b-111">`SN_CMP_SIGONLY`(2)-指定程序集不同只能由签名和校验和。</span><span class="sxs-lookup"><span data-stu-id="0968b-111">`SN_CMP_SIGONLY` (2) - Specifies that the assemblies differ only by signature and checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0968b-112">返回值</span><span class="sxs-lookup"><span data-stu-id="0968b-112">Return Value</span></span>  
 <span data-ttu-id="0968b-113">`S_OK`如果成功，则完成的方法否则为该值指示失败的 HRESULT 值 (请参阅[常见的 HRESULT 值](http://go.microsoft.com/fwlink/?LinkId=213878)有关的列表)。</span><span class="sxs-lookup"><span data-stu-id="0968b-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0968b-114">惠?</span><span class="sxs-lookup"><span data-stu-id="0968b-114">Requirements</span></span>  
 <span data-ttu-id="0968b-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0968b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0968b-116">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="0968b-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="0968b-117">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="0968b-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0968b-118">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0968b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0968b-119">备注</span><span class="sxs-lookup"><span data-stu-id="0968b-119">Remarks</span></span>  
 <span data-ttu-id="0968b-120">程序集的强名称签名组成程序集的文本名称、 版本、 区域性和公钥标记。</span><span class="sxs-lookup"><span data-stu-id="0968b-120">The strong name signature of an assembly consists of the assembly's text name, version, culture, and public key token.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0968b-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="0968b-121">See Also</span></span>  
 [<span data-ttu-id="0968b-122">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="0968b-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
