---
title: 在类构造函数中使用类的默认实例可能会导致无限递归调用
ms.date: 07/20/2015
ms.assetid: 9645b47f-7de5-46d0-bb45-d5fdaa8aaa2a
ms.openlocfilehash: 1cad1e3cf3943e945d519aee061a877c91684b4a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64623472"
---
# <a name="use-of-default-instance-of-a-class-in-the-class-constructor-could-lead-to-infinite-recursive-call"></a>在类构造函数中使用类的默认实例可能会导致无限递归调用
已在类的构造函数中使用类的默认实例。 这可能会导致无限递归调用（也称为无限循环）。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
- 从类构造函数中删除默认实例。  
  
## <a name="see-also"></a>请参阅

- [构造函数](~/docs/visual-basic/programming-guide/concepts/object-oriented-programming.md#constructors)
