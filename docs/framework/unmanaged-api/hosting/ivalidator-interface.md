---
title: IValidator 接口
ms.date: 03/30/2017
api_name:
- IValidator
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IValidator
helpviewer_keywords:
- IValidator interface [.NET Framework hosting]
ms.assetid: b297e3b0-20f9-478f-b707-5e2eecb2b5b2
topic_type:
- apiref
ms.openlocfilehash: d8e5ab607f9310341ded482b35f02f3845926328
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008555"
---
# <a name="ivalidator-interface"></a>IValidator 接口
提供用于验证可移植可执行（PE）映像和报告验证错误的方法。  
  
## <a name="methods"></a>方法  
  
|方法|说明|  
|------------|-----------------|  
|验证|验证指定的 PE 或 Microsoft 中间语言（MSIL）文件。|  
|FormatEventInfo|获取与指定的验证错误相对应的错误消息。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** IValidator，IValidator  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [承载接口](hosting-interfaces.md)
- [CorRuntimeHost 组件类](corruntimehost-coclass.md)
