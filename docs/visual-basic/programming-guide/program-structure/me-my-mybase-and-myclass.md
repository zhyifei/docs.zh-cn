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
ms.openlocfilehash: 7df146e09a1d7cd730f4cf539d6823f7ced44bd1
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002530"
---
# <a name="me-my-mybase-and-myclass-in-visual-basic"></a><span data-ttu-id="b8d4c-102">Visual Basic 中的 Me、My、MyBase 和 MyClass</span><span class="sxs-lookup"><span data-stu-id="b8d4c-102">Me, My, MyBase, and MyClass in Visual Basic</span></span>
<span data-ttu-id="b8d4c-103">`Me`、`My`、`MyBase` 和 Visual Basic 中的 @no__t 为类似的名称，但用途不同。</span><span class="sxs-lookup"><span data-stu-id="b8d4c-103">`Me`, `My`, `MyBase`, and `MyClass` in Visual Basic have similar names, but different purposes.</span></span> <span data-ttu-id="b8d4c-104">本主题将介绍其中的每个实体，以便将它们区分开来。</span><span class="sxs-lookup"><span data-stu-id="b8d4c-104">This topic describes each of these entities in order to distinguish them.</span></span>  
  
## <a name="me"></a><span data-ttu-id="b8d4c-105">Me</span><span class="sxs-lookup"><span data-stu-id="b8d4c-105">Me</span></span>  
 <span data-ttu-id="b8d4c-106">@No__t 关键字提供了一种方法，用于引用当前正在执行代码的类或结构的特定实例。</span><span class="sxs-lookup"><span data-stu-id="b8d4c-106">The `Me` keyword provides a way to refer to the specific instance of a class or structure in which the code is currently executing.</span></span> <span data-ttu-id="b8d4c-107">`Me` 的行为类似于引用当前实例的对象变量或结构变量。</span><span class="sxs-lookup"><span data-stu-id="b8d4c-107">`Me` behaves like either an object variable or a structure variable referring to the current instance.</span></span> <span data-ttu-id="b8d4c-108">在将有关当前正在执行的类或结构实例的信息传递到另一个类、结构或模块中的过程时，使用 @no__t。</span><span class="sxs-lookup"><span data-stu-id="b8d4c-108">Using `Me` is particularly useful for passing information about the currently executing instance of a class or structure to a procedure in another class, structure, or module.</span></span>  
  
 <span data-ttu-id="b8d4c-109">例如，假设你在模块中具有以下过程。</span><span class="sxs-lookup"><span data-stu-id="b8d4c-109">For example, suppose you have the following procedure in a module.</span></span>  
  
```vb  
Sub ChangeFormColor(FormName As Form)  
   Randomize()  
   FormName.BackColor = Color.FromArgb(Rnd() * 256, Rnd() * 256, Rnd() * 256)  
End Sub  
```  
  
 <span data-ttu-id="b8d4c-110">可以调用此过程，并使用以下语句将 @no__t 0 类的当前实例作为参数传递。</span><span class="sxs-lookup"><span data-stu-id="b8d4c-110">You can call this procedure and pass the current instance of the <xref:System.Windows.Forms.Form> class as an argument by using the following statement.</span></span>  
  
```vb  
ChangeFormColor(Me)  
```  
  
## <a name="my"></a><span data-ttu-id="b8d4c-111">My</span><span class="sxs-lookup"><span data-stu-id="b8d4c-111">My</span></span>  
 <span data-ttu-id="b8d4c-112">@No__t-0 功能提供对多个 .NET Framework 类的简单直观访问，使 Visual Basic 用户可以与计算机、应用程序、设置、资源等进行交互。</span><span class="sxs-lookup"><span data-stu-id="b8d4c-112">The `My` feature provides easy and intuitive access to a number of .NET Framework classes, enabling the Visual Basic user to interact with the computer, application, settings, resources, and so on.</span></span>  
  
## <a name="mybase"></a><span data-ttu-id="b8d4c-113">MyBase</span><span class="sxs-lookup"><span data-stu-id="b8d4c-113">MyBase</span></span>  
 <span data-ttu-id="b8d4c-114">@No__t 的关键字的行为类似于引用类的当前实例的基类的对象变量。</span><span class="sxs-lookup"><span data-stu-id="b8d4c-114">The `MyBase` keyword behaves like an object variable referring to the base class of the current instance of a class.</span></span> <span data-ttu-id="b8d4c-115">`MyBase` 通常用于访问派生类中被重写或隐藏的基类成员。</span><span class="sxs-lookup"><span data-stu-id="b8d4c-115">`MyBase` is commonly used to access base class members that are overridden or shadowed in a derived class.</span></span> <span data-ttu-id="b8d4c-116">`MyBase.New` 用于从派生类构造函数中显式调用基类构造函数。</span><span class="sxs-lookup"><span data-stu-id="b8d4c-116">`MyBase.New` is used to explicitly call a base class constructor from a derived class constructor.</span></span>  
  
## <a name="myclass"></a><span data-ttu-id="b8d4c-117">MyClass</span><span class="sxs-lookup"><span data-stu-id="b8d4c-117">MyClass</span></span>  
 <span data-ttu-id="b8d4c-118">@No__t 的关键字的行为类似于引用最初实现的类的当前实例的对象变量。</span><span class="sxs-lookup"><span data-stu-id="b8d4c-118">The `MyClass` keyword behaves like an object variable referring to the current instance of a class as originally implemented.</span></span> <span data-ttu-id="b8d4c-119">`MyClass` 类似于 `Me`，但其上的所有方法调用都被视为 `NotOverridable` 方法。</span><span class="sxs-lookup"><span data-stu-id="b8d4c-119">`MyClass` is similar to `Me`, but all method calls on it are treated as if the method were `NotOverridable`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8d4c-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="b8d4c-120">See also</span></span>

- [<span data-ttu-id="b8d4c-121">继承的基础知识</span><span class="sxs-lookup"><span data-stu-id="b8d4c-121">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
