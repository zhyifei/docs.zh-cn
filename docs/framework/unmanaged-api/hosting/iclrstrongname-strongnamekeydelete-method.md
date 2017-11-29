---
title: "ICLRStrongName::StrongNameKeyDelete 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.StrongNameKeyDelete
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::StrongNameKeyDelete
helpviewer_keywords:
- StrongNameKeyDelete method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameKeyDelete method [.NET Framework hosting]
ms.assetid: 0163412f-f617-4428-89e0-03992fec31e8
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8fbb6af492007eb0dc2a9ea83c53e3559225428d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iclrstrongnamestrongnamekeydelete-method"></a><span data-ttu-id="db93a-102">ICLRStrongName::StrongNameKeyDelete 方法</span><span class="sxs-lookup"><span data-stu-id="db93a-102">ICLRStrongName::StrongNameKeyDelete Method</span></span>
<span data-ttu-id="db93a-103">删除指定的密钥容器。</span><span class="sxs-lookup"><span data-stu-id="db93a-103">Deletes the specified key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db93a-104">语法</span><span class="sxs-lookup"><span data-stu-id="db93a-104">Syntax</span></span>  
  
```  
HRESULT StrongNameKeyDelete (  
    [in]  LPCWSTR   wszKeyContainer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="db93a-105">参数</span><span class="sxs-lookup"><span data-stu-id="db93a-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="db93a-106">[in]要删除的密钥容器的名称。</span><span class="sxs-lookup"><span data-stu-id="db93a-106">[in] The name of the key container to delete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="db93a-107">返回值</span><span class="sxs-lookup"><span data-stu-id="db93a-107">Return Value</span></span>  
 <span data-ttu-id="db93a-108">`S_OK`如果成功，则完成的方法否则为该值指示失败的 HRESULT 值 (请参阅[常见的 HRESULT 值](http://go.microsoft.com/fwlink/?LinkId=213878)有关的列表)。</span><span class="sxs-lookup"><span data-stu-id="db93a-108">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="db93a-109">备注</span><span class="sxs-lookup"><span data-stu-id="db93a-109">Remarks</span></span>  
 <span data-ttu-id="db93a-110">使用[iclrstrongname:: Strongnamekeyinstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)方法导入容器的公钥/私钥对。</span><span class="sxs-lookup"><span data-stu-id="db93a-110">Use the [ICLRStrongName::StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md) method to import a public/private key pair into a container.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db93a-111">要求</span><span class="sxs-lookup"><span data-stu-id="db93a-111">Requirements</span></span>  
 <span data-ttu-id="db93a-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="db93a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db93a-113">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="db93a-113">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="db93a-114">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="db93a-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="db93a-115">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db93a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db93a-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="db93a-116">See Also</span></span>  
 [<span data-ttu-id="db93a-117">StrongNameKeyInstall 方法</span><span class="sxs-lookup"><span data-stu-id="db93a-117">StrongNameKeyInstall Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)  
 [<span data-ttu-id="db93a-118">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="db93a-118">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
