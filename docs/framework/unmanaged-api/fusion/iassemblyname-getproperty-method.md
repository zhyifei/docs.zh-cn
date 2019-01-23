---
title: IAssemblyName::GetProperty 方法
ms.date: 03/30/2017
api_name:
- IAssemblyName.GetProperty
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::GetProperty
helpviewer_keywords:
- IAssemblyName::GetProperty method [.NET Framework fusion]
- GetProperty method [.NET Framework fusion]
ms.assetid: e59fda62-77d5-4e37-89cb-ce7ae4627975
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5d131e9d8c7a1a2b4e4def75ecfb65bb8235a65e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54550664"
---
# <a name="iassemblynamegetproperty-method"></a><span data-ttu-id="1d6dc-102">IAssemblyName::GetProperty 方法</span><span class="sxs-lookup"><span data-stu-id="1d6dc-102">IAssemblyName::GetProperty Method</span></span>
<span data-ttu-id="1d6dc-103">获取一个指针指向引用指定的属性标识符的属性。</span><span class="sxs-lookup"><span data-stu-id="1d6dc-103">Gets a pointer to the property referenced by the specified property identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d6dc-104">语法</span><span class="sxs-lookup"><span data-stu-id="1d6dc-104">Syntax</span></span>  
  
```  
HRESULT GetProperty (  
    [in]      DWORD    PropertyId,  
    [out]     LPVOID   pvProperty,  
    [in, out] LPDWORD  pcbProperty  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1d6dc-105">参数</span><span class="sxs-lookup"><span data-stu-id="1d6dc-105">Parameters</span></span>  
 `PropertyId`  
 <span data-ttu-id="1d6dc-106">[in]请求的属性的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="1d6dc-106">[in] The unique identifier for the requested property.</span></span>  
  
 `pvProperty`  
 <span data-ttu-id="1d6dc-107">[out]返回的属性的数据。</span><span class="sxs-lookup"><span data-stu-id="1d6dc-107">[out] The returned property data.</span></span>  
  
 `pcbProperty`  
 <span data-ttu-id="1d6dc-108">[in、 out]大小，以字节为单位的`pvProperty`。</span><span class="sxs-lookup"><span data-stu-id="1d6dc-108">[in, out] The size, in bytes, of `pvProperty`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d6dc-109">要求</span><span class="sxs-lookup"><span data-stu-id="1d6dc-109">Requirements</span></span>  
 <span data-ttu-id="1d6dc-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1d6dc-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d6dc-111">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="1d6dc-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="1d6dc-112">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d6dc-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d6dc-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="1d6dc-113">See also</span></span>
- [<span data-ttu-id="1d6dc-114">IAssemblyName 接口</span><span class="sxs-lookup"><span data-stu-id="1d6dc-114">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
