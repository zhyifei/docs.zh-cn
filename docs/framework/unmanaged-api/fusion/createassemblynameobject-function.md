---
title: "CreateAssemblyNameObject 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CreateAssemblyNameObject
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type: DLLExport
f1_keywords: CreateAssemblyNameObject
helpviewer_keywords: CreateAssemblyNameObject function [.NET Framework fusion]
ms.assetid: 55c8b41e-fbe4-4ae0-aa29-68fbb2311691
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2d2616bd7aee878ebbc1d196cb1ac5f90ae7bd04
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="createassemblynameobject-function"></a>CreateAssemblyNameObject 函数
获取到的接口指针[IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)表示具有指定名称的程序集的唯一标识的实例。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT CreateAssemblyNameObject (  
    [out] LPASSEMBLYNAME  *ppAssemblyNameObj,  
    [in]  LPCWSTR         szAssemblyName,  
    [in]  DWORD           dwFlags,  
    [in]  LPVOID          pvReserved  
 );  
```  
  
#### <a name="parameters"></a>参数  
 `ppAssemblyNameObj`  
 [out]返回`IAssemblyName`。  
  
 `szAssemblyName`  
 [in]要为其创建新程序集的名称`IAssemblyName`实例。  
  
 `dwFlags`  
 [in]要传递给对象构造函数的标志。  
  
 `pvReserved`  
 [in]留待将来扩展。 `pvReserved`必须是 null 引用。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Fusion.h  
  
 **库：**作为 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [IAssemblyName 接口](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)  
 [合成全局静态函数](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
