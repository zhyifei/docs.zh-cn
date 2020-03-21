---
title: ICorDebugProcess6::GetExportStepInfo 方法
ms.date: 03/30/2017
ms.assetid: a927e0ac-f110-426d-bbec-9377a29c8f17
ms.openlocfilehash: 6580fdaacaea17fcf886bfd7ac5e236925acf453
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178528"
---
# <a name="icordebugprocess6getexportstepinfo-method"></a>ICorDebugProcess6::GetExportStepInfo 方法
提供运行时导出功能信息以帮助单步调试托管代码。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetExportStepInfo(  
    [in] LPCWSTR pszExportName,
    [out] CorDebugCodeInvokeKind* pInvokeKind,
    [out] CorDebugCodeInvokePurpose* pInvokePurpose);  
```  
  
## <a name="parameters"></a>parameters  
 psz导出名  
 [输入] 如 PE 导出表中所写的运行时间导出函数名。  
  
 调用类型  
 [出]指向[CorDebugCodeInvokeKind](cordebugcodeinvokekind-enumeration.md)枚举成员的指针，用于描述导出的函数将如何调用托管代码。  
  
 调用目的  
 [出]指向[CorDebugCodeInvokePurpose](cordebugcodeinvokepurpose-enumeration.md)枚举成员的指针，用于描述导出函数将调用托管代码的原因。  
  
## <a name="return-value"></a>返回值  
 该方法可以返回下表所列的值。  
  
|返回值|说明|  
|------------------|-----------------|  
|`S_OK`|方法调用成功。|  
|`E_POINTER`|`pInvokeKind`或`pInvokePurpose`**为 null**。|  
|其他失败 `HRESULT` 值。|根据需要。|  
  
## <a name="remarks"></a>备注  
  
> [!NOTE]
> 此方法仅适用于 .NET Native。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET 框架版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorDebugProcess6 接口](icordebugprocess6-interface.md)
- [调试接口](debugging-interfaces.md)
