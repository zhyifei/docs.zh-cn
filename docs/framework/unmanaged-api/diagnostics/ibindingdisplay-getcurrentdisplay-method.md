---
title: "IBindingDisplay::GetCurrentDisplay 方法"
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
- IBindingDisplay.GetCurrentDisplay
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- IBindingDisplay::GetCurrentDisplay
helpviewer_keywords:
- IBindingDisplay::GetCurrentDisplay method [.NET Framework debugging]
- GetCurrentDisplay method [.NET Framework debugging]
ms.assetid: d28eeea4-c4e0-40d4-91de-198d98cfa13c
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: cce7638bfe6ffe0d4b5f7f9a64aaff0c59c860cb
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="ibindingdisplaygetcurrentdisplay-method"></a>IBindingDisplay::GetCurrentDisplay 方法
返回当前绑定的显示信息。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetCurrentDisplay (  
    [out, retval] SAFEARRAY(struct BindingDisplayTabControl) *display  
);  
```  
  
#### <a name="parameters"></a>参数  
 `display`  
 [out，retval]指向 safearray 包含绑定显示信息的指针。  
  
## <a name="remarks"></a>备注  
 [Ibindingdisplay:: Initializeforprocess](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md)方法必须具有以前成功，并且必须由调试器停止程序。  
  
 调用方必须释放返回`SAFEARRAY`使用的内存[SafeArrayDestroy](http://msdn.microsoft.com/library/fc94f7e7-b903-4c78-905c-54df1f8d13fa)。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** BindingDisplay.h  
  
 **库：** BindingDisplay.idl  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [IBindingDisplay 接口](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)  
 [InitializeForProcess 方法](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md)
