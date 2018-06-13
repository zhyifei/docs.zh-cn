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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9aef8c40be2456532bd6df6feb8d286cdaeefa7f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445626"
---
# <a name="imetadataassemblyimportenumexportedtypes-method"></a><span data-ttu-id="d256d-102">IMetaDataAssemblyImport::EnumExportedTypes 方法</span><span class="sxs-lookup"><span data-stu-id="d256d-102">IMetaDataAssemblyImport::EnumExportedTypes Method</span></span>
<span data-ttu-id="d256d-103">枚举当前元数据范围内的程序集清单引用的导出的类型。</span><span class="sxs-lookup"><span data-stu-id="d256d-103">Enumerates the exported types referenced in the assembly manifest in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d256d-104">语法</span><span class="sxs-lookup"><span data-stu-id="d256d-104">Syntax</span></span>  
  
```  
HRESULT EnumExportedTypes (  
    [in, out] HCORENUM     *phEnum,   
    [out] mdExportedType   rExportedTypes[],   
    [in]  ULONG            cMax,   
    [out] ULONG            *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d256d-105">参数</span><span class="sxs-lookup"><span data-stu-id="d256d-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="d256d-106">[在中，out]枚举数指向的指针。</span><span class="sxs-lookup"><span data-stu-id="d256d-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="d256d-107">这必须是一个为 null 的值时`EnumExportedTypes`首次调用方法。</span><span class="sxs-lookup"><span data-stu-id="d256d-107">This must be a null value when the `EnumExportedTypes` method is called for the first time.</span></span>  
  
 `rExportedTypes`  
 <span data-ttu-id="d256d-108">[out]枚举`mdExportedType`元数据标记。</span><span class="sxs-lookup"><span data-stu-id="d256d-108">[out] The enumeration of `mdExportedType` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="d256d-109">[in]最大数`mdExportedType`可以放置在令牌`rExportedTypes`数组。</span><span class="sxs-lookup"><span data-stu-id="d256d-109">[in] The maximum number of `mdExportedType` tokens that can be placed in the `rExportedTypes` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="d256d-110">[out]数`mdExportedType`令牌实际放入`rExportedTypes`。</span><span class="sxs-lookup"><span data-stu-id="d256d-110">[out] The number of `mdExportedType` tokens actually placed in `rExportedTypes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d256d-111">返回值</span><span class="sxs-lookup"><span data-stu-id="d256d-111">Return Value</span></span>  
  
|<span data-ttu-id="d256d-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d256d-112">HRESULT</span></span>|<span data-ttu-id="d256d-113">描述</span><span class="sxs-lookup"><span data-stu-id="d256d-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="d256d-114">`EnumExportedTypes` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="d256d-114">`EnumExportedTypes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="d256d-115">没有要枚举的标记。</span><span class="sxs-lookup"><span data-stu-id="d256d-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="d256d-116">在这种情况下，`pcTokens`设置为零。</span><span class="sxs-lookup"><span data-stu-id="d256d-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d256d-117">要求</span><span class="sxs-lookup"><span data-stu-id="d256d-117">Requirements</span></span>  
 <span data-ttu-id="d256d-118">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d256d-118">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d256d-119">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d256d-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d256d-120">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="d256d-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d256d-121">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d256d-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d256d-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="d256d-122">See Also</span></span>  
 [<span data-ttu-id="d256d-123">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="d256d-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
