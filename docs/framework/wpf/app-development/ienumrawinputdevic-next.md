---
title: IEnumRAWINPUTDEVIC:Next
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Next method [WPF]
ms.assetid: 3698b44d-510e-4d18-b32b-85f17188ee26
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: af6cb5bfe07923e13f1b76c785d830a9af15eaf9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ienumrawinputdevicnext"></a>IEnumRAWINPUTDEVIC:Next
枚举的下一步`celt` [RAWINPUTDEVICE](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputstructures/rawinputdevice.asp)在枚举器的列表中，将它们中返回的结构`rgelt`以及枚举中的元素的实际数量`pceltFetched`。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT Next(  
      [in] ULONG celt,  
      [out, size_is(celt), length_is(*pceltFetched)] RAWINPUTDEVICE *rgelt,  
      [out] ULONG *pceltFetched);  
```  
  
#### <a name="parameters"></a>参数  
 `celt`  
  
 [in]数[RAWINPUTDEVICE](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputstructures/rawinputdevice.asp)中返回的结构`rgelt`。  
  
 `rgelt`  
  
 [out] celt 大小（或更大）的数组，用于接收枚举的 RAWINPUTDEVICE 结构。  
  
 `pceltFetched`  
  
 [out] 指向 `rgelt` 中实际提供的元素数量的指针。 如果 `NULL` 为一，则调用方可传入 `rgelt`。  
  
## <a name="property-valuereturn-value"></a>属性值/返回值  
 HRESULT：如果提供的元素数量为 `celt`，则值为 S_OK；否则为 S_FALSE。
