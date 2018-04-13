---
title: 如何：创建集合初始值设定项所使用的 Add 扩展方法 (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- collection initializers [Visual Basic]
ms.assetid: f64b52c7-8b11-4410-93a6-cb3aeebcc772
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d19ac8b03b992eb9b09b5cb45fdcceadad3a822a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-an-add-extension-method-used-by-a-collection-initializer-visual-basic"></a>如何：创建集合初始值设定项所使用的 Add 扩展方法 (Visual Basic)
当使用集合初始值设定项创建集合时，Visual Basic 编译器将搜索`Add`为其集合类型的方法的参数`Add`方法与集合初始值设定项中的值的类型匹配。 这`Add`方法用于填充具有集合初始值设定项中的值的集合。  
  
 如果没有任何匹配`Add`方法存在并且无法修改集合的代码，你可以添加扩展方法调用`Add`采用所需的集合初始值设定项的参数。 这通常是你需要对泛型集合使用集合初始值设定项时执行的操作。  
  
## <a name="example"></a>示例  
 下面的示例演示如何将扩展方法添加到泛型<xref:System.Collections.Generic.List%601>类型，以便可以使用集合初始值设定项来添加类型的对象`Employee`。 扩展方法，可使用缩短的集合初始值设定项语法。  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#1](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-an-add-extension-method-used-by-a-collection-initializer_1.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#2](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-an-add-extension-method-used-by-a-collection-initializer_2.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#3](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-an-add-extension-method-used-by-a-collection-initializer_3.vb)]  
  
## <a name="see-also"></a>另请参阅  
 [集合初始值设定项](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)  
 [如何：创建集合初始值设定项所使用的集合](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-a-collection-used-by-a-collection-initializer.md)
