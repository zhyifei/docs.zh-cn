---
title: GUID“<attribute>”的格式不正确，因此无法应用“<number>”
ms.date: 07/20/2015
f1_keywords:
- vbc32500
- bc32500
helpviewer_keywords:
- BC32500
ms.assetid: 6fa34c55-368e-4d7d-b488-07a3fffe045f
ms.openlocfilehash: f7b6e42480075666ce9f7e8fc6966bd4bb6b888a
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2019
ms.locfileid: "73977318"
---
# <a name="attribute-cannot-be-applied-because-the-format-of-the-guid-number-is-not-correct"></a>由于 GUID "\<数字 >" 的格式不正确，因此无法应用 "\<特性 >"

`COMClassAttribute` 特性块指定全局唯一标识符（GUID），它不符合 GUID 的正确格式。 `COMClassAttribute` 使用 Guid 来唯一标识类、接口和创建事件。  
  
 一个 GUID 由 16 个字节组成，其中前八个是数值，而后八个为二进制形式。 它由 Microsoft 实用程序（如 uuidgen.exe）生成，并且保证在空间和时间中是唯一的。  
  
 **错误 ID：** BC32500  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1. 确定标识 COM 对象所需的正确 GUID 或 Guid。  
  
2. 确保正确复制提供给 `COMClassAttribute` 特性块的 GUID 字符串。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Guid>
- [属性概述](../../../visual-basic/programming-guide/concepts/attributes/index.md)
