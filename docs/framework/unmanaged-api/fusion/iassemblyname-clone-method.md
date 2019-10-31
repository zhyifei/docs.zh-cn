---
title: IAssemblyName::Clone 方法
ms.date: 03/30/2017
api_name:
- IAssemblyName.Clone
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::Clone
helpviewer_keywords:
- Clone method, IAssemblyName interface [.NET Framework fusion]
- IAssemblyName::Clone method [.NET Framework fusion]
ms.assetid: 7b345e08-5e16-4e3d-a044-4e19d0892943
topic_type:
- apiref
ms.openlocfilehash: 1236a574a85c01e3e1be5df9644bd04bbf0753ea
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134406"
---
# <a name="iassemblynameclone-method"></a><span data-ttu-id="4835e-102">IAssemblyName::Clone 方法</span><span class="sxs-lookup"><span data-stu-id="4835e-102">IAssemblyName::Clone Method</span></span>
<span data-ttu-id="4835e-103">创建此[IAssemblyName](iassemblyname-interface.md)对象的浅表副本。</span><span class="sxs-lookup"><span data-stu-id="4835e-103">Creates a shallow copy of this [IAssemblyName](iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4835e-104">语法</span><span class="sxs-lookup"><span data-stu-id="4835e-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone (  
    [out] IAssemblyName **pName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4835e-105">参数</span><span class="sxs-lookup"><span data-stu-id="4835e-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="4835e-106">弄此 `IAssemblyName` 对象的返回副本。</span><span class="sxs-lookup"><span data-stu-id="4835e-106">[out] The returned copy of this `IAssemblyName` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4835e-107">要求</span><span class="sxs-lookup"><span data-stu-id="4835e-107">Requirements</span></span>  
 <span data-ttu-id="4835e-108">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4835e-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4835e-109">**标头：** 合成。h</span><span class="sxs-lookup"><span data-stu-id="4835e-109">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="4835e-110">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4835e-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4835e-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="4835e-111">See also</span></span>

- [<span data-ttu-id="4835e-112">IAssemblyName 接口</span><span class="sxs-lookup"><span data-stu-id="4835e-112">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
