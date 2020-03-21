---
title: IMetaDataAssemblyImport::EnumExportedTypes 方法
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumExportedTypes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumExportedTypes
helpviewer_keywords:
- EnumExportedTypes method [.NET Framework metadata]
- IMetaDataAssemblyImport::EnumExportedTypes method [.NET Framework metadata]
ms.assetid: e5912ed8-e4ce-438b-8ea3-d9e4c288d109
topic_type:
- apiref
ms.openlocfilehash: f00fe5bce2f808265add228406dfaa2ccc267545
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176001"
---
# <a name="imetadataassemblyimportenumexportedtypes-method"></a><span data-ttu-id="ee26a-102">IMetaDataAssemblyImport::EnumExportedTypes 方法</span><span class="sxs-lookup"><span data-stu-id="ee26a-102">IMetaDataAssemblyImport::EnumExportedTypes Method</span></span>
<span data-ttu-id="ee26a-103">枚举当前元数据作用域中程序集清单中引用的导出类型。</span><span class="sxs-lookup"><span data-stu-id="ee26a-103">Enumerates the exported types referenced in the assembly manifest in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee26a-104">语法</span><span class="sxs-lookup"><span data-stu-id="ee26a-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumExportedTypes (  
    [in, out] HCORENUM     *phEnum,
    [out] mdExportedType   rExportedTypes[],
    [in]  ULONG            cMax,
    [out] ULONG            *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ee26a-105">parameters</span><span class="sxs-lookup"><span data-stu-id="ee26a-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="ee26a-106">[进出]指向枚举器的指针。</span><span class="sxs-lookup"><span data-stu-id="ee26a-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="ee26a-107">当首次调用该方法时，`EnumExportedTypes`这必须是 null 值。</span><span class="sxs-lookup"><span data-stu-id="ee26a-107">This must be a null value when the `EnumExportedTypes` method is called for the first time.</span></span>  
  
 `rExportedTypes`  
 <span data-ttu-id="ee26a-108">[出]元数据令牌的`mdExportedType`枚举。</span><span class="sxs-lookup"><span data-stu-id="ee26a-108">[out] The enumeration of `mdExportedType` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="ee26a-109">[在]可放置在`rExportedTypes`数组中`mdExportedType`的最大令牌数。</span><span class="sxs-lookup"><span data-stu-id="ee26a-109">[in] The maximum number of `mdExportedType` tokens that can be placed in the `rExportedTypes` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="ee26a-110">[出]实际放置在`mdExportedType`中的`rExportedTypes`令牌数。</span><span class="sxs-lookup"><span data-stu-id="ee26a-110">[out] The number of `mdExportedType` tokens actually placed in `rExportedTypes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ee26a-111">返回值</span><span class="sxs-lookup"><span data-stu-id="ee26a-111">Return Value</span></span>  
  
|<span data-ttu-id="ee26a-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ee26a-112">HRESULT</span></span>|<span data-ttu-id="ee26a-113">说明</span><span class="sxs-lookup"><span data-stu-id="ee26a-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="ee26a-114">`EnumExportedTypes`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="ee26a-114">`EnumExportedTypes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="ee26a-115">没有要枚举的令牌。</span><span class="sxs-lookup"><span data-stu-id="ee26a-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="ee26a-116">在这种情况下，`pcTokens`设置为零。</span><span class="sxs-lookup"><span data-stu-id="ee26a-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ee26a-117">要求</span><span class="sxs-lookup"><span data-stu-id="ee26a-117">Requirements</span></span>  
 <span data-ttu-id="ee26a-118">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ee26a-118">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee26a-119">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="ee26a-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ee26a-120">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="ee26a-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ee26a-121">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee26a-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee26a-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ee26a-122">See also</span></span>

- [<span data-ttu-id="ee26a-123">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="ee26a-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
