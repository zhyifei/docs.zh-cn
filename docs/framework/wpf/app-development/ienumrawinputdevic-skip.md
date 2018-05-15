---
title: IEnumRAWINPUTDEVIC:Skip
ms.date: 03/30/2017
helpviewer_keywords:
- Skip method [WPF]
ms.assetid: c967b0f8-1c6a-459c-8c16-d4f08918ab65
ms.openlocfilehash: b03d141f1d2bfc18428c2f8651a340b789cfb995
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="ienumrawinputdevicskip"></a><span data-ttu-id="32296-102">IEnumRAWINPUTDEVIC:Skip</span><span class="sxs-lookup"><span data-stu-id="32296-102">IEnumRAWINPUTDEVIC:Skip</span></span>
<span data-ttu-id="32296-103">指示枚举数跳过下一步`celt`枚举中的元素，以便下一次调用到[IEnumRAWINPUTDEVIC:Next](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-next.md)不会返回这些元素。</span><span class="sxs-lookup"><span data-stu-id="32296-103">Instructs the enumerator to skip the next `celt` elements in the enumeration so that the next call to [IEnumRAWINPUTDEVIC:Next](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-next.md) will not return those elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32296-104">语法</span><span class="sxs-lookup"><span data-stu-id="32296-104">Syntax</span></span>  
  
```  
HRESULT Skip( [in] ULONG celt);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="32296-105">参数</span><span class="sxs-lookup"><span data-stu-id="32296-105">Parameters</span></span>  
 `celt`  
  
 <span data-ttu-id="32296-106">[in]要跳过的元素数。</span><span class="sxs-lookup"><span data-stu-id="32296-106">[in] Number of elements to be skipped.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="32296-107">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="32296-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="32296-108">HRESULT：如果提供的元素数量为 `celt`，则值为 S_OK；否则为 S_FALSE。</span><span class="sxs-lookup"><span data-stu-id="32296-108">HRESULT: S_OK if the number of elements supplied is `celt`; S_FALSE otherwise.</span></span>
