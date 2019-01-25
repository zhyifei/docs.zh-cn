---
title: ICorDebugSymbolProvider::GetMergedAssemblyRecords 方法
ms.date: 03/30/2017
ms.assetid: cc4c510d-550d-4941-af34-81987caf3425
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b9b85baf5249c1423d01cbf4d6a9e4bf2f6aadf8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54586483"
---
# <a name="icordebugsymbolprovidergetmergedassemblyrecords-method"></a>ICorDebugSymbolProvider::GetMergedAssemblyRecords 方法
获取所有合并程序集的符号记录。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetMergedAssemblyRecords(  
   [in] ULONG32 cRequestedRecords,  
   [out] ULONG32 *pcFetchedRecords,  
   [out, size_is(cRequestedRecords), length_is(*pcFetchedRecords)] ICorDebugMergedAssemblyRecord *pRecords[]  
);  
```  
  
#### <a name="parameters"></a>参数  
 `cRequestedRecords`  
 [in] 请求的符号记录数。  
  
 `pcFetchedRecords`  
 [out] 指向由方法检索的符号记录数的指针。  
  
 `pRecords`  
 指向数组的指针[ICorDebugMergedAssemblyRecord](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)对象。  
  
## <a name="remarks"></a>备注  
  
> [!NOTE]
>  此方法仅适用于 .NET Native。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>请参阅
- [ICorDebugSymbolProvider 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
