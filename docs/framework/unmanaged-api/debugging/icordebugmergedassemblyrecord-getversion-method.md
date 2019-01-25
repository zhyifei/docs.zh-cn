---
title: ICorDebugMergedAssemblyRecord::GetVersion 方法
ms.date: 03/30/2017
ms.assetid: c6858b06-ae26-4312-b325-ea6025016675
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4895610ba3a8e8e8eb1a1c360ecb2b707f9cee4d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54622086"
---
# <a name="icordebugmergedassemblyrecordgetversion-method"></a>ICorDebugMergedAssemblyRecord::GetVersion 方法
获取程序集的版本信息。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetVersion(  
   [out] USHORT *pMajor,   
   [out] USHORT *pMinor,   
   [out] USHORT *pBuild,   
   [out] USHORT *pRevision  
);  
```  
  
#### <a name="parameters"></a>参数  
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
>  此方法仅适用于 .NET Native。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>请参阅
- [ICorDebugMergedAssemblyRecord 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
