---
title: ICLRStrongName::StrongNameKeyInstall 方法
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameKeyInstall
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameKeyInstall
helpviewer_keywords:
- ICLRStrongName::StrongNameKeyInstall method [.NET Framework hosting]
- StrongNameKeyInstall method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 5c15cf3b-164c-49d1-8e57-e42949d55acf
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 572afc5eb9ec3cf52199e5ad74406c876485461c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434085"
---
# <a name="iclrstrongnamestrongnamekeyinstall-method"></a><span data-ttu-id="9039e-102">ICLRStrongName::StrongNameKeyInstall 方法</span><span class="sxs-lookup"><span data-stu-id="9039e-102">ICLRStrongName::StrongNameKeyInstall Method</span></span>
<span data-ttu-id="9039e-103">将公钥/私钥对导入容器。</span><span class="sxs-lookup"><span data-stu-id="9039e-103">Imports a public/private key pair into a container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9039e-104">语法</span><span class="sxs-lookup"><span data-stu-id="9039e-104">Syntax</span></span>  
  
```  
HRESULT StrongNameKeyInstall (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9039e-105">参数</span><span class="sxs-lookup"><span data-stu-id="9039e-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="9039e-106">[in]密钥容器的名称。</span><span class="sxs-lookup"><span data-stu-id="9039e-106">[in] The name of the key container.</span></span> <span data-ttu-id="9039e-107">`wszKeyContainer` 必须非空字符串。</span><span class="sxs-lookup"><span data-stu-id="9039e-107">`wszKeyContainer` must be a non-empty string.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="9039e-108">[in]二进制的密钥对。</span><span class="sxs-lookup"><span data-stu-id="9039e-108">[in] The binary key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="9039e-109">[in]大小，以字节为单位的`pbKeyBlob`。</span><span class="sxs-lookup"><span data-stu-id="9039e-109">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9039e-110">返回值</span><span class="sxs-lookup"><span data-stu-id="9039e-110">Return Value</span></span>  
 <span data-ttu-id="9039e-111">`S_OK` 如果成功，则完成的方法否则为该值指示失败的 HRESULT 值 (请参阅[常见的 HRESULT 值](http://go.microsoft.com/fwlink/?LinkId=213878)有关的列表)。</span><span class="sxs-lookup"><span data-stu-id="9039e-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9039e-112">备注</span><span class="sxs-lookup"><span data-stu-id="9039e-112">Remarks</span></span>  
 <span data-ttu-id="9039e-113">使用[iclrstrongname:: Strongnamekeydelete](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md)方法来删除密钥容器。</span><span class="sxs-lookup"><span data-stu-id="9039e-113">Use the [ICLRStrongName::StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md) method to delete the key container.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9039e-114">要求</span><span class="sxs-lookup"><span data-stu-id="9039e-114">Requirements</span></span>  
 <span data-ttu-id="9039e-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9039e-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9039e-116">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="9039e-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="9039e-117">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="9039e-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9039e-118">**.NET framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9039e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9039e-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="9039e-119">See Also</span></span>  
 [<span data-ttu-id="9039e-120">StrongNameKeyDelete 方法</span><span class="sxs-lookup"><span data-stu-id="9039e-120">StrongNameKeyDelete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md)  
 [<span data-ttu-id="9039e-121">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="9039e-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
