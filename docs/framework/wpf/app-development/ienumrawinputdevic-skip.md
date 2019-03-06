---
title: IEnumRAWINPUTDEVIC:Skip
ms.date: 03/30/2017
helpviewer_keywords:
- Skip method [WPF]
ms.assetid: c967b0f8-1c6a-459c-8c16-d4f08918ab65
ms.openlocfilehash: fadf7b5526598f446eb7e49640bf4d43ec7395bf
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57354513"
---
# <a name="ienumrawinputdevicskip"></a><span data-ttu-id="a11d7-102">IEnumRAWINPUTDEVIC:Skip</span><span class="sxs-lookup"><span data-stu-id="a11d7-102">IEnumRAWINPUTDEVIC:Skip</span></span>
<span data-ttu-id="a11d7-103">指示枚举器跳过下一步`celt`枚举中的元素，以便下次调用[IEnumRAWINPUTDEVIC:Next](ienumrawinputdevic-next.md)不会返回这些元素。</span><span class="sxs-lookup"><span data-stu-id="a11d7-103">Instructs the enumerator to skip the next `celt` elements in the enumeration so that the next call to [IEnumRAWINPUTDEVIC:Next](ienumrawinputdevic-next.md) will not return those elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a11d7-104">语法</span><span class="sxs-lookup"><span data-stu-id="a11d7-104">Syntax</span></span>  
  
```  
HRESULT Skip( [in] ULONG celt);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a11d7-105">参数</span><span class="sxs-lookup"><span data-stu-id="a11d7-105">Parameters</span></span>  
 `celt`  
  
 <span data-ttu-id="a11d7-106">[in]要跳过的元素数。</span><span class="sxs-lookup"><span data-stu-id="a11d7-106">[in] Number of elements to be skipped.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="a11d7-107">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="a11d7-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="a11d7-108">HRESULT：如果提供的元素数，则为 S_OK `celt`;否则为 S_FALSE。</span><span class="sxs-lookup"><span data-stu-id="a11d7-108">HRESULT: S_OK if the number of elements supplied is `celt`; S_FALSE otherwise.</span></span>
