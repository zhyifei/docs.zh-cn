---
title: "如何：使用泛型类 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- type parameters [Visual Basic], defining
- data type arguments [Visual Basic], defining
- arguments [Visual Basic], data types
- Of keyword [Visual Basic], using
- generic parameters
- data type parameters
- generics [Visual Basic], about generics
- data types [Visual Basic], as parameters
- data types [Visual Basic], as arguments
- parameters [Visual Basic], type
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- generics [Visual Basic], creating generic types
- data type arguments
- parameters [Visual Basic], data type
- data type parameters [Visual Basic], defining
- type arguments [Visual Basic], defining
- arguments [Visual Basic], type
ms.assetid: 242dd2a6-86c4-4ce7-83f2-f2661803f752
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b32707456c9e59d5a81d76c73d867b33554bdbcb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-a-generic-class-visual-basic"></a><span data-ttu-id="28f61-102">如何：使用泛型类 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="28f61-102">How to: Use a Generic Class (Visual Basic)</span></span>
<span data-ttu-id="28f61-103">采用 *类型参数* 的类称为 *泛型类*。</span><span class="sxs-lookup"><span data-stu-id="28f61-103">A class that takes *type parameters* is called a *generic class*.</span></span> <span data-ttu-id="28f61-104">如果使用一个泛型类，则可以通过为每个形参提供 *类型实参* ，从该类生成 *构造类* 。</span><span class="sxs-lookup"><span data-stu-id="28f61-104">If you are using a generic class, you can generate a *constructed class* from it by supplying a *type argument* for each of these parameters.</span></span> <span data-ttu-id="28f61-105">随后可以声明构造类类型的一个变量，可以创建构造类的实例并将它分配给该变量。</span><span class="sxs-lookup"><span data-stu-id="28f61-105">You can then declare a variable of the constructed class type, and you can create an instance of the constructed class and assign it to that variable.</span></span>  
  
 <span data-ttu-id="28f61-106">除了类之外，你还可以定义和使用泛型结构、接口、过程和委托。</span><span class="sxs-lookup"><span data-stu-id="28f61-106">In addition to classes, you can also define and use generic structures, interfaces, procedures, and delegates.</span></span>  
  
 <span data-ttu-id="28f61-107">下面的过程采用在 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 中定义的一个泛型类，并且通过它创建一个实例。</span><span class="sxs-lookup"><span data-stu-id="28f61-107">The following procedure takes a generic class defined in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] and creates an instance from it.</span></span>  
  
### <a name="to-use-a-class-that-takes-a-type-parameter"></a><span data-ttu-id="28f61-108">使用采用类型参数的类</span><span class="sxs-lookup"><span data-stu-id="28f61-108">To use a class that takes a type parameter</span></span>  
  
1.  <span data-ttu-id="28f61-109">在你的源文件的开头，包括[Imports 语句 （.NET Namespace 和类型）](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)导入<xref:System.Collections.Generic?displayProperty=nameWithType>命名空间。</span><span class="sxs-lookup"><span data-stu-id="28f61-109">At the beginning of your source file, include an [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) to import the <xref:System.Collections.Generic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="28f61-110">这使你可以引用 <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType> 类，而不必完全限定它即可将它与其他队列类（如 <xref:System.Collections.Queue?displayProperty=nameWithType>）区分开来。</span><span class="sxs-lookup"><span data-stu-id="28f61-110">This allows you to refer to the <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType> class without having to fully qualify it to differentiate it from other queue classes such as <xref:System.Collections.Queue?displayProperty=nameWithType>.</span></span>  
  
2.  <span data-ttu-id="28f61-111">以正常方式创建对象，但是紧接在类名之后添加 `(Of` `type``)` 。</span><span class="sxs-lookup"><span data-stu-id="28f61-111">Create the object in the normal way, but add `(Of` `type``)` immediately after the class name.</span></span>  
  
     <span data-ttu-id="28f61-112">下面的示例使用相同类 (<xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType>) 创建保存不同数据类型的项的两个队列对象。</span><span class="sxs-lookup"><span data-stu-id="28f61-112">The following example uses the same class (<xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType>) to create two queue objects that hold items of different data types.</span></span> <span data-ttu-id="28f61-113">它将项添加到每个队列末尾，然后从每个队列的前面删除并显示项。</span><span class="sxs-lookup"><span data-stu-id="28f61-113">It adds items to the end of each queue and then removes and displays items from the front of each queue.</span></span>  
  
     [!code-vb[VbVbalrDataTypes#9](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/how-to-use-a-generic-class_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="28f61-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="28f61-114">See Also</span></span>  
 [<span data-ttu-id="28f61-115">数据类型</span><span class="sxs-lookup"><span data-stu-id="28f61-115">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [<span data-ttu-id="28f61-116">Visual Basic 中的泛型类型</span><span class="sxs-lookup"><span data-stu-id="28f61-116">Generic Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [<span data-ttu-id="28f61-117">语言独立性和与语言无关的组件</span><span class="sxs-lookup"><span data-stu-id="28f61-117">Language Independence and Language-Independent Components</span></span>](https://msdn.microsoft.com/library/12a7a7h3)  
 [<span data-ttu-id="28f61-118">Of</span><span class="sxs-lookup"><span data-stu-id="28f61-118">Of</span></span>](../../../../visual-basic/language-reference/statements/of-clause.md)  
 [<span data-ttu-id="28f61-119">Imports 语句（.NET 命名空间和类型）</span><span class="sxs-lookup"><span data-stu-id="28f61-119">Imports Statement (.NET Namespace and Type)</span></span>](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [<span data-ttu-id="28f61-120">如何：定义可对不同数据类型提供相同功能的类</span><span class="sxs-lookup"><span data-stu-id="28f61-120">How to: Define a Class That Can Provide Identical Functionality on Different Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-define-a-class-that-can-provide-identical-functionality.md)  
 [<span data-ttu-id="28f61-121">迭代器</span><span class="sxs-lookup"><span data-stu-id="28f61-121">Iterators</span></span>](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)
