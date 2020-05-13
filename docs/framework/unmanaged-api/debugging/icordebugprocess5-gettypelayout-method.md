---
title: ICorDebugProcess5::GetTypeLayout 方法
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetTypeLayout
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeLayout
helpviewer_keywords:
- ICorDebugProcess5::GetTypeLayout method [.NET Framework debugging]
- GetTypeLayout method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: bd62f5d1-e874-41f1-81e5-a29a7572c15d
topic_type:
- apiref
ms.openlocfilehash: 861af4ba9c6f4d4bdb16abb9d4e1fd79debac59b
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205578"
---
# <a name="icordebugprocess5gettypelayout-method"></a>ICorDebugProcess5::GetTypeLayout 方法
根据对象的类型标识符获取有关该对象在内存中的布局的信息。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetTypeLayout(    [in] COR_TYPEID id,     [out] COR_TYPE_LAYOUT *pLayout);  
```  
  
## <a name="parameters"></a>参数  
 `id`  
 中一个[COR_TYPEID](cor-typeid-structure.md)标记，它指定需要其布局的类型。  
  
 `pLayout`  
 弄指向[COR_TYPE_LAYOUT](cor-type-layout-structure.md)结构的指针，该结构包含有关内存中对象的布局的信息。  
  
## <a name="remarks"></a>备注  
 `ICorDebugProcess5::GetTypeLayout`方法基于对象的[COR_TYPEID](cor-typeid-structure.md)提供有关该对象的信息，该对象由许多其他[ICorDebugProcess5](icordebugprocess5-interface.md)方法返回。 此信息由方法填充的[COR_TYPE_LAYOUT](cor-type-layout-structure.md)结构提供。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [COR_TYPE_LAYOUT 结构](cor-type-layout-structure.md)
- [ICorDebugProcess5 接口](icordebugprocess5-interface.md)
- [调试接口](debugging-interfaces.md)
