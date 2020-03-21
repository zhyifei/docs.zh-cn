---
title: Me、My、MyBase 和 MyClass
ms.date: 07/20/2015
f1_keywords:
- MyClass
- vb.Me
- MyBase
- vb.MyBase
- Me
- vb.MyClass
- vb.This
- vb.My
helpviewer_keywords:
- My object
- self-reference [Visual Basic], Me keyword
- MyClass keyword [Visual Basic], relationship to similar programming elements
- Me keyword [Visual Basic], relationship to similar programming elements
- Me keyword [Visual Basic], referring to the current instance of an object
- Me keyword [Visual Basic]
- self-reference
- current instance [Visual Basic], Me keyword
- MyBase keyword [Visual Basic], relationship to similar programming elements
ms.assetid: f8e241ae-b1ed-4886-9aa0-08c632154029
ms.openlocfilehash: a21dfeb12e8d99f5f8b8afede084846711c299ab
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401429"
---
# <a name="me-my-mybase-and-myclass-in-visual-basic"></a><span data-ttu-id="99f8d-102">Visual Basic 中的 Me、My、MyBase 和 MyClass</span><span class="sxs-lookup"><span data-stu-id="99f8d-102">Me, My, MyBase, and MyClass in Visual Basic</span></span>
<span data-ttu-id="99f8d-103">`Me`、`My``MyBase`和`MyClass`在 Visual Basic 中具有相似的名称，但目的不同。</span><span class="sxs-lookup"><span data-stu-id="99f8d-103">`Me`, `My`, `MyBase`, and `MyClass` in Visual Basic have similar names, but different purposes.</span></span> <span data-ttu-id="99f8d-104">本主题介绍每个实体，以便区分它们。</span><span class="sxs-lookup"><span data-stu-id="99f8d-104">This topic describes each of these entities in order to distinguish them.</span></span>  
  
## <a name="me"></a><span data-ttu-id="99f8d-105">我</span><span class="sxs-lookup"><span data-stu-id="99f8d-105">Me</span></span>  
 <span data-ttu-id="99f8d-106">关键字`Me`提供了一种引用代码当前正在执行的类或结构的特定实例的方法。</span><span class="sxs-lookup"><span data-stu-id="99f8d-106">The `Me` keyword provides a way to refer to the specific instance of a class or structure in which the code is currently executing.</span></span> <span data-ttu-id="99f8d-107">`Me`其活动类似于对象变量或引用当前实例的结构变量。</span><span class="sxs-lookup"><span data-stu-id="99f8d-107">`Me` behaves like either an object variable or a structure variable referring to the current instance.</span></span> <span data-ttu-id="99f8d-108">使用`Me`对于将有关类或结构当前执行实例的信息传递给另一个类、结构或模块中的过程特别有用。</span><span class="sxs-lookup"><span data-stu-id="99f8d-108">Using `Me` is particularly useful for passing information about the currently executing instance of a class or structure to a procedure in another class, structure, or module.</span></span>  
  
 <span data-ttu-id="99f8d-109">例如，假设您在模块中具有以下过程。</span><span class="sxs-lookup"><span data-stu-id="99f8d-109">For example, suppose you have the following procedure in a module.</span></span>  
  
```vb  
Sub ChangeFormColor(FormName As Form)  
   Randomize()  
   FormName.BackColor = Color.FromArgb(Rnd() * 256, Rnd() * 256, Rnd() * 256)  
End Sub  
```  
  
 <span data-ttu-id="99f8d-110">可以使用以下语句调用此过程并将<xref:System.Windows.Forms.Form>类的当前实例作为参数传递。</span><span class="sxs-lookup"><span data-stu-id="99f8d-110">You can call this procedure and pass the current instance of the <xref:System.Windows.Forms.Form> class as an argument by using the following statement.</span></span>  
  
```vb  
ChangeFormColor(Me)  
```  
  
## <a name="my"></a><span data-ttu-id="99f8d-111">My</span><span class="sxs-lookup"><span data-stu-id="99f8d-111">My</span></span>  
 <span data-ttu-id="99f8d-112">此功能`My`提供了对许多 .NET Framework 类的轻松直观访问，使 Visual Basic 用户能够与计算机、应用程序、设置、资源等进行交互。</span><span class="sxs-lookup"><span data-stu-id="99f8d-112">The `My` feature provides easy and intuitive access to a number of .NET Framework classes, enabling the Visual Basic user to interact with the computer, application, settings, resources, and so on.</span></span>  
  
## <a name="mybase"></a><span data-ttu-id="99f8d-113">MyBase</span><span class="sxs-lookup"><span data-stu-id="99f8d-113">MyBase</span></span>  
 <span data-ttu-id="99f8d-114">关键字`MyBase`的作用类似于引用类当前实例的基类的对象变量。</span><span class="sxs-lookup"><span data-stu-id="99f8d-114">The `MyBase` keyword behaves like an object variable referring to the base class of the current instance of a class.</span></span> <span data-ttu-id="99f8d-115">`MyBase`通常用于访问派生类中重写或隐藏基类成员。</span><span class="sxs-lookup"><span data-stu-id="99f8d-115">`MyBase` is commonly used to access base class members that are overridden or shadowed in a derived class.</span></span> <span data-ttu-id="99f8d-116">`MyBase.New`用于从派生类构造函数显式调用基类构造函数。</span><span class="sxs-lookup"><span data-stu-id="99f8d-116">`MyBase.New` is used to explicitly call a base class constructor from a derived class constructor.</span></span>  
  
## <a name="myclass"></a><span data-ttu-id="99f8d-117">MyClass</span><span class="sxs-lookup"><span data-stu-id="99f8d-117">MyClass</span></span>  
 <span data-ttu-id="99f8d-118">关键字`MyClass`的作用类似于一个对象变量，它引用最初实现的类的当前实例。</span><span class="sxs-lookup"><span data-stu-id="99f8d-118">The `MyClass` keyword behaves like an object variable referring to the current instance of a class as originally implemented.</span></span> <span data-ttu-id="99f8d-119">`MyClass`与 类似`Me`，但上它的所有方法调用都被视为方法为`NotOverridable`。</span><span class="sxs-lookup"><span data-stu-id="99f8d-119">`MyClass` is similar to `Me`, but all method calls on it are treated as if the method were `NotOverridable`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99f8d-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="99f8d-120">See also</span></span>

- [<span data-ttu-id="99f8d-121">继承的基础知识</span><span class="sxs-lookup"><span data-stu-id="99f8d-121">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
