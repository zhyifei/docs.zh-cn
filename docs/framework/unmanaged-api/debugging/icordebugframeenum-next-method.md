---
title: "ICorDebugFrameEnum::Next 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFrameEnum.Next
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFrameEnum::Next
helpviewer_keywords:
- ICorDebugFrameEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugFrameEnum interface [.NET Framework debugging]
ms.assetid: 0bc96acb-6179-4328-a447-cda562ce9e98
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a2139661621d7ebe2bf20e96b400096393964b89
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugframeenumnext-method"></a>ICorDebugFrameEnum::Next 方法
获取指定的数量的 ICorDebugFrame 实例，从当前位置开始。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugFrame *frames[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a>参数  
 `celt`  
 [in]数`ICorDebugFrame`要检索的实例。  
  
 `frames`  
 [out]一个指针，其中每个指向数组`ICorDebugFrame`对象。  
  
 `pceltFetched`  
 [out]指向数`ICorDebugFrame`实际返回的实例。 此值可能为 null 如果`celt`是之一。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
