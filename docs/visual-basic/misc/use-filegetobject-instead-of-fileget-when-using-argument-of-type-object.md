---
title: 在使用 "Object" 类型的参数时，请使用 "FileGetObject"，而不要使用 "FileGet"
ms.date: 07/20/2015
ms.assetid: 090b8088-895a-482a-9362-606596bac304
ms.openlocfilehash: fdad64a4b35aa792c996d25a9fd72a9ce1126fbd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59306919"
---
# <a name="use-filegetobject-instead-of-fileget-when-using-argument-of-type-object"></a>在使用 "Object" 类型的参数时，请使用 "FileGetObject"，而不要使用 "FileGet"
`FileGet` 方法包含 `Object`类型的参数。 应使用`FileGetObject` 替代 `FileGet` ，以避免多义性。  
  
 请注意，与 `FileGet` 或 `FileGetObject` 相比，`My.Computer.Filesystem` 提供的功能更易于使用且性能更高。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1. 将 `FileGet` 替换为 `FileGetObject`。  
  
2. 将 `Object` 参数强制转换为一个更明确的类型。  
  
## <a name="see-also"></a>请参阅

- [My.Computer.FileSystem](xref:Microsoft.VisualBasic.FileIO.FileSystem)
