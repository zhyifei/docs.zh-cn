---
title: ICorProfilerInfo8 接口
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 2baa33a7a3527392d8095b5d0ec7ad6af8a71a8e
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928939"
---
# <a name="icorprofilerinfo8-interface"></a>ICorProfilerInfo8 接口

[ICorProfilerInfo7](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)的子类，提供查询有关动态方法的信息的方法。

## <a name="methods"></a>方法  

| 方法|描述|  
| ------------|-----------------|  
|[IsFunctionDynamic 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-isfunctiondynamic-method.md)| 确定函数是否没有关联的元数据。|
|[GetFunctionFromIP3 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-getfunctionfromip3-method.md)| 将托管代码指令指针映射到 FunctionID。 此方法适用于动态和非动态方法。 |
|[GetDynamicFunctionInfo 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-getdynamicfunctioninfo-method.md)| 检索有关动态方法的信息。 |

## <a name="requirements"></a>要求  
**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
**标头：** Corprof.idl，Corprof.idl  
**.NET Framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  

## <a name="see-also"></a>请参阅

- [Profiling 接口](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
