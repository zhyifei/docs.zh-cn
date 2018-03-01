---
title: "CreateInstallReferenceEnum 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- CreateInstallReferenceEnum
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateInstallReference
helpviewer_keywords:
- CreateInstallReference function [.NET Framework fusion]
ms.assetid: 80dbbbf8-54fc-4894-b74a-0179d3201083
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a0c902cf5d9d8b6295cab95552aae6775c5bf889
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="createinstallreferenceenum-function"></a>CreateInstallReferenceEnum 函数
获取一个指向[IInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md)表示的指定程序集的应用程序的引用列表的实例。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT CreateInstallReferenceEnum (  
    [out] IInstallReferenceEnum **ppRefEnum,  
    [in]  IAssemblyName         *pName,  
    [in]  DWORD                 dwFlags,  
    [in]  LPVOID                pvReserved  
 );  
```  
  
#### <a name="parameters"></a>参数  
 `ppRefEnum`  
 [out]返回`IInstallReferenceEnum`指针。  
  
 `pName`  
 [in][IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) ，它标识要枚举引用的程序集。  
  
 `dwFlags`  
 [in]影响枚举器的行为的标志。  
  
 `pvReserved`  
 [in]留待将来扩展。 `pvReserved`必须是 null 引用。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Fusion.h  
  
 **库：**为 Fusion.dll 和 Mscorwks.dll。 使用而不是 Mscorwks.dll 为 Fusion.dll 来确保面向.NET Framework 的正确版本。  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [IInstallReferenceEnum 接口](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md)  
 [IAssemblyName 接口](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)  
 [合成全局静态函数](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
