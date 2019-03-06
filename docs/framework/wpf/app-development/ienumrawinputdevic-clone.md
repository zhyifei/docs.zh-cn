---
title: IEnumRAWINPUTDEVIC:Clone
ms.date: 03/30/2017
helpviewer_keywords:
- Clone method [WPF]
ms.assetid: 2a6a1900-aa55-45fa-9382-241d569a2dc4
ms.openlocfilehash: a4c5e7db813089d1dd138416ac54dd4be467b87b
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57355010"
---
# <a name="ienumrawinputdevicclone"></a><span data-ttu-id="57e2d-102">IEnumRAWINPUTDEVIC:Clone</span><span class="sxs-lookup"><span data-stu-id="57e2d-102">IEnumRAWINPUTDEVIC:Clone</span></span>
<span data-ttu-id="57e2d-103">创建一个与当权枚举器相同状态的原始输入设备枚举器，以循环访问相同的列表。</span><span class="sxs-lookup"><span data-stu-id="57e2d-103">Creates another raw input device enumerator with the same state as the current enumerator to iterate over the same list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57e2d-104">语法</span><span class="sxs-lookup"><span data-stu-id="57e2d-104">Syntax</span></span>  
  
```  
HRESULT Clone( [out] IEnumRAWINPUTDEVICE **ppenum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="57e2d-105">参数</span><span class="sxs-lookup"><span data-stu-id="57e2d-105">Parameters</span></span>  
 `ppenum`  
  
 <span data-ttu-id="57e2d-106">[out]接收的输出变量的地址[IEnumRAWINPUTDEVICE](ienumrawinputdevice.md)接口指针。</span><span class="sxs-lookup"><span data-stu-id="57e2d-106">[out] Address of output variable that receives the [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) interface pointer.</span></span> <span data-ttu-id="57e2d-107">如果该方法不成功，此输出变量的值未定义。</span><span class="sxs-lookup"><span data-stu-id="57e2d-107">If the method is unsuccessful, the value of this output variable is undefined.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="57e2d-108">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="57e2d-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="57e2d-109">HRESULT：此方法支持 E_INVALIDARG 和 e_outofmemory 等 E_UNEXPECTED 标准的返回值。</span><span class="sxs-lookup"><span data-stu-id="57e2d-109">HRESULT: This method supports the standard return values E_INVALIDARG, E_OUTOFMEMORY, and E_UNEXPECTED.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="57e2d-110">备注</span><span class="sxs-lookup"><span data-stu-id="57e2d-110">Remarks</span></span>  
 <span data-ttu-id="57e2d-111">此方法可枚举序列中记录一个点，以便在以后返回到该点。</span><span class="sxs-lookup"><span data-stu-id="57e2d-111">This method makes it possible to record a point in the enumeration sequence in order to return to that point at a later time.</span></span> <span data-ttu-id="57e2d-112">调用方必须释放此独立于第一个枚举器的新枚举器。</span><span class="sxs-lookup"><span data-stu-id="57e2d-112">The caller must release this new enumerator separately from the first enumerator.</span></span>
