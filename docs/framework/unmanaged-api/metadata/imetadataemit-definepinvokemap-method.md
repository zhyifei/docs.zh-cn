---
title: "IMetaDataEmit::DefinePinvokeMap 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefinePinvokeMap
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefinePinvokeMap
helpviewer_keywords:
- DefinePinvokeMap method [.NET Framework metadata]
- IMetaDataEmit::DefinePinvokeMap method [.NET Framework metadata]
ms.assetid: 03abf921-5154-4070-88fa-10b7092901fb
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0c15c6039f116597ee4f2c0f83bed4c5550b30a0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitdefinepinvokemap-method"></a><span data-ttu-id="957f2-102">IMetaDataEmit::DefinePinvokeMap 方法</span><span class="sxs-lookup"><span data-stu-id="957f2-102">IMetaDataEmit::DefinePinvokeMap Method</span></span>
<span data-ttu-id="957f2-103">设置 PInvoke 签名由指定标记所引用的方法的功能。</span><span class="sxs-lookup"><span data-stu-id="957f2-103">Sets features of the PInvoke signature of the method referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="957f2-104">语法</span><span class="sxs-lookup"><span data-stu-id="957f2-104">Syntax</span></span>  
  
```  
HRESULT DefinePinvokeMap (   
    [in]  mdToken            tk,   
    [in]  DWORD              dwMappingFlags,   
    [in]  LPCWSTR            szImportName,   
    [in]  mdModuleRef        mrImportDLL   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="957f2-105">参数</span><span class="sxs-lookup"><span data-stu-id="957f2-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="957f2-106">[in]目标方法的标记。</span><span class="sxs-lookup"><span data-stu-id="957f2-106">[in] The token for the target method.</span></span>  
  
 `dwMappingFlags`  
 <span data-ttu-id="957f2-107">[in]PInvoke 用于进行映射的标志。</span><span class="sxs-lookup"><span data-stu-id="957f2-107">[in] Flags used by PInvoke to do the mapping.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="957f2-108">[in]方法在非托管 DLL 中的导出的目标的名称。</span><span class="sxs-lookup"><span data-stu-id="957f2-108">[in] The name of the target export method in an unmanaged DLL.</span></span>  
  
 `mrImportDLL`  
 <span data-ttu-id="957f2-109">[in]为目标的令牌本机 DLL。</span><span class="sxs-lookup"><span data-stu-id="957f2-109">[in] The token for the target native DLL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="957f2-110">要求</span><span class="sxs-lookup"><span data-stu-id="957f2-110">Requirements</span></span>  
 <span data-ttu-id="957f2-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="957f2-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="957f2-112">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="957f2-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="957f2-113">**库：**用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="957f2-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="957f2-114">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="957f2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="957f2-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="957f2-115">See Also</span></span>  
 [<span data-ttu-id="957f2-116">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="957f2-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="957f2-117">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="957f2-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
