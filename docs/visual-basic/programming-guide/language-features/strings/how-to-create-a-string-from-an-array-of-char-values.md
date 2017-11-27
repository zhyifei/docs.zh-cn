---
title: "如何：从 Char 值的数组创建字符串 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- examples [Visual Basic], arrays
- examples [Visual Basic], Char data type
ms.assetid: 69f94e85-d57c-4ccc-a62a-426e829f5c5e
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 06e5c6923c26f3cb84b38475d6680523853d727d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-string-from-an-array-of-char-values-visual-basic"></a><span data-ttu-id="16046-102">如何：从 Char 值的数组创建字符串 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="16046-102">How to: Create a String from An Array of Char Values (Visual Basic)</span></span>
<span data-ttu-id="16046-103">此示例创建从单独的字符的字符串"abcd"。</span><span class="sxs-lookup"><span data-stu-id="16046-103">This example creates the string "abcd" from individual characters.</span></span>  
  
## <a name="example"></a><span data-ttu-id="16046-104">示例</span><span class="sxs-lookup"><span data-stu-id="16046-104">Example</span></span>  
 [!code-vb[VbVbalrStrings#61](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-create-a-string-from-an-array-of-char-values_1.vb)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="16046-105">编译代码</span><span class="sxs-lookup"><span data-stu-id="16046-105">Compiling the Code</span></span>  
 <span data-ttu-id="16046-106">此方法没有任何特殊要求。</span><span class="sxs-lookup"><span data-stu-id="16046-106">This method has no special requirements.</span></span>  
  
 <span data-ttu-id="16046-107">语法`"a"c`，其中单个`c`跟随用引号括起来的单个字符，用于创建一个字符文本。</span><span class="sxs-lookup"><span data-stu-id="16046-107">The syntax `"a"c`, where a single `c` follows a single character in quotation marks, is used to create a character literal.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="16046-108">可靠编程</span><span class="sxs-lookup"><span data-stu-id="16046-108">Robust Programming</span></span>  
 <span data-ttu-id="16046-109">Null 字符 (等效于`Chr(0)`) 在字符串中导致意外结果时使用的字符串。</span><span class="sxs-lookup"><span data-stu-id="16046-109">Null characters (equivalent to `Chr(0)`) in the string lead to unexpected results when using the string.</span></span> <span data-ttu-id="16046-110">Null 字符将包括替换字符串，但在某些情况下将不会显示在 null 字符后面的字符。</span><span class="sxs-lookup"><span data-stu-id="16046-110">The null character will be included with the string, but characters following the null character will not be displayed in some situations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16046-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="16046-111">See Also</span></span>  
 <xref:System.String>  
 [<span data-ttu-id="16046-112">Char 数据类型</span><span class="sxs-lookup"><span data-stu-id="16046-112">Char Data Type</span></span>](../../../../visual-basic/language-reference/data-types/char-data-type.md)  
 [<span data-ttu-id="16046-113">数据类型</span><span class="sxs-lookup"><span data-stu-id="16046-113">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
