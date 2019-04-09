---
title: IMetaDataEmit::DefinePinvokeMap 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefinePinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefinePinvokeMap
helpviewer_keywords:
- DefinePinvokeMap method [.NET Framework metadata]
- IMetaDataEmit::DefinePinvokeMap method [.NET Framework metadata]
ms.assetid: 03abf921-5154-4070-88fa-10b7092901fb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 15fd75ae807ee5cd7f94f6e650639c3be0628429
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59136534"
---
# <a name="imetadataemitdefinepinvokemap-method"></a><span data-ttu-id="022cd-102">IMetaDataEmit::DefinePinvokeMap 方法</span><span class="sxs-lookup"><span data-stu-id="022cd-102">IMetaDataEmit::DefinePinvokeMap Method</span></span>
<span data-ttu-id="022cd-103">设置指定的标记所引用的方法的 PInvoke 签名的功能。</span><span class="sxs-lookup"><span data-stu-id="022cd-103">Sets features of the PInvoke signature of the method referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="022cd-104">语法</span><span class="sxs-lookup"><span data-stu-id="022cd-104">Syntax</span></span>  
  
```  
HRESULT DefinePinvokeMap (   
    [in]  mdToken            tk,   
    [in]  DWORD              dwMappingFlags,   
    [in]  LPCWSTR            szImportName,   
    [in]  mdModuleRef        mrImportDLL   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="022cd-105">参数</span><span class="sxs-lookup"><span data-stu-id="022cd-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="022cd-106">[in]目标方法的标记。</span><span class="sxs-lookup"><span data-stu-id="022cd-106">[in] The token for the target method.</span></span>  
  
 `dwMappingFlags`  
 <span data-ttu-id="022cd-107">[in]PInvoke 用于执行映射标志。</span><span class="sxs-lookup"><span data-stu-id="022cd-107">[in] Flags used by PInvoke to do the mapping.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="022cd-108">[in]目标的名称导出非托管 DLL 中的方法。</span><span class="sxs-lookup"><span data-stu-id="022cd-108">[in] The name of the target export method in an unmanaged DLL.</span></span>  
  
 `mrImportDLL`  
 <span data-ttu-id="022cd-109">[in]为目标的令牌本机 DLL。</span><span class="sxs-lookup"><span data-stu-id="022cd-109">[in] The token for the target native DLL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="022cd-110">要求</span><span class="sxs-lookup"><span data-stu-id="022cd-110">Requirements</span></span>  
 <span data-ttu-id="022cd-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="022cd-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="022cd-112">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="022cd-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="022cd-113">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="022cd-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="022cd-114">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="022cd-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="022cd-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="022cd-115">See also</span></span>

- [<span data-ttu-id="022cd-116">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="022cd-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="022cd-117">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="022cd-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
