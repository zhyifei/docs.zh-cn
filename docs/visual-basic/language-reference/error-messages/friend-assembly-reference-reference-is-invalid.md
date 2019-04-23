---
title: 友元程序集引用 <reference> 无效
ms.date: 07/20/2015
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords:
- BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
ms.openlocfilehash: 0c1526e32ddc64cb4124c6f8205d58deef911dd6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59298989"
---
# <a name="friend-assembly-reference-reference-is-invalid"></a>友元程序集引用\<引用 > 无效
友元程序集引用\<引用 > 无效。 用强名称签名的程序集必须在他们的 InternalsVisibleTo 声明中指定一个公钥。  
  
 程序集名称传递给<xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>属性构造函数将识别的强名称的程序集，但它不包括`PublicKey`属性。  
  
 **错误 ID:** BC31535  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1. 确定强名称的友元程序集的公钥。 将公钥包含为程序集名称的一部分传递给<xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>特性构造函数通过使用`PublicKey`属性。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Reflection.AssemblyName>
- [友元程序集](../../../standard/assembly/friend-assemblies.md)
