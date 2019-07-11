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
ms.openlocfilehash: 62c44d0c3bd2e931b1708abb48bc9c854431419f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67751147"
---
# <a name="imetadataassemblyimportenumexportedtypes-method"></a><span data-ttu-id="70b1b-102">IMetaDataAssemblyImport::EnumExportedTypes 方法</span><span class="sxs-lookup"><span data-stu-id="70b1b-102">IMetaDataAssemblyImport::EnumExportedTypes Method</span></span>
<span data-ttu-id="70b1b-103">枚举当前元数据范围中的程序集清单中引用的导出的类型。</span><span class="sxs-lookup"><span data-stu-id="70b1b-103">Enumerates the exported types referenced in the assembly manifest in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70b1b-104">语法</span><span class="sxs-lookup"><span data-stu-id="70b1b-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumExportedTypes (  
    [in, out] HCORENUM     *phEnum,   
    [out] mdExportedType   rExportedTypes[],   
    [in]  ULONG            cMax,   
    [out] ULONG            *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="70b1b-105">参数</span><span class="sxs-lookup"><span data-stu-id="70b1b-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="70b1b-106">[in、 out]一个指向枚举器。</span><span class="sxs-lookup"><span data-stu-id="70b1b-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="70b1b-107">这必须是一个 null 值时`EnumExportedTypes`第一次调用方法。</span><span class="sxs-lookup"><span data-stu-id="70b1b-107">This must be a null value when the `EnumExportedTypes` method is called for the first time.</span></span>  
  
 `rExportedTypes`  
 <span data-ttu-id="70b1b-108">[out]枚举`mdExportedType`元数据标记。</span><span class="sxs-lookup"><span data-stu-id="70b1b-108">[out] The enumeration of `mdExportedType` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="70b1b-109">[in]最大数目`mdExportedType`令牌可以置于`rExportedTypes`数组。</span><span class="sxs-lookup"><span data-stu-id="70b1b-109">[in] The maximum number of `mdExportedType` tokens that can be placed in the `rExportedTypes` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="70b1b-110">[out]数`mdExportedType`令牌实际置于`rExportedTypes`。</span><span class="sxs-lookup"><span data-stu-id="70b1b-110">[out] The number of `mdExportedType` tokens actually placed in `rExportedTypes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="70b1b-111">返回值</span><span class="sxs-lookup"><span data-stu-id="70b1b-111">Return Value</span></span>  
  
|<span data-ttu-id="70b1b-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="70b1b-112">HRESULT</span></span>|<span data-ttu-id="70b1b-113">描述</span><span class="sxs-lookup"><span data-stu-id="70b1b-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="70b1b-114">`EnumExportedTypes` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="70b1b-114">`EnumExportedTypes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="70b1b-115">没有要枚举的标记。</span><span class="sxs-lookup"><span data-stu-id="70b1b-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="70b1b-116">在这种情况下，`pcTokens`设置为零。</span><span class="sxs-lookup"><span data-stu-id="70b1b-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="70b1b-117">要求</span><span class="sxs-lookup"><span data-stu-id="70b1b-117">Requirements</span></span>  
 <span data-ttu-id="70b1b-118">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="70b1b-118">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70b1b-119">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="70b1b-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="70b1b-120">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="70b1b-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="70b1b-121">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70b1b-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70b1b-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="70b1b-122">See also</span></span>

- [<span data-ttu-id="70b1b-123">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="70b1b-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
