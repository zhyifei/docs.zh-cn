---
title: 如何：访问对象 (Visual Basic 中) 的成员
ms.date: 07/20/2015
helpviewer_keywords:
- members [Visual Basic], accessing
- object variables [Visual Basic], accessing members
ms.assetid: a0072514-6a79-4dd6-8d03-ca8c13e61ddc
ms.openlocfilehash: 5e91f1b99a17f4bbdc65a77ab26050ee57e96ac4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54724838"
---
# <a name="how-to-access-members-of-an-object-visual-basic"></a><span data-ttu-id="f99e3-102">如何：访问对象 (Visual Basic 中) 的成员</span><span class="sxs-lookup"><span data-stu-id="f99e3-102">How to: Access Members of an Object (Visual Basic)</span></span>
<span data-ttu-id="f99e3-103">引用的对象的对象变量后，你通常想要与该对象，例如其方法、 属性、 字段和事件的成员。</span><span class="sxs-lookup"><span data-stu-id="f99e3-103">When you have an object variable that refers to an object, you often want to work with the members of that object, such as its methods, properties, fields, and events.</span></span> <span data-ttu-id="f99e3-104">例如，一次创建一个新<xref:System.Windows.Forms.Form>对象，你可能想要设置其<xref:System.Windows.Forms.Control.Text%2A>属性或调用其<xref:System.Windows.Forms.Control.Focus%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="f99e3-104">For example, once you have created a new <xref:System.Windows.Forms.Form> object, you might want to set its <xref:System.Windows.Forms.Control.Text%2A> property or call its <xref:System.Windows.Forms.Control.Focus%2A> method.</span></span>  
  
## <a name="accessing-members"></a><span data-ttu-id="f99e3-105">成员访问</span><span class="sxs-lookup"><span data-stu-id="f99e3-105">Accessing Members</span></span>  
 <span data-ttu-id="f99e3-106">通过对引用该变量访问对象的成员。</span><span class="sxs-lookup"><span data-stu-id="f99e3-106">You access an object's members through the variable that refers to it.</span></span>  
  
#### <a name="to-access-members-of-an-object"></a><span data-ttu-id="f99e3-107">若要访问对象的成员</span><span class="sxs-lookup"><span data-stu-id="f99e3-107">To access members of an object</span></span>  
  
-   <span data-ttu-id="f99e3-108">使用成员访问运算符 (`.`) 之间的对象变量名称和成员名称。</span><span class="sxs-lookup"><span data-stu-id="f99e3-108">Use the member-access operator (`.`) between the object variable name and the member name.</span></span>  
  
    ```  
    currentText = newForm.Text  
    ```  
  
     <span data-ttu-id="f99e3-109">如果该成员是[共享](../../../../visual-basic/language-reference/modifiers/shared.md)，不需要一个变量来访问它。</span><span class="sxs-lookup"><span data-stu-id="f99e3-109">If the member is [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), you do not need a variable to access it.</span></span>  
  
## <a name="accessing-members-of-an-object-of-known-type"></a><span data-ttu-id="f99e3-110">已知类型的对象的成员访问</span><span class="sxs-lookup"><span data-stu-id="f99e3-110">Accessing Members of an Object of Known Type</span></span>  
 <span data-ttu-id="f99e3-111">如果在编译时知道对象的类型，则可以使用*早期绑定*指的是它的变量。</span><span class="sxs-lookup"><span data-stu-id="f99e3-111">If you know the type of an object at compile time, you can use *early binding* for a variable that refers to it.</span></span>  
  
#### <a name="to-access-members-of-an-object-for-which-you-know-the-type-at-compile-time"></a><span data-ttu-id="f99e3-112">若要访问的对象，您知道该类型在编译时成员</span><span class="sxs-lookup"><span data-stu-id="f99e3-112">To access members of an object for which you know the type at compile time</span></span>  
  
1.  <span data-ttu-id="f99e3-113">你想要分配给该变量的对象类型的对象变量声明。</span><span class="sxs-lookup"><span data-stu-id="f99e3-113">Declare the object variable to be of the type of the object you intend to assign to the variable.</span></span>  
  
    ```  
    Dim extraForm As System.Windows.Forms.Form  
    ```  
  
     <span data-ttu-id="f99e3-114">与`Option Strict On`，可以仅将分配<xref:System.Windows.Forms.Form>对象 (或类型的对象派生自<xref:System.Windows.Forms.Form>) 到`extraForm`。</span><span class="sxs-lookup"><span data-stu-id="f99e3-114">With `Option Strict On`, you can assign only <xref:System.Windows.Forms.Form> objects (or objects of a type derived from <xref:System.Windows.Forms.Form>) to `extraForm`.</span></span> <span data-ttu-id="f99e3-115">如果已定义的类或结构优先于具有拓宽`CType`转换为<xref:System.Windows.Forms.Form>，还可以将该类或结构`extraForm`。</span><span class="sxs-lookup"><span data-stu-id="f99e3-115">If you have defined a class or structure with a widening `CType` conversion to <xref:System.Windows.Forms.Form>, you can also assign that class or structure to `extraForm`.</span></span>  
  
2.  <span data-ttu-id="f99e3-116">使用成员访问运算符 (`.`) 之间的对象变量名称和成员名称。</span><span class="sxs-lookup"><span data-stu-id="f99e3-116">Use the member-access operator (`.`) between the object variable name and the member name.</span></span>  
  
    ```  
    extraForm.Show()  
    ```  
  
     <span data-ttu-id="f99e3-117">您可以访问的所有方法和属性特定于<xref:System.Windows.Forms.Form>类，无论什么`Option Strict`设置。</span><span class="sxs-lookup"><span data-stu-id="f99e3-117">You can access all of the methods and properties specific to the <xref:System.Windows.Forms.Form> class, no matter what the `Option Strict` setting is.</span></span>  
  
## <a name="accessing-members-of-an-object-of-unknown-type"></a><span data-ttu-id="f99e3-118">未知类型的对象的成员访问</span><span class="sxs-lookup"><span data-stu-id="f99e3-118">Accessing Members of an Object of Unknown Type</span></span>  
 <span data-ttu-id="f99e3-119">如果在编译时不知道对象的类型，则必须使用*后期绑定*它是指任何变量。</span><span class="sxs-lookup"><span data-stu-id="f99e3-119">If you do not know the type of an object at compile time, you must use *late binding* for any variable that refers to it.</span></span>  
  
#### <a name="to-access-members-of-an-object-for-which-you-do-not-know-the-type-at-compile-time"></a><span data-ttu-id="f99e3-120">若要访问的对象为其您不知道该类型在编译时成员</span><span class="sxs-lookup"><span data-stu-id="f99e3-120">To access members of an object for which you do not know the type at compile time</span></span>  
  
1.  <span data-ttu-id="f99e3-121">对象变量的声明[Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)。</span><span class="sxs-lookup"><span data-stu-id="f99e3-121">Declare the object variable to be of the [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md).</span></span> <span data-ttu-id="f99e3-122">(声明一个变量，作为`Object`等同于其声明为<xref:System.Object?displayProperty=nameWithType>。)</span><span class="sxs-lookup"><span data-stu-id="f99e3-122">(Declaring a variable as `Object` is the same as declaring it as <xref:System.Object?displayProperty=nameWithType>.)</span></span>  
  
    ```  
    Dim someControl As Object  
    ```  
  
     <span data-ttu-id="f99e3-123">与`Option Strict On`，可以访问成员上定义的<xref:System.Object>类。</span><span class="sxs-lookup"><span data-stu-id="f99e3-123">With `Option Strict On`, you can access only the members that are defined on the <xref:System.Object> class.</span></span>  
  
2.  <span data-ttu-id="f99e3-124">使用成员访问运算符 (`.`) 之间的对象变量名称和成员名称。</span><span class="sxs-lookup"><span data-stu-id="f99e3-124">Use the member-access operator (`.`) between the object variable name and the member name.</span></span>  
  
    ```  
    someControl.GetType()  
    ```  
  
     <span data-ttu-id="f99e3-125">若要能够访问分配给对象变量的任何对象的成员，必须设置`Option Strict Off`。</span><span class="sxs-lookup"><span data-stu-id="f99e3-125">To be able to access the members of any object you assign to the object variable, you must set `Option Strict Off`.</span></span> <span data-ttu-id="f99e3-126">当执行此操作时，编译器无法保证给定的成员由分配给变量的对象。</span><span class="sxs-lookup"><span data-stu-id="f99e3-126">When you do this, the compiler cannot guarantee that a given member is exposed by the object you assign to the variable.</span></span> <span data-ttu-id="f99e3-127">如果对象未公开的成员尝试访问，<xref:System.MemberAccessException>会发生异常。</span><span class="sxs-lookup"><span data-stu-id="f99e3-127">If the object does not expose a member you attempt to access, a <xref:System.MemberAccessException> exception occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f99e3-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="f99e3-128">See also</span></span>
- <xref:System.Object>
- <xref:System.Windows.Forms.Form>
- <xref:System.MemberAccessException>
- [<span data-ttu-id="f99e3-129">对象变量</span><span class="sxs-lookup"><span data-stu-id="f99e3-129">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="f99e3-130">对象变量声明</span><span class="sxs-lookup"><span data-stu-id="f99e3-130">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [<span data-ttu-id="f99e3-131">Object 数据类型</span><span class="sxs-lookup"><span data-stu-id="f99e3-131">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="f99e3-132">Option Strict 语句</span><span class="sxs-lookup"><span data-stu-id="f99e3-132">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
