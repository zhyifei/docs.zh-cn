---
title: 此第一条语句&#39;Sub New&#39;必须是对调用&#39;MyBase.New&#39;或&#39;MyClass.New&#39; （没有可访问构造函数不带参数）
ms.date: 07/20/2015
f1_keywords:
- bc30148
- vbc30148
helpviewer_keywords:
- BC30148
ms.assetid: 4426e8fc-cb39-4eb8-ba95-503cd32fcc89
ms.openlocfilehash: 75832ae88908094c1cb74ce04ad84c0d2ae91e68
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54728890"
---
# <a name="first-statement-of-this-39sub-new39-must-be-a-call-to-39mybasenew39-or-39myclassnew39-no-accessible-constructor-without-parameters"></a>此第一条语句&#39;Sub New&#39;必须是对调用&#39;MyBase.New&#39;或&#39;MyClass.New&#39; （没有可访问构造函数不带参数）
此 Sub New 的第一个语句必须是对 MyBase.New 或 MyClass.New 的调用，因为基类 '\<basename > 的\<derivedname > 不具有可访问 Sub New，可以调用不带任何参数。  
  
 在派生类中，每个构造函数必须调用基类构造函数 (`MyBase.New`)。 如果基类具有不带任何参数是可用于派生类的构造函数`MyBase.New`可以自动调用。 如果没有，则必须使用参数，调用基类构造函数，这不能自动完成。 在这种情况下，每个派生的类构造函数的第一个语句必须在基础类上调用参数化构造函数或调用另一个构造函数可以调用基类构造函数在派生类中。  
  
 **错误 ID:** BC30148  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   调用`MyBase.New`提供所需的参数，或调用此类调用对等构造函数。  
  
     例如，如果基本类具有声明为一个构造函数`Public Sub New(ByVal index as Integer)`中，第一个语句中的派生类构造函数可能是`MyBase.New(100)`。  
  
## <a name="see-also"></a>请参阅
- [继承的基础知识](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
