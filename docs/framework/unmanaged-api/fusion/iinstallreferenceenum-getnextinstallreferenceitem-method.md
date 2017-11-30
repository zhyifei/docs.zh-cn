---
title: "IInstallReferenceEnum::GetNextInstallReferenceItem 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IInstallReferenceEnum.GetNextInstallReferenceItem
api_location: fusion.dll
api_type: COM
f1_keywords: IInstallReferenceEnum::GetNextInstallReferenceItem
helpviewer_keywords:
- IInstallReferenceEnum::GetNextInstallReferenceItem method [.NET Framework fusion]
- GetNextInstallReferenceItem method [.NET Framework fusion]
ms.assetid: ce969c9d-6538-4c34-8784-148ffd99fe7a
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: db7e8bfaf396293f89f4b2e2bb20b5f6f532db19
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iinstallreferenceenumgetnextinstallreferenceitem-method"></a>IInstallReferenceEnum::GetNextInstallReferenceItem 方法
获取一个指针指向下一步[IInstallReferenceItem](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)包含在此对象[IInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md)对象。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetNextInstallReferenceItem (  
    [out] IInstallReferenceItem **ppRefItem,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppRefItem`  
 [out]返回`IInstallReferenceItem`指针。  
  
 `dwFlags`  
 [in]留待将来扩展。 `dwFlags`必须为 0 （零）。  
  
 `pvReserved`  
 [in]留待将来扩展。 `pvReserved`必须是 null 引用。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Fusion.h  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [IInstallReferenceItem 接口](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)  
 [IInstallReferenceEnum 接口](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md)
