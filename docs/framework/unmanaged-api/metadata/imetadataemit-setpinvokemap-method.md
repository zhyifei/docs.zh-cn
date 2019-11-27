---
title: IMetaDataEmit::SetPinvokeMap 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetPinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetPinvokeMap
helpviewer_keywords:
- IMetaDataEmit::SetPinvokeMap method [.NET Framework metadata]
- SetPinvokeMap method [.NET Framework metadata]
ms.assetid: c6bfd574-1da3-4ba7-82f2-46ca5efcbaba
topic_type:
- apiref
ms.openlocfilehash: 4e2a78e2d049e952aa1be0b3a8fd640eb18d0320
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440566"
---
# <a name="imetadataemitsetpinvokemap-method"></a><span data-ttu-id="ddc36-102">IMetaDataEmit::SetPinvokeMap 方法</span><span class="sxs-lookup"><span data-stu-id="ddc36-102">IMetaDataEmit::SetPinvokeMap Method</span></span>
<span data-ttu-id="ddc36-103">设置或更改方法的 PInvoke 签名的功能，由之前调用[IMetaDataEmit：:D efinepinvokemap](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepinvokemap-method.md)定义。</span><span class="sxs-lookup"><span data-stu-id="ddc36-103">Sets or changes features of a method's PInvoke signature, as defined by a prior call to [IMetaDataEmit::DefinePinvokeMap](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepinvokemap-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ddc36-104">语法</span><span class="sxs-lookup"><span data-stu-id="ddc36-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPinvokeMap (   
    [in]  mdToken      tk,   
    [in]  DWORD        dwMappingFlags,  
    [in]  LPCWSTR      szImportName,   
    [in]  mdModuleRef  mrImportDLL   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ddc36-105">参数</span><span class="sxs-lookup"><span data-stu-id="ddc36-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="ddc36-106">中应用映射信息的 `mdToken`。</span><span class="sxs-lookup"><span data-stu-id="ddc36-106">[in] The `mdToken` to which mapping information applies.</span></span>  
  
 `dwMappingFlags`  
 <span data-ttu-id="ddc36-107">中PInvoke 用来执行映射的标志。</span><span class="sxs-lookup"><span data-stu-id="ddc36-107">[in] Flags used by PInvoke to do the mapping.</span></span> <span data-ttu-id="ddc36-108">这是 `CorPinvokeMap` 值的位掩码。</span><span class="sxs-lookup"><span data-stu-id="ddc36-108">This is a bitmask of `CorPinvokeMap` values.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="ddc36-109">中本机 DLL 中目标导出的名称。</span><span class="sxs-lookup"><span data-stu-id="ddc36-109">[in] The name of the target export in the native DLL.</span></span>  
  
 `mrImportDLL`  
 <span data-ttu-id="ddc36-110">中目标非托管 DLL 的 `mdModuleRef` 标记。</span><span class="sxs-lookup"><span data-stu-id="ddc36-110">[in] The `mdModuleRef` token for the target unmanaged DLL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ddc36-111">要求</span><span class="sxs-lookup"><span data-stu-id="ddc36-111">Requirements</span></span>  
 <span data-ttu-id="ddc36-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ddc36-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ddc36-113">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="ddc36-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ddc36-114">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="ddc36-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ddc36-115">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ddc36-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddc36-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ddc36-116">See also</span></span>

- [<span data-ttu-id="ddc36-117">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="ddc36-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="ddc36-118">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="ddc36-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
