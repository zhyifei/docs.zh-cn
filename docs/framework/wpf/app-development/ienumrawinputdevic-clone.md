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
ms.workload: dotnet
ms.openlocfilehash: db218ec824dfe163946b0c1bd412efd0f78f4ad8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
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
