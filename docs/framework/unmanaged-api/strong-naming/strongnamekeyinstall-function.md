---
title: StrongNameKeyInstall 函数
ms.date: 03/30/2017
api_name:
- StrongNameKeyInstall
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyInstall
helpviewer_keywords:
- StrongNameKeyInstall function [.NET Framework strong naming]
ms.assetid: e32fd546-7757-4681-be3d-658e93281e50
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ecd52fce8033876f0599fa0ba25fae0850c0e01f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54508475"
---
# <a name="strongnamekeyinstall-function"></a><span data-ttu-id="358f6-102">StrongNameKeyInstall 函数</span><span class="sxs-lookup"><span data-stu-id="358f6-102">StrongNameKeyInstall Function</span></span>
<span data-ttu-id="358f6-103">将公钥/私钥对导入容器。</span><span class="sxs-lookup"><span data-stu-id="358f6-103">Imports a public/private key pair into a container.</span></span>  
  
 <span data-ttu-id="358f6-104">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="358f6-104">This function has been deprecated.</span></span> <span data-ttu-id="358f6-105">使用[iclrstrongname:: Strongnamekeyinstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)方法相反。</span><span class="sxs-lookup"><span data-stu-id="358f6-105">Use the [ICLRStrongName::StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="358f6-106">语法</span><span class="sxs-lookup"><span data-stu-id="358f6-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameKeyInstall (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="358f6-107">参数</span><span class="sxs-lookup"><span data-stu-id="358f6-107">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="358f6-108">[in]密钥容器的名称。</span><span class="sxs-lookup"><span data-stu-id="358f6-108">[in] The name of the key container.</span></span> <span data-ttu-id="358f6-109">`wszKeyContainer` 必须为非空字符串。</span><span class="sxs-lookup"><span data-stu-id="358f6-109">`wszKeyContainer` must be a non-empty string.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="358f6-110">[in]二进制密钥对。</span><span class="sxs-lookup"><span data-stu-id="358f6-110">[in] The binary key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="358f6-111">[in]大小，以字节为单位的`pbKeyBlob`。</span><span class="sxs-lookup"><span data-stu-id="358f6-111">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="358f6-112">返回值</span><span class="sxs-lookup"><span data-stu-id="358f6-112">Return Value</span></span>  
 <span data-ttu-id="358f6-113">`true` 在成功完成;否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="358f6-113">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="358f6-114">备注</span><span class="sxs-lookup"><span data-stu-id="358f6-114">Remarks</span></span>  
 <span data-ttu-id="358f6-115">使用[StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeydelete-function.md)函数来删除密钥容器。</span><span class="sxs-lookup"><span data-stu-id="358f6-115">Use the [StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeydelete-function.md) function to delete the key container.</span></span>  
  
 <span data-ttu-id="358f6-116">如果`StrongNameKeyInstall`函数不成功完成，则调用[StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md)函数检索最后一个生成的错误。</span><span class="sxs-lookup"><span data-stu-id="358f6-116">If the `StrongNameKeyInstall` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="358f6-117">要求</span><span class="sxs-lookup"><span data-stu-id="358f6-117">Requirements</span></span>  
 <span data-ttu-id="358f6-118">**平台：** WindSee[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="358f6-118">**Platforms:** WindSee [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="358f6-119">**标头：** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="358f6-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="358f6-120">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="358f6-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="358f6-121">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="358f6-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="358f6-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="358f6-122">See also</span></span>
- [<span data-ttu-id="358f6-123">StrongNameKeyInstall 方法</span><span class="sxs-lookup"><span data-stu-id="358f6-123">StrongNameKeyInstall Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="358f6-124">StrongNameKeyDelete 方法</span><span class="sxs-lookup"><span data-stu-id="358f6-124">StrongNameKeyDelete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="358f6-125">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="358f6-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
