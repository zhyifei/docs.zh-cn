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
ms.openlocfilehash: 4e72818be6808c519677192d3744bbc5ec414d0d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73135080"
---
# <a name="iclrstrongnamestrongnamekeydelete-method"></a><span data-ttu-id="95222-102">ICLRStrongName::StrongNameKeyDelete 方法</span><span class="sxs-lookup"><span data-stu-id="95222-102">ICLRStrongName::StrongNameKeyDelete Method</span></span>
<span data-ttu-id="95222-103">删除指定的密钥容器。</span><span class="sxs-lookup"><span data-stu-id="95222-103">Deletes the specified key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95222-104">语法</span><span class="sxs-lookup"><span data-stu-id="95222-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyDelete (  
    [in]  LPCWSTR   wszKeyContainer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="95222-105">参数</span><span class="sxs-lookup"><span data-stu-id="95222-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="95222-106">中要删除的密钥容器的名称。</span><span class="sxs-lookup"><span data-stu-id="95222-106">[in] The name of the key container to delete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="95222-107">返回值</span><span class="sxs-lookup"><span data-stu-id="95222-107">Return Value</span></span>  
 <span data-ttu-id="95222-108">如果方法已成功完成，则 `S_OK`;否则，表示失败的 HRESULT 值（请参阅列表的[常见 HRESULT 值](https://go.microsoft.com/fwlink/?LinkId=213878)）。</span><span class="sxs-lookup"><span data-stu-id="95222-108">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="95222-109">备注</span><span class="sxs-lookup"><span data-stu-id="95222-109">Remarks</span></span>  
 <span data-ttu-id="95222-110">使用[ICLRStrongName：： StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)方法将公钥/私钥对导入到容器中。</span><span class="sxs-lookup"><span data-stu-id="95222-110">Use the [ICLRStrongName::StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md) method to import a public/private key pair into a container.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95222-111">要求</span><span class="sxs-lookup"><span data-stu-id="95222-111">Requirements</span></span>  
 <span data-ttu-id="95222-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="95222-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95222-113">**标头：** MetaHost</span><span class="sxs-lookup"><span data-stu-id="95222-113">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="95222-114">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="95222-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="95222-115">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95222-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95222-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="95222-116">See also</span></span>

- [<span data-ttu-id="95222-117">StrongNameKeyInstall 方法</span><span class="sxs-lookup"><span data-stu-id="95222-117">StrongNameKeyInstall Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="95222-118">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="95222-118">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
