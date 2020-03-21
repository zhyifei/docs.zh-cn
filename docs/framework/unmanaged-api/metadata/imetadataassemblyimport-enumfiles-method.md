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
ms.openlocfilehash: 70f76318f51047cb81262f744a6fbed5fe401692
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177813"
---
# <a name="imetadataassemblyimportenumfiles-method"></a><span data-ttu-id="f6306-102">IMetaDataAssemblyImport::EnumFiles 方法</span><span class="sxs-lookup"><span data-stu-id="f6306-102">IMetaDataAssemblyImport::EnumFiles Method</span></span>
<span data-ttu-id="f6306-103">枚举当前程序集清单中引用的文件。</span><span class="sxs-lookup"><span data-stu-id="f6306-103">Enumerates the files referenced in the current assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6306-104">语法</span><span class="sxs-lookup"><span data-stu-id="f6306-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumFiles (  
    [in, out] HCORENUM    *phEnum,
    [out] mdFile          rFiles[],
    [in]  ULONG           cMax,
    [out] ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f6306-105">parameters</span><span class="sxs-lookup"><span data-stu-id="f6306-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="f6306-106">[进出]指向枚举器的指针。</span><span class="sxs-lookup"><span data-stu-id="f6306-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="f6306-107">对于此方法的第一个调用，这必须是 null 值。</span><span class="sxs-lookup"><span data-stu-id="f6306-107">This must be a null value for the first call of this method.</span></span>  
  
 `rFiles`  
 <span data-ttu-id="f6306-108">[出]用于存储元数据令牌的`mdFile`数组。</span><span class="sxs-lookup"><span data-stu-id="f6306-108">[out] The array used to store the `mdFile` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="f6306-109">[在]可放置在 中`mdFile`的最大令牌数`rFiles`。</span><span class="sxs-lookup"><span data-stu-id="f6306-109">[in] The maximum number of `mdFile` tokens that can be placed in `rFiles`.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="f6306-110">[出]实际放置在`mdFile`中的`rFiles`令牌数。</span><span class="sxs-lookup"><span data-stu-id="f6306-110">[out] The number of `mdFile` tokens actually placed in `rFiles`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f6306-111">返回值</span><span class="sxs-lookup"><span data-stu-id="f6306-111">Return Value</span></span>  
  
|<span data-ttu-id="f6306-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f6306-112">HRESULT</span></span>|<span data-ttu-id="f6306-113">说明</span><span class="sxs-lookup"><span data-stu-id="f6306-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="f6306-114">`EnumFiles`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="f6306-114">`EnumFiles` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="f6306-115">没有要枚举的令牌。</span><span class="sxs-lookup"><span data-stu-id="f6306-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="f6306-116">在这种情况下，`pcTokens`设置为零。</span><span class="sxs-lookup"><span data-stu-id="f6306-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f6306-117">要求</span><span class="sxs-lookup"><span data-stu-id="f6306-117">Requirements</span></span>  
 <span data-ttu-id="f6306-118">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f6306-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6306-119">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="f6306-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f6306-120">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="f6306-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f6306-121">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6306-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6306-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f6306-122">See also</span></span>

- [<span data-ttu-id="f6306-123">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="f6306-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
