---
title: ICorPublishProcessEnum::Next 方法
ms.date: 03/30/2017
api_name:
- ICorPublishProcessEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcessEnum::Next
helpviewer_keywords:
- ICorPublishProcessEnum::Next method [.NET Framework debugging]
- Next method, ICorPublishProcessEnum interface [.NET Framework debugging]
ms.assetid: 6c399f37-1e38-4ca1-b70d-8ae41f7228b7
topic_type:
- apiref
ms.openlocfilehash: 084af87acd73ef65739ba69ef2bd66d10d7c27c2
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790514"
---
# <a name="icorpublishprocessenumnext-method"></a>ICorPublishProcessEnum::Next 方法
从当前游标位置开始，获取集合中指定数量的进程。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorPublishProcess **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>参数  
 `celt`  
 中要检索的进程数。  
  
 `objects`  
 弄一个指针，指向检索到的[ICorPublishProcess](icorpublishprocess-interface.md)对象的数组，其中每个对象都表示一个进程。  
  
 `pceltFetched`  
 弄一个指针，指向实际返回的进程数。 如果 `celt` 为1，则此值可以为 null。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorPub，CorPub  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorPublishProcessEnum 接口](icorpublishprocessenum-interface.md)
