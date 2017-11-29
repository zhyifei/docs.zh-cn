---
title: "构造函数 &#39;&lt;名称&gt;&#39; 不能调用其自身"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30298
- vbc30298
helpviewer_keywords: BC30298
ms.assetid: 2d77b7f4-0640-4f89-9c65-f101fd2847c0
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2361d6f4d710e17a4f4e29ac03bfde523191fa83
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="constructor-39ltnamegt39-cannot-call-itself"></a>构造函数 &#39;&lt;名称&gt;&#39; 不能调用其自身
A`Sub New`类或结构中的过程调用其自身。  
  
 构造函数的用途是初始化类的实例，或创建结构时第一个。 类或结构可以具有多个构造函数，前提是它们都具有不同参数列表。 允许一个构造函数调用另一个构造函数来执行其自身除了其功能。 但该无意义的构造函数调用自身，并且实际上会导致无限递归如果允许。  
  
 **错误 ID:** BC30298  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  检查正在调用的构造函数的参数列表。 它应不同于该构造函数进行调用。  
  
2.  如果你不想要调用的其他构造函数，则删除`Sub New`完全调用。  
  
## <a name="see-also"></a>另请参阅  
 [对象生存期：如何创建和销毁对象](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
