---
title: GetALinkMessageDll 函数
ms.date: 03/30/2017
api_name:
- GetALinkMessageDll
api_location:
- alink.dll
api_type:
- DLLExport
f1_keywords:
- GetALinkMessageDll
helpviewer_keywords:
- Alink API, GetALinkMessageDll function
- GetALinkMessageDll function
ms.assetid: 67985a22-88a2-4c54-8d99-4bcde9d6213e
topic_type:
- apiref
ms.openlocfilehash: 63719d0c6e13768e9dc7ed80e52e2a293e32a8a1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449344"
---
# <a name="getalinkmessagedll-function"></a>GetALinkMessageDll 函数
查找并加载消息 DLL。 如果找不到或无法加载消息 DLL，则返回0。 消息 DLL 应位于其名称为语言 ID 的子目录中，或位于当前目录中。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HINSTANCE WINAPI GetALinkMessageDll();  
```  
  
## <a name="requirements"></a>要求  
 **标头：** alink。h  
  
 **库**： alink  
  
## <a name="see-also"></a>另请参阅

- [Al.exe（程序集链接器）](../../tools/al-exe-assembly-linker.md)
