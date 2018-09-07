---
title: ICLRStrongName::StrongNameKeyDelete 方法
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameKeyDelete
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameKeyDelete
helpviewer_keywords:
- StrongNameKeyDelete method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameKeyDelete method [.NET Framework hosting]
ms.assetid: 0163412f-f617-4428-89e0-03992fec31e8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2515eb0e33a033e78843d68754d3175e91165dff
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "44087334"
---
# <a name="iclrstrongnamestrongnamekeydelete-method"></a><span data-ttu-id="6d4af-102">ICLRStrongName::StrongNameKeyDelete 方法</span><span class="sxs-lookup"><span data-stu-id="6d4af-102">ICLRStrongName::StrongNameKeyDelete Method</span></span>
<span data-ttu-id="6d4af-103">删除指定的密钥容器。</span><span class="sxs-lookup"><span data-stu-id="6d4af-103">Deletes the specified key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d4af-104">语法</span><span class="sxs-lookup"><span data-stu-id="6d4af-104">Syntax</span></span>  
  
```  
HRESULT StrongNameKeyDelete (  
    [in]  LPCWSTR   wszKeyContainer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6d4af-105">参数</span><span class="sxs-lookup"><span data-stu-id="6d4af-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="6d4af-106">[in]若要删除的密钥容器的名称。</span><span class="sxs-lookup"><span data-stu-id="6d4af-106">[in] The name of the key container to delete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6d4af-107">返回值</span><span class="sxs-lookup"><span data-stu-id="6d4af-107">Return Value</span></span>  
 <span data-ttu-id="6d4af-108">`S_OK` 如果成功，则完成的方法否则为指示失败的 HRESULT 值 (请参阅[常见的 HRESULT 值](https://go.microsoft.com/fwlink/?LinkId=213878)列表)。</span><span class="sxs-lookup"><span data-stu-id="6d4af-108">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6d4af-109">备注</span><span class="sxs-lookup"><span data-stu-id="6d4af-109">Remarks</span></span>  
 <span data-ttu-id="6d4af-110">使用[iclrstrongname:: Strongnamekeyinstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)方法来导入容器的公钥/私钥对。</span><span class="sxs-lookup"><span data-stu-id="6d4af-110">Use the [ICLRStrongName::StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md) method to import a public/private key pair into a container.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d4af-111">要求</span><span class="sxs-lookup"><span data-stu-id="6d4af-111">Requirements</span></span>  
 <span data-ttu-id="6d4af-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6d4af-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d4af-113">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="6d4af-113">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="6d4af-114">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="6d4af-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6d4af-115">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d4af-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d4af-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="6d4af-116">See Also</span></span>  
 [<span data-ttu-id="6d4af-117">StrongNameKeyInstall 方法</span><span class="sxs-lookup"><span data-stu-id="6d4af-117">StrongNameKeyInstall Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)  
 [<span data-ttu-id="6d4af-118">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="6d4af-118">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
