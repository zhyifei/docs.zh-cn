---
title: 方法参数（C# 参考）
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- methods [C#], parameters
- method parameters [C#]
- parameters [C#]
ms.assetid: 680e39ff-775b-48b0-9f47-4186a5bfc4a1
caps.latest.revision: 8
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 35d96066deb866e02f6bf624121376fe3ae94373
ms.sourcegitcommit: 935d5267c44f9bce801468ef95f44572f1417e8c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="method-parameters-c-reference"></a>方法参数（C# 参考）

为不具有 [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md)、[ref](../../../csharp/language-reference/keywords/ref.md) 或 [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) 的方法声明的参数会按值传递给调用的方法。 可以在方法中更改该值，但当控制传递回调用过程时，不会保留更改后的值。 可以通过使用方法参数关键字更改此行为。  
  
 本部分介绍声明方法参数时可以使用的关键字：  
  
-   [params](../../../csharp/language-reference/keywords/params.md) 指定此参数采用可变数量的参数。
  
-   [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md) 指定此参数由引用传递，但只由调用方法读取。
  
-   [ref](../../../csharp/language-reference/keywords/ref.md) 指定此参数由引用传递，可能由调用方法读取或写入。
  
-   [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) 指定此参数由引用传递，由调用方法写入。
  
## <a name="see-also"></a>请参阅  
 [C# 参考](../../../csharp/language-reference/index.md)  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [C# 关键字](../../../csharp/language-reference/keywords/index.md)
