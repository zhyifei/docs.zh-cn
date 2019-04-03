---
title: 结构变量 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- structures [Visual Basic], variables
- structures [Visual Basic], structure variables
- variables [Visual Basic], structure variables
- structure variables [Visual Basic]
ms.assetid: 156872f8-aabc-4454-8e2d-f2253c3c13c9
ms.openlocfilehash: 9a6e542e297a17f44d929235530ae6058cf13a36
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58816325"
---
# <a name="structure-variables-visual-basic"></a><span data-ttu-id="de790-102">结构变量 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="de790-102">Structure Variables (Visual Basic)</span></span>
<span data-ttu-id="de790-103">创建结构后，可以将过程级别和模块级变量声明该类型。</span><span class="sxs-lookup"><span data-stu-id="de790-103">Once you have created a structure, you can declare procedure-level and module-level variables as that type.</span></span> <span data-ttu-id="de790-104">例如，可以创建一个结构该记录有关计算机系统的信息。</span><span class="sxs-lookup"><span data-stu-id="de790-104">For example, you can create a structure that records information about a computer system.</span></span> <span data-ttu-id="de790-105">下面的示例演示这一操作。</span><span class="sxs-lookup"><span data-stu-id="de790-105">The following example demonstrates this.</span></span>  
  
```  
Public Structure systemInfo  
    Public cPU As String  
    Public memory As Long  
    Public purchaseDate As Date  
End Structure  
```  
  
 <span data-ttu-id="de790-106">现在可以声明该类型的变量。</span><span class="sxs-lookup"><span data-stu-id="de790-106">You can now declare variables of that type.</span></span> <span data-ttu-id="de790-107">下面的声明阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="de790-107">The following declaration illustrates this.</span></span>  
  
```  
Dim mySystem, yourSystem As systemInfo  
```  
  
> [!NOTE]
>  <span data-ttu-id="de790-108">类和模块，请在结构声明使用[Dim 语句](../../../../visual-basic/language-reference/statements/dim-statement.md)默认为公共访问。</span><span class="sxs-lookup"><span data-stu-id="de790-108">In classes and modules, structures declared using the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) default to public access.</span></span> <span data-ttu-id="de790-109">如果你想要为私有构造函数的结构，请确保将其使用声明[专用](../../../../visual-basic/language-reference/modifiers/private.md)关键字。</span><span class="sxs-lookup"><span data-stu-id="de790-109">If you intend a structure to be private, make sure you declare it using the [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword.</span></span>  
  
## <a name="access-to-structure-values"></a><span data-ttu-id="de790-110">对结构值的访问</span><span class="sxs-lookup"><span data-stu-id="de790-110">Access to Structure Values</span></span>  
 <span data-ttu-id="de790-111">若要赋值和检索值的结构变量的元素，您使用相同的语法为用于设置和获取对某个对象的属性。</span><span class="sxs-lookup"><span data-stu-id="de790-111">To assign and retrieve values from the elements of a structure variable, you use the same syntax as you use to set and get properties on an object.</span></span> <span data-ttu-id="de790-112">将成员访问运算符 (`.`) 之间的结构变量名称和元素名称。</span><span class="sxs-lookup"><span data-stu-id="de790-112">You place the member access operator (`.`) between the structure variable name and the element name.</span></span> <span data-ttu-id="de790-113">以下示例访问以前声明为类型的变量的元素`systemInfo`。</span><span class="sxs-lookup"><span data-stu-id="de790-113">The following example accesses elements of the variables previously declared as type `systemInfo`.</span></span>  
  
```  
mySystem.cPU = "486"  
Dim tooOld As Boolean  
If yourSystem.purchaseDate < #1/1/1992# Then tooOld = True  
```  
  
## <a name="assigning-structure-variables"></a><span data-ttu-id="de790-114">结构变量赋值</span><span class="sxs-lookup"><span data-stu-id="de790-114">Assigning Structure Variables</span></span>  
 <span data-ttu-id="de790-115">如果两者都是相同的结构类型的还可以将一个变量分配到另一个。</span><span class="sxs-lookup"><span data-stu-id="de790-115">You can also assign one variable to another if both are of the same structure type.</span></span> <span data-ttu-id="de790-116">这将一个结构的所有元素都复制到其他的相应元素。</span><span class="sxs-lookup"><span data-stu-id="de790-116">This copies all the elements of one structure to the corresponding elements in the other.</span></span> <span data-ttu-id="de790-117">下面的声明阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="de790-117">The following declaration illustrates this.</span></span>  
  
```  
yourSystem = mySystem  
```  
  
 <span data-ttu-id="de790-118">如果结构元素是引用类型，例如`String`， `Object`，或复制数组，对数据的指针。</span><span class="sxs-lookup"><span data-stu-id="de790-118">If a structure element is a reference type, such as a `String`, `Object`, or array, the pointer to the data is copied.</span></span> <span data-ttu-id="de790-119">在上一示例中，如果`systemInfo`已包含一个对象的变量，则前面的示例将复制从指针`mySystem`到`yourSystem`，和一个结构时，通过该对象的数据的更改都是有效的访问时通过其他结构。</span><span class="sxs-lookup"><span data-stu-id="de790-119">In the previous example, if `systemInfo` had included an object variable, then the preceding example would have copied the pointer from `mySystem` to `yourSystem`, and a change to the object's data through one structure would be in effect when accessed through the other structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de790-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="de790-120">See also</span></span>

- [<span data-ttu-id="de790-121">数据类型</span><span class="sxs-lookup"><span data-stu-id="de790-121">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="de790-122">基本数据类型</span><span class="sxs-lookup"><span data-stu-id="de790-122">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [<span data-ttu-id="de790-123">复合数据类型</span><span class="sxs-lookup"><span data-stu-id="de790-123">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [<span data-ttu-id="de790-124">值类型和引用类型</span><span class="sxs-lookup"><span data-stu-id="de790-124">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="de790-125">结构</span><span class="sxs-lookup"><span data-stu-id="de790-125">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="de790-126">数据类型疑难解答</span><span class="sxs-lookup"><span data-stu-id="de790-126">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="de790-127">如何：声明结构</span><span class="sxs-lookup"><span data-stu-id="de790-127">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="de790-128">结构和其他编程元素</span><span class="sxs-lookup"><span data-stu-id="de790-128">Structures and Other Programming Elements</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)
- [<span data-ttu-id="de790-129">结构和类</span><span class="sxs-lookup"><span data-stu-id="de790-129">Structures and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
- [<span data-ttu-id="de790-130">Structure 语句</span><span class="sxs-lookup"><span data-stu-id="de790-130">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
