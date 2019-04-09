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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b838a83a160707e546b05ef334eb17d0c6e6cc27
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59133557"
---
# <a name="imetadataemitsetpinvokemap-method"></a><span data-ttu-id="5b685-102">IMetaDataEmit::SetPinvokeMap 方法</span><span class="sxs-lookup"><span data-stu-id="5b685-102">IMetaDataEmit::SetPinvokeMap Method</span></span>
<span data-ttu-id="5b685-103">设置或更改功能的方法的 PInvoke 签名定义的调用之前[imetadataemit:: Definepinvokemap](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepinvokemap-method.md)。</span><span class="sxs-lookup"><span data-stu-id="5b685-103">Sets or changes features of a method's PInvoke signature, as defined by a prior call to [IMetaDataEmit::DefinePinvokeMap](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepinvokemap-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b685-104">语法</span><span class="sxs-lookup"><span data-stu-id="5b685-104">Syntax</span></span>  
  
```  
HRESULT SetPinvokeMap (   
    [in]  mdToken      tk,   
    [in]  DWORD        dwMappingFlags,  
    [in]  LPCWSTR      szImportName,   
    [in]  mdModuleRef  mrImportDLL   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5b685-105">参数</span><span class="sxs-lookup"><span data-stu-id="5b685-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="5b685-106">[in]`mdToken`信息应用到的映射。</span><span class="sxs-lookup"><span data-stu-id="5b685-106">[in] The `mdToken` to which mapping information applies.</span></span>  
  
 `dwMappingFlags`  
 <span data-ttu-id="5b685-107">[in]PInvoke 用于执行映射标志。</span><span class="sxs-lookup"><span data-stu-id="5b685-107">[in] Flags used by PInvoke to do the mapping.</span></span> <span data-ttu-id="5b685-108">这是一个位掩码的`CorPinvokeMap`值。</span><span class="sxs-lookup"><span data-stu-id="5b685-108">This is a bitmask of `CorPinvokeMap` values.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="5b685-109">[in]本机 DLL 中导出的目标的名称。</span><span class="sxs-lookup"><span data-stu-id="5b685-109">[in] The name of the target export in the native DLL.</span></span>  
  
 `mrImportDLL`  
 <span data-ttu-id="5b685-110">[in]`mdModuleRef`令牌为目标的非托管 DLL。</span><span class="sxs-lookup"><span data-stu-id="5b685-110">[in] The `mdModuleRef` token for the target unmanaged DLL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b685-111">要求</span><span class="sxs-lookup"><span data-stu-id="5b685-111">Requirements</span></span>  
 <span data-ttu-id="5b685-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5b685-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b685-113">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5b685-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5b685-114">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="5b685-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="5b685-115">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="5b685-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5b685-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="5b685-116">See also</span></span>

- [<span data-ttu-id="5b685-117">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="5b685-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="5b685-118">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="5b685-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
