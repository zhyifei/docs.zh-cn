---
title: 方法参数 - C# 参考
ms.date: 07/20/2015
helpviewer_keywords:
- methods [C#], parameters
- method parameters [C#]
- parameters [C#]
ms.assetid: 680e39ff-775b-48b0-9f47-4186a5bfc4a1
ms.openlocfilehash: 2cc7f9178fa5c1a040be9d45ba66fac292bb0e28
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713377"
---
# <a name="method-parameters-c-reference"></a>方法参数（C# 参考）

为不具有 [in](./in-parameter-modifier.md)、[ref](./ref.md) 或 [out](./out-parameter-modifier.md) 的方法声明的参数会按值传递给调用的方法。 可以在方法中更改该值，但当控制传递回调用过程时，不会保留更改后的值。 可以通过使用方法参数关键字更改此行为。  
  
 本部分介绍声明方法参数时可以使用的关键字：  
  
- [params](./params.md) 指定此参数采用可变数量的参数。
  
- [in](./in-parameter-modifier.md) 指定此参数由引用传递，但只由调用方法读取。
  
- [ref](./ref.md) 指定此参数由引用传递，可能由调用方法读取或写入。
  
- [out](./out-parameter-modifier.md) 指定此参数由引用传递，由调用方法写入。
  
## <a name="see-also"></a>请参阅

- [C# 参考](../index.md)
- [C# 编程指南](../../programming-guide/index.md)
- [C# 关键字](./index.md)
