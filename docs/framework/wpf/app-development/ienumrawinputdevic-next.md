---
title: IEnumRAWINPUTDEVIC:Next
ms.date: 03/30/2017
helpviewer_keywords:
- Next method [WPF]
ms.assetid: 3698b44d-510e-4d18-b32b-85f17188ee26
ms.openlocfilehash: 05867af48b64cd1898b13fa055859c8cc0367c8c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494176"
---
# <a name="ienumrawinputdevicnext"></a><span data-ttu-id="021a0-102">IEnumRAWINPUTDEVIC:Next</span><span class="sxs-lookup"><span data-stu-id="021a0-102">IEnumRAWINPUTDEVIC:Next</span></span>
<span data-ttu-id="021a0-103">枚举下一个`celt` [RAWINPUTDEVICE](/windows/desktop/api/winuser/ns-winuser-rawinputdevice)在枚举器的列表中，将它们中返回的结构`rgelt`以及中枚举元素的实际数目`pceltFetched`。</span><span class="sxs-lookup"><span data-stu-id="021a0-103">Enumerates the next `celt` [RAWINPUTDEVICE](/windows/desktop/api/winuser/ns-winuser-rawinputdevice) structures in the enumerator's list, returning them in `rgelt` along with the actual number of enumerated elements in `pceltFetched`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="021a0-104">语法</span><span class="sxs-lookup"><span data-stu-id="021a0-104">Syntax</span></span>  
  
```  
HRESULT Next(  
      [in] ULONG celt,  
      [out, size_is(celt), length_is(*pceltFetched)] RAWINPUTDEVICE *rgelt,  
      [out] ULONG *pceltFetched);  
```  
  
## <a name="parameters"></a><span data-ttu-id="021a0-105">参数</span><span class="sxs-lookup"><span data-stu-id="021a0-105">Parameters</span></span>  
 `celt`  
  
 <span data-ttu-id="021a0-106">[in]数[RAWINPUTDEVICE](/windows/desktop/api/winuser/ns-winuser-rawinputdevice)结构中返回`rgelt`。</span><span class="sxs-lookup"><span data-stu-id="021a0-106">[in] Number of [RAWINPUTDEVICE](/windows/desktop/api/winuser/ns-winuser-rawinputdevice) structures returned in `rgelt`.</span></span>  
  
 `rgelt`  
  
 <span data-ttu-id="021a0-107">[out] celt 大小（或更大）的数组，用于接收枚举的 RAWINPUTDEVICE 结构。</span><span class="sxs-lookup"><span data-stu-id="021a0-107">[out] Array of size celt (or larger) to receive enumerated RAWINPUTDEVICE structures.</span></span>  
  
 `pceltFetched`  
  
 <span data-ttu-id="021a0-108">[out] 指向 `rgelt` 中实际提供的元素数量的指针。</span><span class="sxs-lookup"><span data-stu-id="021a0-108">[out] Pointer to the number of elements actually supplied in `rgelt`.</span></span> <span data-ttu-id="021a0-109">如果 `rgelt` 为一，则调用方可传入 `NULL`。</span><span class="sxs-lookup"><span data-stu-id="021a0-109">Caller can pass in `NULL` if `rgelt` is one.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="021a0-110">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="021a0-110">Property Value/Return Value</span></span>  
 <span data-ttu-id="021a0-111">HRESULT：如果提供的元素数，则为 S_OK `celt`;否则为 S_FALSE。</span><span class="sxs-lookup"><span data-stu-id="021a0-111">HRESULT: S_OK if the number of elements supplied is `celt`; S_FALSE otherwise.</span></span>
