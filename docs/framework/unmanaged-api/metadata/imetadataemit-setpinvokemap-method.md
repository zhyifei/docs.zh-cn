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
ms.openlocfilehash: 84b2c0571a7991829e65b45759bd61fa4009aa71
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445872"
---
# <a name="imetadataemitsetpinvokemap-method"></a><span data-ttu-id="b0685-102">IMetaDataEmit::SetPinvokeMap 方法</span><span class="sxs-lookup"><span data-stu-id="b0685-102">IMetaDataEmit::SetPinvokeMap Method</span></span>
<span data-ttu-id="b0685-103">设置或更改的方法的 PInvoke 签名功能，通过调用定义[imetadataemit:: Definepinvokemap](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepinvokemap-method.md)。</span><span class="sxs-lookup"><span data-stu-id="b0685-103">Sets or changes features of a method's PInvoke signature, as defined by a prior call to [IMetaDataEmit::DefinePinvokeMap](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepinvokemap-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0685-104">语法</span><span class="sxs-lookup"><span data-stu-id="b0685-104">Syntax</span></span>  
  
```  
HRESULT SetPinvokeMap (   
    [in]  mdToken      tk,   
    [in]  DWORD        dwMappingFlags,  
    [in]  LPCWSTR      szImportName,   
    [in]  mdModuleRef  mrImportDLL   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b0685-105">参数</span><span class="sxs-lookup"><span data-stu-id="b0685-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="b0685-106">[in]`mdToken`信息应用到的映射。</span><span class="sxs-lookup"><span data-stu-id="b0685-106">[in] The `mdToken` to which mapping information applies.</span></span>  
  
 `dwMappingFlags`  
 <span data-ttu-id="b0685-107">[in]PInvoke 用于进行映射的标志。</span><span class="sxs-lookup"><span data-stu-id="b0685-107">[in] Flags used by PInvoke to do the mapping.</span></span> <span data-ttu-id="b0685-108">这是一个位掩码的`CorPinvokeMap`值。</span><span class="sxs-lookup"><span data-stu-id="b0685-108">This is a bitmask of `CorPinvokeMap` values.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="b0685-109">[in]在本机 DLL 中导出的目标的名称。</span><span class="sxs-lookup"><span data-stu-id="b0685-109">[in] The name of the target export in the native DLL.</span></span>  
  
 `mrImportDLL`  
 <span data-ttu-id="b0685-110">[in]`mdModuleRef`令牌为目标的非托管 DLL。</span><span class="sxs-lookup"><span data-stu-id="b0685-110">[in] The `mdModuleRef` token for the target unmanaged DLL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0685-111">要求</span><span class="sxs-lookup"><span data-stu-id="b0685-111">Requirements</span></span>  
 <span data-ttu-id="b0685-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b0685-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0685-113">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b0685-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b0685-114">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="b0685-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b0685-115">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0685-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0685-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="b0685-116">See Also</span></span>  
 [<span data-ttu-id="b0685-117">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="b0685-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="b0685-118">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="b0685-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
