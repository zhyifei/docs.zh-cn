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
ms.openlocfilehash: 95098cbb060c06d2d5a5a4c04b6fa9017bca66a1
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2020
ms.locfileid: "75899598"
---
# <a name="iclrstrongnamestrongnamekeydelete-method"></a><span data-ttu-id="d2a39-102">ICLRStrongName::StrongNameKeyDelete 方法</span><span class="sxs-lookup"><span data-stu-id="d2a39-102">ICLRStrongName::StrongNameKeyDelete Method</span></span>
<span data-ttu-id="d2a39-103">删除指定的密钥容器。</span><span class="sxs-lookup"><span data-stu-id="d2a39-103">Deletes the specified key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2a39-104">语法</span><span class="sxs-lookup"><span data-stu-id="d2a39-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyDelete (  
    [in]  LPCWSTR   wszKeyContainer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d2a39-105">参数</span><span class="sxs-lookup"><span data-stu-id="d2a39-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="d2a39-106">中要删除的密钥容器的名称。</span><span class="sxs-lookup"><span data-stu-id="d2a39-106">[in] The name of the key container to delete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d2a39-107">返回值</span><span class="sxs-lookup"><span data-stu-id="d2a39-107">Return Value</span></span>  
 <span data-ttu-id="d2a39-108">如果方法已成功完成，则 `S_OK`;否则，表示失败的 HRESULT 值（请参阅列表的[常见 HRESULT 值](/windows/win32/seccrypto/common-hresult-values)）。</span><span class="sxs-lookup"><span data-stu-id="d2a39-108">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d2a39-109">备注</span><span class="sxs-lookup"><span data-stu-id="d2a39-109">Remarks</span></span>  
 <span data-ttu-id="d2a39-110">使用[ICLRStrongName：： StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)方法将公钥/私钥对导入到容器中。</span><span class="sxs-lookup"><span data-stu-id="d2a39-110">Use the [ICLRStrongName::StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md) method to import a public/private key pair into a container.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2a39-111">需求</span><span class="sxs-lookup"><span data-stu-id="d2a39-111">Requirements</span></span>  
 <span data-ttu-id="d2a39-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d2a39-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2a39-113">**标头：** MetaHost</span><span class="sxs-lookup"><span data-stu-id="d2a39-113">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="d2a39-114">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="d2a39-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d2a39-115">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2a39-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2a39-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d2a39-116">See also</span></span>

- [<span data-ttu-id="d2a39-117">StrongNameKeyInstall 方法</span><span class="sxs-lookup"><span data-stu-id="d2a39-117">StrongNameKeyInstall Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="d2a39-118">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="d2a39-118">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
