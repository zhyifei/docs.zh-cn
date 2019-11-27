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
ms.openlocfilehash: 9d4ea16a212ac5f0120d63510f07eaee69af739e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431488"
---
# <a name="imetadataemitdefinepinvokemap-method"></a><span data-ttu-id="f83d5-102">IMetaDataEmit::DefinePinvokeMap 方法</span><span class="sxs-lookup"><span data-stu-id="f83d5-102">IMetaDataEmit::DefinePinvokeMap Method</span></span>
<span data-ttu-id="f83d5-103">设置指定的标记所引用的方法的 PInvoke 签名功能。</span><span class="sxs-lookup"><span data-stu-id="f83d5-103">Sets features of the PInvoke signature of the method referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f83d5-104">语法</span><span class="sxs-lookup"><span data-stu-id="f83d5-104">Syntax</span></span>  
  
```cpp  
HRESULT DefinePinvokeMap (   
    [in]  mdToken            tk,   
    [in]  DWORD              dwMappingFlags,   
    [in]  LPCWSTR            szImportName,   
    [in]  mdModuleRef        mrImportDLL   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f83d5-105">参数</span><span class="sxs-lookup"><span data-stu-id="f83d5-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="f83d5-106">中目标方法的标记。</span><span class="sxs-lookup"><span data-stu-id="f83d5-106">[in] The token for the target method.</span></span>  
  
 `dwMappingFlags`  
 <span data-ttu-id="f83d5-107">中PInvoke 用来执行映射的标志。</span><span class="sxs-lookup"><span data-stu-id="f83d5-107">[in] Flags used by PInvoke to do the mapping.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="f83d5-108">中非托管 DLL 中目标导出方法的名称。</span><span class="sxs-lookup"><span data-stu-id="f83d5-108">[in] The name of the target export method in an unmanaged DLL.</span></span>  
  
 `mrImportDLL`  
 <span data-ttu-id="f83d5-109">中目标本机 DLL 的标记。</span><span class="sxs-lookup"><span data-stu-id="f83d5-109">[in] The token for the target native DLL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f83d5-110">要求</span><span class="sxs-lookup"><span data-stu-id="f83d5-110">Requirements</span></span>  
 <span data-ttu-id="f83d5-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f83d5-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f83d5-112">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="f83d5-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f83d5-113">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="f83d5-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f83d5-114">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f83d5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f83d5-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f83d5-115">See also</span></span>

- [<span data-ttu-id="f83d5-116">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="f83d5-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="f83d5-117">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="f83d5-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
