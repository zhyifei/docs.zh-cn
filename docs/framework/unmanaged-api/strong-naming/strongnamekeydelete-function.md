---
title: "StrongNameKeyDelete 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameKeyDelete
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: StrongNameKeyDelete
helpviewer_keywords: StrongNameKeyDelete function [.NET Framework strong naming]
ms.assetid: 313e71e4-1790-4d2f-b68b-5040ebd1c149
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4c7b3ccc9ec1b8cbc81de115f734e1d11e0e0ae0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="strongnamekeydelete-function"></a><span data-ttu-id="bb102-102">StrongNameKeyDelete 函数</span><span class="sxs-lookup"><span data-stu-id="bb102-102">StrongNameKeyDelete Function</span></span>
<span data-ttu-id="bb102-103">删除指定的密钥容器。</span><span class="sxs-lookup"><span data-stu-id="bb102-103">Deletes the specified key container.</span></span>  
  
 <span data-ttu-id="bb102-104">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="bb102-104">This function has been deprecated.</span></span> <span data-ttu-id="bb102-105">使用[iclrstrongname:: Strongnamekeydelete](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md)方法相反。</span><span class="sxs-lookup"><span data-stu-id="bb102-105">Use the [ICLRStrongName::StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb102-106">语法</span><span class="sxs-lookup"><span data-stu-id="bb102-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameKeyDelete (  
    [in]  LPCWSTR   wszKeyContainer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bb102-107">参数</span><span class="sxs-lookup"><span data-stu-id="bb102-107">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="bb102-108">[in]要删除的密钥容器的名称。</span><span class="sxs-lookup"><span data-stu-id="bb102-108">[in] The name of the key container to delete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bb102-109">返回值</span><span class="sxs-lookup"><span data-stu-id="bb102-109">Return Value</span></span>  
 <span data-ttu-id="bb102-110">`true`在成功完成;否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="bb102-110">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bb102-111">备注</span><span class="sxs-lookup"><span data-stu-id="bb102-111">Remarks</span></span>  
 <span data-ttu-id="bb102-112">使用[StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeyinstall-function.md)函数来 importa 公钥/私钥对到容器。</span><span class="sxs-lookup"><span data-stu-id="bb102-112">Use the [StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeyinstall-function.md) function to importa a public/private key pair into a container.</span></span>  
  
 <span data-ttu-id="bb102-113">如果`StrongNameKeyDelete`函数未成功完成，请调用[StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md)函数可检索的最后一个生成的错误。</span><span class="sxs-lookup"><span data-stu-id="bb102-113">If the `StrongNameKeyDelete` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb102-114">要求</span><span class="sxs-lookup"><span data-stu-id="bb102-114">Requirements</span></span>  
 <span data-ttu-id="bb102-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bb102-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb102-116">**标头：** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="bb102-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="bb102-117">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="bb102-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bb102-118">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb102-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb102-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bb102-119">See Also</span></span>  
 [<span data-ttu-id="bb102-120">StrongNameKeyDelete 方法</span><span class="sxs-lookup"><span data-stu-id="bb102-120">StrongNameKeyDelete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md)  
 [<span data-ttu-id="bb102-121">StrongNameKeyInstall 方法</span><span class="sxs-lookup"><span data-stu-id="bb102-121">StrongNameKeyInstall Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)  
 [<span data-ttu-id="bb102-122">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="bb102-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
