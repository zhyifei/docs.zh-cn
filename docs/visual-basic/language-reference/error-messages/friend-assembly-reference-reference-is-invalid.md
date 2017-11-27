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
ms.openlocfilehash: 39ae94e309ee8d18e6b5317445b7e4b7f6a42af9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="friend-assembly-reference-ltreferencegt-is-invalid"></a>友元程序集引用&lt;引用&gt;无效
友元程序集引用\<引用 > 无效。 用强名称签名的程序集必须在他们的 InternalsVisibleTo 声明中指定一个公钥。  
  
 程序集名称传递给<xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>属性构造函数标识强名称的程序集，但它不包括`PublicKey`属性。  
  
 **错误 ID:** BC31535  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  确定具有强名称的友元程序集的公钥。 将公钥包含如程序集名称的一部分传递到<xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>属性构造函数通过使用`PublicKey`属性。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Reflection.AssemblyName>  
 [友元程序集](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055)  
 [如何：创建签名的友元程序集](http://msdn.microsoft.com/library/f5542300-58b4-4e1c-b809-8df11e95e69b)
