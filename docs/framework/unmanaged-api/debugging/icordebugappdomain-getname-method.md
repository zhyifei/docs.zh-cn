---
title: ICorDebugAppDomain::GetName 方法
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetName
helpviewer_keywords:
- ICorDebugAppDomain::GetName method [.NET Framework debugging]
- GetName method, ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: 02c596d7-00b0-4e2c-856b-5425158fcefd
topic_type:
- apiref
ms.openlocfilehash: 45d27fca888bdabedf197525c63dbd03af7ba1ee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179092"
---
# <a name="icordebugappdomaingetname-method"></a>ICorDebugAppDomain::GetName 方法
获取应用程序域的名称。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetName (  
    [in]  ULONG32           cchName,  
    [out] ULONG32           *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]
         WCHAR              szName[]  
);  
```  
  
## <a name="parameters"></a>parameters  
 `cchName`  
 [in] `szName` 数组的大小。 将此值设置为零，以将此方法置于查询模式。  
  
 `pcchName`  
 [出]指向名称大小或 中`szName`实际返回的字符数的指针。 在查询模式下，此值允许调用方知道要为名称分配缓冲区有多大。  
  
 `szName`  
 [出]存储应用程序域名称的数组。  
  
## <a name="remarks"></a>备注  
 调试器调用`GetName`该方法一次，以获得名称所需的缓冲区大小。 调试器分配缓冲区，然后第二次调用 该方法以填充缓冲区。 第一个调用（获取名称的大小）称为*查询模式*。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
