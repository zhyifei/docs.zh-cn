---
title: 如何：创建集合初始值设定项所使用的集合 (Visual Basic)
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
ms.assetid: c858db10-424d-47e0-92cd-e08087cc5ebc
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cff862f16530bc268628d9406ae81d23f2761926
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-collection-used-by-a-collection-initializer-visual-basic"></a><span data-ttu-id="7e8d6-102">如何：创建集合初始值设定项所使用的集合 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7e8d6-102">How to: Create a Collection Used by a Collection Initializer (Visual Basic)</span></span>
<span data-ttu-id="7e8d6-103">当使用集合初始值设定项创建集合时，Visual Basic 编译器将搜索`Add`为其集合类型的方法的参数`Add`方法与集合初始值设定项中的值的类型匹配。</span><span class="sxs-lookup"><span data-stu-id="7e8d6-103">When you use a collection initializer to create a collection, the Visual Basic compiler searches for an `Add` method of the collection type for which the parameters for the `Add` method match the types of the values in the collection initializer.</span></span> <span data-ttu-id="7e8d6-104">这`Add`方法用于填充具有集合初始值设定项中的值的集合。</span><span class="sxs-lookup"><span data-stu-id="7e8d6-104">This `Add` method is used to populate the collection with the values from the collection initializer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7e8d6-105">示例</span><span class="sxs-lookup"><span data-stu-id="7e8d6-105">Example</span></span>  
 <span data-ttu-id="7e8d6-106">下面的示例演示`OrderCollection`集合，其中包含一个公共`Add`集合初始值设定项可用于添加类型的对象的方法`Order`。</span><span class="sxs-lookup"><span data-stu-id="7e8d6-106">The following example shows an `OrderCollection` collection that contains a public `Add` method that a collection initializer can use to add objects of type `Order`.</span></span> <span data-ttu-id="7e8d6-107">`Add`方法使您能够使用缩短的集合初始值设定项语法。</span><span class="sxs-lookup"><span data-stu-id="7e8d6-107">The `Add` method enables you to use the shortened collection initializer syntax.</span></span>  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#4](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-used-by-a-collection-initializer_1.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#1](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-used-by-a-collection-initializer_2.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#2](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-used-by-a-collection-initializer_3.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#3](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-used-by-a-collection-initializer_4.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="7e8d6-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7e8d6-108">See Also</span></span>  
 [<span data-ttu-id="7e8d6-109">集合初始值设定项</span><span class="sxs-lookup"><span data-stu-id="7e8d6-109">Collection Initializers</span></span>](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)  
 [<span data-ttu-id="7e8d6-110">如何：创建集合初始值设定项所使用的 Add 扩展方法</span><span class="sxs-lookup"><span data-stu-id="7e8d6-110">How to: Create an Add Extension Method Used by a Collection Initializer</span></span>](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-an-add-extension-method-used-by-a-collection-initializer.md)
