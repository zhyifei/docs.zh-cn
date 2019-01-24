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
ms.openlocfilehash: ed406254435602dcd98bc97716cc88710a470ed1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54679586"
---
# <a name="structures-and-other-programming-elements-visual-basic"></a><span data-ttu-id="b0820-102">结构和其他编程元素 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b0820-102">Structures and Other Programming Elements (Visual Basic)</span></span>
<span data-ttu-id="b0820-103">可以结合使用数组、 对象和过程，以及与每个其他使用结构。</span><span class="sxs-lookup"><span data-stu-id="b0820-103">You can use structures in conjunction with arrays, objects, and procedures, as well as with each other.</span></span> <span data-ttu-id="b0820-104">交互使用相同的语法，如单独使用这些元素。</span><span class="sxs-lookup"><span data-stu-id="b0820-104">The interactions use the same syntax as these elements use individually.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b0820-105">无法初始化任何在结构声明中的结构元素。</span><span class="sxs-lookup"><span data-stu-id="b0820-105">You cannot initialize any of the structure elements in the structure declaration.</span></span> <span data-ttu-id="b0820-106">可以仅对元素的已声明为结构类型的变量赋值。</span><span class="sxs-lookup"><span data-stu-id="b0820-106">You can assign values only to elements of a variable that has been declared to be of a structure type.</span></span>  
  
## <a name="structures-and-arrays"></a><span data-ttu-id="b0820-107">结构和数组</span><span class="sxs-lookup"><span data-stu-id="b0820-107">Structures and Arrays</span></span>  
 <span data-ttu-id="b0820-108">一种结构可以包含为一个或多个元素的数组。</span><span class="sxs-lookup"><span data-stu-id="b0820-108">A structure can contain an array as one or more of its elements.</span></span> <span data-ttu-id="b0820-109">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="b0820-109">The following example illustrates this.</span></span>  
  
```vb  
Public Structure systemInfo  
    Public cPU As String  
    Public memory As Long  
    Public diskDrives() As String  
    Public purchaseDate As Date  
End Structure   
```  
  
 <span data-ttu-id="b0820-110">访问对象的属性一样访问数组在结构中的值。</span><span class="sxs-lookup"><span data-stu-id="b0820-110">You access the values of an array within a structure the same way you access a property on an object.</span></span> <span data-ttu-id="b0820-111">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="b0820-111">The following example illustrates this.</span></span>  
  
```vb  
Dim mySystem As systemInfo  
ReDim mySystem.diskDrives(3)  
mySystem.diskDrives(0) = "1.44 MB"  
```  
  
 <span data-ttu-id="b0820-112">此外可以声明为结构数组。</span><span class="sxs-lookup"><span data-stu-id="b0820-112">You can also declare an array of structures.</span></span> <span data-ttu-id="b0820-113">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="b0820-113">The following example illustrates this.</span></span>  
  
```vb  
Dim allSystems(100) As systemInfo  
```  
  
 <span data-ttu-id="b0820-114">按照相同的规则来访问此数据体系结构的组件。</span><span class="sxs-lookup"><span data-stu-id="b0820-114">You follow the same rules to access the components of this data architecture.</span></span> <span data-ttu-id="b0820-115">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="b0820-115">The following example illustrates this.</span></span>  
  
```vb  
ReDim allSystems(5).diskDrives(3)  
allSystems(5).CPU = "386SX"  
allSystems(5).diskDrives(2) = "100M SCSI"  
```  
  
## <a name="structures-and-objects"></a><span data-ttu-id="b0820-116">结构和对象</span><span class="sxs-lookup"><span data-stu-id="b0820-116">Structures and Objects</span></span>  
 <span data-ttu-id="b0820-117">结构包含一个作为一个或多个元素的对象。</span><span class="sxs-lookup"><span data-stu-id="b0820-117">A structure can contain an object as one or more of its elements.</span></span> <span data-ttu-id="b0820-118">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="b0820-118">The following example illustrates this.</span></span>  
  
```vb  
Protected Structure userInput  
    Public userName As String  
    Public inputForm As System.Windows.Forms.Form  
    Public userFileNumber As Integer  
End Structure  
```  
  
 <span data-ttu-id="b0820-119">应在此类声明中，使用特定的对象类而不是`Object`。</span><span class="sxs-lookup"><span data-stu-id="b0820-119">You should use a specific object class in such a declaration, rather than `Object`.</span></span>  
  
## <a name="structures-and-procedures"></a><span data-ttu-id="b0820-120">结构和过程</span><span class="sxs-lookup"><span data-stu-id="b0820-120">Structures and Procedures</span></span>  
 <span data-ttu-id="b0820-121">可以将结构作为过程自变量传递。</span><span class="sxs-lookup"><span data-stu-id="b0820-121">You can pass a structure as a procedure argument.</span></span> <span data-ttu-id="b0820-122">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="b0820-122">The following example illustrates this.</span></span>  
  
```vb  
Public currentCPUName As String = "700MHz Pentium compatible"  
Public currentMemorySize As Long = 256  
Public Sub fillSystem(ByRef someSystem As systemInfo)  
    someSystem.cPU = currentCPUName  
    someSystem.memory = currentMemorySize  
    someSystem.purchaseDate = Now  
End Sub  
```  
  
 <span data-ttu-id="b0820-123">前面的示例中将此结构传递*通过引用*，这将允许过程来修改它的元素，以便在调用代码中所做的更改生效。</span><span class="sxs-lookup"><span data-stu-id="b0820-123">The preceding example passes the structure *by reference*, which allows the procedure to modify its elements so that the changes take effect in the calling code.</span></span> <span data-ttu-id="b0820-124">如果你想要保护的结构避免这种修改，将它传递的值。</span><span class="sxs-lookup"><span data-stu-id="b0820-124">If you want to protect a structure against such modification, pass it by value.</span></span>  
  
 <span data-ttu-id="b0820-125">您还可以返回从结构`Function`过程。</span><span class="sxs-lookup"><span data-stu-id="b0820-125">You can also return a structure from a `Function` procedure.</span></span> <span data-ttu-id="b0820-126">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="b0820-126">The following example illustrates this.</span></span>  
  
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
  
## <a name="structures-within-structures"></a><span data-ttu-id="b0820-127">结构中的结构</span><span class="sxs-lookup"><span data-stu-id="b0820-127">Structures Within Structures</span></span>  
 <span data-ttu-id="b0820-128">结构可以包含其他结构。</span><span class="sxs-lookup"><span data-stu-id="b0820-128">Structures can contain other structures.</span></span> <span data-ttu-id="b0820-129">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="b0820-129">The following example illustrates this.</span></span>  
  
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
  
 <span data-ttu-id="b0820-130">此方法还可用于封装在模块中的另一个模块中定义的结构中定义的结构。</span><span class="sxs-lookup"><span data-stu-id="b0820-130">You can also use this technique to encapsulate a structure defined in one module within a structure defined in a different module.</span></span>  
  
 <span data-ttu-id="b0820-131">结构可以包含其他任意深度的结构。</span><span class="sxs-lookup"><span data-stu-id="b0820-131">Structures can contain other structures to an arbitrary depth.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0820-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="b0820-132">See also</span></span>
- [<span data-ttu-id="b0820-133">数据类型</span><span class="sxs-lookup"><span data-stu-id="b0820-133">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="b0820-134">基本数据类型</span><span class="sxs-lookup"><span data-stu-id="b0820-134">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [<span data-ttu-id="b0820-135">复合数据类型</span><span class="sxs-lookup"><span data-stu-id="b0820-135">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [<span data-ttu-id="b0820-136">值类型和引用类型</span><span class="sxs-lookup"><span data-stu-id="b0820-136">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="b0820-137">结构</span><span class="sxs-lookup"><span data-stu-id="b0820-137">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="b0820-138">数据类型疑难解答</span><span class="sxs-lookup"><span data-stu-id="b0820-138">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="b0820-139">如何：声明结构</span><span class="sxs-lookup"><span data-stu-id="b0820-139">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="b0820-140">结构变量</span><span class="sxs-lookup"><span data-stu-id="b0820-140">Structure Variables</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structure-variables.md)
- [<span data-ttu-id="b0820-141">结构和类</span><span class="sxs-lookup"><span data-stu-id="b0820-141">Structures and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
- [<span data-ttu-id="b0820-142">Structure 语句</span><span class="sxs-lookup"><span data-stu-id="b0820-142">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
