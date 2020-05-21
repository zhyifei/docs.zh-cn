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
ms.openlocfilehash: 0087636c68d0748ad2b143de9b132278ab9d43f5
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762053"
---
# <a name="iclrstrongnamestrongnamecompareassemblies-method"></a><span data-ttu-id="03ef0-102">ICLRStrongName::StrongNameCompareAssemblies 方法</span><span class="sxs-lookup"><span data-stu-id="03ef0-102">ICLRStrongName::StrongNameCompareAssemblies Method</span></span>
<span data-ttu-id="03ef0-103">确定两个程序集是否仅是强名称签名不同。</span><span class="sxs-lookup"><span data-stu-id="03ef0-103">Determines whether two assemblies differ only by their strong name signatures.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03ef0-104">语法</span><span class="sxs-lookup"><span data-stu-id="03ef0-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="03ef0-105">参数</span><span class="sxs-lookup"><span data-stu-id="03ef0-105">Parameters</span></span>  
 `wszAssembly1`  
 <span data-ttu-id="03ef0-106">中第一个程序集的路径。</span><span class="sxs-lookup"><span data-stu-id="03ef0-106">[in] The path to the first assembly.</span></span>  
  
 `wszAssembly2`  
 <span data-ttu-id="03ef0-107">中第二个程序集的路径。</span><span class="sxs-lookup"><span data-stu-id="03ef0-107">[in] The path to the second assembly.</span></span>  
  
 `pdwResult`  
 <span data-ttu-id="03ef0-108">弄以下值之一：</span><span class="sxs-lookup"><span data-stu-id="03ef0-108">[out] One of the following values:</span></span>  
  
- <span data-ttu-id="03ef0-109">`SN_CMP_DIFFERENT`（0）-指定程序集包含不同的数据。</span><span class="sxs-lookup"><span data-stu-id="03ef0-109">`SN_CMP_DIFFERENT` (0) - Specifies that the assemblies contain different data.</span></span>  
  
- <span data-ttu-id="03ef0-110">`SN_CMP_IDENTICAL`（1）-指定程序集完全相同，包括它们的签名和校验和。</span><span class="sxs-lookup"><span data-stu-id="03ef0-110">`SN_CMP_IDENTICAL` (1) - Specifies that the assemblies are exactly the same, including their signatures and checksum.</span></span>  
  
- <span data-ttu-id="03ef0-111">`SN_CMP_SIGONLY`（2）-指定程序集不同于签名和校验和。</span><span class="sxs-lookup"><span data-stu-id="03ef0-111">`SN_CMP_SIGONLY` (2) - Specifies that the assemblies differ only by signature and checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="03ef0-112">返回值</span><span class="sxs-lookup"><span data-stu-id="03ef0-112">Return Value</span></span>  
 <span data-ttu-id="03ef0-113">`S_OK`如果该方法已成功完成，则为;否则，表示失败的 HRESULT 值（请参阅列表的[常见 HRESULT 值](/windows/win32/seccrypto/common-hresult-values)）。</span><span class="sxs-lookup"><span data-stu-id="03ef0-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03ef0-114">要求</span><span class="sxs-lookup"><span data-stu-id="03ef0-114">Requirements</span></span>  
 <span data-ttu-id="03ef0-115">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="03ef0-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03ef0-116">**标头：** MetaHost</span><span class="sxs-lookup"><span data-stu-id="03ef0-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="03ef0-117">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="03ef0-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="03ef0-118">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03ef0-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="03ef0-119">注解</span><span class="sxs-lookup"><span data-stu-id="03ef0-119">Remarks</span></span>  
 <span data-ttu-id="03ef0-120">程序集的强名称签名由程序集的文本名称、版本、区域性和公钥标记组成。</span><span class="sxs-lookup"><span data-stu-id="03ef0-120">The strong name signature of an assembly consists of the assembly's text name, version, culture, and public key token.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03ef0-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="03ef0-121">See also</span></span>

- [<span data-ttu-id="03ef0-122">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="03ef0-122">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
