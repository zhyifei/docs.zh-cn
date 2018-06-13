---
title: 如何：确定对象变量引用的类型 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- TypeOf operator [Visual Basic], determining object variable type
- variables [Visual Basic], object
- object variables [Visual Basic], determining type
ms.assetid: 6f6a138d-58a4-40d1-9f4e-0a3c598eaf81
ms.openlocfilehash: 0dfd4ed87b65f536802ae71cbc3de41e1c4f83af
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33651309"
---
# <a name="how-to-determine-what-type-an-object-variable-refers-to-visual-basic"></a><span data-ttu-id="11f52-102">如何：确定对象变量引用的类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="11f52-102">How to: Determine What Type an Object Variable Refers To (Visual Basic)</span></span>
<span data-ttu-id="11f52-103">对象变量包含指向存储在其他位置的数据的指针。</span><span class="sxs-lookup"><span data-stu-id="11f52-103">An object variable contains a pointer to data that is stored elsewhere.</span></span> <span data-ttu-id="11f52-104">在运行时可以更改该数据的类型。</span><span class="sxs-lookup"><span data-stu-id="11f52-104">The type of that data can change during run time.</span></span> <span data-ttu-id="11f52-105">在任何时刻，你可以使用<xref:System.Type.GetTypeCode%2A>方法来确定当前的运行时类型，或[TypeOf 运算符](../../../../visual-basic/language-reference/operators/typeof-operator.md)若要查明当前运行时类型是否与指定的类型兼容。</span><span class="sxs-lookup"><span data-stu-id="11f52-105">At any moment, you can use the <xref:System.Type.GetTypeCode%2A> method to determine the current run-time type, or the [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md) to find out if the current run-time type is compatible with a specified type.</span></span>  
  
### <a name="to-determine-the-exact-type-an-object-variable-currently-refers-to"></a><span data-ttu-id="11f52-106">若要确定确切类型的对象变量当前引用</span><span class="sxs-lookup"><span data-stu-id="11f52-106">To determine the exact type an object variable currently refers to</span></span>  
  
1.  <span data-ttu-id="11f52-107">对象变量上调用<xref:System.Object.GetType%2A>方法来检索<xref:System.Type?displayProperty=nameWithType>对象。</span><span class="sxs-lookup"><span data-stu-id="11f52-107">On the object variable, call the <xref:System.Object.GetType%2A> method to retrieve a <xref:System.Type?displayProperty=nameWithType> object.</span></span>  
  
    ```  
    Dim myObject As Object  
    myObject.GetType()  
    ```  
  
2.  <span data-ttu-id="11f52-108">上<xref:System.Type?displayProperty=nameWithType>类中，调用共享的方法<xref:System.Type.GetTypeCode%2A>检索<xref:System.TypeCode>对象的类型的枚举值。</span><span class="sxs-lookup"><span data-stu-id="11f52-108">On the <xref:System.Type?displayProperty=nameWithType> class, call the shared method <xref:System.Type.GetTypeCode%2A> to retrieve the <xref:System.TypeCode> enumeration value for the object's type.</span></span>  
  
    ```  
    Dim myObject As Object  
    Dim datTyp As Integer = Type.GetTypeCode(myObject.GetType())  
    MsgBox("myObject currently has type code " & CStr(datTyp))  
    ```  
  
     <span data-ttu-id="11f52-109">你可以测试<xref:System.TypeCode>针对任何枚举成员感兴趣，例如的枚举值`Double`。</span><span class="sxs-lookup"><span data-stu-id="11f52-109">You can test the <xref:System.TypeCode> enumeration value against whichever enumeration members are of interest, such as `Double`.</span></span>  
  
### <a name="to-determine-whether-an-object-variables-type-is-compatible-with-a-specified-type"></a><span data-ttu-id="11f52-110">若要确定是否一个对象变量的类型与指定的类型兼容</span><span class="sxs-lookup"><span data-stu-id="11f52-110">To determine whether an object variable's type is compatible with a specified type</span></span>  
  
-   <span data-ttu-id="11f52-111">使用`TypeOf`结合运算符[Is 运算符](../../../../visual-basic/language-reference/operators/is-operator.md)与对象进行测试`TypeOf`...`Is`表达式。</span><span class="sxs-lookup"><span data-stu-id="11f52-111">Use the `TypeOf` operator in combination with the [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) to test the object with a `TypeOf`...`Is` expression.</span></span>  
  
    ```  
    If TypeOf objA Is System.Windows.Forms.Control Then  
        MsgBox("objA is compatible with the Control class")  
    End If  
    ```  
  
     <span data-ttu-id="11f52-112">`TypeOf`...`Is`表达式返回`True`对象的运行时类型是否与指定的类型兼容。</span><span class="sxs-lookup"><span data-stu-id="11f52-112">The `TypeOf`...`Is` expression returns `True` if the object's run-time type is compatible with the specified type.</span></span>  
  
     <span data-ttu-id="11f52-113">兼容性的条件取决于指定的类型是类、 结构或接口。</span><span class="sxs-lookup"><span data-stu-id="11f52-113">The criterion for compatibility depends on whether the specified type is a class, structure, or interface.</span></span> <span data-ttu-id="11f52-114">一般情况下，则类型是兼容的如果将对象与同一类型、 继承自，或实现指定的类型。</span><span class="sxs-lookup"><span data-stu-id="11f52-114">In general, the types are compatible if the object is of the same type as, inherits from, or implements the specified type.</span></span> <span data-ttu-id="11f52-115">有关详细信息，请参阅[TypeOf 运算符](../../../../visual-basic/language-reference/operators/typeof-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="11f52-115">For more information, see [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="11f52-116">编译代码</span><span class="sxs-lookup"><span data-stu-id="11f52-116">Compiling the Code</span></span>  
 <span data-ttu-id="11f52-117">请注意指定的类型不能为变量或表达式。</span><span class="sxs-lookup"><span data-stu-id="11f52-117">Note that the specified type cannot be a variable or expression.</span></span> <span data-ttu-id="11f52-118">它必须已定义的类型，如类、 结构或接口的名称。</span><span class="sxs-lookup"><span data-stu-id="11f52-118">It must be the name of a defined type, such as a class, structure, or interface.</span></span> <span data-ttu-id="11f52-119">这包括内部类型，如`Integer`和`String`。</span><span class="sxs-lookup"><span data-stu-id="11f52-119">This includes intrinsic types such as `Integer` and `String`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11f52-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="11f52-120">See Also</span></span>  
 <xref:System.Object.GetType%2A>  
 <xref:System.Type?displayProperty=nameWithType>  
 <xref:System.Type.GetTypeCode%2A>  
 <xref:System.TypeCode>  
 [<span data-ttu-id="11f52-121">对象变量</span><span class="sxs-lookup"><span data-stu-id="11f52-121">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [<span data-ttu-id="11f52-122">对象变量值</span><span class="sxs-lookup"><span data-stu-id="11f52-122">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)  
 [<span data-ttu-id="11f52-123">Object 数据类型</span><span class="sxs-lookup"><span data-stu-id="11f52-123">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
