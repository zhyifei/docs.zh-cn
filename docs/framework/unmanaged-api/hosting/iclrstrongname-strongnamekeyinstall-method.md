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
ms.openlocfilehash: 693a5831934647256ac48c8f3a2d30325dee4349
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73135035"
---
# <a name="iclrstrongnamestrongnamekeyinstall-method"></a><span data-ttu-id="0cb35-102">ICLRStrongName::StrongNameKeyInstall 方法</span><span class="sxs-lookup"><span data-stu-id="0cb35-102">ICLRStrongName::StrongNameKeyInstall Method</span></span>
<span data-ttu-id="0cb35-103">将公钥/私钥对导入容器。</span><span class="sxs-lookup"><span data-stu-id="0cb35-103">Imports a public/private key pair into a container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0cb35-104">语法</span><span class="sxs-lookup"><span data-stu-id="0cb35-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyInstall (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0cb35-105">参数</span><span class="sxs-lookup"><span data-stu-id="0cb35-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="0cb35-106">中密钥容器的名称。</span><span class="sxs-lookup"><span data-stu-id="0cb35-106">[in] The name of the key container.</span></span> <span data-ttu-id="0cb35-107">`wszKeyContainer` 必须为非空字符串。</span><span class="sxs-lookup"><span data-stu-id="0cb35-107">`wszKeyContainer` must be a non-empty string.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="0cb35-108">中二进制密钥对。</span><span class="sxs-lookup"><span data-stu-id="0cb35-108">[in] The binary key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="0cb35-109">中`pbKeyBlob`的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="0cb35-109">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0cb35-110">返回值</span><span class="sxs-lookup"><span data-stu-id="0cb35-110">Return Value</span></span>  
 <span data-ttu-id="0cb35-111">如果方法已成功完成，则 `S_OK`;否则，表示失败的 HRESULT 值（请参阅列表的[常见 HRESULT 值](https://go.microsoft.com/fwlink/?LinkId=213878)）。</span><span class="sxs-lookup"><span data-stu-id="0cb35-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0cb35-112">备注</span><span class="sxs-lookup"><span data-stu-id="0cb35-112">Remarks</span></span>  
 <span data-ttu-id="0cb35-113">使用[ICLRStrongName：： StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md)方法删除密钥容器。</span><span class="sxs-lookup"><span data-stu-id="0cb35-113">Use the [ICLRStrongName::StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md) method to delete the key container.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0cb35-114">要求</span><span class="sxs-lookup"><span data-stu-id="0cb35-114">Requirements</span></span>  
 <span data-ttu-id="0cb35-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0cb35-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0cb35-116">**标头：** MetaHost</span><span class="sxs-lookup"><span data-stu-id="0cb35-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="0cb35-117">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="0cb35-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0cb35-118">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0cb35-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cb35-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="0cb35-119">See also</span></span>

- [<span data-ttu-id="0cb35-120">StrongNameKeyDelete 方法</span><span class="sxs-lookup"><span data-stu-id="0cb35-120">StrongNameKeyDelete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="0cb35-121">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="0cb35-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
