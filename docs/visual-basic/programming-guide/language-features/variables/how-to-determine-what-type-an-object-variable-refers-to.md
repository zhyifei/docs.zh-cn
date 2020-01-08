---
title: 如何：确定对象变量引用的类型
ms.date: 07/20/2015
helpviewer_keywords:
- TypeOf operator [Visual Basic], determining object variable type
- variables [Visual Basic], object
- object variables [Visual Basic], determining type
ms.assetid: 6f6a138d-58a4-40d1-9f4e-0a3c598eaf81
ms.openlocfilehash: b3778a170759f685db78e7dcde219138196f9eca
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344199"
---
# <a name="how-to-determine-what-type-an-object-variable-refers-to-visual-basic"></a><span data-ttu-id="a4fa2-102">如何：确定对象变量引用的类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a4fa2-102">How to: Determine What Type an Object Variable Refers To (Visual Basic)</span></span>

<span data-ttu-id="a4fa2-103">对象变量包含指向存储在其他位置的数据的指针。</span><span class="sxs-lookup"><span data-stu-id="a4fa2-103">An object variable contains a pointer to data that is stored elsewhere.</span></span> <span data-ttu-id="a4fa2-104">该数据的类型在运行时可能会更改。</span><span class="sxs-lookup"><span data-stu-id="a4fa2-104">The type of that data can change during run time.</span></span> <span data-ttu-id="a4fa2-105">随时都可以使用 <xref:System.Type.GetTypeCode%2A> 方法来确定当前运行时类型，或使用[TypeOf 运算符](../../../../visual-basic/language-reference/operators/typeof-operator.md)来确定当前运行时类型是否与指定的类型兼容。</span><span class="sxs-lookup"><span data-stu-id="a4fa2-105">At any moment, you can use the <xref:System.Type.GetTypeCode%2A> method to determine the current run-time type, or the [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md) to find out if the current run-time type is compatible with a specified type.</span></span>

### <a name="to-determine-the-exact-type-an-object-variable-currently-refers-to"></a><span data-ttu-id="a4fa2-106">确定对象变量当前所引用的确切类型</span><span class="sxs-lookup"><span data-stu-id="a4fa2-106">To determine the exact type an object variable currently refers to</span></span>

1. <span data-ttu-id="a4fa2-107">在对象变量上，调用 <xref:System.Object.GetType%2A> 方法检索 <xref:System.Type?displayProperty=nameWithType> 对象。</span><span class="sxs-lookup"><span data-stu-id="a4fa2-107">On the object variable, call the <xref:System.Object.GetType%2A> method to retrieve a <xref:System.Type?displayProperty=nameWithType> object.</span></span>

    ```vb
    Dim myObject As Object
    myObject.GetType()
    ```

2. <span data-ttu-id="a4fa2-108">在 <xref:System.Type?displayProperty=nameWithType> 类上，调用共享方法 <xref:System.Type.GetTypeCode%2A> 以检索该对象的类型的 <xref:System.TypeCode> 枚举值。</span><span class="sxs-lookup"><span data-stu-id="a4fa2-108">On the <xref:System.Type?displayProperty=nameWithType> class, call the shared method <xref:System.Type.GetTypeCode%2A> to retrieve the <xref:System.TypeCode> enumeration value for the object's type.</span></span>

    ```vb
    Dim myObject As Object
    Dim datTyp As Integer = Type.GetTypeCode(myObject.GetType())
    MsgBox("myObject currently has type code " & CStr(datTyp))
    ```

    <span data-ttu-id="a4fa2-109">您可以根据所需的任何枚举成员（如 `Double`）测试 <xref:System.TypeCode> 枚举值。</span><span class="sxs-lookup"><span data-stu-id="a4fa2-109">You can test the <xref:System.TypeCode> enumeration value against whichever enumeration members are of interest, such as `Double`.</span></span>

### <a name="to-determine-whether-an-object-variables-type-is-compatible-with-a-specified-type"></a><span data-ttu-id="a4fa2-110">确定对象变量的类型是否与指定的类型兼容</span><span class="sxs-lookup"><span data-stu-id="a4fa2-110">To determine whether an object variable's type is compatible with a specified type</span></span>

- <span data-ttu-id="a4fa2-111">结合使用 `TypeOf` 运算符和[Is 运算符](../../../../visual-basic/language-reference/operators/is-operator.md)来测试具有 `TypeOf`...`Is` 表达式的对象。</span><span class="sxs-lookup"><span data-stu-id="a4fa2-111">Use the `TypeOf` operator in combination with the [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) to test the object with a `TypeOf`...`Is` expression.</span></span>

    ```vb
    If TypeOf objA Is System.Windows.Forms.Control Then
        MsgBox("objA is compatible with the Control class")
    End If
    ```

    <span data-ttu-id="a4fa2-112">`TypeOf`...如果对象的运行时类型与指定的类型兼容, 则表达式返回`True`。 `Is`</span><span class="sxs-lookup"><span data-stu-id="a4fa2-112">The `TypeOf`...`Is` expression returns `True` if the object's run-time type is compatible with the specified type.</span></span>

    <span data-ttu-id="a4fa2-113">兼容性的条件取决于指定的类型是类、结构还是接口。</span><span class="sxs-lookup"><span data-stu-id="a4fa2-113">The criterion for compatibility depends on whether the specified type is a class, structure, or interface.</span></span> <span data-ttu-id="a4fa2-114">通常，如果对象的类型与、继承自或实现指定的类型，则类型是兼容的。</span><span class="sxs-lookup"><span data-stu-id="a4fa2-114">In general, the types are compatible if the object is of the same type as, inherits from, or implements the specified type.</span></span> <span data-ttu-id="a4fa2-115">有关详细信息，请参阅[TypeOf 运算符](../../../../visual-basic/language-reference/operators/typeof-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="a4fa2-115">For more information, see [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md).</span></span>

## <a name="compile-the-code"></a><span data-ttu-id="a4fa2-116">编译代码</span><span class="sxs-lookup"><span data-stu-id="a4fa2-116">Compile the code</span></span>

<span data-ttu-id="a4fa2-117">请注意，指定的类型不能为变量或表达式。</span><span class="sxs-lookup"><span data-stu-id="a4fa2-117">Note that the specified type cannot be a variable or expression.</span></span> <span data-ttu-id="a4fa2-118">它必须是已定义类型的名称，如类、结构或接口。</span><span class="sxs-lookup"><span data-stu-id="a4fa2-118">It must be the name of a defined type, such as a class, structure, or interface.</span></span> <span data-ttu-id="a4fa2-119">这包括内部类型（如 `Integer` 和 `String`）。</span><span class="sxs-lookup"><span data-stu-id="a4fa2-119">This includes intrinsic types such as `Integer` and `String`.</span></span>

## <a name="see-also"></a><span data-ttu-id="a4fa2-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a4fa2-120">See also</span></span>

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.GetTypeCode%2A>
- <xref:System.TypeCode>
- [<span data-ttu-id="a4fa2-121">对象变量</span><span class="sxs-lookup"><span data-stu-id="a4fa2-121">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="a4fa2-122">对象变量值</span><span class="sxs-lookup"><span data-stu-id="a4fa2-122">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [<span data-ttu-id="a4fa2-123">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="a4fa2-123">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
