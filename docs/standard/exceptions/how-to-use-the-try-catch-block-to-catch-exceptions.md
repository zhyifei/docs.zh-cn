---
title: 如何：使用 Try-Catch 块捕获异常
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- exceptions, try/catch blocks
- try blocks
- try/catch blocks
- catch blocks
ms.assetid: a3ce6dfd-1f64-471b-8ad8-8cfaf406275d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 852df5cb3eeea2ee5fa44ddce2f97e9c4f8d8b5a
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2018
ms.locfileid: "47236973"
---
# <a name="how-to-use-the-trycatch-block-to-catch-exceptions"></a>如何使用 try/catch 块捕获异常

将可能引发异常的代码部分置于 `try` 块，将可处理异常的代码置于 `catch` 块。 `catch` 块是一系列以关键字 `catch` 开头的语句，后跟要执行的异常类型和操作。

下方代码示例使用 `try`/`catch` 块来捕获可能的异常。 `Main` 方法包含带有 <xref:System.IO.StreamReader> 语句的 `try` 块，此块可打开名为 `data.txt` 的数据文件，并写入该文件的字符串。 以下 `try` 块是可捕获由 `try` 块导致的任何异常的 `catch` 块。

 [!code-cpp[CatchException#3](../../../samples/snippets/cpp/VS_Snippets_CLR/CatchException/CPP/catchexception2.cpp#3)]
 [!code-csharp[CatchException#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CatchException/CS/catchexception2.cs#3)]
 [!code-vb[CatchException#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CatchException/VB/catchexception2.vb#3)]  

公共语言运行时可捕获未被 catch 块捕获的异常。 会出现调试对话框，或是停止运行程序且会出现含有异常信息的对话框，或者会将错误打印到 STDERR，具体情况取决于运行时的配置方式。

> [!NOTE] 
> 几乎任何代码行都可能导致异常，尤其是由公共语言运行时本身造成的异常，如 <xref:System.OutOfMemoryException>。 大多数应用程序无需处理这些异常，但在编写供他人使用的库时，应注意到这种可能性。 有关何时在 try 块中设置代码的建议，请参阅[异常的最佳做法](best-practices-for-exceptions.md)。

## <a name="see-also"></a>请参阅

- [异常](index.md)
