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
ms.openlocfilehash: ade404557d65fa073b6a0e66fe8234b41223ecde
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134438"
---
# <a name="iassemblyenumgetnextassembly-method"></a><span data-ttu-id="89989-102">IAssemblyEnum::GetNextAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="89989-102">IAssemblyEnum::GetNextAssembly Method</span></span>
<span data-ttu-id="89989-103">获取一个指针，该指针指向此[IAssemblyEnum](iassemblyenum-interface.md)对象中包含的下一个[IAssemblyName](iassemblyname-interface.md) 。</span><span class="sxs-lookup"><span data-stu-id="89989-103">Gets a pointer to the next [IAssemblyName](iassemblyname-interface.md) contained in this [IAssemblyEnum](iassemblyenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89989-104">语法</span><span class="sxs-lookup"><span data-stu-id="89989-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextAssembly (  
    [in]  LPVOID          pvReserved,  
    [out] IAssemblyName   **ppName,  
    [in]  DWORD           dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="89989-105">参数</span><span class="sxs-lookup"><span data-stu-id="89989-105">Parameters</span></span>  
 `pvReserved`  
 <span data-ttu-id="89989-106">中保留以供将来进行扩展。</span><span class="sxs-lookup"><span data-stu-id="89989-106">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="89989-107">`pvReserved` 必须为空引用。</span><span class="sxs-lookup"><span data-stu-id="89989-107">`pvReserved` must be a null reference.</span></span>  
  
 `ppName`  
 <span data-ttu-id="89989-108">弄返回的 `IAssemblyName` 指针。</span><span class="sxs-lookup"><span data-stu-id="89989-108">[out] The returned `IAssemblyName` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="89989-109">中保留以供将来进行扩展。</span><span class="sxs-lookup"><span data-stu-id="89989-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="89989-110">`dwFlags` 必须为0（零）。</span><span class="sxs-lookup"><span data-stu-id="89989-110">`dwFlags` must be 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89989-111">要求</span><span class="sxs-lookup"><span data-stu-id="89989-111">Requirements</span></span>  
 <span data-ttu-id="89989-112">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="89989-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89989-113">**标头：** 合成。h</span><span class="sxs-lookup"><span data-stu-id="89989-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="89989-114">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89989-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89989-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="89989-115">See also</span></span>

- [<span data-ttu-id="89989-116">IAssemblyName 接口</span><span class="sxs-lookup"><span data-stu-id="89989-116">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="89989-117">IAssemblyEnum 接口</span><span class="sxs-lookup"><span data-stu-id="89989-117">IAssemblyEnum Interface</span></span>](iassemblyenum-interface.md)
