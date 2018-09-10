---
title: 如何：显式引发异常
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- exceptions, try/catch blocks
- FileNotFoundException class
- try/catch blocks
- exceptions, throwing
- implicitly throwing exceptions
ms.assetid: 72bdd157-caa9-4478-9ee3-cb4500b84528
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a1a8658999f08d295e76afc9df6ec8acd146abe2
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43863221"
---
# <a name="how-to-explicitly-throw-exceptions"></a><span data-ttu-id="e6e98-102">如何显式引发异常</span><span class="sxs-lookup"><span data-stu-id="e6e98-102">How to explicitly throw exceptions</span></span>

<span data-ttu-id="e6e98-103">可使用 `throw` 语句显式引发异常。</span><span class="sxs-lookup"><span data-stu-id="e6e98-103">You can explicitly throw an exception using the `throw` statement.</span></span> <span data-ttu-id="e6e98-104">可使用 `throw` 语句再次引发捕获的异常。</span><span class="sxs-lookup"><span data-stu-id="e6e98-104">You can also throw a caught exception again using the `throw` statement.</span></span> <span data-ttu-id="e6e98-105">向重新引发的异常添加信息以在调试时提供详细信息，这是很好的编码做法。</span><span class="sxs-lookup"><span data-stu-id="e6e98-105">It is good coding practice to add information to an exception that is re-thrown to provide more information when debugging.</span></span>

<span data-ttu-id="e6e98-106">下方代码示例使用 `try`/`catch` 块来捕获可能的 <xref:System.IO.FileNotFoundException>。</span><span class="sxs-lookup"><span data-stu-id="e6e98-106">The following code example uses a `try`/`catch` block to catch a possible <xref:System.IO.FileNotFoundException>.</span></span> <span data-ttu-id="e6e98-107">以下 `try` 块为可捕获 <xref:System.IO.FileNotFoundException> 并在未找到数据文件时将消息写入控制台的 `catch` 块。</span><span class="sxs-lookup"><span data-stu-id="e6e98-107">Following the `try` block is a `catch` block that catches the <xref:System.IO.FileNotFoundException> and writes a message to the console if the data file is not found.</span></span> <span data-ttu-id="e6e98-108">下一语句为 `throw` 语句，可引发新的 <xref:System.IO.FileNotFoundException> 并向异常添加文本信息。</span><span class="sxs-lookup"><span data-stu-id="e6e98-108">The next statement is the `throw` statement that throws a new <xref:System.IO.FileNotFoundException> and adds text information to the exception.</span></span>

[!code-csharp[Exception.Throwing#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Exception.Throwing/CS/throw.cs#1)]
[!code-vb[Exception.Throwing#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Exception.Throwing/VB/throw.vb#1)]  

## <a name="see-also"></a><span data-ttu-id="e6e98-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="e6e98-109">See also</span></span>

- [<span data-ttu-id="e6e98-110">异常</span><span class="sxs-lookup"><span data-stu-id="e6e98-110">Exceptions</span></span>](index.md)
