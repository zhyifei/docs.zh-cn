---
title: 在使用 "Object" 类型的自变量时，请使用 "FilePutObject"，而不要使用 "FilePut"
ms.date: 07/20/2015
f1_keywords:
- vbrUseFilePutObject
ms.assetid: d207b9b7-5898-4c13-8b03-9feefac5f726
ms.openlocfilehash: df7d7c54992984bcb1684e41f60ae8361a3aed03
ms.sourcegitcommit: 0888d7b24f475c346a3f444de8d83ec1ca7cd234
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2018
ms.locfileid: "53774220"
---
# <a name="use-fileputobject-instead-of-fileput-when-using-argument-of-type-object"></a>在使用 "Object" 类型的自变量时，请使用 "FilePutObject"，而不要使用 "FilePut"
`FilePut` 方法包含 `Object`类型的参数。 应使用`FilePutObject` 替代 `FilePut` ，以避免多义性。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   将 `FilePut` 替换为 `FilePutObject`。  
  
-   将 `Object` 参数强制转换为一个更明确的类型。  
  
-   使用 `My.Computer.FileSystem` 对象中的可用功能。  
  
## <a name="see-also"></a>请参阅  
   
 [My.Computer.FileSystem](xref:Microsoft.VisualBasic.FileIO.FileSystem)  
 [My.Computer.FileSystem.WriteAllBytes](xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.WriteAllBytes%2A)
