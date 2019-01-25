---
title: 如何：创建 Add 扩展方法使用集合初始值设定项 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- collection initializers [Visual Basic]
ms.assetid: f64b52c7-8b11-4410-93a6-cb3aeebcc772
ms.openlocfilehash: 3a1db8ede8162b329d546c0e712ef1c2df7d7883
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54661667"
---
# <a name="how-to-create-an-add-extension-method-used-by-a-collection-initializer-visual-basic"></a><span data-ttu-id="2aa55-102">如何：创建 Add 扩展方法使用集合初始值设定项 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2aa55-102">How to: Create an Add Extension Method Used by a Collection Initializer (Visual Basic)</span></span>
<span data-ttu-id="2aa55-103">当使用集合初始值设定项创建集合时，Visual Basic 编译器中搜索`Add`为其集合类型的方法的参数`Add`方法与集合初始值设定项中的值的类型匹配。</span><span class="sxs-lookup"><span data-stu-id="2aa55-103">When you use a collection initializer to create a collection, the Visual Basic compiler searches for an `Add` method of the collection type for which the parameters for the `Add` method match the types of the values in the collection initializer.</span></span> <span data-ttu-id="2aa55-104">这`Add`方法用于填充集合初始值设定项中的值的集合。</span><span class="sxs-lookup"><span data-stu-id="2aa55-104">This `Add` method is used to populate the collection with the values from the collection initializer.</span></span>  
  
 <span data-ttu-id="2aa55-105">如果没有匹配`Add`存在方法并不能修改集合的代码，你可以添加扩展方法调用`Add`采用所需的集合初始值设定项的参数。</span><span class="sxs-lookup"><span data-stu-id="2aa55-105">If no matching `Add` method exists and you cannot modify the code for the collection, you can add an extension method called `Add` that takes the parameters that are required by the collection initializer.</span></span> <span data-ttu-id="2aa55-106">这通常是需要对泛型集合使用集合初始值设定项时执行的操作。</span><span class="sxs-lookup"><span data-stu-id="2aa55-106">This is typically what you need to do when you use collection initializers for generic collections.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2aa55-107">示例</span><span class="sxs-lookup"><span data-stu-id="2aa55-107">Example</span></span>  
 <span data-ttu-id="2aa55-108">下面的示例演示如何将扩展方法添加到泛型<xref:System.Collections.Generic.List%601>类型，以便可以使用集合初始值设定项来添加类型的对象`Employee`。</span><span class="sxs-lookup"><span data-stu-id="2aa55-108">The following example shows how to add an extension method to the generic <xref:System.Collections.Generic.List%601> type so that a collection initializer can be used to add objects of type `Employee`.</span></span> <span data-ttu-id="2aa55-109">扩展方法，可使用缩短了的集合初始值设定项语法。</span><span class="sxs-lookup"><span data-stu-id="2aa55-109">The extension method enables you to use the shortened collection initializer syntax.</span></span>  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#1](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-an-add-extension-method-used-by-a-collection-initializer_1.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#2](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-an-add-extension-method-used-by-a-collection-initializer_2.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#3](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-an-add-extension-method-used-by-a-collection-initializer_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="2aa55-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="2aa55-110">See also</span></span>
- [<span data-ttu-id="2aa55-111">集合初始值设定项</span><span class="sxs-lookup"><span data-stu-id="2aa55-111">Collection Initializers</span></span>](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)
- [<span data-ttu-id="2aa55-112">如何：创建使用集合初始值设定项的集合</span><span class="sxs-lookup"><span data-stu-id="2aa55-112">How to: Create a Collection Used by a Collection Initializer</span></span>](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-a-collection-used-by-a-collection-initializer.md)
