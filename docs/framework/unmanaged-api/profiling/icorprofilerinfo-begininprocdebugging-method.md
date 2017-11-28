---
title: "ICorProfilerInfo::BeginInprocDebugging 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.BeginInprocDebugging
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::BeginInprocDebugging
helpviewer_keywords:
- BeginInprocDebugging method [.NET Framework profiling]
- ICorProfilerInfo::BeginInprocDebugging method [.NET Framework profiling]
ms.assetid: c5c82c69-99f8-4447-aee0-42cca0a5eb5c
topic_type: apiref
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8c7c0b3c0a20c98b9ca2e5dd5ea51053008e415a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfobegininprocdebugging-method"></a>ICorProfilerInfo::BeginInprocDebugging 方法
初始化进程内调试支持。 此方法是.NET Framework 2.0 版中过时。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT BeginInprocDebugging(  
    [in]  BOOL   fThisThreadOnly,  
    [out] DWORD *pdwProfilerContext);  
```  
  
#### <a name="parameters"></a>参数  
 `fThisThreadOnly`  
 [in]将此值设置为`true`初始化调试支持仅当前线程; 将其设置为`false`初始化的所有线程的调试支持。  
  
 `pdwProfilerContext`  
 [out]指向标识调试会话的返回值的指针。  
  
## <a name="remarks"></a>备注  
 CLR 调试服务支持在.NET framework 1.0 和 1.1 版中的有限进程内调试。 探查器使用了调试 API 的检查部分启用进程内调试。 但是，由于客户反馈，进程内调试已从.NET Framework 2.0 版中，在中删除和替换为一组是根据分析 API 的详细信息的功能。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** 1.0  
  
## <a name="see-also"></a>另请参阅  
 [ICorProfilerInfo 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
