---
title: IAssemblyEnum::Clone 方法
ms.date: 03/30/2017
api_name:
- IAssemblyEnum.Clone
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyEnum::Clone
helpviewer_keywords:
- Clone method, IAssemblyEnum interface [.NET Framework fusion]
- IAssemblyEnum::Clone method [.NET Framework fusion]
ms.assetid: 0014bb66-590c-486c-9ade-f2133905cd99
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d288f4ccf91567224546df1a3309a411590a5a12
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779025"
---
# <a name="iassemblyenumclone-method"></a><span data-ttu-id="b9870-102">IAssemblyEnum::Clone 方法</span><span class="sxs-lookup"><span data-stu-id="b9870-102">IAssemblyEnum::Clone Method</span></span>
<span data-ttu-id="b9870-103">创建的浅表副本[IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)对象。</span><span class="sxs-lookup"><span data-stu-id="b9870-103">Creates a shallow copy of this [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9870-104">语法</span><span class="sxs-lookup"><span data-stu-id="b9870-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone (  
    [out] IAssemblyEnum   **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b9870-105">参数</span><span class="sxs-lookup"><span data-stu-id="b9870-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="b9870-106">[out]指向该副本的指针。</span><span class="sxs-lookup"><span data-stu-id="b9870-106">[out] A pointer to the copy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9870-107">要求</span><span class="sxs-lookup"><span data-stu-id="b9870-107">Requirements</span></span>  
 <span data-ttu-id="b9870-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b9870-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9870-109">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="b9870-109">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="b9870-110">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9870-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9870-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="b9870-111">See also</span></span>

- [<span data-ttu-id="b9870-112">IAssemblyEnum 接口</span><span class="sxs-lookup"><span data-stu-id="b9870-112">IAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)
