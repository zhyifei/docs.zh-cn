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
# <a name="me-my-mybase-and-myclass-in-visual-basic"></a>Visual Basic 中的 Me、My、MyBase 和 MyClass
`Me`、`My`、`MyBase` 和 Visual Basic 中的 @no__t 为类似的名称，但用途不同。 本主题将介绍其中的每个实体，以便将它们区分开来。  
  
## <a name="me"></a>Me  
 @No__t 关键字提供了一种方法，用于引用当前正在执行代码的类或结构的特定实例。 `Me` 的行为类似于引用当前实例的对象变量或结构变量。 在将有关当前正在执行的类或结构实例的信息传递到另一个类、结构或模块中的过程时，使用 @no__t。  
  
 例如，假设你在模块中具有以下过程。  
  
```vb  
Sub ChangeFormColor(FormName As Form)  
   Randomize()  
   FormName.BackColor = Color.FromArgb(Rnd() * 256, Rnd() * 256, Rnd() * 256)  
End Sub  
```  
  
 可以调用此过程，并使用以下语句将 @no__t 0 类的当前实例作为参数传递。  
  
```vb  
ChangeFormColor(Me)  
```  
  
## <a name="my"></a>My  
 @No__t-0 功能提供对多个 .NET Framework 类的简单直观访问，使 Visual Basic 用户可以与计算机、应用程序、设置、资源等进行交互。  
  
## <a name="mybase"></a>MyBase  
 @No__t 的关键字的行为类似于引用类的当前实例的基类的对象变量。 `MyBase` 通常用于访问派生类中被重写或隐藏的基类成员。 `MyBase.New` 用于从派生类构造函数中显式调用基类构造函数。  
  
## <a name="myclass"></a>MyClass  
 @No__t 的关键字的行为类似于引用最初实现的类的当前实例的对象变量。 `MyClass` 类似于 `Me`，但其上的所有方法调用都被视为 `NotOverridable` 方法。  
  
## <a name="see-also"></a>请参阅

- [继承的基础知识](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
