---
title: 'ICorProfilerInfo7:: GetInMemorySymbolsLength 方法'
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo7.GetInMemorySymbolsLength
api_location:
- mscorwks.dll
- icorprof.idl
api_type:
- COM
ms.assetid: d62c4a4c-8a62-45aa-8f01-a8387cf36159
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 157b0e215f8afa58cccb3d54a65baa9c307ba966
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69955424"
---
# <a name="icorprofilerinfo7getinmemorysymbolslength-method"></a>ICorProfilerInfo7:: GetInMemorySymbolsLength 方法
[仅在 .NET Framework 4.6.1 及更高版本中受支持]  
  
 返回内存中符号流的长度。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetInMemorySymbolsLength(  
        [in] ModuleID moduleId,  
        [out] DWORD* pCountSymbolBytes  
);  
```  
  
## <a name="parameters"></a>参数  
 `moduleId`  
 中包含内存中流的模块的标识符。  
  
 pCountSymbolBytes  
 弄一个指向`DWORD`值的指针, 当该方法返回时, 将包含流的长度 (以字节为单位)。  
  
## <a name="return-value"></a>返回值  
 如果可以确定`S_OK`内存流的长度 (即使它为零 (0)), 则方法将返回。  
  
 如果该方法`CORPROF_E_MODULE_IS_DYNAMIC`是使用<xref:System.Reflection.Emit?displayProperty=nameWithType>创建的, 则该方法返回。  
  
## <a name="remarks"></a>备注  
 如果模块有内存中符号, 则流的长度将被置于中`pCountSymbolBytes`。 如果模块没有内存中符号, `*pCountSymbolBytes = 0`则为。  
  
> [!NOTE]
> 当前实现不支持反射。发出。 如果该模块是使用反射创建的, 则该方法返回`CORPROF_E_MODULE_IS_DYNAMIC`。  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Corprof.idl, Corprof.idl  
  
 **类库**CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICorProfilerInfo7 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
