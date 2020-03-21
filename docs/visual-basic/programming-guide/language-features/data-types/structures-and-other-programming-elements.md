---
title: 结构和其他编程元素
ms.date: 07/20/2015
helpviewer_keywords:
- structures [Visual Basic], arrays
- procedures [Visual Basic], structures as arguments to
- objects [Visual Basic], structure elements
- arrays [Visual Basic], structure elements
- nested structures [Visual Basic]
ms.assetid: 0f849313-ccd2-4c9a-acb9-69de6751c088
ms.openlocfilehash: 73d3f999e95c484dff3f5409f2cdb9032b64fe38
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266854"
---
# <a name="structures-and-other-programming-elements-visual-basic"></a><span data-ttu-id="dfcaa-102">结构和其他编程元素 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dfcaa-102">Structures and Other Programming Elements (Visual Basic)</span></span>
<span data-ttu-id="dfcaa-103">您可以将结构与数组、对象和过程结合使用，也可以彼此结合使用。</span><span class="sxs-lookup"><span data-stu-id="dfcaa-103">You can use structures in conjunction with arrays, objects, and procedures, as well as with each other.</span></span> <span data-ttu-id="dfcaa-104">交互使用与这些元素单独使用的语法相同。</span><span class="sxs-lookup"><span data-stu-id="dfcaa-104">The interactions use the same syntax as these elements use individually.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dfcaa-105">不能初始化结构声明中的任何结构元素。</span><span class="sxs-lookup"><span data-stu-id="dfcaa-105">You cannot initialize any of the structure elements in the structure declaration.</span></span> <span data-ttu-id="dfcaa-106">只能将值分配给已声明为结构类型的变量的元素。</span><span class="sxs-lookup"><span data-stu-id="dfcaa-106">You can assign values only to elements of a variable that has been declared to be of a structure type.</span></span>  
  
## <a name="structures-and-arrays"></a><span data-ttu-id="dfcaa-107">结构和数组</span><span class="sxs-lookup"><span data-stu-id="dfcaa-107">Structures and Arrays</span></span>  
 <span data-ttu-id="dfcaa-108">结构可以包含数组作为其一个或多个元素。</span><span class="sxs-lookup"><span data-stu-id="dfcaa-108">A structure can contain an array as one or more of its elements.</span></span> <span data-ttu-id="dfcaa-109">下面的示例对此进行了演示。</span><span class="sxs-lookup"><span data-stu-id="dfcaa-109">The following example illustrates this.</span></span>  
  
```vb  
Public Structure systemInfo  
    Public cPU As String  
    Public memory As Long  
    Public diskDrives() As String  
    Public purchaseDate As Date  
End Structure
```  
  
 <span data-ttu-id="dfcaa-110">访问结构中数组的值的方式与访问对象的属性的方式相同。</span><span class="sxs-lookup"><span data-stu-id="dfcaa-110">You access the values of an array within a structure the same way you access a property on an object.</span></span> <span data-ttu-id="dfcaa-111">下面的示例对此进行了演示。</span><span class="sxs-lookup"><span data-stu-id="dfcaa-111">The following example illustrates this.</span></span>  
  
```vb  
Dim mySystem As systemInfo  
ReDim mySystem.diskDrives(3)  
mySystem.diskDrives(0) = "1.44 MB"  
```  
  
 <span data-ttu-id="dfcaa-112">您还可以声明结构数组。</span><span class="sxs-lookup"><span data-stu-id="dfcaa-112">You can also declare an array of structures.</span></span> <span data-ttu-id="dfcaa-113">下面的示例对此进行了演示。</span><span class="sxs-lookup"><span data-stu-id="dfcaa-113">The following example illustrates this.</span></span>  
  
```vb  
Dim allSystems(100) As systemInfo  
```  
  
 <span data-ttu-id="dfcaa-114">您可以遵循相同的规则来访问此数据体系结构的组件。</span><span class="sxs-lookup"><span data-stu-id="dfcaa-114">You follow the same rules to access the components of this data architecture.</span></span> <span data-ttu-id="dfcaa-115">下面的示例对此进行了演示。</span><span class="sxs-lookup"><span data-stu-id="dfcaa-115">The following example illustrates this.</span></span>  
  
```vb  
ReDim allSystems(5).diskDrives(3)  
allSystems(5).CPU = "386SX"  
allSystems(5).diskDrives(2) = "100M SCSI"  
```  
  
## <a name="structures-and-objects"></a><span data-ttu-id="dfcaa-116">结构和对象</span><span class="sxs-lookup"><span data-stu-id="dfcaa-116">Structures and Objects</span></span>  
 <span data-ttu-id="dfcaa-117">结构可以包含对象作为其一个或多个元素。</span><span class="sxs-lookup"><span data-stu-id="dfcaa-117">A structure can contain an object as one or more of its elements.</span></span> <span data-ttu-id="dfcaa-118">下面的示例对此进行了演示。</span><span class="sxs-lookup"><span data-stu-id="dfcaa-118">The following example illustrates this.</span></span>  
  
```vb  
Protected Structure userInput  
    Public userName As String  
    Public inputForm As System.Windows.Forms.Form  
    Public userFileNumber As Integer  
End Structure  
```  
  
 <span data-ttu-id="dfcaa-119">应在此类声明中使用特定对象类，而不是`Object`。</span><span class="sxs-lookup"><span data-stu-id="dfcaa-119">You should use a specific object class in such a declaration, rather than `Object`.</span></span>  
  
## <a name="structures-and-procedures"></a><span data-ttu-id="dfcaa-120">结构和程序</span><span class="sxs-lookup"><span data-stu-id="dfcaa-120">Structures and Procedures</span></span>  
 <span data-ttu-id="dfcaa-121">可以将结构作为过程参数传递。</span><span class="sxs-lookup"><span data-stu-id="dfcaa-121">You can pass a structure as a procedure argument.</span></span> <span data-ttu-id="dfcaa-122">下面的示例对此进行了演示。</span><span class="sxs-lookup"><span data-stu-id="dfcaa-122">The following example illustrates this.</span></span>  
  
```vb  
Public currentCPUName As String = "700MHz Pentium compatible"  
Public currentMemorySize As Long = 256  
Public Sub fillSystem(ByRef someSystem As systemInfo)  
    someSystem.cPU = currentCPUName  
    someSystem.memory = currentMemorySize  
    someSystem.purchaseDate = Now  
End Sub  
```  
  
 <span data-ttu-id="dfcaa-123">前面的示例*通过 引用*传递结构，这允许过程修改其元素，以便更改在调用代码中生效。</span><span class="sxs-lookup"><span data-stu-id="dfcaa-123">The preceding example passes the structure *by reference*, which allows the procedure to modify its elements so that the changes take effect in the calling code.</span></span> <span data-ttu-id="dfcaa-124">如果要保护结构免受此类修改，则按值传递它。</span><span class="sxs-lookup"><span data-stu-id="dfcaa-124">If you want to protect a structure against such modification, pass it by value.</span></span>  
  
 <span data-ttu-id="dfcaa-125">您还可以从`Function`过程返回结构。</span><span class="sxs-lookup"><span data-stu-id="dfcaa-125">You can also return a structure from a `Function` procedure.</span></span> <span data-ttu-id="dfcaa-126">下面的示例对此进行了演示。</span><span class="sxs-lookup"><span data-stu-id="dfcaa-126">The following example illustrates this.</span></span>  
  
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
  
## <a name="structures-within-structures"></a><span data-ttu-id="dfcaa-127">结构内部的结构</span><span class="sxs-lookup"><span data-stu-id="dfcaa-127">Structures Within Structures</span></span>  
 <span data-ttu-id="dfcaa-128">结构可以包含其他结构。</span><span class="sxs-lookup"><span data-stu-id="dfcaa-128">Structures can contain other structures.</span></span> <span data-ttu-id="dfcaa-129">下面的示例对此进行了演示。</span><span class="sxs-lookup"><span data-stu-id="dfcaa-129">The following example illustrates this.</span></span>  
  
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
  
 <span data-ttu-id="dfcaa-130">您还可以使用此技术封装在不同模块中定义的结构中一个模块中定义的结构。</span><span class="sxs-lookup"><span data-stu-id="dfcaa-130">You can also use this technique to encapsulate a structure defined in one module within a structure defined in a different module.</span></span>  
  
 <span data-ttu-id="dfcaa-131">结构可以包含任意深度的其他结构。</span><span class="sxs-lookup"><span data-stu-id="dfcaa-131">Structures can contain other structures to an arbitrary depth.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfcaa-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dfcaa-132">See also</span></span>

- [<span data-ttu-id="dfcaa-133">数据类型</span><span class="sxs-lookup"><span data-stu-id="dfcaa-133">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="dfcaa-134">基本数据类型</span><span class="sxs-lookup"><span data-stu-id="dfcaa-134">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [<span data-ttu-id="dfcaa-135">复合数据类型</span><span class="sxs-lookup"><span data-stu-id="dfcaa-135">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [<span data-ttu-id="dfcaa-136">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="dfcaa-136">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="dfcaa-137">结构</span><span class="sxs-lookup"><span data-stu-id="dfcaa-137">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="dfcaa-138">数据类型疑难解答</span><span class="sxs-lookup"><span data-stu-id="dfcaa-138">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="dfcaa-139">如何：声明结构</span><span class="sxs-lookup"><span data-stu-id="dfcaa-139">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="dfcaa-140">结构变量</span><span class="sxs-lookup"><span data-stu-id="dfcaa-140">Structure Variables</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structure-variables.md)
- [<span data-ttu-id="dfcaa-141">结构和类</span><span class="sxs-lookup"><span data-stu-id="dfcaa-141">Structures and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
- [<span data-ttu-id="dfcaa-142">Structure 语句</span><span class="sxs-lookup"><span data-stu-id="dfcaa-142">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
