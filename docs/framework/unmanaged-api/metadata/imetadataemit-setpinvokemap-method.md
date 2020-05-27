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
ms.openlocfilehash: 0d34c7a2992a2779b96ec87f1a0175d8fcbce34a
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007788"
---
# <a name="imetadataemitsetpinvokemap-method"></a><span data-ttu-id="1768e-102">IMetaDataEmit::SetPinvokeMap 方法</span><span class="sxs-lookup"><span data-stu-id="1768e-102">IMetaDataEmit::SetPinvokeMap Method</span></span>
<span data-ttu-id="1768e-103">设置或更改方法的 PInvoke 签名的功能，由之前调用[IMetaDataEmit：:D efinepinvokemap](imetadataemit-definepinvokemap-method.md)定义。</span><span class="sxs-lookup"><span data-stu-id="1768e-103">Sets or changes features of a method's PInvoke signature, as defined by a prior call to [IMetaDataEmit::DefinePinvokeMap](imetadataemit-definepinvokemap-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1768e-104">语法</span><span class="sxs-lookup"><span data-stu-id="1768e-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPinvokeMap (
    [in]  mdToken      tk,
    [in]  DWORD        dwMappingFlags,  
    [in]  LPCWSTR      szImportName,
    [in]  mdModuleRef  mrImportDLL
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1768e-105">参数</span><span class="sxs-lookup"><span data-stu-id="1768e-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="1768e-106">中`mdToken`应用映射信息的。</span><span class="sxs-lookup"><span data-stu-id="1768e-106">[in] The `mdToken` to which mapping information applies.</span></span>  
  
 `dwMappingFlags`  
 <span data-ttu-id="1768e-107">中PInvoke 用来执行映射的标志。</span><span class="sxs-lookup"><span data-stu-id="1768e-107">[in] Flags used by PInvoke to do the mapping.</span></span> <span data-ttu-id="1768e-108">这是一个值的位掩码 `CorPinvokeMap` 。</span><span class="sxs-lookup"><span data-stu-id="1768e-108">This is a bitmask of `CorPinvokeMap` values.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="1768e-109">中本机 DLL 中目标导出的名称。</span><span class="sxs-lookup"><span data-stu-id="1768e-109">[in] The name of the target export in the native DLL.</span></span>  
  
 `mrImportDLL`  
 <span data-ttu-id="1768e-110">中`mdModuleRef`目标非托管 DLL 的标记。</span><span class="sxs-lookup"><span data-stu-id="1768e-110">[in] The `mdModuleRef` token for the target unmanaged DLL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1768e-111">要求</span><span class="sxs-lookup"><span data-stu-id="1768e-111">Requirements</span></span>  
 <span data-ttu-id="1768e-112">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1768e-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1768e-113">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="1768e-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1768e-114">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="1768e-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1768e-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1768e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1768e-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1768e-116">See also</span></span>

- [<span data-ttu-id="1768e-117">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="1768e-117">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="1768e-118">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="1768e-118">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
