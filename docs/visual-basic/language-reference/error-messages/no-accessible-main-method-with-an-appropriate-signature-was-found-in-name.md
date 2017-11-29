---
title: "没有可访问 &#39;Main &#39;在已找到具有正确签名方法 &#39;&lt;名称&gt;&#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30737
- vbc30737
helpviewer_keywords: BC30737
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3f45dc17304c3c9d62b65760f2c1b5d461812a66
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="no-accessible-39main39-method-with-an-appropriate-signature-was-found-in-39ltnamegt39"></a>没有可访问 &#39;Main &#39;在已找到具有正确签名方法 &#39;&lt;名称&gt;&#39;
命令行应用程序必须具有`Sub Main`定义。 `Main`必须声明为`Public Shared`如果它定义在类中，或作为`Public`如果的模块中定义。  
  
 有关详细信息`Main`，请参阅[NIB: Visual Basic 版本的 Hello，World](http://msdn.microsoft.com/en-us/9d030b60-e148-4366-a462-69532f02294c)。  
  
 **错误 ID:** BC30737  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   定义`Public Sub Main`为你的项目的过程。 将其声明为`Shared`当且仅当定义的类中。  
  
## <a name="see-also"></a>另请参阅  
 [Hello，World NIB: Visual Basic 版本](http://msdn.microsoft.com/en-us/9d030b60-e148-4366-a462-69532f02294c)  
 [Visual Basic 程序的结构](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)  
 [过程](../../../visual-basic/programming-guide/language-features/procedures/index.md)
