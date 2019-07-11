---
title: IAssemblyEnum::GetNextAssembly 方法
ms.date: 03/30/2017
api_name:
- IAssemblyEnum.GetNextAssembly
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyEnum::GetNextAssembly
helpviewer_keywords:
- GetNextAssembly method [.NET Framework fusion]
- IAssemblyEnum::GetNextAssembly method [.NET Framework fusion]
ms.assetid: 5d7a4ca2-5f46-4ef1-a9a2-257884e9dc11
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 57d64096ea693be41359aef63c04674ca77769c6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760975"
---
# <a name="iassemblyenumgetnextassembly-method"></a><span data-ttu-id="1509e-102">IAssemblyEnum::GetNextAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="1509e-102">IAssemblyEnum::GetNextAssembly Method</span></span>
<span data-ttu-id="1509e-103">获取一个指针指向下一步[IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)包含在此[IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)对象。</span><span class="sxs-lookup"><span data-stu-id="1509e-103">Gets a pointer to the next [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) contained in this [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1509e-104">语法</span><span class="sxs-lookup"><span data-stu-id="1509e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextAssembly (  
    [in]  LPVOID          pvReserved,  
    [out] IAssemblyName   **ppName,  
    [in]  DWORD           dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1509e-105">参数</span><span class="sxs-lookup"><span data-stu-id="1509e-105">Parameters</span></span>  
 `pvReserved`  
 <span data-ttu-id="1509e-106">[in]保留供将来的扩展。</span><span class="sxs-lookup"><span data-stu-id="1509e-106">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="1509e-107">`pvReserved` 必须是 null 引用。</span><span class="sxs-lookup"><span data-stu-id="1509e-107">`pvReserved` must be a null reference.</span></span>  
  
 `ppName`  
 <span data-ttu-id="1509e-108">[out]返回`IAssemblyName`指针。</span><span class="sxs-lookup"><span data-stu-id="1509e-108">[out] The returned `IAssemblyName` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="1509e-109">[in]保留供将来的扩展。</span><span class="sxs-lookup"><span data-stu-id="1509e-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="1509e-110">`dwFlags` 必须为 0 （零）。</span><span class="sxs-lookup"><span data-stu-id="1509e-110">`dwFlags` must be 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1509e-111">要求</span><span class="sxs-lookup"><span data-stu-id="1509e-111">Requirements</span></span>  
 <span data-ttu-id="1509e-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1509e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1509e-113">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="1509e-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="1509e-114">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1509e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1509e-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="1509e-115">See also</span></span>

- [<span data-ttu-id="1509e-116">IAssemblyName 接口</span><span class="sxs-lookup"><span data-stu-id="1509e-116">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="1509e-117">IAssemblyEnum 接口</span><span class="sxs-lookup"><span data-stu-id="1509e-117">IAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)
