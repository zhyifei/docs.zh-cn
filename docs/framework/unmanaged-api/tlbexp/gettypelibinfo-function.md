---
title: "GetTypeLibInfo 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetTypeLibInfo
api_location: TlbRef.dll
api_type: DLLExport
f1_keywords: GetTypeLibInfo
helpviewer_keywords: GetTypeLibInfo function [.NET Framework]
ms.assetid: a1c4d165-9bdc-4ca8-940e-292d4ffcc338
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a5dc55a9538798b81dce9db02583c271b9f2ed54
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="gettypelibinfo-function"></a>GetTypeLibInfo 函数
返回有关指定的类型库的信息通过检查其[TLIBATTR](https://msdn.microsoft.com/library/ms221376\(v=vs.85\).aspx)结构。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetTypeLibInfo(  
    [in]   LPWSTR     szFile,  
    [out]  GUID      *pTypeLibID,  
    [out]  LCID      *pTypeLibLCID,  
    [out]  SYSKIND   *pTypeLibPlatform,  
    [out]  USHORT    *pTypeLibMajorVer,  
    [out]  USHORT    *pTypeLibMinorVer  
);  
```  
  
#### <a name="parameters"></a>参数  
 `szFile`  
 [in]类型库的文件名称。  
  
 `pTypeLibID`  
 [out]类型库的 GUID。  
  
 `pTypeLibLCID`  
 [out]类型库的本地化 ID。  
  
 `pTypeLibPlatform`  
 [out]A [SYSKIND](https://msdn.microsoft.com/library/ms221272\(v=vs.85\).aspx)标识目标操作系统为类型库的标志。 常见的值为 SYS_WIN32 和 SYS_WIN64。  
  
 `pTypeLibMajorVer`  
 [out]主版本号，类型库。 例如，对于版本*x.y*，主版本号是*x*。  
  
 `pTypeLibMinorVer`  
 [out]类型库次版本号。 例如，对于版本*x.y*，次版本号是*y*。  
  
## <a name="remarks"></a>备注  
 `GetTypeLibInfo`函数调用[Tlbexp.exe （类型库导出程序）](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md)。 此工具会生成类型库描述公共语言运行时 (CLR) 程序集中的类型。  
  
 如果任何参数为 null，则该函数将返回`HRESULT`的`E_POINTER`。 否则，它将返回 `S_OK`。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** TlbRef.h  
  
 **库：** TlbRef.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [Tlbexp Helper 函数](../../../../docs/framework/unmanaged-api/tlbexp/index.md)  
 [LoadTypeLibEx 函数](https://msdn.microsoft.com/library/ms221249\(v=vs.85\).aspx)
