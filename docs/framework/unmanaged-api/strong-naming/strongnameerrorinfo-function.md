---
title: StrongNameErrorInfo 函数
ms.date: 03/30/2017
api_name:
- StrongNameErrorInfo
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameErrorInfo
helpviewer_keywords:
- StrongNameErrorInfo function [.NET Framework strong naming]
ms.assetid: e91bf8c3-7c26-4732-938e-2e5b04abfc99
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: db818f638898da6379ce4dadfada8eccc3adeb12
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455414"
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
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** StrongName.h  
  
 **库：** 作为 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [强命名的全局静态函数](http://msdn.microsoft.com/library/efa715df-e8cc-48f2-9ec4-26586f0dc8d0)
