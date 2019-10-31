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
ms.openlocfilehash: 4d08644307e48b607ef700876845a0f0aad13fc9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127106"
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
 弄返回的 `IUnknown` 指针。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** 合成。h  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [IAssemblyCache 接口](iassemblycache-interface.md)
