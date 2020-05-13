---
title: ICorDebugMergedAssemblyRecord::GetVersion 方法
ms.date: 03/30/2017
ms.assetid: c6858b06-ae26-4312-b325-ea6025016675
ms.openlocfilehash: cad71080c86e92beb318722db86011b09ce02e91
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83207627"
---
# <a name="icordebugmergedassemblyrecordgetversion-method"></a>ICorDebugMergedAssemblyRecord::GetVersion 方法
获取程序集的版本信息。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetVersion(  
   [out] USHORT *pMajor,
   [out] USHORT *pMinor,
   [out] USHORT *pBuild,
   [out] USHORT *pRevision  
);  
```  
  
## <a name="parameters"></a>参数  
 `pMajor`  
 [out] 指向主版本号的指针。  
  
 `pMinor`  
 [out] 指向次版本号的指针。  
  
 `pBuild`  
 [out] 指向内部版本号的指针。  
  
 `pRevision`  
 [out] 指向修订号的指针。  
  
## <a name="remarks"></a>备注  
 有关程序集版本号的信息，请参阅 <xref:System.Version> 类主题。  
  
> [!NOTE]
> 此方法仅适用于 .NET Native。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICorDebugMergedAssemblyRecord 接口](icordebugmergedassemblyrecord-interface.md)
- [调试接口](debugging-interfaces.md)
