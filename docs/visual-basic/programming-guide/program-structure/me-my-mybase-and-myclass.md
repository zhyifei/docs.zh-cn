---
title: Visual Basic 中的 Me、My、MyBase 和 MyClass
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
ms.openlocfilehash: a8df6e48fd5bce9bb28d8aef7e031f36741ad0ad
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "58813387"
---
# <a name="me-my-mybase-and-myclass-in-visual-basic"></a><span data-ttu-id="5c8b8-102">Visual Basic 中的 Me、My、MyBase 和 MyClass</span><span class="sxs-lookup"><span data-stu-id="5c8b8-102">Me, My, MyBase, and MyClass in Visual Basic</span></span>
<span data-ttu-id="5c8b8-103">`Me``My`， `MyBase`，和`MyClass`在 Visual Basic 中具有类似名称，但不同的用途。</span><span class="sxs-lookup"><span data-stu-id="5c8b8-103">`Me`, `My`, `MyBase`, and `MyClass` in Visual Basic have similar names, but different purposes.</span></span> <span data-ttu-id="5c8b8-104">本主题介绍上述每个实体以将它们区分开来。</span><span class="sxs-lookup"><span data-stu-id="5c8b8-104">This topic describes each of these entities in order to distinguish them.</span></span>  
  
## <a name="me"></a><span data-ttu-id="5c8b8-105">Me</span><span class="sxs-lookup"><span data-stu-id="5c8b8-105">Me</span></span>  
 <span data-ttu-id="5c8b8-106">`Me`关键字提供了一种方法来指代类或当前正在其中执行代码的结构的特定实例。</span><span class="sxs-lookup"><span data-stu-id="5c8b8-106">The `Me` keyword provides a way to refer to the specific instance of a class or structure in which the code is currently executing.</span></span> <span data-ttu-id="5c8b8-107">`Me` 行为类似于的对象变量或结构变量引用当前实例。</span><span class="sxs-lookup"><span data-stu-id="5c8b8-107">`Me` behaves like either an object variable or a structure variable referring to the current instance.</span></span> <span data-ttu-id="5c8b8-108">使用`Me`特别适合将类或结构的当前正在执行的实例的信息传递给另一个类、 结构或模块中的过程。</span><span class="sxs-lookup"><span data-stu-id="5c8b8-108">Using `Me` is particularly useful for passing information about the currently executing instance of a class or structure to a procedure in another class, structure, or module.</span></span>  
  
 <span data-ttu-id="5c8b8-109">例如，假设在模块中有下面的过程。</span><span class="sxs-lookup"><span data-stu-id="5c8b8-109">For example, suppose you have the following procedure in a module.</span></span>  
  
```  
Sub ChangeFormColor(FormName As Form)  
   Randomize()  
   FormName.BackColor = Color.FromArgb(Rnd() * 256, Rnd() * 256, Rnd() * 256)  
End Sub  
```  
  
 <span data-ttu-id="5c8b8-110">可以调用此过程，并将传递的当前实例<xref:System.Windows.Forms.Form>作为通过使用以下语句参数的类。</span><span class="sxs-lookup"><span data-stu-id="5c8b8-110">You can call this procedure and pass the current instance of the <xref:System.Windows.Forms.Form> class as an argument by using the following statement.</span></span>  
  
```  
ChangeFormColor(Me)  
```  
  
## <a name="my"></a><span data-ttu-id="5c8b8-111">My</span><span class="sxs-lookup"><span data-stu-id="5c8b8-111">My</span></span>  
 <span data-ttu-id="5c8b8-112">`My`功能提供对许多比较容易、 直观访问[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]类，使 Visual Basic 用户与计算机、 应用程序、 设置、 资源等进行交互。</span><span class="sxs-lookup"><span data-stu-id="5c8b8-112">The `My` feature provides easy and intuitive access to a number of [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] classes, enabling the Visual Basic user to interact with the computer, application, settings, resources, and so on.</span></span>  
  
## <a name="mybase"></a><span data-ttu-id="5c8b8-113">MyBase</span><span class="sxs-lookup"><span data-stu-id="5c8b8-113">MyBase</span></span>  
 <span data-ttu-id="5c8b8-114">`MyBase`关键字的行为类似于一个类的当前实例的基类引用的对象变量。</span><span class="sxs-lookup"><span data-stu-id="5c8b8-114">The `MyBase` keyword behaves like an object variable referring to the base class of the current instance of a class.</span></span> <span data-ttu-id="5c8b8-115">`MyBase` 通常用于访问基类成员被重写或派生类中被隐藏。</span><span class="sxs-lookup"><span data-stu-id="5c8b8-115">`MyBase` is commonly used to access base class members that are overridden or shadowed in a derived class.</span></span> <span data-ttu-id="5c8b8-116">`MyBase.New` 用于从派生的类构造函数中显式调用基类构造函数。</span><span class="sxs-lookup"><span data-stu-id="5c8b8-116">`MyBase.New` is used to explicitly call a base class constructor from a derived class constructor.</span></span>  
  
## <a name="myclass"></a><span data-ttu-id="5c8b8-117">MyClass</span><span class="sxs-lookup"><span data-stu-id="5c8b8-117">MyClass</span></span>  
 <span data-ttu-id="5c8b8-118">`MyClass`关键字的行为类似于与最初实现的类的当前实例引用的对象变量。</span><span class="sxs-lookup"><span data-stu-id="5c8b8-118">The `MyClass` keyword behaves like an object variable referring to the current instance of a class as originally implemented.</span></span> <span data-ttu-id="5c8b8-119">`MyClass` 类似于`Me`，但方法是在其上的所有方法调用都被都看作`NotOverridable`。</span><span class="sxs-lookup"><span data-stu-id="5c8b8-119">`MyClass` is similar to `Me`, but all method calls on it are treated as if the method were `NotOverridable`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c8b8-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="5c8b8-120">See also</span></span>

- [<span data-ttu-id="5c8b8-121">继承的基础知识</span><span class="sxs-lookup"><span data-stu-id="5c8b8-121">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
