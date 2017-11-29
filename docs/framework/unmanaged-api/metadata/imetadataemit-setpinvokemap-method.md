---
title: "IMetaDataEmit::SetPinvokeMap 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SetPinvokeMap
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SetPinvokeMap
helpviewer_keywords:
- IMetaDataEmit::SetPinvokeMap method [.NET Framework metadata]
- SetPinvokeMap method [.NET Framework metadata]
ms.assetid: c6bfd574-1da3-4ba7-82f2-46ca5efcbaba
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a10482b12f9a34b0f247779f22c7cc70f871324a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitsetpinvokemap-method"></a><span data-ttu-id="7c68d-102">IMetaDataEmit::SetPinvokeMap 方法</span><span class="sxs-lookup"><span data-stu-id="7c68d-102">IMetaDataEmit::SetPinvokeMap Method</span></span>
<span data-ttu-id="7c68d-103">设置或更改的方法的 PInvoke 签名功能，通过调用定义[imetadataemit:: Definepinvokemap](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepinvokemap-method.md)。</span><span class="sxs-lookup"><span data-stu-id="7c68d-103">Sets or changes features of a method's PInvoke signature, as defined by a prior call to [IMetaDataEmit::DefinePinvokeMap](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepinvokemap-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c68d-104">语法</span><span class="sxs-lookup"><span data-stu-id="7c68d-104">Syntax</span></span>  
  
```  
HRESULT SetPinvokeMap (   
    [in]  mdToken      tk,   
    [in]  DWORD        dwMappingFlags,  
    [in]  LPCWSTR      szImportName,   
    [in]  mdModuleRef  mrImportDLL   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7c68d-105">参数</span><span class="sxs-lookup"><span data-stu-id="7c68d-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="7c68d-106">[in]`mdToken`信息应用到的映射。</span><span class="sxs-lookup"><span data-stu-id="7c68d-106">[in] The `mdToken` to which mapping information applies.</span></span>  
  
 `dwMappingFlags`  
 <span data-ttu-id="7c68d-107">[in]PInvoke 用于进行映射的标志。</span><span class="sxs-lookup"><span data-stu-id="7c68d-107">[in] Flags used by PInvoke to do the mapping.</span></span> <span data-ttu-id="7c68d-108">这是一个位掩码的`CorPinvokeMap`值。</span><span class="sxs-lookup"><span data-stu-id="7c68d-108">This is a bitmask of `CorPinvokeMap` values.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="7c68d-109">[in]在本机 DLL 中导出的目标的名称。</span><span class="sxs-lookup"><span data-stu-id="7c68d-109">[in] The name of the target export in the native DLL.</span></span>  
  
 `mrImportDLL`  
 <span data-ttu-id="7c68d-110">[in]`mdModuleRef`令牌为目标的非托管 DLL。</span><span class="sxs-lookup"><span data-stu-id="7c68d-110">[in] The `mdModuleRef` token for the target unmanaged DLL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c68d-111">要求</span><span class="sxs-lookup"><span data-stu-id="7c68d-111">Requirements</span></span>  
 <span data-ttu-id="7c68d-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7c68d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c68d-113">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7c68d-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7c68d-114">**库：**用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="7c68d-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7c68d-115">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c68d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c68d-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7c68d-116">See Also</span></span>  
 [<span data-ttu-id="7c68d-117">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="7c68d-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="7c68d-118">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="7c68d-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
