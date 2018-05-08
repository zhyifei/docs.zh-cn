---
title: IEnumRAWINPUTDEVIC:Clone
ms.date: 03/30/2017
helpviewer_keywords:
- Clone method [WPF]
ms.assetid: 2a6a1900-aa55-45fa-9382-241d569a2dc4
ms.openlocfilehash: da089e5342e641ffebe22ca6a4a593f97faeb89c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="ienumrawinputdevicclone"></a>IEnumRAWINPUTDEVIC:Clone
创建一个与当权枚举器相同状态的原始输入设备枚举器，以循环访问相同的列表。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT Clone( [out] IEnumRAWINPUTDEVICE **ppenum);  
```  
  
#### <a name="parameters"></a>参数  
 `ppenum`  
  
 [out]接收的输出变量的地址[IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md)接口指针。 如果方法不成功，则此输出变量的值不确定。  
  
## <a name="property-valuereturn-value"></a>属性值/返回值  
 HRESULT： 此方法支持 E_INVALIDARG、 E_OUTOFMEMORY 和 E_UNEXPECTED 标准的返回值。  
  
## <a name="remarks"></a>备注  
 此方法使可以枚举序列中记录一个点，以便稍后返回到该点。 调用方必须释放此新的枚举器，单独从第一个枚举器。
