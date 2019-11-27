---
title: IMetaDataImport::EnumPermissionSets 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumPermissionSets
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumPermissionSets
helpviewer_keywords:
- EnumPermissionSets method [.NET Framework metadata]
- IMetaDataImport::EnumPermissionSets method [.NET Framework metadata]
ms.assetid: 347d7e5c-c90f-45ad-bd1e-2c7912b0b19c
topic_type:
- apiref
ms.openlocfilehash: 9d0f443b5b7d2d358534e888c3fc84ad3f554119
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450042"
---
# <a name="imetadataimportenumpermissionsets-method"></a><span data-ttu-id="f5904-102">IMetaDataImport::EnumPermissionSets 方法</span><span class="sxs-lookup"><span data-stu-id="f5904-102">IMetaDataImport::EnumPermissionSets Method</span></span>
<span data-ttu-id="f5904-103">枚举指定的元数据范围内的对象的权限。</span><span class="sxs-lookup"><span data-stu-id="f5904-103">Enumerates permissions for the objects in a specified metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5904-104">语法</span><span class="sxs-lookup"><span data-stu-id="f5904-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumPermissionSets  
   [in, out] HCORENUM      *phEnum,   
   [in]      mdToken       tk,   
   [in]      DWORD         dwActions,  
   [out]     mdPermission  rPermission[],  
   [in]      ULONG         cMax,  
   [out]     ULONG         *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f5904-105">参数</span><span class="sxs-lookup"><span data-stu-id="f5904-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="f5904-106">[in，out]指向枚举器的指针。</span><span class="sxs-lookup"><span data-stu-id="f5904-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="f5904-107">第一次调用此方法时，此值必须为 NULL。</span><span class="sxs-lookup"><span data-stu-id="f5904-107">This must be NULL for the first call of this method.</span></span>  
  
 `tk`  
 <span data-ttu-id="f5904-108">中一个元数据令牌，用于限制搜索范围，或为 NULL 以搜索尽可能大的范围。</span><span class="sxs-lookup"><span data-stu-id="f5904-108">[in] A metadata token that limits the scope of the search, or NULL to search the widest scope possible.</span></span>  
  
 `dwActions`  
 <span data-ttu-id="f5904-109">中表示要包含在 `rPermission`中的 <xref:System.Security.Permissions.SecurityAction> 值的标志，或者为零以返回所有操作。</span><span class="sxs-lookup"><span data-stu-id="f5904-109">[in] Flags representing the <xref:System.Security.Permissions.SecurityAction> values to include in `rPermission`, or zero to return all actions.</span></span>  
  
 `rPermission`  
 <span data-ttu-id="f5904-110">弄用于存储权限令牌的数组。</span><span class="sxs-lookup"><span data-stu-id="f5904-110">[out] The array used to store the Permission tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="f5904-111">[in] `rPermission` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="f5904-111">[in] The maximum size of the `rPermission` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="f5904-112">弄`rPermission`中返回的权限令牌数。</span><span class="sxs-lookup"><span data-stu-id="f5904-112">[out] The number of Permission tokens returned in `rPermission`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f5904-113">返回值</span><span class="sxs-lookup"><span data-stu-id="f5904-113">Return Value</span></span>  
  
|<span data-ttu-id="f5904-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f5904-114">HRESULT</span></span>|<span data-ttu-id="f5904-115">说明</span><span class="sxs-lookup"><span data-stu-id="f5904-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="f5904-116">`EnumPermissionSets` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="f5904-116">`EnumPermissionSets` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="f5904-117">没有要枚举的令牌。</span><span class="sxs-lookup"><span data-stu-id="f5904-117">There are no tokens to enumerate.</span></span> <span data-ttu-id="f5904-118">在这种情况下，`pcTokens` 为零。</span><span class="sxs-lookup"><span data-stu-id="f5904-118">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f5904-119">要求</span><span class="sxs-lookup"><span data-stu-id="f5904-119">Requirements</span></span>  
 <span data-ttu-id="f5904-120">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f5904-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5904-121">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="f5904-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f5904-122">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="f5904-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f5904-123">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5904-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5904-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f5904-124">See also</span></span>

- [<span data-ttu-id="f5904-125">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="f5904-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="f5904-126">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="f5904-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
