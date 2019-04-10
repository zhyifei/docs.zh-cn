---
title: StrongNameCompareAssemblies 函数
ms.date: 03/30/2017
api_name:
- StrongNameCompareAssemblies
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameCompareAssemblies
helpviewer_keywords:
- StrongNameCompareAssemblies function [.NET Framework strong naming]
ms.assetid: 763f2375-efc6-4219-8806-a3b0567ef72b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2a49252d00f75b4d0b6325aeae0aab22f8ada5e4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59191375"
---
# <a name="strongnamecompareassemblies-function"></a><span data-ttu-id="01766-102">StrongNameCompareAssemblies 函数</span><span class="sxs-lookup"><span data-stu-id="01766-102">StrongNameCompareAssemblies Function</span></span>
<span data-ttu-id="01766-103">确定两个程序集是否仅是强名称签名不同。</span><span class="sxs-lookup"><span data-stu-id="01766-103">Determines whether two assemblies differ only by their strong name signatures.</span></span>  
  
 <span data-ttu-id="01766-104">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="01766-104">This function has been deprecated.</span></span> <span data-ttu-id="01766-105">使用[iclrstrongname:: Strongnamecompareassemblies](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamecompareassemblies-method.md)方法相反。</span><span class="sxs-lookup"><span data-stu-id="01766-105">Use the [ICLRStrongName::StrongNameCompareAssemblies](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamecompareassemblies-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01766-106">语法</span><span class="sxs-lookup"><span data-stu-id="01766-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="01766-107">参数</span><span class="sxs-lookup"><span data-stu-id="01766-107">Parameters</span></span>  
 `wszAssembly1`  
 <span data-ttu-id="01766-108">[in]第一个程序集的路径。</span><span class="sxs-lookup"><span data-stu-id="01766-108">[in] The path to the first assembly.</span></span>  
  
 `wszAssembly2`  
 <span data-ttu-id="01766-109">[in]第二个程序集的路径。</span><span class="sxs-lookup"><span data-stu-id="01766-109">[in] The path to the second assembly.</span></span>  
  
 `pdwResult`  
 <span data-ttu-id="01766-110">[out]以下值之一：</span><span class="sxs-lookup"><span data-stu-id="01766-110">[out] One of the following values:</span></span>  
  
-   `SN_CMP_DIFFERENT` <span data-ttu-id="01766-111">(0)-指定程序集包含不同的数据。</span><span class="sxs-lookup"><span data-stu-id="01766-111">(0) - Specifies that the assemblies contain different data.</span></span>  
  
-   `SN_CMP_IDENTICAL` <span data-ttu-id="01766-112">(1)-指定程序的程序集完全相同，包括其签名和校验和。</span><span class="sxs-lookup"><span data-stu-id="01766-112">(1) - Specifies that the assemblies are exactly the same, including their signatures and checksum.</span></span>  
  
-   `SN_CMP_SIGONLY` <span data-ttu-id="01766-113">(2)-指定程序集仅签名和校验和不同。</span><span class="sxs-lookup"><span data-stu-id="01766-113">(2) - Specifies that the assemblies differ only by signature and checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="01766-114">返回值</span><span class="sxs-lookup"><span data-stu-id="01766-114">Return Value</span></span>  
 `true` <span data-ttu-id="01766-115">在成功完成;否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="01766-115">on successful completion; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01766-116">要求</span><span class="sxs-lookup"><span data-stu-id="01766-116">Requirements</span></span>  
 <span data-ttu-id="01766-117">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="01766-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01766-118">**标头：** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="01766-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="01766-119">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="01766-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="01766-120">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="01766-120">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="remarks"></a><span data-ttu-id="01766-121">备注</span><span class="sxs-lookup"><span data-stu-id="01766-121">Remarks</span></span>  
 <span data-ttu-id="01766-122">程序集的强名称签名包含程序集的文本名称、 版本、 区域性和公钥标记。</span><span class="sxs-lookup"><span data-stu-id="01766-122">The strong name signature of an assembly consists of the assembly's text name, version, culture, and public key token.</span></span>  
  
 <span data-ttu-id="01766-123">如果`StrongNameCompareAssemblies`函数不成功完成，则调用[StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md)函数检索最后一个生成的错误。</span><span class="sxs-lookup"><span data-stu-id="01766-123">If the `StrongNameCompareAssemblies` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01766-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="01766-124">See also</span></span>

- [<span data-ttu-id="01766-125">StrongNameCompareAssemblies 方法</span><span class="sxs-lookup"><span data-stu-id="01766-125">StrongNameCompareAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamecompareassemblies-method.md)
- [<span data-ttu-id="01766-126">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="01766-126">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
