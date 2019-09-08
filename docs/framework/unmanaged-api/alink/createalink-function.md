---
title: CreateALink 函数
ms.date: 03/30/2017
api_name:
- CreateALink
api_location:
- alink.dll
api_type:
- DLLExport
f1_keywords:
- CreateALink
helpviewer_keywords:
- CreateALink function
- Alink API, CreateALink function
ms.assetid: fc73bcb9-6af6-44d8-bc39-2f4400325dae
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 24f7e2d5a547b78ceb4808feaf581c6f49807cf7
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787627"
---
# <a name="createalink-function"></a>CreateALink 函数
创建程序集链接器的实例，并设置指向指定接口的指针。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT CreateALink (  
   REFIID riid,  
   IUnknown **ppInterface  
);  
```  
  
## <a name="parameters"></a>参数  
  
|参数|描述|  
|---------------|-----------------|  
|`riid`|某个程序集链接器接口的物理名称。|  
|`ppInterface`|成功完成后的位置包含指向`riid`接口的指针。|  
  
## <a name="requirements"></a>要求  
 **库**： alink  
  
## <a name="see-also"></a>请参阅

- [Al.exe（程序集链接器）](../../tools/al-exe-assembly-linker.md)
