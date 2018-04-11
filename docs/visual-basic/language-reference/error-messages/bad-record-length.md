---
title: 错误的记录长度
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID59
ms.assetid: 0926a3a4-177b-4452-9b33-d8a01e24cc21
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 747d62cb41ef841b4486e0c7108c37a86929683e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="bad-record-length"></a><span data-ttu-id="0bf65-102">错误的记录长度</span><span class="sxs-lookup"><span data-stu-id="0bf65-102">Bad record length</span></span>
<span data-ttu-id="0bf65-103">此错误的可能原因包括：</span><span class="sxs-lookup"><span data-stu-id="0bf65-103">Among the possible causes of this error are:</span></span>  
  
-   <span data-ttu-id="0bf65-104">记录变量中指定的长度`FileGet`， `FileGetObject`，`FilePut`或`FilePutObject`语句不同于指定的相应的长度`FileOpen`语句。</span><span class="sxs-lookup"><span data-stu-id="0bf65-104">The length of a record variable specified in a `FileGet`, `FileGetObject`, `FilePut` or `FilePutObject` statement differs from the length specified in the corresponding `FileOpen` statement.</span></span>  
  
-   <span data-ttu-id="0bf65-105">中的变量`FilePut`或`FilePutObject`语句或者包括可变长度字符串。</span><span class="sxs-lookup"><span data-stu-id="0bf65-105">The variable in a `FilePut` or `FilePutObject` statement is or includes a variable-length string.</span></span>  
  
-   <span data-ttu-id="0bf65-106">中的变量`FilePut`或`FilePutObject`长字符串或者包括`Variant`类型。</span><span class="sxs-lookup"><span data-stu-id="0bf65-106">The variable in a `FilePut` or `FilePutObject` is or includes a `Variant` type.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="0bf65-107">更正此错误</span><span class="sxs-lookup"><span data-stu-id="0bf65-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="0bf65-108">请确保记录变量的类型定义的用户定义类型中的固定长度变量的大小的总和是相同的值中所述`FileOpen`语句的`Len`子句。</span><span class="sxs-lookup"><span data-stu-id="0bf65-108">Make sure the sum of the sizes of fixed-length variables in the user-defined type defining the record variable's type is the same as the value stated in the `FileOpen` statement's `Len` clause.</span></span>  
  
2.  <span data-ttu-id="0bf65-109">如果中的变量`FilePut`或`FilePutObject`语句或者包括可变长度字符串，请确保可变长度字符串是短于中指定的记录长度至少 2 个字符`Len`子句`FileOpen`语句。</span><span class="sxs-lookup"><span data-stu-id="0bf65-109">If the variable in a `FilePut` or `FilePutObject` statement is or includes a variable-length string, make sure the variable-length string is at least 2 characters shorter than the record length specified in the `Len` clause of the `FileOpen` statement.</span></span>  
  
3.  <span data-ttu-id="0bf65-110">如果中的变量`FilePut`或`FilePutObject`长字符串或者包括`Variant`确保可变长度字符串至少 4 个字节短于中指定的记录长度`Len`子句`FileOpen`语句。</span><span class="sxs-lookup"><span data-stu-id="0bf65-110">If the variable in a `FilePut` or `FilePutObject` is or includes a `Variant` make sure the variable-length string is at least 4 bytes shorter than the record length specified in the `Len` clause of the `FileOpen` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bf65-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0bf65-111">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileSystem.FileGet%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.FileGetObject%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.FilePut%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.FilePutObject%2A>
