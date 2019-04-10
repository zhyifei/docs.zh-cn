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
ms.openlocfilehash: 412aa8fd30294ac9681a5edd02bb4bdfe25b3fab
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59143983"
---
# <a name="iclrstrongnamestrongnamekeydelete-method"></a><span data-ttu-id="fbed5-102">ICLRStrongName::StrongNameKeyDelete 方法</span><span class="sxs-lookup"><span data-stu-id="fbed5-102">ICLRStrongName::StrongNameKeyDelete Method</span></span>
<span data-ttu-id="fbed5-103">删除指定的密钥容器。</span><span class="sxs-lookup"><span data-stu-id="fbed5-103">Deletes the specified key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbed5-104">语法</span><span class="sxs-lookup"><span data-stu-id="fbed5-104">Syntax</span></span>  
  
```  
HRESULT StrongNameKeyDelete (  
    [in]  LPCWSTR   wszKeyContainer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fbed5-105">参数</span><span class="sxs-lookup"><span data-stu-id="fbed5-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="fbed5-106">[in]若要删除的密钥容器的名称。</span><span class="sxs-lookup"><span data-stu-id="fbed5-106">[in] The name of the key container to delete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fbed5-107">返回值</span><span class="sxs-lookup"><span data-stu-id="fbed5-107">Return Value</span></span>  
 `S_OK` <span data-ttu-id="fbed5-108">如果成功，则完成的方法否则为指示失败的 HRESULT 值 (请参阅[常见的 HRESULT 值](https://go.microsoft.com/fwlink/?LinkId=213878)列表)。</span><span class="sxs-lookup"><span data-stu-id="fbed5-108">if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fbed5-109">备注</span><span class="sxs-lookup"><span data-stu-id="fbed5-109">Remarks</span></span>  
 <span data-ttu-id="fbed5-110">使用[iclrstrongname:: Strongnamekeyinstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)方法来导入容器的公钥/私钥对。</span><span class="sxs-lookup"><span data-stu-id="fbed5-110">Use the [ICLRStrongName::StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md) method to import a public/private key pair into a container.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fbed5-111">要求</span><span class="sxs-lookup"><span data-stu-id="fbed5-111">Requirements</span></span>  
 <span data-ttu-id="fbed5-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fbed5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fbed5-113">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="fbed5-113">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="fbed5-114">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="fbed5-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="fbed5-115">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="fbed5-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fbed5-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="fbed5-116">See also</span></span>

- [<span data-ttu-id="fbed5-117">StrongNameKeyInstall 方法</span><span class="sxs-lookup"><span data-stu-id="fbed5-117">StrongNameKeyInstall Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="fbed5-118">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="fbed5-118">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
