---
title: Visual Basic 中的 Me、My、MyBase 和 MyClass
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
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
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4d06c97bdf4824e878d617b2d09993d18c60336b
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="me-my-mybase-and-myclass-in-visual-basic"></a>Visual Basic 中的 Me、My、MyBase 和 MyClass
`Me``My`， `MyBase`，和`MyClass`在 Visual Basic 中具有类似的名称，但不同的用途。 本主题将介绍上述每个实体以便将它们区分开来。  
  
## <a name="me"></a>Me  
 `Me`关键字提供了一种方法来指代类或结构当前在其中执行代码的特定实例。 `Me` 行为类似对象变量或结构变量引用的当前实例。 使用`Me`很适合用于将有关当前正在执行实例的类或结构的信息传递给另一个类、 结构或模块中的过程。  
  
 例如，假设模块中有以下过程。  
  
```  
Sub ChangeFormColor(FormName As Form)  
   Randomize()  
   FormName.BackColor = Color.FromArgb(Rnd() * 256, Rnd() * 256, Rnd() * 256)  
End Sub  
```  
  
 你可以调用此过程，并将传递的当前实例<xref:System.Windows.Forms.Form>作为通过使用以下语句参数的类。  
  
```  
ChangeFormColor(Me)  
```  
  
## <a name="my"></a>My  
 `My`功能提供对大量的简单和直观访问[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]类，使 Visual Basic 用户与计算机、 应用程序、 设置、 资源和等等进行交互。  
  
## <a name="mybase"></a>MyBase  
 `MyBase`关键字的行为类似于类的当前实例的基类引用的对象变量。 `MyBase` 通常用于访问被重写或派生类中被隐藏基类成员。 `MyBase.New` 用于从派生的类构造函数中显式调用基类构造函数。  
  
## <a name="myclass"></a>MyClass  
 `MyClass`关键字的行为方式类似于最初实现的类的当前实例引用的对象变量。 `MyClass` 类似于`Me`，但在其上的所有方法调用被都视为方法`NotOverridable`。  
  
## <a name="see-also"></a>请参阅  
 [继承的基础知识](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
