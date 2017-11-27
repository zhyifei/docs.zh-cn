---
title: "如何：在 Visual Basic 中将字符串转换为字节数组"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- string conversion [Visual Basic], arrays
- arrays [Visual Basic], converting strings to
- byte arrays
- examples [Visual Basic], string conversion
- arrays [Visual Basic], byte arrays
ms.assetid: f477d35c-a3fc-4a30-b1d4-cd0d353aae1d
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6d527434dc0a61c9c771b42d05c1ee316094e7fd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-convert-strings-into-an-array-of-bytes-in-visual-basic"></a><span data-ttu-id="666c7-102">如何：在 Visual Basic 中将字符串转换为字节数组</span><span class="sxs-lookup"><span data-stu-id="666c7-102">How to: Convert Strings into an Array of Bytes in Visual Basic</span></span>
<span data-ttu-id="666c7-103">本主题演示如何将字符串转换为字节数组。</span><span class="sxs-lookup"><span data-stu-id="666c7-103">This topic shows how to convert a string into an array of bytes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="666c7-104">示例</span><span class="sxs-lookup"><span data-stu-id="666c7-104">Example</span></span>  
 <span data-ttu-id="666c7-105">此示例使用<xref:System.Text.Encoding.GetBytes%2A>方法<xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>编码类将字符串转换为字节数组。</span><span class="sxs-lookup"><span data-stu-id="666c7-105">This example uses the <xref:System.Text.Encoding.GetBytes%2A> method of the <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType> encoding class to convert a string into an array of bytes.</span></span>  
  
 [!code-vb[VbVbalrStrings#74](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-strings-into-an-array-of-bytes_1.vb)]  
  
 <span data-ttu-id="666c7-106">你可以从多个编码选项以将字符串转换为字节数组中进行选择：</span><span class="sxs-lookup"><span data-stu-id="666c7-106">You can choose from several encoding options to convert a string into a byte array:</span></span>  
  
-   <span data-ttu-id="666c7-107"><xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>： 获取 ASCII （7 位） 字符的编码设置。</span><span class="sxs-lookup"><span data-stu-id="666c7-107"><xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>: Gets an encoding for the ASCII (7-bit) character set.</span></span>  
  
-   <span data-ttu-id="666c7-108"><xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>： 获取使用 big endian 字节顺序的 utf-16 格式的编码。</span><span class="sxs-lookup"><span data-stu-id="666c7-108"><xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-16 format using the big-endian byte order.</span></span>  
  
-   <span data-ttu-id="666c7-109"><xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>： 获取系统的当前 ANSI 代码页的编码。</span><span class="sxs-lookup"><span data-stu-id="666c7-109"><xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>: Gets an encoding for the system's current ANSI code page.</span></span>  
  
-   <span data-ttu-id="666c7-110"><xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>： 获取使用 little-endian 字节顺序的 utf-16 格式的编码。</span><span class="sxs-lookup"><span data-stu-id="666c7-110"><xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-16 format using the little-endian byte order.</span></span>  
  
-   <span data-ttu-id="666c7-111"><xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>： 获取使用 little-endian 字节顺序的 utf-32 格式的编码。</span><span class="sxs-lookup"><span data-stu-id="666c7-111"><xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-32 format using the little-endian byte order.</span></span>  
  
-   <span data-ttu-id="666c7-112"><xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>： 获取 utf-7 格式的编码。</span><span class="sxs-lookup"><span data-stu-id="666c7-112"><xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-7 format.</span></span>  
  
-   <span data-ttu-id="666c7-113"><xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>： 获取 utf-8 格式的编码。</span><span class="sxs-lookup"><span data-stu-id="666c7-113"><xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-8 format.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="666c7-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="666c7-114">See Also</span></span>  
 <xref:System.Text.Encoding?displayProperty=nameWithType>  
 <xref:System.Text.Encoding.GetBytes%2A>  
 [<span data-ttu-id="666c7-115">如何： 将字节数组转换为 Visual Basic 中的字符串</span><span class="sxs-lookup"><span data-stu-id="666c7-115">How to: Convert an Array of Bytes into a String in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-an-array-of-bytes-into-a-string.md)
