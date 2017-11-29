---
title: "这 &#39; 第一条语句新的子 &#39;必须调用 &#39;MyBase.New &#39;或 &#39;MyClass.New &#39;（不带参数没有可访问构造函数）"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30148
- vbc30148
helpviewer_keywords: BC30148
ms.assetid: 4426e8fc-cb39-4eb8-ba95-503cd32fcc89
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1065643e1f6c868092fbad839af0dbbd33afaf01
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="first-statement-of-this-39sub-new39-must-be-a-call-to-39mybasenew39-or-39myclassnew39-no-accessible-constructor-without-parameters"></a>这 &#39; 第一条语句新的子 &#39;必须调用 &#39;MyBase.New &#39;或 &#39;MyClass.New &#39;（不带参数没有可访问构造函数）
此 Sub New 的第一个语句必须是对 MyBase.New 或 MyClass.New 的调用，因为基类的\<基名称 > 的\<derivedname > 没有可访问 Sub New 可调用不带任何参数。  
  
 在派生类中，每个构造函数必须调用基类构造函数 (`MyBase.New`)。 如果基类中存在的构造函数不带任何参数派生的类，可以访问的`MyBase.New`可以自动调用。 如果没有，则必须使用参数，调用基类构造函数，这不能自动完成。 在这种情况下，每个派生的类构造函数的第一个语句必须调用基类，参数化构造函数，或使基类构造函数调用派生类中调用另一个构造函数。  
  
 **错误 ID:** BC30148  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   调用`MyBase.New`提供所需的参数，或调用此类调用的对等构造函数。  
  
     例如，如果基类具有构造函数声明为`Public Sub New(ByVal index as Integer)`，第一个语句中派生类构造函数可能`MyBase.New(100)`。  
  
## <a name="see-also"></a>另请参阅  
 [继承的基础知识](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
