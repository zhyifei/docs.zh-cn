---
title: 如何：创建集合初始值设定项所使用的 Add 扩展方法
ms.date: 07/20/2015
helpviewer_keywords:
- collection initializers [Visual Basic]
ms.assetid: f64b52c7-8b11-4410-93a6-cb3aeebcc772
ms.openlocfilehash: 6d5f9d38b413b79f111a14ec3829c57a9797ce54
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346714"
---
# <a name="how-to-create-an-add-extension-method-used-by-a-collection-initializer-visual-basic"></a>如何：创建集合初始值设定项所使用的 Add 扩展方法 (Visual Basic)
使用集合初始值设定项创建集合时，Visual Basic 编译器会搜索 `Add` 方法的参数与集合初始值设定项中的值的类型相匹配的集合类型的 `Add` 方法。 此 `Add` 方法用于在集合中填充集合初始值设定项中的值。  
  
 如果不存在匹配的 `Add` 方法并且无法修改集合的代码，则可以添加一个名为 `Add` 的扩展方法，该方法采用集合初始值设定项所需的参数。 这通常是使用泛型集合的集合初始值设定项时需要执行的操作。  
  
## <a name="example"></a>示例  
 下面的示例演示如何将扩展方法添加到泛型 <xref:System.Collections.Generic.List%601> 类型，以便可以使用集合初始值设定项添加 `Employee`类型的对象。 通过扩展方法，可以使用简化的集合初始值设定项语法。  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#2)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#3)]  
  
## <a name="see-also"></a>另请参阅

- [集合初始值设定项](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)
- [如何：创建集合初始值设定项所使用的集合](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-a-collection-used-by-a-collection-initializer.md)
