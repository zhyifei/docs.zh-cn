---
title: ICorProfilerInfo3::GetRuntimeInformation 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetRuntimeInformation Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetRuntimeInformation
helpviewer_keywords:
- GetRuntimeInformation method [.NET Framework profiling]
- ICorProfilerInfo3::GetRuntimeInformation method [.NET Framework profiling]
ms.assetid: 4400fb8c-0407-4791-8557-f011fd2aee51
topic_type:
- apiref
ms.openlocfilehash: 20556d85655a0a1bbe069a94b99c19c774a13ce6
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449683"
---
# <a name="icorprofilerinfo3getruntimeinformation-method"></a>ICorProfilerInfo3::GetRuntimeInformation 方法
提供有关正在分析的公共语言运行时（CLR）的版本信息。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetRuntimeInformation(  
       [out] USHORT *pClrInstanceId,  
       [out] COR_PRF_RUNTIME_TYPE *pRuntimeType,  
       [out] USHORT *pMajorVersion,  
       [out] USHORT *pMinorVersion,  
       [out] USHORT *pBuildNumber,  
       [out] USHORT *pQFEVersion,  
       [in]  ULONG  cchVersionString,  
       [out] ULONG  *pcchVersionString,  
       [out, size_is(cchVersionString), length_is(*pcchVersionString)]  
                   WCHAR  szVersionString[]);  
```  
  
## <a name="parameters"></a>参数  
 `pClrInstanceId`  
 弄进程中正在运行的 CLR 实例的代表 ID。 这与 Windows 事件跟踪（ETW）启动事件报告的 `ClrInstanceID` 相同。  
  
 `pRuntimeType`  
 弄运行时类型。 此参数为 CLR 的桌面版本或在 Silverlight 中使用的 CLR 核心版本 `COR_PRF_CORE_CLR` 返回 `COR_PRF_DESKTOP_CLR`。  
  
 `pMajorVersion`  
 弄CLR 的主版本号。  
  
 `pMinorVersion`  
 弄CLR 的次版本号。  
  
 `pBuildVersion`  
 弄CLR 的内部版本号。  
  
 `pQFEVersion`  
 弄与软件更新关联的 CLR 的版本号。  
  
 `cchVersionString`  
 中`szVersionString` 指向的缓冲区的长度（以字符为单位）。  
  
 `pcchVersionString`  
 弄`szVersionString`的长度（以字符为字符）。  
  
 `szVersionString`  
 弄CLR 版本字符串。  
  
## <a name="remarks"></a>备注  
 可以为任何参数传递 null。 但 `pcchVersionString` 不能为 null，除非 `szVersionString` 也为 null。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorProfilerInfo3 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [Profiling 接口](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [分析](../../../../docs/framework/unmanaged-api/profiling/index.md)
