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
ms.openlocfilehash: 428b022ed560648f59798154d5987d382938c280
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176066"
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
  
## <a name="parameters"></a>parameters  
 `tkImp`  
 [在]表示导入的代码对象的元数据令牌。  
  
 `tkEmit`  
 [在]表示已发出的代码对象的元数据令牌。  
  
## <a name="remarks"></a>备注  
 当令牌重新映射在合并期间发生时，原始令牌在导入的（源）元数据作用域中作用域，新令牌在已发出（目标）元数据作用域中作用域。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** 科尔赫  
  
 **库：** 用作 MsCorEE.dll 中的资源  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IMapToken 接口](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md)
