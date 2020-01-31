---
title: ICorDebugType2 接口
ms.date: 03/30/2017
api_name:
- ICorDebugType2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType2
helpviewer_keywords:
- ICorDebugType2 interface
ms.assetid: 376fb03f-f1ef-4107-baa4-4d9d55884862
topic_type:
- apiref
ms.openlocfilehash: e90952a92c408762a98a2bfcb91b6aeb72052df1
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791223"
---
# <a name="icordebugtype2-interface"></a>ICorDebugType2 接口
扩展 ICorDebugType 接口以检索基类型或复杂（用户定义）类型的类型标识符。  
  
## <a name="methods"></a>方法  
  
|方法||  
|------------|-|  
|[GetTypeID 方法](icordebugtype2-gettypeid-method.md)|获取此类型的[COR_TYPEID](cor-typeid-structure.md) 。|  
  
## <a name="remarks"></a>备注  
 此接口是 ICorDebugType 接口的逻辑扩展。  
  
> [!NOTE]
> 此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="example"></a>示例  
 下面的代码段演示了如何使用[ICorDebugType2：： GetTypeID](icordebugtype2-gettypeid-method.md)方法。  
  
```cpp  
// (error checking omitted for brevity)  
// given an ICorDebugType *pType  
  
ICorDebugType2 *pType2 = NULL;  
pType->QueryInterface(IID_ICorDebugType2, &pType);  
  
COR_TYPEID id;  
pType2->GetTypeID(&id);  
  
// now we can use existing APIs to get information about this COR_TYPEID  
```  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [调试接口](debugging-interfaces.md)
