---
title: 派生类无法引发基类事件
ms.date: 07/20/2015
f1_keywords:
- vbc30029
- bc30029
helpviewer_keywords:
- BC30029
ms.assetid: 63afa1c6-2f93-4512-a2f0-372455979771
ms.openlocfilehash: 3cb61a40e4522695b876d85f67dac1a109d3c3e0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54595859"
---
# <a name="derived-classes-cannot-raise-base-class-events"></a>派生类无法引发基类事件
只能从声明它的声明空间，可以引发一个事件。 因此，一个类无法引发从任何其他类，甚至从其派生的其中一个事件。  
  
 **错误 ID:** BC30029  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   移动`Event`语句或`RaiseEvent`语句，使它们位于同一个类。  
  
## <a name="see-also"></a>请参阅
- [Event 语句](../../../visual-basic/language-reference/statements/event-statement.md)
- [RaiseEvent 语句](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
