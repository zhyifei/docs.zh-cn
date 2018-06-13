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
ms.openlocfilehash: bebee019595143d25e950719ad62d9e10b76a3e9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418901"
---
# <a name="icordebugmodulegetname-method"></a>ICorDebugModule::GetName 方法
获取模块的文件名。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetName(  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
#### <a name="parameters"></a>参数  
 `cchname`  
 [in] `szName` 数组的大小。  
  
 `pcchName`  
 [in]指向返回的名称的长度的指针。  
  
 `szName`  
 [out]一个数组，将存储返回的名称。  
  
## <a name="remarks"></a>备注  
 `GetName`方法返回，则为 S_OK HRESULT，如果模块的文件名称与磁盘上的名称相匹配。 `GetName` 如果名称为虚构，例如对于动态或内存中的模块，请返回一个 S_FALSE HRESULT。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
    
 
