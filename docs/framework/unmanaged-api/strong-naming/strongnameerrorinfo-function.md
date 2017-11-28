---
title: "StrongNameErrorInfo 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameErrorInfo
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: StrongNameErrorInfo
helpviewer_keywords: StrongNameErrorInfo function [.NET Framework strong naming]
ms.assetid: e91bf8c3-7c26-4732-938e-2e5b04abfc99
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0fbe77f16ed022458a036b6627b82f80d194276c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="strongnameerrorinfo-function"></a>StrongNameErrorInfo 函数
获取引发的强名称函数之一的最后一个错误代码。  
  
 此函数已弃用。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT StrongNameErrorInfo ();   
```  
  
## <a name="return-value"></a>返回值  
 设置由某一个强名称函数的最后一个 COM 错误代码。  
  
## <a name="remarks"></a>备注  
 大多数的强名称方法返回一个简单`true`或`false`成功完成的指示。 使用`StrongNameErrorInfo`函数可检索指定生成的强名称函数的最后一个错误的 HRESULT。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** StrongName.h  
  
 **库：**作为 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [强命名的全局静态函数](http://msdn.microsoft.com/en-us/efa715df-e8cc-48f2-9ec4-26586f0dc8d0)
