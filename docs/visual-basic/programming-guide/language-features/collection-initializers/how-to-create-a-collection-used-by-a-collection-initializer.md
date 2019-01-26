---
title: 如何：创建集合使用集合初始值设定项 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- collection initializers [Visual Basic]
ms.assetid: c858db10-424d-47e0-92cd-e08087cc5ebc
ms.openlocfilehash: aaa367e5a1739f26e9b0458d8f2fc44462b73b7b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54631719"
---
# <a name="how-to-create-a-collection-used-by-a-collection-initializer-visual-basic"></a>如何：创建集合使用集合初始值设定项 (Visual Basic)
当使用集合初始值设定项创建集合时，Visual Basic 编译器中搜索`Add`为其集合类型的方法的参数`Add`方法与集合初始值设定项中的值的类型匹配。 这`Add`方法用于填充集合初始值设定项中的值的集合。  
  
## <a name="example"></a>示例  
 下面的示例演示`OrderCollection`集合，其中包含一个公共`Add`方法，可以使用集合初始值设定项类型的对象添加`Order`。 `Add`方法，可使用缩短了的集合初始值设定项语法。  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#4](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-used-by-a-collection-initializer_1.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#1](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-used-by-a-collection-initializer_2.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#2](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-used-by-a-collection-initializer_3.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#3](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-used-by-a-collection-initializer_4.vb)]  
  
## <a name="see-also"></a>请参阅
- [集合初始值设定项](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)
- [如何：创建 Add 扩展方法使用集合初始值设定项](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-an-add-extension-method-used-by-a-collection-initializer.md)
