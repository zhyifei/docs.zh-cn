---
title: "结构变量 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- structures [Visual Basic], variables
- structures [Visual Basic], structure variables
- variables [Visual Basic], structure variables
- structure variables [Visual Basic]
ms.assetid: 156872f8-aabc-4454-8e2d-f2253c3c13c9
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ef42c44de84caffde909eb2b3e9361016a6abb97
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="structure-variables-visual-basic"></a><span data-ttu-id="d6692-102">结构变量 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d6692-102">Structure Variables (Visual Basic)</span></span>
<span data-ttu-id="d6692-103">一旦你已创建一个结构，你可以将过程级别和模块级变量声明该类型。</span><span class="sxs-lookup"><span data-stu-id="d6692-103">Once you have created a structure, you can declare procedure-level and module-level variables as that type.</span></span> <span data-ttu-id="d6692-104">例如，可以创建一个有关计算机系统该记录的信息。</span><span class="sxs-lookup"><span data-stu-id="d6692-104">For example, you can create a structure that records information about a computer system.</span></span> <span data-ttu-id="d6692-105">下面的示例演示这一操作。</span><span class="sxs-lookup"><span data-stu-id="d6692-105">The following example demonstrates this.</span></span>  
  
```  
Public Structure systemInfo  
    Public cPU As String  
    Public memory As Long  
    Public purchaseDate As Date  
End Structure  
```  
  
 <span data-ttu-id="d6692-106">你现在可以声明该类型的变量。</span><span class="sxs-lookup"><span data-stu-id="d6692-106">You can now declare variables of that type.</span></span> <span data-ttu-id="d6692-107">以下声明阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="d6692-107">The following declaration illustrates this.</span></span>  
  
```  
Dim mySystem, yourSystem As systemInfo  
```  
  
> [!NOTE]
>  <span data-ttu-id="d6692-108">类和模块，请在结构声明使用[Dim 语句](../../../../visual-basic/language-reference/statements/dim-statement.md)默认为公共访问。</span><span class="sxs-lookup"><span data-stu-id="d6692-108">In classes and modules, structures declared using the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) default to public access.</span></span> <span data-ttu-id="d6692-109">如果你想要一个结构，用于为私有构造函数，请确保将其使用声明[私有](../../../../visual-basic/language-reference/modifiers/private.md)关键字。</span><span class="sxs-lookup"><span data-stu-id="d6692-109">If you intend a structure to be private, make sure you declare it using the [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword.</span></span>  
  
## <a name="access-to-structure-values"></a><span data-ttu-id="d6692-110">对结构值的访问</span><span class="sxs-lookup"><span data-stu-id="d6692-110">Access to Structure Values</span></span>  
 <span data-ttu-id="d6692-111">若要分配，并从结构变量的元素中检索值，你使用相同的语法为用于设置和获取对某个对象的属性。</span><span class="sxs-lookup"><span data-stu-id="d6692-111">To assign and retrieve values from the elements of a structure variable, you use the same syntax as you use to set and get properties on an object.</span></span> <span data-ttu-id="d6692-112">将成员访问运算符 (`.`) 之间的结构变量名称和元素名称。</span><span class="sxs-lookup"><span data-stu-id="d6692-112">You place the member access operator (`.`) between the structure variable name and the element name.</span></span> <span data-ttu-id="d6692-113">以下示例访问之前声明为类型的变量的元素`systemInfo`。</span><span class="sxs-lookup"><span data-stu-id="d6692-113">The following example accesses elements of the variables previously declared as type `systemInfo`.</span></span>  
  
```  
mySystem.cPU = "486"  
Dim tooOld As Boolean  
If yourSystem.purchaseDate < #1/1/1992# Then tooOld = True  
```  
  
## <a name="assigning-structure-variables"></a><span data-ttu-id="d6692-114">结构变量赋值</span><span class="sxs-lookup"><span data-stu-id="d6692-114">Assigning Structure Variables</span></span>  
 <span data-ttu-id="d6692-115">如果两个均为相同的结构类型，还可以为另一个分配一个变量。</span><span class="sxs-lookup"><span data-stu-id="d6692-115">You can also assign one variable to another if both are of the same structure type.</span></span> <span data-ttu-id="d6692-116">这会将一个结构的所有元素都复制到另一部分中的相应元素。</span><span class="sxs-lookup"><span data-stu-id="d6692-116">This copies all the elements of one structure to the corresponding elements in the other.</span></span> <span data-ttu-id="d6692-117">以下声明阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="d6692-117">The following declaration illustrates this.</span></span>  
  
```  
yourSystem = mySystem  
```  
  
 <span data-ttu-id="d6692-118">如果某个结构元素是引用类型，如`String`， `Object`，或复制数组，指向的数据。</span><span class="sxs-lookup"><span data-stu-id="d6692-118">If a structure element is a reference type, such as a `String`, `Object`, or array, the pointer to the data is copied.</span></span> <span data-ttu-id="d6692-119">在前面的示例中，如果`systemInfo`已包含的对象变量，则前面的示例将具有将复制从指针`mySystem`到`yourSystem`，并通过一个结构的对象的数据的更改都是有效的访问时通过其他结构。</span><span class="sxs-lookup"><span data-stu-id="d6692-119">In the previous example, if `systemInfo` had included an object variable, then the preceding example would have copied the pointer from `mySystem` to `yourSystem`, and a change to the object's data through one structure would be in effect when accessed through the other structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6692-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d6692-120">See Also</span></span>  
 [<span data-ttu-id="d6692-121">数据类型</span><span class="sxs-lookup"><span data-stu-id="d6692-121">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [<span data-ttu-id="d6692-122">基本数据类型</span><span class="sxs-lookup"><span data-stu-id="d6692-122">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [<span data-ttu-id="d6692-123">复合数据类型</span><span class="sxs-lookup"><span data-stu-id="d6692-123">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)  
 [<span data-ttu-id="d6692-124">值类型和引用类型</span><span class="sxs-lookup"><span data-stu-id="d6692-124">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [<span data-ttu-id="d6692-125">结构</span><span class="sxs-lookup"><span data-stu-id="d6692-125">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="d6692-126">数据类型疑难解答</span><span class="sxs-lookup"><span data-stu-id="d6692-126">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [<span data-ttu-id="d6692-127">如何：声明结构</span><span class="sxs-lookup"><span data-stu-id="d6692-127">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [<span data-ttu-id="d6692-128">结构和其他编程元素</span><span class="sxs-lookup"><span data-stu-id="d6692-128">Structures and Other Programming Elements</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)  
 [<span data-ttu-id="d6692-129">结构和类</span><span class="sxs-lookup"><span data-stu-id="d6692-129">Structures and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)  
 [<span data-ttu-id="d6692-130">Structure 语句</span><span class="sxs-lookup"><span data-stu-id="d6692-130">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
