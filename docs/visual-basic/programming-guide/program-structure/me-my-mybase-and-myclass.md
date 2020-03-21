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
# <a name="me-my-mybase-and-myclass-in-visual-basic"></a>Visual Basic 中的 Me、My、MyBase 和 MyClass
`Me`、`My``MyBase`和`MyClass`在 Visual Basic 中具有相似的名称，但目的不同。 本主题介绍每个实体，以便区分它们。  
  
## <a name="me"></a>我  
 关键字`Me`提供了一种引用代码当前正在执行的类或结构的特定实例的方法。 `Me`其活动类似于对象变量或引用当前实例的结构变量。 使用`Me`对于将有关类或结构当前执行实例的信息传递给另一个类、结构或模块中的过程特别有用。  
  
 例如，假设您在模块中具有以下过程。  
  
```vb  
Sub ChangeFormColor(FormName As Form)  
   Randomize()  
   FormName.BackColor = Color.FromArgb(Rnd() * 256, Rnd() * 256, Rnd() * 256)  
End Sub  
```  
  
 可以使用以下语句调用此过程并将<xref:System.Windows.Forms.Form>类的当前实例作为参数传递。  
  
```vb  
ChangeFormColor(Me)  
```  
  
## <a name="my"></a>My  
 此功能`My`提供了对许多 .NET Framework 类的轻松直观访问，使 Visual Basic 用户能够与计算机、应用程序、设置、资源等进行交互。  
  
## <a name="mybase"></a>MyBase  
 关键字`MyBase`的作用类似于引用类当前实例的基类的对象变量。 `MyBase`通常用于访问派生类中重写或隐藏基类成员。 `MyBase.New`用于从派生类构造函数显式调用基类构造函数。  
  
## <a name="myclass"></a>MyClass  
 关键字`MyClass`的作用类似于一个对象变量，它引用最初实现的类的当前实例。 `MyClass`与 类似`Me`，但上它的所有方法调用都被视为方法为`NotOverridable`。  
  
## <a name="see-also"></a>另请参阅

- [继承的基础知识](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
