---
title: ICorDebugProcess6::GetExportStepInfo 方法
ms.date: 03/30/2017
ms.assetid: a927e0ac-f110-426d-bbec-9377a29c8f17
ms.openlocfilehash: 118f52db63464b4c9355ba9ee7f330b996c5bf71
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792250"
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
  
## <a name="parameters"></a>参数  
 psz导出名  
 [输入] 如 PE 导出表中所写的运行时间导出函数名。  
  
 调用类型  
 弄一个指针，指向[CorDebugCodeInvokeKind](cordebugcodeinvokekind-enumeration.md)枚举的成员，该枚举描述导出函数将如何调用托管代码。  
  
 调用目的  
 弄指向[CorDebugCodeInvokePurpose](cordebugcodeinvokepurpose-enumeration.md)枚举的成员的指针，该成员描述导出函数将调用托管代码的原因。  
  
## <a name="return-value"></a>返回值  
 该方法可以返回下表所列的值。  
  
|返回值|描述|  
|------------------|-----------------|  
|`S_OK`|方法调用成功。|  
|`E_POINTER`|`pInvokeKind` 或 `pInvokePurpose` 为**null**。|  
|其他失败 `HRESULT` 值。|根据需要。|  
  
## <a name="remarks"></a>备注  
  
> [!NOTE]
> 此方法仅适用于 .NET Native。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorDebugProcess6 接口](icordebugprocess6-interface.md)
- [调试接口](debugging-interfaces.md)
