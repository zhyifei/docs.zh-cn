---
title: IMetaDataImport::GetPermissionSetProps 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetPermissionSetProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetPermissionSetProps
helpviewer_keywords:
- GetPermissionSetProps method [.NET Framework metadata]
- IMetaDataImport::GetPermissionSetProps method [.NET Framework metadata]
ms.assetid: 9855f0e4-12c0-4d3d-ab5d-d6bc52d25eae
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: be9b2fa3037dc00bce52d9ff89291d1c02cffc38
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449294"
---
# <a name="imetadataimportgetpermissionsetprops-method"></a><span data-ttu-id="73b15-102">IMetaDataImport::GetPermissionSetProps 方法</span><span class="sxs-lookup"><span data-stu-id="73b15-102">IMetaDataImport::GetPermissionSetProps Method</span></span>
<span data-ttu-id="73b15-103">获取与关联的元数据<xref:System.Security.PermissionSet?displayProperty=nameWithType>由指定的 Permission 标记表示。</span><span class="sxs-lookup"><span data-stu-id="73b15-103">Gets the metadata associated with the <xref:System.Security.PermissionSet?displayProperty=nameWithType> represented by the specified Permission token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73b15-104">语法</span><span class="sxs-lookup"><span data-stu-id="73b15-104">Syntax</span></span>  
  
```  
HRESULT GetPermissionSetProps (  
   [in]  mdPermission      pm,  
   [out] DWORD             *pdwAction,   
   [out] void const        **ppvPermission,   
   [out] ULONG             *pcbPermission  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="73b15-105">参数</span><span class="sxs-lookup"><span data-stu-id="73b15-105">Parameters</span></span>  
 `pm`  
 <span data-ttu-id="73b15-106">[in]表示要获取的元数据属性的权限集权限元数据标记。</span><span class="sxs-lookup"><span data-stu-id="73b15-106">[in] The Permission metadata token that represents the permission set to get the metadata properties for.</span></span>  
  
 `pdwAction`  
 <span data-ttu-id="73b15-107">[out]指向的权限集的指针。</span><span class="sxs-lookup"><span data-stu-id="73b15-107">[out] A pointer to the permission set.</span></span>  
  
 `ppvPermission`  
 <span data-ttu-id="73b15-108">[out]指向的权限集的二进制元数据签名的指针。</span><span class="sxs-lookup"><span data-stu-id="73b15-108">[out] A pointer to the binary metadata signature of the permission set.</span></span>  
  
 `pcbPermission`  
 <span data-ttu-id="73b15-109">[out]以字节为单位的大小`ppvPermission`。</span><span class="sxs-lookup"><span data-stu-id="73b15-109">[out] The size in bytes of `ppvPermission`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73b15-110">要求</span><span class="sxs-lookup"><span data-stu-id="73b15-110">Requirements</span></span>  
 <span data-ttu-id="73b15-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="73b15-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73b15-112">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="73b15-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="73b15-113">**库：** 作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="73b15-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="73b15-114">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73b15-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73b15-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="73b15-115">See Also</span></span>  
 <xref:System.Security.PermissionSet>  
 [<span data-ttu-id="73b15-116">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="73b15-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="73b15-117">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="73b15-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
