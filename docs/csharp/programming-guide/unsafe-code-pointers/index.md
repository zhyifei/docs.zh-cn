---
title: 不安全代码和指针 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- security [C#], type safety
- C# language, unsafe code
- type safety [C#]
- unsafe keyword [C#]
- unsafe code [C#]
- C# language, pointers
- pointers [C#], about pointers
ms.assetid: b0fcca10-a92d-4f2a-835b-b0ccae6739ee
ms.openlocfilehash: 99f0b925a37bff8b6ab1ff46e9ce2f0ea0a38aed
ms.sourcegitcommit: ffd7dd79468a81bbb0d6449f6d65513e050c04c4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/21/2019
ms.locfileid: "65959477"
---
# <a name="unsafe-code-and-pointers-c-programming-guide"></a>不安全代码和指针（C# 编程指南）

为了保持类型安全性，默认情况下，C# 不支持指针算法。 但是，通过使用 [unsafe](../../language-reference/keywords/unsafe.md) 关键字，可以定义可在其中使用指针的不安全上下文。 若要详细了解指针，请参阅[指针类型](pointer-types.md)。  
  
> [!NOTE]
> 在公共语言运行时 (CLR) 中，不安全代码是指无法验证的代码。 C# 中的不安全代码不一定是危险的；只是 CLR 无法验证该代码的安全性。 因此，CLR 将仅执行完全信任的程序集中的不安全代码。 如果你使用不安全代码，你应该负责确保代码不会引发安全风险或指针错误。  
  
## <a name="unsafe-code-overview"></a>不安全代码概述

不安全代码具有以下属性：

- 可将方法、类型和代码块定义为不安全。

- 在某些情况下，通过移除数组绑定检查，不安全代码可提高应用程序的性能。

- 调用需要指针的本机函数时，需使用不安全代码。

- 使用不安全代码将引发安全风险和稳定性风险。

- 必须使用 [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md) 编译器选项来编译包含不安全块的代码。
  
## <a name="related-sections"></a>相关章节

有关详细信息，请参见:

- [指针类型](pointer-types.md)

- [固定大小的缓冲区](fixed-size-buffers.md)

## <a name="c-language-specification"></a>C# 语言规范

有关详细信息，请参阅 [C# 语言规范](~/_csharplang/spec/introduction.md)中的[不安全代码](~/_csharplang/spec/unsafe-code.md)主题。
  
## <a name="see-also"></a>请参阅

- [C# 编程指南](../index.md)
- [unsafe](../../language-reference/keywords/unsafe.md)
