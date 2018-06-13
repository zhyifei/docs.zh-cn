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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f2633bfadaabf208a2b86fda83375c3a136b93b9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448167"
---
# <a name="imaptokenmap-method"></a>IMapToken::Map 方法
映射使用元数据签名的程序集之间的关系。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT Map (  
    [in]  mdToken tkImp,   
    [in]  mdToken tkEmit  
);  
```  
  
#### <a name="parameters"></a>参数  
 `tkImp`  
 [in]表示导入的代码对象的元数据标记。  
  
 `tkEmit`  
 [in]表示发出的代码对象的元数据标记。  
  
## <a name="remarks"></a>备注  
 当令牌重新映射发生在合并过程时，原始令牌的作用范围导入 （源） 元数据范围内，而且新令牌范围发出 （目标） 元数据范围内。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：** 用作 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [IMapToken 接口](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md)
