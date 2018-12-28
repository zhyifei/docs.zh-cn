---
title: 在使用 "Object" 类型的自变量时，请使用 "FileGetObject"，而不要使用 "FileGet"
ms.date: 07/20/2015
ms.assetid: 090b8088-895a-482a-9362-606596bac304
ms.openlocfilehash: ddbe187ed1210d238448a5ff3feaee18beea1def
ms.sourcegitcommit: 0888d7b24f475c346a3f444de8d83ec1ca7cd234
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2018
ms.locfileid: "53768006"
---
# <a name="use-filegetobject-instead-of-fileget-when-using-argument-of-type-object"></a>在使用 "Object" 类型的自变量时，请使用 "FileGetObject"，而不要使用 "FileGet"
`FileGet` 方法包含 `Object` 类型的参数。 应使用`FileGetObject` 替代 `FileGet` ，以避免多义性。  
  
 请注意，与 `FileGet` 或 `FileGetObject` 相比，`My.Computer.Filesystem` 提供的功能更易于使用且性能更高。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  将 `FileGet` 替换为 `FileGetObject`。  
  
2.  将 `Object` 参数强制转换为一个更明确的类型。  
  
## <a name="see-also"></a>请参阅  
   
 [My.Computer.FileSystem](xref:Microsoft.VisualBasic.FileIO.FileSystem)
