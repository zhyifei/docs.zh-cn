---
title: IAssemblyCache::CreateAssemblyScavenger 方法
ms.date: 03/30/2017
api_name:
- IAssemblyCache.CreateAssemblyScavenger
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache::CreateAssemblyScavenger
helpviewer_keywords:
- CreateAssemblyScavenger method [.NET Framework fusion]
- IAssemblyCache::CreateAssemblyScavenger method [.NET Framework fusion]
ms.assetid: e8bb98f1-e477-45d2-8956-ba404137cd2d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 851abcae9c3edea5c971bd2bc4523c3cec757cc9
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796819"
---
# <a name="iassemblycachecreateassemblyscavenger-method"></a>IAssemblyCache::CreateAssemblyScavenger 方法
保留供合成技术内部使用。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT CreateAssemblyScavenger (  
    [out] IUnknown **ppUnkReserved  
);  
```  
  
## <a name="parameters"></a>参数  
 `ppUnkReserved`  
 弄返回`IUnknown`的指针。  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../get-started/system-requirements.md)。  
  
 **标头：** 合成。h  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [IAssemblyCache 接口](iassemblycache-interface.md)
