---
title: IMetaDataEmit::DefinePermissionSet 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefinePermissionSet
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefinePermissionSet
helpviewer_keywords:
- DefinePermissionSet method [.NET Framework metadata]
- IMetaDataEmit::DefinePermissionSet method [.NET Framework metadata]
ms.assetid: 36cffbf7-82ca-4cf9-bf60-50ab491ac2d9
topic_type:
- apiref
ms.openlocfilehash: 4e11a52c977de7796043868e80c147d8cfd1f506
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431571"
---
# <a name="imetadataemitdefinepermissionset-method"></a><span data-ttu-id="12cd5-102">IMetaDataEmit::DefinePermissionSet 方法</span><span class="sxs-lookup"><span data-stu-id="12cd5-102">IMetaDataEmit::DefinePermissionSet Method</span></span>
<span data-ttu-id="12cd5-103">Creates a definition for a permission set with the specified metadata signature, and gets a token to that permission set definition.</span><span class="sxs-lookup"><span data-stu-id="12cd5-103">Creates a definition for a permission set with the specified metadata signature, and gets a token to that permission set definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12cd5-104">语法</span><span class="sxs-lookup"><span data-stu-id="12cd5-104">Syntax</span></span>  
  
```cpp  
HRESULT DefinePermissionSet (  
    [in]  mdToken        tk,   
    [in]  DWORD          dwAction,   
    [in]  void const     *pvPermission,   
    [in]  ULONG          cbPermission,   
    [out] mdPermission   *ppm   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="12cd5-105">参数</span><span class="sxs-lookup"><span data-stu-id="12cd5-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="12cd5-106">[in] The object to be decorated.</span><span class="sxs-lookup"><span data-stu-id="12cd5-106">[in] The object to be decorated.</span></span>  
  
 `dwAction`  
 <span data-ttu-id="12cd5-107">[in] A [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span><span class="sxs-lookup"><span data-stu-id="12cd5-107">[in] A [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span></span>  
  
 `pvPermission`  
 <span data-ttu-id="12cd5-108">[in] The permission BLOB.</span><span class="sxs-lookup"><span data-stu-id="12cd5-108">[in] The permission BLOB.</span></span>  
  
 `cbPermission`  
 <span data-ttu-id="12cd5-109">[in] The size, in bytes, of `pvPermission`.</span><span class="sxs-lookup"><span data-stu-id="12cd5-109">[in] The size, in bytes, of `pvPermission`.</span></span>  
  
 `ppm`  
 <span data-ttu-id="12cd5-110">[out] The returned permission token.</span><span class="sxs-lookup"><span data-stu-id="12cd5-110">[out] The returned permission token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12cd5-111">要求</span><span class="sxs-lookup"><span data-stu-id="12cd5-111">Requirements</span></span>  
 <span data-ttu-id="12cd5-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="12cd5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12cd5-113">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="12cd5-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="12cd5-114">**Library:** Used as a resource in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="12cd5-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="12cd5-115">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12cd5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12cd5-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="12cd5-116">See also</span></span>

- [<span data-ttu-id="12cd5-117">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="12cd5-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="12cd5-118">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="12cd5-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
