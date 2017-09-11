---
title: "如何︰ 创建项的列表 |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- list [LINQ in Visual Basic]
- objects [Visual Basic], list of items
ms.assetid: fe941aba-6340-455c-8b1f-ffd9c3eb1ac5
caps.latest.revision: 29
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: ad0d2dfd38e30ddff1a5b030ec1ace884539d134
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-create-a-list-of-items"></a><span data-ttu-id="6ee6f-102">如何：创建项列表</span><span class="sxs-lookup"><span data-stu-id="6ee6f-102">How to: Create a List of Items</span></span>
<span data-ttu-id="6ee6f-103">本主题中的代码定义一个 `Student` 类，并创建该类的实例列表。</span><span class="sxs-lookup"><span data-stu-id="6ee6f-103">The code in this topic defines a `Student` class and creates a list of instances of the class.</span></span> <span data-ttu-id="6ee6f-104">该列表旨在支持主题[演练︰ 在 Visual Basic 中编写查询](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)。</span><span class="sxs-lookup"><span data-stu-id="6ee6f-104">The list is designed to support the topic [Walkthrough: Writing Queries in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md).</span></span> <span data-ttu-id="6ee6f-105">它还可以用于需要对象列表的任何应用程序。</span><span class="sxs-lookup"><span data-stu-id="6ee6f-105">It also can be used for any application that requires a list of objects.</span></span> <span data-ttu-id="6ee6f-106">代码使用对象初始值设定项定义学生列表中的项。</span><span class="sxs-lookup"><span data-stu-id="6ee6f-106">The code defines the items in the list of students by using object initializers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6ee6f-107">示例</span><span class="sxs-lookup"><span data-stu-id="6ee6f-107">Example</span></span>  
 <span data-ttu-id="6ee6f-108">如果你在使用演练，则可以将此代码用于在其中创建的项目的 Module1.vb 文件。</span><span class="sxs-lookup"><span data-stu-id="6ee6f-108">If you are working on the walkthrough, you can use this code for the Module1.vb file of the project that is created there.</span></span> <span data-ttu-id="6ee6f-109">只需将 `Main` 方法中使用 **** 进行标记的行替换为在演练中提供的查询和查询执行。</span><span class="sxs-lookup"><span data-stu-id="6ee6f-109">Just replace the lines marked with **** in the `Main` method with the queries and query executions that are provided in the walkthrough.</span></span>  
  
 <span data-ttu-id="6ee6f-110">[!code-vb[VbLINQHowToCreateList #&1;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/how-to-create-a-list-of-items_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="6ee6f-110">[!code-vb[VbLINQHowToCreateList#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/how-to-create-a-list-of-items_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ee6f-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6ee6f-111">See Also</span></span>  
 <span data-ttu-id="6ee6f-112">[演练︰ 在 Visual Basic 中编写查询](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md) </span><span class="sxs-lookup"><span data-stu-id="6ee6f-112">[Walkthrough: Writing Queries in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md) </span></span>  
<span data-ttu-id="6ee6f-113"> [在 Visual Basic 中的 LINQ 入门](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md) </span><span class="sxs-lookup"><span data-stu-id="6ee6f-113"> [Getting Started with LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md) </span></span>  
<span data-ttu-id="6ee6f-114"> [对象初始值设定项︰ 命名类型和匿名类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md) </span><span class="sxs-lookup"><span data-stu-id="6ee6f-114"> [Object Initializers: Named and Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md) </span></span>  
<span data-ttu-id="6ee6f-115"> [在 Visual Basic 中的 LINQ 简介](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) </span><span class="sxs-lookup"><span data-stu-id="6ee6f-115"> [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) </span></span>  
<span data-ttu-id="6ee6f-116"> [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span><span class="sxs-lookup"><span data-stu-id="6ee6f-116"> [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span></span>  
<span data-ttu-id="6ee6f-117"> [查询](../../../../visual-basic/language-reference/queries/queries.md)</span><span class="sxs-lookup"><span data-stu-id="6ee6f-117"> [Queries](../../../../visual-basic/language-reference/queries/queries.md)</span></span>
