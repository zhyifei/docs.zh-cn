---
title: "IAssemblyName::SetProperty 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IAssemblyName.SetProperty
api_location: fusion.dll
api_type: COM
f1_keywords: IAssemblyName::SetProperty
helpviewer_keywords:
- IAssemblyName::SetProperty method [.NET Framework fusion]
- SetProperty method [.NET Framework fusion]
ms.assetid: 496c3add-f60b-4073-943f-d1bcf33330cb
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 60ef27021ec3431c90086e0dfbae56bb6e6ccc86
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iassemblynamesetproperty-method"></a><span data-ttu-id="694cb-102">IAssemblyName::SetProperty 方法</span><span class="sxs-lookup"><span data-stu-id="694cb-102">IAssemblyName::SetProperty Method</span></span>
<span data-ttu-id="694cb-103">设置所引用的指定的属性标识符的属性的值。</span><span class="sxs-lookup"><span data-stu-id="694cb-103">Sets the value of the property referenced by the specified property identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="694cb-104">语法</span><span class="sxs-lookup"><span data-stu-id="694cb-104">Syntax</span></span>  
  
```  
HRESULT SetProperty (  
    [in] DWORD  PropertyId,  
    [in] LPVOID pvProperty,  
    [in] DWORD  cbProperty  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="694cb-105">参数</span><span class="sxs-lookup"><span data-stu-id="694cb-105">Parameters</span></span>  
 `PropertyId`  
 <span data-ttu-id="694cb-106">[in]将设置其值属性的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="694cb-106">[in] The unique identifier of the property whose value will be set.</span></span>  
  
 `pvProperty`  
 <span data-ttu-id="694cb-107">[in]要将所引用的属性设置为值`PropertyId`。</span><span class="sxs-lookup"><span data-stu-id="694cb-107">[in] The value to which to set the property referenced by `PropertyId`.</span></span>  
  
 `cbProperty`  
 <span data-ttu-id="694cb-108">[in]大小，以字节为单位的`pvProperty`。</span><span class="sxs-lookup"><span data-stu-id="694cb-108">[in] The size, in bytes, of `pvProperty`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="694cb-109">惠?</span><span class="sxs-lookup"><span data-stu-id="694cb-109">Requirements</span></span>  
 <span data-ttu-id="694cb-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="694cb-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="694cb-111">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="694cb-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="694cb-112">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="694cb-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="694cb-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="694cb-113">See Also</span></span>  
 [<span data-ttu-id="694cb-114">IAssemblyName 接口</span><span class="sxs-lookup"><span data-stu-id="694cb-114">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
