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
ms.openlocfilehash: 4c68754bc44fe035fd8e7143c52895928beae395
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175585"
---
# <a name="imetadataemitsetpinvokemap-method"></a><span data-ttu-id="4a521-102">IMetaDataEmit::SetPinvokeMap 方法</span><span class="sxs-lookup"><span data-stu-id="4a521-102">IMetaDataEmit::SetPinvokeMap Method</span></span>
<span data-ttu-id="4a521-103">设置或更改方法的 PInvoke 签名的功能，由之前调用[IMetaDataEmit：:DefinePinvokeMap](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepinvokemap-method.md)定义。</span><span class="sxs-lookup"><span data-stu-id="4a521-103">Sets or changes features of a method's PInvoke signature, as defined by a prior call to [IMetaDataEmit::DefinePinvokeMap](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepinvokemap-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a521-104">语法</span><span class="sxs-lookup"><span data-stu-id="4a521-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPinvokeMap (
    [in]  mdToken      tk,
    [in]  DWORD        dwMappingFlags,  
    [in]  LPCWSTR      szImportName,
    [in]  mdModuleRef  mrImportDLL
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4a521-105">parameters</span><span class="sxs-lookup"><span data-stu-id="4a521-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="4a521-106">[在]映射`mdToken`信息应用于的。</span><span class="sxs-lookup"><span data-stu-id="4a521-106">[in] The `mdToken` to which mapping information applies.</span></span>  
  
 `dwMappingFlags`  
 <span data-ttu-id="4a521-107">[在]PInvoke 用于执行映射的标志。</span><span class="sxs-lookup"><span data-stu-id="4a521-107">[in] Flags used by PInvoke to do the mapping.</span></span> <span data-ttu-id="4a521-108">这是值的`CorPinvokeMap`位掩码。</span><span class="sxs-lookup"><span data-stu-id="4a521-108">This is a bitmask of `CorPinvokeMap` values.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="4a521-109">[在]本机 DLL 中的目标导出的名称。</span><span class="sxs-lookup"><span data-stu-id="4a521-109">[in] The name of the target export in the native DLL.</span></span>  
  
 `mrImportDLL`  
 <span data-ttu-id="4a521-110">[在]目标`mdModuleRef`非托管 DLL 的令牌。</span><span class="sxs-lookup"><span data-stu-id="4a521-110">[in] The `mdModuleRef` token for the target unmanaged DLL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a521-111">要求</span><span class="sxs-lookup"><span data-stu-id="4a521-111">Requirements</span></span>  
 <span data-ttu-id="4a521-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4a521-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a521-113">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="4a521-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4a521-114">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="4a521-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4a521-115">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a521-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a521-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4a521-116">See also</span></span>

- [<span data-ttu-id="4a521-117">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="4a521-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="4a521-118">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="4a521-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
