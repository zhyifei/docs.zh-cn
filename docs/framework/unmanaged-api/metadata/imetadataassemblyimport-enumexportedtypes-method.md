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
ms.openlocfilehash: 1beb76012d5f0351ee644c8dea89cabdbe2c8970
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54555019"
---
# <a name="imetadataassemblyimportenumexportedtypes-method"></a><span data-ttu-id="72404-102">IMetaDataAssemblyImport::EnumExportedTypes 方法</span><span class="sxs-lookup"><span data-stu-id="72404-102">IMetaDataAssemblyImport::EnumExportedTypes Method</span></span>
<span data-ttu-id="72404-103">枚举当前元数据范围中的程序集清单中引用的导出的类型。</span><span class="sxs-lookup"><span data-stu-id="72404-103">Enumerates the exported types referenced in the assembly manifest in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72404-104">语法</span><span class="sxs-lookup"><span data-stu-id="72404-104">Syntax</span></span>  
  
```  
HRESULT EnumExportedTypes (  
    [in, out] HCORENUM     *phEnum,   
    [out] mdExportedType   rExportedTypes[],   
    [in]  ULONG            cMax,   
    [out] ULONG            *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="72404-105">参数</span><span class="sxs-lookup"><span data-stu-id="72404-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="72404-106">[in、 out]一个指向枚举器。</span><span class="sxs-lookup"><span data-stu-id="72404-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="72404-107">这必须是一个 null 值时`EnumExportedTypes`第一次调用方法。</span><span class="sxs-lookup"><span data-stu-id="72404-107">This must be a null value when the `EnumExportedTypes` method is called for the first time.</span></span>  
  
 `rExportedTypes`  
 <span data-ttu-id="72404-108">[out]枚举`mdExportedType`元数据标记。</span><span class="sxs-lookup"><span data-stu-id="72404-108">[out] The enumeration of `mdExportedType` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="72404-109">[in]最大数目`mdExportedType`令牌可以置于`rExportedTypes`数组。</span><span class="sxs-lookup"><span data-stu-id="72404-109">[in] The maximum number of `mdExportedType` tokens that can be placed in the `rExportedTypes` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="72404-110">[out]数`mdExportedType`令牌实际置于`rExportedTypes`。</span><span class="sxs-lookup"><span data-stu-id="72404-110">[out] The number of `mdExportedType` tokens actually placed in `rExportedTypes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="72404-111">返回值</span><span class="sxs-lookup"><span data-stu-id="72404-111">Return Value</span></span>  
  
|<span data-ttu-id="72404-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="72404-112">HRESULT</span></span>|<span data-ttu-id="72404-113">描述</span><span class="sxs-lookup"><span data-stu-id="72404-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="72404-114">`EnumExportedTypes` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="72404-114">`EnumExportedTypes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="72404-115">没有要枚举的标记。</span><span class="sxs-lookup"><span data-stu-id="72404-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="72404-116">在这种情况下，`pcTokens`设置为零。</span><span class="sxs-lookup"><span data-stu-id="72404-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="72404-117">要求</span><span class="sxs-lookup"><span data-stu-id="72404-117">Requirements</span></span>  
 <span data-ttu-id="72404-118">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="72404-118">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72404-119">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="72404-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="72404-120">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="72404-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="72404-121">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72404-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72404-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="72404-122">See also</span></span>
- [<span data-ttu-id="72404-123">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="72404-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
