---
title: 结构和其他编程元素 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- structures [Visual Basic], arrays
- procedures [Visual Basic], structures as arguments to
- objects [Visual Basic], structure elements
- arrays [Visual Basic], structure elements
- nested structures [Visual Basic]
ms.assetid: 0f849313-ccd2-4c9a-acb9-69de6751c088
ms.openlocfilehash: 7b375c5a45998fc0bd06f7c075f23a30dd377295
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33652020"
---
# <a name="structures-and-other-programming-elements-visual-basic"></a><span data-ttu-id="dd78f-102">结构和其他编程元素 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dd78f-102">Structures and Other Programming Elements (Visual Basic)</span></span>
<span data-ttu-id="dd78f-103">你可以结合使用数组、 对象和过程，以及与每个其他使用结构。</span><span class="sxs-lookup"><span data-stu-id="dd78f-103">You can use structures in conjunction with arrays, objects, and procedures, as well as with each other.</span></span> <span data-ttu-id="dd78f-104">交互使用相同的语法，如单独使用这些元素。</span><span class="sxs-lookup"><span data-stu-id="dd78f-104">The interactions use the same syntax as these elements use individually.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dd78f-105">无法初始化任何结构声明中的结构元素。</span><span class="sxs-lookup"><span data-stu-id="dd78f-105">You cannot initialize any of the structure elements in the structure declaration.</span></span> <span data-ttu-id="dd78f-106">您可以分配到已被声明为结构类型的变量的元素的值。</span><span class="sxs-lookup"><span data-stu-id="dd78f-106">You can assign values only to elements of a variable that has been declared to be of a structure type.</span></span>  
  
## <a name="structures-and-arrays"></a><span data-ttu-id="dd78f-107">结构和数组</span><span class="sxs-lookup"><span data-stu-id="dd78f-107">Structures and Arrays</span></span>  
 <span data-ttu-id="dd78f-108">结构可以包含数组作为一个或多个它的元素。</span><span class="sxs-lookup"><span data-stu-id="dd78f-108">A structure can contain an array as one or more of its elements.</span></span> <span data-ttu-id="dd78f-109">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="dd78f-109">The following example illustrates this.</span></span>  
  
```vb  
Public Structure systemInfo  
    Public cPU As String  
    Public memory As Long  
    Public diskDrives() As String  
    Public purchaseDate As Date  
End Structure   
```  
  
 <span data-ttu-id="dd78f-110">你可以访问数组结构中的值相同的方式访问对象的属性。</span><span class="sxs-lookup"><span data-stu-id="dd78f-110">You access the values of an array within a structure the same way you access a property on an object.</span></span> <span data-ttu-id="dd78f-111">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="dd78f-111">The following example illustrates this.</span></span>  
  
```vb  
Dim mySystem As systemInfo  
ReDim mySystem.diskDrives(3)  
mySystem.diskDrives(0) = "1.44 MB"  
```  
  
 <span data-ttu-id="dd78f-112">你也可以声明结构的数组。</span><span class="sxs-lookup"><span data-stu-id="dd78f-112">You can also declare an array of structures.</span></span> <span data-ttu-id="dd78f-113">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="dd78f-113">The following example illustrates this.</span></span>  
  
```vb  
Dim allSystems(100) As systemInfo  
```  
  
 <span data-ttu-id="dd78f-114">按照相同的规则来访问此数据体系结构的组件。</span><span class="sxs-lookup"><span data-stu-id="dd78f-114">You follow the same rules to access the components of this data architecture.</span></span> <span data-ttu-id="dd78f-115">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="dd78f-115">The following example illustrates this.</span></span>  
  
```vb  
ReDim allSystems(5).diskDrives(3)  
allSystems(5).CPU = "386SX"  
allSystems(5).diskDrives(2) = "100M SCSI"  
```  
  
## <a name="structures-and-objects"></a><span data-ttu-id="dd78f-116">结构和对象</span><span class="sxs-lookup"><span data-stu-id="dd78f-116">Structures and Objects</span></span>  
 <span data-ttu-id="dd78f-117">结构只能包含一个作为一个或多个它的元素的对象。</span><span class="sxs-lookup"><span data-stu-id="dd78f-117">A structure can contain an object as one or more of its elements.</span></span> <span data-ttu-id="dd78f-118">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="dd78f-118">The following example illustrates this.</span></span>  
  
```vb  
Protected Structure userInput  
    Public userName As String  
    Public inputForm As System.Windows.Forms.Form  
    Public userFileNumber As Integer  
End Structure  
```  
  
 <span data-ttu-id="dd78f-119">应在此类声明中，使用特定的对象类而不是`Object`。</span><span class="sxs-lookup"><span data-stu-id="dd78f-119">You should use a specific object class in such a declaration, rather than `Object`.</span></span>  
  
## <a name="structures-and-procedures"></a><span data-ttu-id="dd78f-120">结构和过程</span><span class="sxs-lookup"><span data-stu-id="dd78f-120">Structures and Procedures</span></span>  
 <span data-ttu-id="dd78f-121">可以将结构作为过程自变量传递。</span><span class="sxs-lookup"><span data-stu-id="dd78f-121">You can pass a structure as a procedure argument.</span></span> <span data-ttu-id="dd78f-122">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="dd78f-122">The following example illustrates this.</span></span>  
  
```vb  
Public currentCPUName As String = "700MHz Pentium compatible"  
Public currentMemorySize As Long = 256  
Public Sub fillSystem(ByRef someSystem As systemInfo)  
    someSystem.cPU = currentCPUName  
    someSystem.memory = currentMemorySize  
    someSystem.purchaseDate = Now  
End Sub  
```  
  
 <span data-ttu-id="dd78f-123">前面的示例将此结构传递*通过引用*，这样，过程来修改其元素，以便在调用代码中所做的更改生效。</span><span class="sxs-lookup"><span data-stu-id="dd78f-123">The preceding example passes the structure *by reference*, which allows the procedure to modify its elements so that the changes take effect in the calling code.</span></span> <span data-ttu-id="dd78f-124">如果你想要保护避免这种修改的结构，则按值传递它。</span><span class="sxs-lookup"><span data-stu-id="dd78f-124">If you want to protect a structure against such modification, pass it by value.</span></span>  
  
 <span data-ttu-id="dd78f-125">你还可以返回的结构从`Function`过程。</span><span class="sxs-lookup"><span data-stu-id="dd78f-125">You can also return a structure from a `Function` procedure.</span></span> <span data-ttu-id="dd78f-126">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="dd78f-126">The following example illustrates this.</span></span>  
  
```vb  
Dim allSystems(100) As systemInfo  
Function findByDate(ByVal searchDate As Date) As systemInfo  
    Dim i As Integer  
    For i = 1 To 100  
        If allSystems(i).purchaseDate = searchDate Then Return allSystems(i)  
    Next i  
   ' Process error: system with desired purchase date not found.  
End Function  
```  
  
## <a name="structures-within-structures"></a><span data-ttu-id="dd78f-127">结构中的结构</span><span class="sxs-lookup"><span data-stu-id="dd78f-127">Structures Within Structures</span></span>  
 <span data-ttu-id="dd78f-128">结构可以包含其他结构。</span><span class="sxs-lookup"><span data-stu-id="dd78f-128">Structures can contain other structures.</span></span> <span data-ttu-id="dd78f-129">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="dd78f-129">The following example illustrates this.</span></span>  
  
```vb  
Public Structure driveInfo  
    Public type As String  
    Public size As Long  
End Structure  
Public Structure systemInfo  
    Public cPU As String  
    Public memory As Long  
    Public diskDrives() As driveInfo  
    Public purchaseDate As Date  
End Structure  
```  
  
```vb  
Dim allSystems(100) As systemInfo  
ReDim allSystems(1).diskDrives(3)  
allSystems(1).diskDrives(0).type = "Floppy"  
```  
  
 <span data-ttu-id="dd78f-130">此方法还可用于封装在另一个模块中定义结构中的一个模块中定义的结构。</span><span class="sxs-lookup"><span data-stu-id="dd78f-130">You can also use this technique to encapsulate a structure defined in one module within a structure defined in a different module.</span></span>  
  
 <span data-ttu-id="dd78f-131">结构可以包含其他结构到任意深度。</span><span class="sxs-lookup"><span data-stu-id="dd78f-131">Structures can contain other structures to an arbitrary depth.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd78f-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="dd78f-132">See Also</span></span>  
 [<span data-ttu-id="dd78f-133">数据类型</span><span class="sxs-lookup"><span data-stu-id="dd78f-133">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [<span data-ttu-id="dd78f-134">基本数据类型</span><span class="sxs-lookup"><span data-stu-id="dd78f-134">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [<span data-ttu-id="dd78f-135">复合数据类型</span><span class="sxs-lookup"><span data-stu-id="dd78f-135">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)  
 [<span data-ttu-id="dd78f-136">值类型和引用类型</span><span class="sxs-lookup"><span data-stu-id="dd78f-136">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [<span data-ttu-id="dd78f-137">结构</span><span class="sxs-lookup"><span data-stu-id="dd78f-137">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="dd78f-138">数据类型疑难解答</span><span class="sxs-lookup"><span data-stu-id="dd78f-138">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [<span data-ttu-id="dd78f-139">如何：声明结构</span><span class="sxs-lookup"><span data-stu-id="dd78f-139">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [<span data-ttu-id="dd78f-140">结构变量</span><span class="sxs-lookup"><span data-stu-id="dd78f-140">Structure Variables</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structure-variables.md)  
 [<span data-ttu-id="dd78f-141">结构和类</span><span class="sxs-lookup"><span data-stu-id="dd78f-141">Structures and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)  
 [<span data-ttu-id="dd78f-142">Structure 语句</span><span class="sxs-lookup"><span data-stu-id="dd78f-142">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
