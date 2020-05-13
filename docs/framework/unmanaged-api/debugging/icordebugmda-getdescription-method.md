---
title: ICorDebugMDA::GetDescription 方法
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetDescription
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetDescription
helpviewer_keywords:
- GetDescription method [.NET Framework debugging]
- ICorDebugMDA::GetDescription method [.NET Framework debugging]
ms.assetid: 01d1b481-ca67-4712-8744-d342ec0df639
topic_type:
- apiref
ms.openlocfilehash: 522e992e6d7e9a64f7590bbec0e9106e0e1f8f47
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212134"
---
# <a name="icordebugmdagetdescription-method"></a>ICorDebugMDA::GetDescription 方法
获取一个字符串，该字符串包含[ICorDebugMDA](icordebugmda-interface.md)表示的托管调试助手（MDA）的说明。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetDescription (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
## <a name="parameters"></a>参数  
 `cchName`  
 中将存储说明的字符串缓冲区的大小。  
  
 `pcchName`  
 弄指向字符串缓冲区中返回的字节数的指针。  
  
 `szName`  
 弄包含 MDA 说明的字符串缓冲区。  
  
## <a name="remarks"></a>备注  
 字符串的长度可以为零。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICorDebugMDA 接口](icordebugmda-interface.md)
- [使用托管调试助手诊断错误](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
