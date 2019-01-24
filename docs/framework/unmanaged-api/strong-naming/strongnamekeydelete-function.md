---
title: StrongNameKeyDelete 函数
ms.date: 03/30/2017
api_name:
- StrongNameKeyDelete
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyDelete
helpviewer_keywords:
- StrongNameKeyDelete function [.NET Framework strong naming]
ms.assetid: 313e71e4-1790-4d2f-b68b-5040ebd1c149
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3eace88e5034c61b7608a6d777608cc2544b8564
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54688475"
---
# <a name="strongnamekeydelete-function"></a><span data-ttu-id="42175-102">StrongNameKeyDelete 函数</span><span class="sxs-lookup"><span data-stu-id="42175-102">StrongNameKeyDelete Function</span></span>
<span data-ttu-id="42175-103">删除指定的密钥容器。</span><span class="sxs-lookup"><span data-stu-id="42175-103">Deletes the specified key container.</span></span>  
  
 <span data-ttu-id="42175-104">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="42175-104">This function has been deprecated.</span></span> <span data-ttu-id="42175-105">使用[iclrstrongname:: Strongnamekeydelete](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md)方法相反。</span><span class="sxs-lookup"><span data-stu-id="42175-105">Use the [ICLRStrongName::StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42175-106">语法</span><span class="sxs-lookup"><span data-stu-id="42175-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameKeyDelete (  
    [in]  LPCWSTR   wszKeyContainer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="42175-107">参数</span><span class="sxs-lookup"><span data-stu-id="42175-107">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="42175-108">[in]若要删除的密钥容器的名称。</span><span class="sxs-lookup"><span data-stu-id="42175-108">[in] The name of the key container to delete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="42175-109">返回值</span><span class="sxs-lookup"><span data-stu-id="42175-109">Return Value</span></span>  
 <span data-ttu-id="42175-110">`true` 在成功完成;否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="42175-110">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="42175-111">备注</span><span class="sxs-lookup"><span data-stu-id="42175-111">Remarks</span></span>  
 <span data-ttu-id="42175-112">使用[StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeyinstall-function.md)函数 importa 公钥/私钥对到容器中。</span><span class="sxs-lookup"><span data-stu-id="42175-112">Use the [StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeyinstall-function.md) function to importa a public/private key pair into a container.</span></span>  
  
 <span data-ttu-id="42175-113">如果`StrongNameKeyDelete`函数不成功完成，则调用[StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md)函数检索最后一个生成的错误。</span><span class="sxs-lookup"><span data-stu-id="42175-113">If the `StrongNameKeyDelete` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42175-114">要求</span><span class="sxs-lookup"><span data-stu-id="42175-114">Requirements</span></span>  
 <span data-ttu-id="42175-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="42175-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42175-116">**标头：** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="42175-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="42175-117">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="42175-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="42175-118">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42175-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42175-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="42175-119">See also</span></span>
- [<span data-ttu-id="42175-120">StrongNameKeyDelete 方法</span><span class="sxs-lookup"><span data-stu-id="42175-120">StrongNameKeyDelete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="42175-121">StrongNameKeyInstall 方法</span><span class="sxs-lookup"><span data-stu-id="42175-121">StrongNameKeyInstall Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="42175-122">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="42175-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
