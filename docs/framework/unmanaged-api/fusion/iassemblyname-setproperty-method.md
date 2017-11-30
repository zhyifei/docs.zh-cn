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
ms.openlocfilehash: 2b99b9c01d014f7b6c02eedde157fa6fdd4e142a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="iassemblynamesetproperty-method"></a><span data-ttu-id="62911-102">IAssemblyName::SetProperty 方法</span><span class="sxs-lookup"><span data-stu-id="62911-102">IAssemblyName::SetProperty Method</span></span>
<span data-ttu-id="62911-103">设置所引用的指定的属性标识符的属性的值。</span><span class="sxs-lookup"><span data-stu-id="62911-103">Sets the value of the property referenced by the specified property identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62911-104">语法</span><span class="sxs-lookup"><span data-stu-id="62911-104">Syntax</span></span>  
  
```  
HRESULT SetProperty (  
    [in] DWORD  PropertyId,  
    [in] LPVOID pvProperty,  
    [in] DWORD  cbProperty  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="62911-105">参数</span><span class="sxs-lookup"><span data-stu-id="62911-105">Parameters</span></span>  
 `PropertyId`  
 <span data-ttu-id="62911-106">[in]将设置其值属性的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="62911-106">[in] The unique identifier of the property whose value will be set.</span></span>  
  
 `pvProperty`  
 <span data-ttu-id="62911-107">[in]要将所引用的属性设置为值`PropertyId`。</span><span class="sxs-lookup"><span data-stu-id="62911-107">[in] The value to which to set the property referenced by `PropertyId`.</span></span>  
  
 `cbProperty`  
 <span data-ttu-id="62911-108">[in]大小，以字节为单位的`pvProperty`。</span><span class="sxs-lookup"><span data-stu-id="62911-108">[in] The size, in bytes, of `pvProperty`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62911-109">要求</span><span class="sxs-lookup"><span data-stu-id="62911-109">Requirements</span></span>  
 <span data-ttu-id="62911-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="62911-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62911-111">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="62911-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="62911-112">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62911-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62911-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="62911-113">See Also</span></span>  
 [<span data-ttu-id="62911-114">IAssemblyName 接口</span><span class="sxs-lookup"><span data-stu-id="62911-114">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
