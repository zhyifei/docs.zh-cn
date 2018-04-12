---
title: 在不是定义类的实例的对象上不能调用友元函数
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID97
ms.assetid: b9d821f0-8565-4f15-bb35-184789c69662
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2f1ac1ea14efb0cdf0d8ca03257e4da33d35e368
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="cannot-call-friend-function-on-object-which-is-not-an-instance-of-defining-class"></a>在不是定义类的实例的对象上不能调用友元函数
尝试调用某个类的 `Friend` 过程，或者尝试跨进程或跨线程访问 `Friend` 属性或方法。 `Friend` 过程可从类外部的模块中调用，但该模块是在其中定义该类的项目的一部分。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   确保从模块中调用或访问该过程，此模块是在其中定义该类的项目的一部分。  
  
## <a name="see-also"></a>另请参阅  
 [Friend](../../visual-basic/language-reference/modifiers/friend.md)
