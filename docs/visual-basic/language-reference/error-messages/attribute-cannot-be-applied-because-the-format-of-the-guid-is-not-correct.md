---
title: '&#39;&lt;属性&gt;&#39; 无法应用，因为 GUID &#39; 的格式&lt;数&gt;&#39; 不正确'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc32500
- bc32500
helpviewer_keywords:
- BC32500
ms.assetid: 6fa34c55-368e-4d7d-b488-07a3fffe045f
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8ead07d12064dbe18a1e23d4d1343b1efba1b533
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="39ltattributegt39-cannot-be-applied-because-the-format-of-the-guid-39ltnumbergt39-is-not-correct"></a>&#39;&lt;属性&gt;&#39; 无法应用，因为 GUID &#39; 的格式&lt;数&gt;&#39; 不正确
A`COMClassAttribute`特性块指定为 GUID 不到正确的格式不符合的全局唯一标识符 (GUID)。 `COMClassAttribute`使用 Guid 来唯一地标识类、 接口和创建事件。  
  
 一个 GUID 由 16 个字节组成，其中前八个是数值，而后八个为二进制形式。 它由 Microsoft 的实用工具，例如 uuidgen.exe 生成，并保证在空间和时间是唯一的。  
  
 **错误 ID:** BC32500  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  确定正确的 GUID 或标识的 COM 对象所需的 Guid。  
  
2.  确保正确复制提供给 `COMClassAttribute` 特性块的 GUID 字符串。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Guid>  
[属性概述](../../../visual-basic/programming-guide/concepts/attributes/index.md)

