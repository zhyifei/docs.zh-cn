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
ms.openlocfilehash: c5ddc2646b560814adef01f2508f3792abe13c1d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744534"
---
# <a name="iassemblynamegetproperty-method"></a><span data-ttu-id="df8e5-102">IAssemblyName::GetProperty 方法</span><span class="sxs-lookup"><span data-stu-id="df8e5-102">IAssemblyName::GetProperty Method</span></span>
<span data-ttu-id="df8e5-103">获取一个指针指向引用指定的属性标识符的属性。</span><span class="sxs-lookup"><span data-stu-id="df8e5-103">Gets a pointer to the property referenced by the specified property identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df8e5-104">语法</span><span class="sxs-lookup"><span data-stu-id="df8e5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProperty (  
    [in]      DWORD    PropertyId,  
    [out]     LPVOID   pvProperty,  
    [in, out] LPDWORD  pcbProperty  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df8e5-105">参数</span><span class="sxs-lookup"><span data-stu-id="df8e5-105">Parameters</span></span>  
 `PropertyId`  
 <span data-ttu-id="df8e5-106">[in]请求的属性的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="df8e5-106">[in] The unique identifier for the requested property.</span></span>  
  
 `pvProperty`  
 <span data-ttu-id="df8e5-107">[out]返回的属性的数据。</span><span class="sxs-lookup"><span data-stu-id="df8e5-107">[out] The returned property data.</span></span>  
  
 `pcbProperty`  
 <span data-ttu-id="df8e5-108">[in、 out]大小，以字节为单位的`pvProperty`。</span><span class="sxs-lookup"><span data-stu-id="df8e5-108">[in, out] The size, in bytes, of `pvProperty`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df8e5-109">要求</span><span class="sxs-lookup"><span data-stu-id="df8e5-109">Requirements</span></span>  
 <span data-ttu-id="df8e5-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="df8e5-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df8e5-111">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="df8e5-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="df8e5-112">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df8e5-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df8e5-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="df8e5-113">See also</span></span>

- [<span data-ttu-id="df8e5-114">IAssemblyName 接口</span><span class="sxs-lookup"><span data-stu-id="df8e5-114">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
