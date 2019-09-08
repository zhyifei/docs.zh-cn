---
title: StrongNameErrorInfo 函数
ms.date: 03/30/2017
api_name:
- StrongNameErrorInfo
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameErrorInfo
helpviewer_keywords:
- StrongNameErrorInfo function [.NET Framework strong naming]
ms.assetid: e91bf8c3-7c26-4732-938e-2e5b04abfc99
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 021fa1668247bc59a4412d2b5f4bac3f5ee8cc6b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799111"
---
# <a name="strongnameerrorinfo-function"></a>StrongNameErrorInfo 函数
获取由其中一个强名称函数引发的最后一个错误代码。  
  
 此函数已弃用。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT StrongNameErrorInfo ();   
```  
  
## <a name="return-value"></a>返回值  
 由一个强名称函数设置的最后一个 COM 错误代码。  
  
## <a name="remarks"></a>备注  
 大多数强名称方法返回成功完成的简单`true`或`false`指示。 `StrongNameErrorInfo`使用函数检索 HRESULT，该 HRESULT 指定强名称函数生成的最后一个错误。  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../get-started/system-requirements.md)。  
  
 **标头：** Stackexchange.redis.strongname  
  
 **类库**作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
