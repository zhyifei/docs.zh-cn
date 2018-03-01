---
title: "StrongNameSignatureSize 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- StrongNameSignatureSize
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureSize
helpviewer_keywords:
- StrongNameSignatureSize function [.NET Framework strong naming]
ms.assetid: 4fde4cd0-f53e-4411-a2fe-fc5c54472f95
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 70aa82d5eef62856e8377c75515fb3b187d3ae6d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="strongnamesignaturesize-function"></a><span data-ttu-id="7a0c4-102">StrongNameSignatureSize 函数</span><span class="sxs-lookup"><span data-stu-id="7a0c4-102">StrongNameSignatureSize Function</span></span>
<span data-ttu-id="7a0c4-103">返回强名称签名的大小。</span><span class="sxs-lookup"><span data-stu-id="7a0c4-103">Returns the size of the strong name signature.</span></span> <span data-ttu-id="7a0c4-104">`StrongNameSignatureSize`通常用于由编译器确定要创建延迟签名的程序集时，在该文件中保留多少空间。</span><span class="sxs-lookup"><span data-stu-id="7a0c4-104">`StrongNameSignatureSize` is typically used by compilers to determine how much space to reserve in the file when creating a delay-signed assembly.</span></span>  
  
 <span data-ttu-id="7a0c4-105">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="7a0c4-105">This function has been deprecated.</span></span> <span data-ttu-id="7a0c4-106">使用[iclrstrongname:: Strongnamesignaturesize](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturesize-method.md)方法相反。</span><span class="sxs-lookup"><span data-stu-id="7a0c4-106">Use the [ICLRStrongName::StrongNameSignatureSize](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturesize-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a0c4-107">语法</span><span class="sxs-lookup"><span data-stu-id="7a0c4-107">Syntax</span></span>  
  
```  
BOOLEAN StrongNameSignatureSize (   
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,   
    [in]  DWORD  *pcbSize  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="7a0c4-108">参数</span><span class="sxs-lookup"><span data-stu-id="7a0c4-108">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="7a0c4-109">[in]类型的结构[PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)包含用于生成强名称签名的密钥对的公共部分。</span><span class="sxs-lookup"><span data-stu-id="7a0c4-109">[in] A structure of type [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="7a0c4-110">[in]大小，以字节为单位的`pbPublicKeyBlob`。</span><span class="sxs-lookup"><span data-stu-id="7a0c4-110">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="7a0c4-111">[in]存储的强名称签名所需的字节数。</span><span class="sxs-lookup"><span data-stu-id="7a0c4-111">[in] The number of bytes required to store the strong name signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7a0c4-112">返回值</span><span class="sxs-lookup"><span data-stu-id="7a0c4-112">Return Value</span></span>  
 <span data-ttu-id="7a0c4-113">`true`在成功完成;否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="7a0c4-113">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7a0c4-114">备注</span><span class="sxs-lookup"><span data-stu-id="7a0c4-114">Remarks</span></span>  
 <span data-ttu-id="7a0c4-115">如果`StrongNameSignatureSize`函数未成功完成，请调用[StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md)函数可检索的最后一个生成的错误。</span><span class="sxs-lookup"><span data-stu-id="7a0c4-115">If the `StrongNameSignatureSize` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a0c4-116">惠?</span><span class="sxs-lookup"><span data-stu-id="7a0c4-116">Requirements</span></span>  
 <span data-ttu-id="7a0c4-117">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7a0c4-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a0c4-118">**标头：** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="7a0c4-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="7a0c4-119">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="7a0c4-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7a0c4-120">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a0c4-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a0c4-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="7a0c4-121">See Also</span></span>  
 [<span data-ttu-id="7a0c4-122">StrongNameSignatureSize 方法</span><span class="sxs-lookup"><span data-stu-id="7a0c4-122">StrongNameSignatureSize Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturesize-method.md)  
 [<span data-ttu-id="7a0c4-123">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="7a0c4-123">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
