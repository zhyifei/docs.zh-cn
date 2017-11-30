---
title: "CoUninitializeCor 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CoUninitializeCor
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: CoUninitializeCor
helpviewer_keywords: CoUninitializeCor function [.NET Framework hosting]
ms.assetid: 50a95b8b-9766-470e-bb29-2c7ecddfd4a1
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 57740ed8f20891b240bca5e9e19591484022b8ec
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="couninitializecor-function"></a>CoUninitializeCor 函数
`CoUninitializeCor` 已过时。  
  
## <a name="syntax"></a>语法  
  
```  
STDAPI_(void) CoUninitializeCor(void);  
```  
  
## <a name="remarks"></a>备注  
 公共语言运行时不能为从进程中卸载。 若要完全删除从正在运行的进程的运行时，必须关闭该进程。  
  
## <a name="see-also"></a>另请参阅  
 [元数据全局静态函数](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
