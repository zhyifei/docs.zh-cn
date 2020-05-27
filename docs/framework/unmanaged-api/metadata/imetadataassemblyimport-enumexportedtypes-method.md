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
ms.openlocfilehash: 514488c6e0d2e89de0d8ee483def485ec9f3ef25
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009092"
---
# <a name="imetadataassemblyimportenumexportedtypes-method"></a><span data-ttu-id="8c03a-102">IMetaDataAssemblyImport::EnumExportedTypes 方法</span><span class="sxs-lookup"><span data-stu-id="8c03a-102">IMetaDataAssemblyImport::EnumExportedTypes Method</span></span>
<span data-ttu-id="8c03a-103">枚举当前元数据范围内的程序集清单中引用的导出类型。</span><span class="sxs-lookup"><span data-stu-id="8c03a-103">Enumerates the exported types referenced in the assembly manifest in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c03a-104">语法</span><span class="sxs-lookup"><span data-stu-id="8c03a-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumExportedTypes (  
    [in, out] HCORENUM     *phEnum,
    [out] mdExportedType   rExportedTypes[],
    [in]  ULONG            cMax,
    [out] ULONG            *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8c03a-105">参数</span><span class="sxs-lookup"><span data-stu-id="8c03a-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="8c03a-106">[in，out]指向枚举器的指针。</span><span class="sxs-lookup"><span data-stu-id="8c03a-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="8c03a-107">第一次调用方法时，此值必须为 null 值 `EnumExportedTypes` 。</span><span class="sxs-lookup"><span data-stu-id="8c03a-107">This must be a null value when the `EnumExportedTypes` method is called for the first time.</span></span>  
  
 `rExportedTypes`  
 <span data-ttu-id="8c03a-108">弄`mdExportedType`元数据标记的枚举。</span><span class="sxs-lookup"><span data-stu-id="8c03a-108">[out] The enumeration of `mdExportedType` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="8c03a-109">中`mdExportedType`可置于数组中的最大标记数 `rExportedTypes` 。</span><span class="sxs-lookup"><span data-stu-id="8c03a-109">[in] The maximum number of `mdExportedType` tokens that can be placed in the `rExportedTypes` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="8c03a-110">弄`mdExportedType`实际置于中的标记数 `rExportedTypes` 。</span><span class="sxs-lookup"><span data-stu-id="8c03a-110">[out] The number of `mdExportedType` tokens actually placed in `rExportedTypes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8c03a-111">返回值</span><span class="sxs-lookup"><span data-stu-id="8c03a-111">Return Value</span></span>  
  
|<span data-ttu-id="8c03a-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8c03a-112">HRESULT</span></span>|<span data-ttu-id="8c03a-113">说明</span><span class="sxs-lookup"><span data-stu-id="8c03a-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="8c03a-114">`EnumExportedTypes`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="8c03a-114">`EnumExportedTypes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="8c03a-115">没有要枚举的令牌。</span><span class="sxs-lookup"><span data-stu-id="8c03a-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="8c03a-116">在这种情况下， `pcTokens` 设置为零。</span><span class="sxs-lookup"><span data-stu-id="8c03a-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8c03a-117">要求</span><span class="sxs-lookup"><span data-stu-id="8c03a-117">Requirements</span></span>  
 <span data-ttu-id="8c03a-118">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8c03a-118">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c03a-119">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="8c03a-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8c03a-120">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="8c03a-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8c03a-121">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c03a-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c03a-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8c03a-122">See also</span></span>

- [<span data-ttu-id="8c03a-123">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="8c03a-123">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
