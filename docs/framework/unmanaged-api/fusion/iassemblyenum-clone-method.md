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
ms.openlocfilehash: 141e6e303933c46a85adf08339856f8964b21f4e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796693"
---
# <a name="iassemblyenumclone-method"></a><span data-ttu-id="7f6c6-102">IAssemblyEnum::Clone 方法</span><span class="sxs-lookup"><span data-stu-id="7f6c6-102">IAssemblyEnum::Clone Method</span></span>
<span data-ttu-id="7f6c6-103">创建此[IAssemblyEnum](iassemblyenum-interface.md)对象的浅表副本。</span><span class="sxs-lookup"><span data-stu-id="7f6c6-103">Creates a shallow copy of this [IAssemblyEnum](iassemblyenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f6c6-104">语法</span><span class="sxs-lookup"><span data-stu-id="7f6c6-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone (  
    [out] IAssemblyEnum   **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7f6c6-105">参数</span><span class="sxs-lookup"><span data-stu-id="7f6c6-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="7f6c6-106">弄指向复制的指针。</span><span class="sxs-lookup"><span data-stu-id="7f6c6-106">[out] A pointer to the copy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f6c6-107">要求</span><span class="sxs-lookup"><span data-stu-id="7f6c6-107">Requirements</span></span>  
 <span data-ttu-id="7f6c6-108">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7f6c6-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f6c6-109">**标头：** 合成。h</span><span class="sxs-lookup"><span data-stu-id="7f6c6-109">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="7f6c6-110">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f6c6-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f6c6-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="7f6c6-111">See also</span></span>

- [<span data-ttu-id="7f6c6-112">IAssemblyEnum 接口</span><span class="sxs-lookup"><span data-stu-id="7f6c6-112">IAssemblyEnum Interface</span></span>](iassemblyenum-interface.md)
