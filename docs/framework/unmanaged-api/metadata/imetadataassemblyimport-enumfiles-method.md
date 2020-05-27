---
title: IMetaDataAssemblyImport::EnumFiles 方法
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumFiles
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumFiles
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumFiles method [.NET Framework metadata]
- EnumFiles method [.NET Framework metadata]
ms.assetid: f0d721e2-b946-426d-8e20-9124bd04e4cb
topic_type:
- apiref
ms.openlocfilehash: ed8bafd67b5d55a5116111b7721fbdc31c52aca6
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009088"
---
# <a name="imetadataassemblyimportenumfiles-method"></a><span data-ttu-id="8f8fc-102">IMetaDataAssemblyImport::EnumFiles 方法</span><span class="sxs-lookup"><span data-stu-id="8f8fc-102">IMetaDataAssemblyImport::EnumFiles Method</span></span>
<span data-ttu-id="8f8fc-103">枚举当前程序集清单中引用的文件。</span><span class="sxs-lookup"><span data-stu-id="8f8fc-103">Enumerates the files referenced in the current assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f8fc-104">语法</span><span class="sxs-lookup"><span data-stu-id="8f8fc-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumFiles (  
    [in, out] HCORENUM    *phEnum,
    [out] mdFile          rFiles[],
    [in]  ULONG           cMax,
    [out] ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f8fc-105">参数</span><span class="sxs-lookup"><span data-stu-id="8f8fc-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="8f8fc-106">[in，out]指向枚举器的指针。</span><span class="sxs-lookup"><span data-stu-id="8f8fc-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="8f8fc-107">第一次调用此方法时，此值必须为 null 值。</span><span class="sxs-lookup"><span data-stu-id="8f8fc-107">This must be a null value for the first call of this method.</span></span>  
  
 `rFiles`  
 <span data-ttu-id="8f8fc-108">弄用于存储 `mdFile` 元数据标记的数组。</span><span class="sxs-lookup"><span data-stu-id="8f8fc-108">[out] The array used to store the `mdFile` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="8f8fc-109">中可以放入的标记的最大数目 `mdFile` `rFiles` 。</span><span class="sxs-lookup"><span data-stu-id="8f8fc-109">[in] The maximum number of `mdFile` tokens that can be placed in `rFiles`.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="8f8fc-110">弄`mdFile`实际置于中的标记数 `rFiles` 。</span><span class="sxs-lookup"><span data-stu-id="8f8fc-110">[out] The number of `mdFile` tokens actually placed in `rFiles`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8f8fc-111">返回值</span><span class="sxs-lookup"><span data-stu-id="8f8fc-111">Return Value</span></span>  
  
|<span data-ttu-id="8f8fc-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8f8fc-112">HRESULT</span></span>|<span data-ttu-id="8f8fc-113">说明</span><span class="sxs-lookup"><span data-stu-id="8f8fc-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="8f8fc-114">`EnumFiles`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="8f8fc-114">`EnumFiles` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="8f8fc-115">没有要枚举的令牌。</span><span class="sxs-lookup"><span data-stu-id="8f8fc-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="8f8fc-116">在这种情况下， `pcTokens` 设置为零。</span><span class="sxs-lookup"><span data-stu-id="8f8fc-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8f8fc-117">要求</span><span class="sxs-lookup"><span data-stu-id="8f8fc-117">Requirements</span></span>  
 <span data-ttu-id="8f8fc-118">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8f8fc-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f8fc-119">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="8f8fc-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8f8fc-120">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="8f8fc-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8f8fc-121">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f8fc-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f8fc-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8f8fc-122">See also</span></span>

- [<span data-ttu-id="8f8fc-123">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="8f8fc-123">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
