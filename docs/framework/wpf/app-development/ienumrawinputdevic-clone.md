---
title: IEnumRAWINPUTDEVIC:Clone
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Clone method [WPF]
ms.assetid: 2a6a1900-aa55-45fa-9382-241d569a2dc4
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 35f3c00f3a0efd41c425ba29f8465a73e78d624c
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="ienumrawinputdevicclone"></a><span data-ttu-id="f12aa-102">IEnumRAWINPUTDEVIC:Clone</span><span class="sxs-lookup"><span data-stu-id="f12aa-102">IEnumRAWINPUTDEVIC:Clone</span></span>
<span data-ttu-id="f12aa-103">创建一个与当权枚举器相同状态的原始输入设备枚举器，以循环访问相同的列表。</span><span class="sxs-lookup"><span data-stu-id="f12aa-103">Creates another raw input device enumerator with the same state as the current enumerator to iterate over the same list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f12aa-104">语法</span><span class="sxs-lookup"><span data-stu-id="f12aa-104">Syntax</span></span>  
  
```  
HRESULT Clone( [out] IEnumRAWINPUTDEVICE **ppenum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f12aa-105">参数</span><span class="sxs-lookup"><span data-stu-id="f12aa-105">Parameters</span></span>  
 `ppenum`  
  
 <span data-ttu-id="f12aa-106">[out]接收的输出变量的地址[IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md)接口指针。</span><span class="sxs-lookup"><span data-stu-id="f12aa-106">[out] Address of output variable that receives the [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) interface pointer.</span></span> <span data-ttu-id="f12aa-107">如果方法不成功，则此输出变量的值不确定。</span><span class="sxs-lookup"><span data-stu-id="f12aa-107">If the method is unsuccessful, the value of this output variable is undefined.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="f12aa-108">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="f12aa-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="f12aa-109">HRESULT： 此方法支持 E_INVALIDARG、 E_OUTOFMEMORY 和 E_UNEXPECTED 标准的返回值。</span><span class="sxs-lookup"><span data-stu-id="f12aa-109">HRESULT: This method supports the standard return values E_INVALIDARG, E_OUTOFMEMORY, and E_UNEXPECTED.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f12aa-110">备注</span><span class="sxs-lookup"><span data-stu-id="f12aa-110">Remarks</span></span>  
 <span data-ttu-id="f12aa-111">此方法使可以枚举序列中记录一个点，以便稍后返回到该点。</span><span class="sxs-lookup"><span data-stu-id="f12aa-111">This method makes it possible to record a point in the enumeration sequence in order to return to that point at a later time.</span></span> <span data-ttu-id="f12aa-112">调用方必须释放此新的枚举器，单独从第一个枚举器。</span><span class="sxs-lookup"><span data-stu-id="f12aa-112">The caller must release this new enumerator separately from the first enumerator.</span></span>
