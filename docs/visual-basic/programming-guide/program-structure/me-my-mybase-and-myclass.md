---
title: "Me、 My、 MyBase 和 MyClass 在 Visual Basic |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- MyClass
- vb.Me
- MyBase
- vb.MyBase
- Me
- vb.MyClass
- vb.This
- vb.My
dev_langs:
- VB
helpviewer_keywords:
- My object
- self-reference, Me keyword
- MyClass keyword, relationship to similar programming elements
- Me keyword, relationship to similar programming elements
- Me keyword, referring to the current instance of an object
- Me keyword
- self-reference
- current instance, Me keyword
- MyBase keyword, relationship to similar programming elements
ms.assetid: f8e241ae-b1ed-4886-9aa0-08c632154029
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 3ba634eb28c25f47a0e88c856b916383b6ad15a2
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="me-my-mybase-and-myclass-in-visual-basic"></a><span data-ttu-id="0d880-102">Visual Basic 中的 Me、My、MyBase 和 MyClass</span><span class="sxs-lookup"><span data-stu-id="0d880-102">Me, My, MyBase, and MyClass in Visual Basic</span></span>
<span data-ttu-id="0d880-103">`Me``My`， `MyBase`，和`MyClass`中[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]具有类似的名称，但不同的用途。</span><span class="sxs-lookup"><span data-stu-id="0d880-103">`Me`, `My`, `MyBase`, and `MyClass` in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] have similar names, but different purposes.</span></span> <span data-ttu-id="0d880-104">本主题将介绍其中每个实体以便将它们区分开来。</span><span class="sxs-lookup"><span data-stu-id="0d880-104">This topic describes each of these entities in order to distinguish them.</span></span>  
  
## <a name="me"></a><span data-ttu-id="0d880-105">Me</span><span class="sxs-lookup"><span data-stu-id="0d880-105">Me</span></span>  
 <span data-ttu-id="0d880-106">`Me`关键字提供了一种方法来指代类或当前正在其中执行代码的结构的特定实例。</span><span class="sxs-lookup"><span data-stu-id="0d880-106">The `Me` keyword provides a way to refer to the specific instance of a class or structure in which the code is currently executing.</span></span> <span data-ttu-id="0d880-107">`Me`行为类似的对象变量或结构变量引用当前实例。</span><span class="sxs-lookup"><span data-stu-id="0d880-107">`Me` behaves like either an object variable or a structure variable referring to the current instance.</span></span> <span data-ttu-id="0d880-108">使用`Me`很适合用于将有关当前执行实例的类或结构的信息传递给另一个类、 结构或模块中的过程。</span><span class="sxs-lookup"><span data-stu-id="0d880-108">Using `Me` is particularly useful for passing information about the currently executing instance of a class or structure to a procedure in another class, structure, or module.</span></span>  
  
 <span data-ttu-id="0d880-109">例如，假设在模块中有下面的过程。</span><span class="sxs-lookup"><span data-stu-id="0d880-109">For example, suppose you have the following procedure in a module.</span></span>  
  
```  
Sub ChangeFormColor(FormName As Form)  
   Randomize()  
   FormName.BackColor = Color.FromArgb(Rnd() * 256, Rnd() * 256, Rnd() * 256)  
End Sub  
```  
  
 <span data-ttu-id="0d880-110">您可以调用此过程，并将传递的当前实例<xref:System.Windows.Forms.Form>作为通过使用以下语句参数的类。</xref:System.Windows.Forms.Form></span><span class="sxs-lookup"><span data-stu-id="0d880-110">You can call this procedure and pass the current instance of the <xref:System.Windows.Forms.Form> class as an argument by using the following statement.</span></span>  
  
```  
ChangeFormColor(Me)  
```  
  
## <a name="my"></a><span data-ttu-id="0d880-111">My</span><span class="sxs-lookup"><span data-stu-id="0d880-111">My</span></span>  
 <span data-ttu-id="0d880-112">`My`功能提供对多种容易、 直观访问[!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]类，从而[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]用户与计算机、 应用程序、 设置、 资源等进行交互。</span><span class="sxs-lookup"><span data-stu-id="0d880-112">The `My` feature provides easy and intuitive access to a number of [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] classes, enabling the [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] user to interact with the computer, application, settings, resources, and so on.</span></span>  
  
## <a name="mybase"></a><span data-ttu-id="0d880-113">MyBase</span><span class="sxs-lookup"><span data-stu-id="0d880-113">MyBase</span></span>  
 <span data-ttu-id="0d880-114">`MyBase`关键字的行为类似于一个类的当前实例的基类引用的对象变量。</span><span class="sxs-lookup"><span data-stu-id="0d880-114">The `MyBase` keyword behaves like an object variable referring to the base class of the current instance of a class.</span></span> <span data-ttu-id="0d880-115">`MyBase`通常用于访问基类成员被重写或派生类中被隐藏。</span><span class="sxs-lookup"><span data-stu-id="0d880-115">`MyBase` is commonly used to access base class members that are overridden or shadowed in a derived class.</span></span> <span data-ttu-id="0d880-116">`MyBase.New`用于从派生的类构造函数中显式调用基类构造函数。</span><span class="sxs-lookup"><span data-stu-id="0d880-116">`MyBase.New` is used to explicitly call a base class constructor from a derived class constructor.</span></span>  
  
## <a name="myclass"></a><span data-ttu-id="0d880-117">MyClass</span><span class="sxs-lookup"><span data-stu-id="0d880-117">MyClass</span></span>  
 <span data-ttu-id="0d880-118">`MyClass`关键字的行为类似于最初实现的类的当前实例引用的对象变量。</span><span class="sxs-lookup"><span data-stu-id="0d880-118">The `MyClass` keyword behaves like an object variable referring to the current instance of a class as originally implemented.</span></span> <span data-ttu-id="0d880-119">`MyClass`类似于`Me`，但在其上的所有方法调用将被都视为是`NotOverridable`。</span><span class="sxs-lookup"><span data-stu-id="0d880-119">`MyClass` is similar to `Me`, but all method calls on it are treated as if the method were `NotOverridable`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d880-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0d880-120">See Also</span></span>  
 [<span data-ttu-id="0d880-121">继承的基础知识</span><span class="sxs-lookup"><span data-stu-id="0d880-121">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
