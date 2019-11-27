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
ms.openlocfilehash: 45e2348b4726447548544d975e60b93e464fb402
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450339"
---
# <a name="imetadataassemblyimportenumexportedtypes-method"></a><span data-ttu-id="de0c2-102">IMetaDataAssemblyImport::EnumExportedTypes 方法</span><span class="sxs-lookup"><span data-stu-id="de0c2-102">IMetaDataAssemblyImport::EnumExportedTypes Method</span></span>
<span data-ttu-id="de0c2-103">枚举当前元数据范围内的程序集清单中引用的导出类型。</span><span class="sxs-lookup"><span data-stu-id="de0c2-103">Enumerates the exported types referenced in the assembly manifest in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de0c2-104">语法</span><span class="sxs-lookup"><span data-stu-id="de0c2-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumExportedTypes (  
    [in, out] HCORENUM     *phEnum,   
    [out] mdExportedType   rExportedTypes[],   
    [in]  ULONG            cMax,   
    [out] ULONG            *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="de0c2-105">参数</span><span class="sxs-lookup"><span data-stu-id="de0c2-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="de0c2-106">[in，out]指向枚举器的指针。</span><span class="sxs-lookup"><span data-stu-id="de0c2-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="de0c2-107">当首次调用 `EnumExportedTypes` 方法时，此值必须为 null 值。</span><span class="sxs-lookup"><span data-stu-id="de0c2-107">This must be a null value when the `EnumExportedTypes` method is called for the first time.</span></span>  
  
 `rExportedTypes`  
 <span data-ttu-id="de0c2-108">弄`mdExportedType` 元数据标记的枚举。</span><span class="sxs-lookup"><span data-stu-id="de0c2-108">[out] The enumeration of `mdExportedType` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="de0c2-109">中可放置在 `rExportedTypes` 数组中的 `mdExportedType` 标记的最大数目。</span><span class="sxs-lookup"><span data-stu-id="de0c2-109">[in] The maximum number of `mdExportedType` tokens that can be placed in the `rExportedTypes` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="de0c2-110">弄实际置于 `rExportedTypes`中 `mdExportedType` 标记的数目。</span><span class="sxs-lookup"><span data-stu-id="de0c2-110">[out] The number of `mdExportedType` tokens actually placed in `rExportedTypes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="de0c2-111">返回值</span><span class="sxs-lookup"><span data-stu-id="de0c2-111">Return Value</span></span>  
  
|<span data-ttu-id="de0c2-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="de0c2-112">HRESULT</span></span>|<span data-ttu-id="de0c2-113">说明</span><span class="sxs-lookup"><span data-stu-id="de0c2-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="de0c2-114">`EnumExportedTypes` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="de0c2-114">`EnumExportedTypes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="de0c2-115">没有要枚举的令牌。</span><span class="sxs-lookup"><span data-stu-id="de0c2-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="de0c2-116">在这种情况下，`pcTokens` 设置为零。</span><span class="sxs-lookup"><span data-stu-id="de0c2-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="de0c2-117">要求</span><span class="sxs-lookup"><span data-stu-id="de0c2-117">Requirements</span></span>  
 <span data-ttu-id="de0c2-118">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="de0c2-118">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de0c2-119">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="de0c2-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="de0c2-120">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="de0c2-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="de0c2-121">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de0c2-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de0c2-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="de0c2-122">See also</span></span>

- [<span data-ttu-id="de0c2-123">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="de0c2-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
