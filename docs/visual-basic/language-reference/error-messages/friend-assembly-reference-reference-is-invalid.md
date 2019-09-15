---
title: 友元程序集引用 <reference> 无效
ms.date: 07/20/2015
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords:
- BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
ms.openlocfilehash: 6eb46c6479adc69eaf65b34c69aa69977b4d62ef
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2019
ms.locfileid: "70972390"
---
# <a name="friend-assembly-reference-reference-is-invalid"></a>友元程序\<集引用引用 > 无效
友元程序\<集引用引用 > 无效。 用强名称签名的程序集必须在他们的 InternalsVisibleTo 声明中指定一个公钥。  
  
 传递给<xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>特性构造函数的程序集名称标识强名称程序集，但不`PublicKey`包括特性。  
  
 **错误 ID：** BC31535  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1. 确定强名称友元程序集的公钥。 使用属性将公钥包含为传递给<xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>特性构造函数的程序集名称的一部分。 `PublicKey`  
  
## <a name="see-also"></a>请参阅

- <xref:System.Reflection.AssemblyName>
- [友元程序集](../../../standard/assembly/friend.md)
