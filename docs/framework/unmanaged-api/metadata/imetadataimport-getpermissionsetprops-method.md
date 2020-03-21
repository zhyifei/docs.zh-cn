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
ms.openlocfilehash: 5faf1a6ae89045b2ef17fab789ee6e5bf23eecf2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175338"
---
# <a name="imetadataimportgetpermissionsetprops-method"></a><span data-ttu-id="013ff-102">IMetaDataImport::GetPermissionSetProps 方法</span><span class="sxs-lookup"><span data-stu-id="013ff-102">IMetaDataImport::GetPermissionSetProps Method</span></span>
<span data-ttu-id="013ff-103">获取与指定权限令牌<xref:System.Security.PermissionSet?displayProperty=nameWithType>表示的元数据。</span><span class="sxs-lookup"><span data-stu-id="013ff-103">Gets the metadata associated with the <xref:System.Security.PermissionSet?displayProperty=nameWithType> represented by the specified Permission token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="013ff-104">语法</span><span class="sxs-lookup"><span data-stu-id="013ff-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPermissionSetProps (  
   [in]  mdPermission      pm,  
   [out] DWORD             *pdwAction,
   [out] void const        **ppvPermission,
   [out] ULONG             *pcbPermission  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="013ff-105">parameters</span><span class="sxs-lookup"><span data-stu-id="013ff-105">Parameters</span></span>  
 `pm`  
 <span data-ttu-id="013ff-106">[在]表示获取元数据属性的权限集的权限元数据令牌。</span><span class="sxs-lookup"><span data-stu-id="013ff-106">[in] The Permission metadata token that represents the permission set to get the metadata properties for.</span></span>  
  
 `pdwAction`  
 <span data-ttu-id="013ff-107">[出]指向权限集的指针。</span><span class="sxs-lookup"><span data-stu-id="013ff-107">[out] A pointer to the permission set.</span></span>  
  
 `ppvPermission`  
 <span data-ttu-id="013ff-108">[出]指向权限集的二进制元数据签名的指针。</span><span class="sxs-lookup"><span data-stu-id="013ff-108">[out] A pointer to the binary metadata signature of the permission set.</span></span>  
  
 `pcbPermission`  
 <span data-ttu-id="013ff-109">[出]的大小（以字节为单位）。 `ppvPermission`</span><span class="sxs-lookup"><span data-stu-id="013ff-109">[out] The size in bytes of `ppvPermission`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="013ff-110">要求</span><span class="sxs-lookup"><span data-stu-id="013ff-110">Requirements</span></span>  
 <span data-ttu-id="013ff-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="013ff-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="013ff-112">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="013ff-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="013ff-113">**库：** 作为资源包含在 MsCorEE.dll 中</span><span class="sxs-lookup"><span data-stu-id="013ff-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="013ff-114">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="013ff-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="013ff-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="013ff-115">See also</span></span>

- <xref:System.Security.PermissionSet>
- [<span data-ttu-id="013ff-116">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="013ff-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="013ff-117">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="013ff-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
