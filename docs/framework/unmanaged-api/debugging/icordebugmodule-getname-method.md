---
title: ICorDebugModule::GetName 方法
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetName
helpviewer_keywords:
- ICorDebugModule::GetName method [.NET Framework debugging]
- GetName method, ICorDebugModule interface [.NET Framework debugging]
ms.assetid: db499637-7ba9-421e-b8b1-35856995e80b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a7f62385031967c164915fd31735a6d962f557fa
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/11/2019
ms.locfileid: "70894985"
---
# <a name="icordebugmodulegetname-method"></a>ICorDebugModule::GetName 方法
获取模块的文件名。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT GetName(  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a>参数  
 `cchname`  
 [in] `szName` 数组的大小。  
  
 `pcchName`  
 中指向返回名称的长度的指针。  
  
 `szName`  
 弄存储返回的名称的数组。  
  
## <a name="remarks"></a>备注  
 如果`GetName`模块的文件名与磁盘上的名称相匹配，则该方法将返回 S_OK HRESULT。 `GetName`如果名称是虚构的，则返回 S_FALSE HRESULT，如用于动态或内存中的模块。  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cordebug.idl，Cordebug.idl  
  
 **类库**CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅
