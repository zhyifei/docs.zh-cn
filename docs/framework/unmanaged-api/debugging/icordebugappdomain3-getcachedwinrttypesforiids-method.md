---
title: ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs 方法
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain3.GetCachedWinRTTypesForIIDs
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs
helpviewer_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs method, [.NET Framework debugging]
- GetCachedWinRTTypesForIIDs method, ICorDebugAppDomain3 interface [.NET Framework debugging]
ms.assetid: 23682ca0-1bcf-48e6-996e-69f7ba337682
topic_type:
- apiref
ms.openlocfilehash: f8e92ec4f813e8810273a1514298d0739a3d2406
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179061"
---
# <a name="icordebugappdomain3getcachedwinrttypesforiids-method"></a>ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs 方法
根据应用程序域中的接口标识符获取应用程序域中缓存的 Windows 运行时类型的枚举器。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetCachedWinRTTypesForIIDs (
    [in]  ULONG32            cReqTypes,  
    [in]  GUID                *iidsToResolve,  
    [out] ICorDebugTypeEnum   **ppTypesEnum  
);  
```  
  
## <a name="parameters"></a>parameters  
 `cReqTypes`  
 [在]所需类型的数量。  
  
 `iidsToResolve`  
 [在]指向数组的指针，其中包含与要检索的 Windows 运行时类型的托管表示形式对应的接口标识符。  
  
 `ppTypesEnum`  
 [出]指向"ICorDebugTypeEnum"接口对象的地址的指针，该对象允许根据 中的`iidsToResolve`接口标识符检索到已检索的 Windows 运行时类型的缓存托管表示形式。  
  
## <a name="remarks"></a>备注  
 如果方法无法检索特定接口标识符的信息，则"ICorDebugTypeEnum"集合中的相应条目将具有一种`ELEMENT_TYPE_END`因数据检索问题或`ELEMENT_TYPE_VOID`未知接口标识符而导致的错误类型。  
  
## <a name="requirements"></a>要求  
 **平台：** 窗口运行时  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorDebugAppDomain3 接口](icordebugappdomain3-interface.md)
