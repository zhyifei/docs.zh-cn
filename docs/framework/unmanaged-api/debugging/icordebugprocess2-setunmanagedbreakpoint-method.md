---
title: ICorDebugProcess2::SetUnmanagedBreakpoint 方法
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.SetUnmanagedBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::SetUnmanagedBreakpoint
helpviewer_keywords:
- ICorDebugProcess2::SetUnmanagedBreakpoint method [.NET Framework debugging]
- SetUnmanagedBreakpoint method [.NET Framework debugging]
ms.assetid: 93829d15-d942-4e2d-b7a4-dfc9d7fb96be
topic_type:
- apiref
ms.openlocfilehash: 6b9396d03892f29e3698af90856d0c0023dc628a
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213460"
---
# <a name="icordebugprocess2setunmanagedbreakpoint-method"></a>ICorDebugProcess2::SetUnmanagedBreakpoint 方法
在指定的本机映像偏移量处设置非托管断点。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT SetUnmanagedBreakpoint (  
    [in]  CORDB_ADDRESS    address,  
    [in]  ULONG32          bufsize,  
    [out, size_is(bufsize), length_is(*bufLen)]
        BYTE               buffer[],  
    [out] ULONG32          *bufLen  
);  
```  
  
## <a name="parameters"></a>参数  
 `address`  
 中一个 `CORDB_ADDRESS` 对象，该对象指定本机映像偏移量。  
  
 `bufsize`  
 中数组的大小（以字节为单位） `buffer` 。  
  
 `buffer`  
 弄一个数组，其中包含由断点替换的操作码。  
  
 `bufLen`  
 弄指向数组中返回的字节数的指针 `buffer` 。  
  
## <a name="remarks"></a>备注  
 如果本机映像偏移量在公共语言运行时（CLR）中，则将忽略该断点。 当调试器设置断点时，这允许 CLR 避免调度带外断点。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
