---
title: IMapToken::Map 方法
ms.date: 03/30/2017
api_name:
- IMapToken.Map
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMapToken::Map
helpviewer_keywords:
- IMapToken::Map method [.NET Framework metadata]
- Map method [.NET Framework metadata]
ms.assetid: b9b4bf2f-1098-43d6-9619-a99b4bda1940
topic_type:
- apiref
ms.openlocfilehash: 027694cee1b3e4d990796ba31300918f6d859679
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008191"
---
# <a name="imaptokenmap-method"></a>IMapToken::Map 方法
使用元数据签名映射程序集之间的关系。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT Map (  
    [in]  mdToken tkImp,
    [in]  mdToken tkEmit  
);  
```  
  
## <a name="parameters"></a>参数  
 `tkImp`  
 中表示导入的代码对象的元数据标记。  
  
 `tkEmit`  
 中表示发出的代码对象的元数据标记。  
  
## <a name="remarks"></a>备注  
 如果在合并过程中发生令牌重新映射，则原始令牌的作用域为导入（源）元数据范围内，并且新令牌的范围限定为发出（目标）元数据范围。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** Cor  
  
 **库：** 用作 Mscoree.dll 中的资源  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IMapToken 接口](imaptoken-interface.md)
