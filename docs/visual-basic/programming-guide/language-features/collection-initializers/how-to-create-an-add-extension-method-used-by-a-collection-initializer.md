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
# <a name="how-to-create-an-add-extension-method-used-by-a-collection-initializer-visual-basic"></a><span data-ttu-id="2ae86-102">如何：创建集合初始值设定项所使用的 Add 扩展方法 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2ae86-102">How to: Create an Add Extension Method Used by a Collection Initializer (Visual Basic)</span></span>
<span data-ttu-id="2ae86-103">当使用集合初始值设定项创建集合时，Visual Basic 编译器将搜索`Add`为其集合类型的方法的参数`Add`方法与集合初始值设定项中的值的类型匹配。</span><span class="sxs-lookup"><span data-stu-id="2ae86-103">When you use a collection initializer to create a collection, the Visual Basic compiler searches for an `Add` method of the collection type for which the parameters for the `Add` method match the types of the values in the collection initializer.</span></span> <span data-ttu-id="2ae86-104">这`Add`方法用于填充具有集合初始值设定项中的值的集合。</span><span class="sxs-lookup"><span data-stu-id="2ae86-104">This `Add` method is used to populate the collection with the values from the collection initializer.</span></span>  
  
 <span data-ttu-id="2ae86-105">如果没有任何匹配`Add`方法存在并且无法修改集合的代码，你可以添加扩展方法调用`Add`采用所需的集合初始值设定项的参数。</span><span class="sxs-lookup"><span data-stu-id="2ae86-105">If no matching `Add` method exists and you cannot modify the code for the collection, you can add an extension method called `Add` that takes the parameters that are required by the collection initializer.</span></span> <span data-ttu-id="2ae86-106">这通常是你需要对泛型集合使用集合初始值设定项时执行的操作。</span><span class="sxs-lookup"><span data-stu-id="2ae86-106">This is typically what you need to do when you use collection initializers for generic collections.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2ae86-107">示例</span><span class="sxs-lookup"><span data-stu-id="2ae86-107">Example</span></span>  
 <span data-ttu-id="2ae86-108">下面的示例演示如何将扩展方法添加到泛型<xref:System.Collections.Generic.List%601>类型，以便可以使用集合初始值设定项来添加类型的对象`Employee`。</span><span class="sxs-lookup"><span data-stu-id="2ae86-108">The following example shows how to add an extension method to the generic <xref:System.Collections.Generic.List%601> type so that a collection initializer can be used to add objects of type `Employee`.</span></span> <span data-ttu-id="2ae86-109">扩展方法，可使用缩短的集合初始值设定项语法。</span><span class="sxs-lookup"><span data-stu-id="2ae86-109">The extension method enables you to use the shortened collection initializer syntax.</span></span>  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#1](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-an-add-extension-method-used-by-a-collection-initializer_1.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#2](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-an-add-extension-method-used-by-a-collection-initializer_2.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#3](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-an-add-extension-method-used-by-a-collection-initializer_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="2ae86-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2ae86-110">See Also</span></span>  
 [<span data-ttu-id="2ae86-111">集合初始值设定项</span><span class="sxs-lookup"><span data-stu-id="2ae86-111">Collection Initializers</span></span>](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)  
 [<span data-ttu-id="2ae86-112">如何：创建集合初始值设定项所使用的集合</span><span class="sxs-lookup"><span data-stu-id="2ae86-112">How to: Create a Collection Used by a Collection Initializer</span></span>](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-a-collection-used-by-a-collection-initializer.md)
