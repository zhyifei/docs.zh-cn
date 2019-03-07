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
ms.openlocfilehash: 806f1ebcacb9e7ad27b7370f9976b3341bf64f8c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466929"
---
# <a name="imetadataimportgetpermissionsetprops-method"></a><span data-ttu-id="b8a40-102">IMetaDataImport::GetPermissionSetProps 方法</span><span class="sxs-lookup"><span data-stu-id="b8a40-102">IMetaDataImport::GetPermissionSetProps Method</span></span>
<span data-ttu-id="b8a40-103">获取与关联的元数据<xref:System.Security.PermissionSet?displayProperty=nameWithType>所表示的指定权限令牌。</span><span class="sxs-lookup"><span data-stu-id="b8a40-103">Gets the metadata associated with the <xref:System.Security.PermissionSet?displayProperty=nameWithType> represented by the specified Permission token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8a40-104">语法</span><span class="sxs-lookup"><span data-stu-id="b8a40-104">Syntax</span></span>  
  
```  
HRESULT GetPermissionSetProps (  
   [in]  mdPermission      pm,  
   [out] DWORD             *pdwAction,   
   [out] void const        **ppvPermission,   
   [out] ULONG             *pcbPermission  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b8a40-105">参数</span><span class="sxs-lookup"><span data-stu-id="b8a40-105">Parameters</span></span>  
 `pm`  
 <span data-ttu-id="b8a40-106">[in]表示要获取其元数据属性的权限集的权限的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="b8a40-106">[in] The Permission metadata token that represents the permission set to get the metadata properties for.</span></span>  
  
 `pdwAction`  
 <span data-ttu-id="b8a40-107">[out]指向在权限集中的指针。</span><span class="sxs-lookup"><span data-stu-id="b8a40-107">[out] A pointer to the permission set.</span></span>  
  
 `ppvPermission`  
 <span data-ttu-id="b8a40-108">[out]一个指向权限集的二进制元数据签名。</span><span class="sxs-lookup"><span data-stu-id="b8a40-108">[out] A pointer to the binary metadata signature of the permission set.</span></span>  
  
 `pcbPermission`  
 <span data-ttu-id="b8a40-109">[out]以字节为单位的大小`ppvPermission`。</span><span class="sxs-lookup"><span data-stu-id="b8a40-109">[out] The size in bytes of `ppvPermission`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8a40-110">要求</span><span class="sxs-lookup"><span data-stu-id="b8a40-110">Requirements</span></span>  
 <span data-ttu-id="b8a40-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b8a40-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8a40-112">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b8a40-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b8a40-113">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="b8a40-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b8a40-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8a40-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8a40-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="b8a40-115">See also</span></span>
- <xref:System.Security.PermissionSet>
- [<span data-ttu-id="b8a40-116">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="b8a40-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="b8a40-117">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="b8a40-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
