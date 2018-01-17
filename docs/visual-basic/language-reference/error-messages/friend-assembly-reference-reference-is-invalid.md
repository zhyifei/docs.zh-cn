---
title: "友元程序集引用&lt;引用&gt;无效"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords: BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ab1c7c5cc7a7f4ad899df7722769238e05d96e6b
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="friend-assembly-reference-ltreferencegt-is-invalid"></a>友元程序集引用&lt;引用&gt;无效
友元程序集引用\<引用 > 无效。 用强名称签名的程序集必须在他们的 InternalsVisibleTo 声明中指定一个公钥。  
  
 程序集名称传递给<xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>属性构造函数标识强名称的程序集，但它不包括`PublicKey`属性。  
  
 **错误 ID:** BC31535  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  确定具有强名称的友元程序集的公钥。 将公钥包含如程序集名称的一部分传递到<xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>属性构造函数通过使用`PublicKey`属性。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Reflection.AssemblyName>  
 [友元程序集](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md)  
 

