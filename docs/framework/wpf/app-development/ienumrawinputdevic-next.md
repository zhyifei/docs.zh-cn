---
title: IEnumRAWINPUTDEVIC:Next
ms.date: 03/30/2017
helpviewer_keywords:
- Next method [WPF]
ms.assetid: 3698b44d-510e-4d18-b32b-85f17188ee26
ms.openlocfilehash: c7450a9ababa9cf3cb02d572f5ed84f0791d74e4
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053403"
---
# <a name="ienumrawinputdevicnext"></a>IEnumRAWINPUTDEVIC:Next
枚举枚举器`celt`列表中的下一个[RAWINPUTDEVICE](/windows/desktop/api/winuser/ns-winuser-rawinputdevice)结构`rgelt` ，将它们与中`pceltFetched`的枚举元素的实际数目一起返回。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT Next(  
      [in] ULONG celt,  
      [out, size_is(celt), length_is(*pceltFetched)] RAWINPUTDEVICE *rgelt,  
      [out] ULONG *pceltFetched);  
```  
  
## <a name="parameters"></a>参数  
 `celt`  
  
 中返回`rgelt`的[RAWINPUTDEVICE](/windows/desktop/api/winuser/ns-winuser-rawinputdevice)结构的数目。  
  
 `rgelt`  
  
 [out] celt 大小（或更大）的数组，用于接收枚举的 RAWINPUTDEVICE 结构。  
  
 `pceltFetched`  
  
 [out] 指向 `rgelt` 中实际提供的元素数量的指针。 如果 `NULL` 为一，则调用方可传入 `rgelt`。  
  
## <a name="property-valuereturn-value"></a>属性值/返回值  
 HRESULT：如果提供的元素数为`celt`，则为 S_OK;否则为 S_FALSE。
